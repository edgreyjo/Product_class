class Product {
  constructor(name, price) {
    this.name = name;
    this.price = price;
  }
}

class ShoppingCart {
  constructor() {
    this.items = [];
  }

  addItem(product) {
    this.items.push(product);
  }

  removeItem(product) {
    const index = this.items.findIndex(item => item === product);
    if (index !== -1) {
      this.items.splice(index, 1);
    }
  }

  getTotal() {
    const totalPrice = this.items.reduce((total, item) => total + item.price, 0);
    return totalPrice.toFixed(2);
  }

  displayItems() {
    this.items.forEach(item => console.log(Product: ${item.name}, Price: $${item.price}));
  }
}

// Create instances of products
const product1 = new Product('Shirt', 19.99);
const product2 = new Product('Pants', 29.99);
const product3 = new Product('Shoes', 49.99);

// Create an instance of the shopping cart
const cart = new ShoppingCart();

// Add products to the cart
cart.addItem(product1);
cart.addItem(product2);
cart.addItem(product3);

// Display the items in the cart
console.log('Items in the cart:');
cart.displayItems();

// Remove a product from the cart
cart.removeItem(product2);

// Display the updated items in the cart
console.log('Updated items in the cart:');
cart.displayItems();

// Calculate and display the total price of items in the cart
console.log('Total price:', cart.getTotal());
