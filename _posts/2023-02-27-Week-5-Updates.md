---
layout: post
title:  "Week 5-7 Updates"
date:  2023-03-10 12:05:25
categories: jekyll update
tags: featured
image: /assets/article_images/2023-02-12-Week-3-Updates/image.jpg
---

# Development Update: Beginning Stages of Application

## Introduction
This report provides an update on the initial stages of developing the ClothesShare application using React Native CLI with TypeScript. The focus has been on setting up the project, creating essential screens, and implementing basic functionalities to establish a solid foundation for further development.

## Project Setup
The following steps were undertaken to set up the development environment and initialize the project:

1. **Environment Configuration**: Node.js and React Native CLI were installed to ensure a compatible development environment. TypeScript support was also added to leverage its static typing capabilities.

2. **Project Initialization**: A new React Native project was created using the React Native CLI command `npx react-native init ClothesShare --template react-native-template-typescript`. This initialized the project with TypeScript support and created the necessary files and folders.

3. **Dependencies Installation**: Required dependencies, such as React Navigation for navigation purposes and Axios for handling API requests, were installed using `npm`.

4. **Version Control**: Git was initialized within the project directory to enable version control and collaboration.

## Initial Screen Implementation
To establish the basic structure of the application, the following screens were created using React Native components and TypeScript:

1. **Home Screen**: The home screen serves as the main entry point for users. It includes a search bar, a list of available items for rent, and filtering options. Here's an example of the initial code for the Home screen:

```typescript
import React from 'react';
import { View, Text, TextInput, FlatList } from 'react-native';

interface Item {
  id: string;
  name: string;
  description: string;
  price: number;
}

const HomeScreen: React.FC = () => {
  const [searchText, setSearchText] = React.useState('');
  const [items, setItems] = React.useState<Item[]>([]);

  // Function to fetch items from the server
  const fetchItems = async () => {
    try {
      // Make an API request to fetch the items
      const response = await axios.get('/items', {
        params: { searchText },
      });

      setItems(response.data);
    } catch (error) {
      console.error('Failed to fetch items:', error);
    }
  };

  React.useEffect(() => {
    fetchItems();
  }, [searchText]);

  return (
    <View>
      <TextInput
        placeholder="Search for items"
        value={searchText}
        onChangeText={setSearchText}
      />

      <FlatList
        data={items}
        keyExtractor={(item) => item.id}
        renderItem={({ item }) => (
          <View>
            <Text>{item.name}</Text>
            <Text>{item.description}</Text>
            <Text>Price: ${item.price}</Text>
          </View>
        )}
      />
    </View>
  );
};

export default HomeScreen;
```

2. **Item Details Screen**: This screen displays the detailed information of a selected item, including additional images, rental duration, and the option to contact the owner. Here's an example of the initial code for the Item Details screen:

```typescript
import React from 'react';
import { View, Text, Image, Button } from 'react-native';

interface Item {
  id: string;
  name: string;
  description: string;
  price: number;
  images: string[];
  owner: string;
}

const ItemDetailsScreen: React.FC<{ item: Item }> = ({ item }) => {
  const handleRent = () => {
    // Implement the logic to initiate the rental process
  };

  return (
    <View>
      <Text>{item.name}</Text>
      <Text>{item.description}</Text>
      <Text>Price: ${item.price}</Text>
      <Image source={{ uri: item.images[0] }} />
      <Button title="Rent" onPress={handleRent} />
      <Button title="Contact Owner" onPress={() => {}} />
    </View>
  );
};

export default ItemDetailsScreen;
```

## Next Steps
The initial screens and basic functionalities have been implemented to kickstart the development of the ClothesShare application. The next steps in the development process include:

1. Implementing authentication and user management features to allow users to create accounts, log in, and manage their profiles.

2. Building the backend server and API endpoints to handle data storage and retrieval, as well as facilitating the communication between renters and owners.

3. Enhancing the user interface and experience by incorporating feedback received from user testing sessions and iterations on the design.

4. Integrating third-party services for secure payments, image uploads, and push notifications to enhance the functionality of the application.

5. Conducting rigorous testing to ensure stability, performance, and compatibility across different devices and screen sizes.

