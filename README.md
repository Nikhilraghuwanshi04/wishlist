# Wishlist App

This simple React app allows users to add items to a wishlist and clear the wishlist.

## UserInput Component

The `UserInput` component is responsible for allowing users to add items to the wishlist and clear the wishlist. It consists of an input field where users can enter their wishlist item, an "Add" button to add the item to the wishlist, and a "Clear" button to clear the entire wishlist.

### Props

- `addToWishList`: Function to add an item to the wishlist.
- `clearWishList`: Function to clear the wishlist.

## Data Component

The `Data` component displays the wishlist items added by the user. Each item is displayed as a list item with a delete button next to it. Clicking on the delete button removes the corresponding item from the wishlist.

### Props

- `wishList`: Array of wishlist items.
- `removeFromWishList`: Function to remove an item from the wishlist.

## Usage

To use these components, simply import them into your React application and render them where needed. You can pass the necessary props to customize the functionality as per your requirements.

Example:

```jsx
import React, { useState } from 'react';
import UserInput from './UserInput';
import Data from './Data';

function App() {
    const [wishlist, setWishlist] = useState([]);

    const addToWishlist = (item) => {
        setWishlist([...wishlist, item]);
    };

    const clearWishlist = () => {
        setWishlist([]);
    };

    const removeFromWishlist = (index) => {
        const newWishlist = [...wishlist];
        newWishlist.splice(index, 1);
        setWishlist(newWishlist);
    };

    return (
        <div>
            <h1>My Wishlist</h1>
            <UserInput addToWishlist={addToWishlist} clearWishlist={clearWishlist} />
            <Data wishlist={wishlist} removeFromWishlist={removeFromWishlist} />
        </div>
    );
}

export default App;

Replace the example usage with your actual usage if it's different, and adjust any other details as necessary.
