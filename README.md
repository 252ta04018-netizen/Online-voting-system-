# ONLINE SHOPPING SYSTEM

products = {
    1: ["Laptop", 50000],
    2: ["Mobile", 20000],
    3: ["Headphones", 1500],
    4: ["Keyboard", 1000],
    5: ["Mouse", 500]
}

cart = {}

while True:
    print("\n===== ONLINE SHOPPING SYSTEM =====")
    print("1. View Products")
    print("2. Add to Cart")
    print("3. View Cart")
    print("4. Checkout")
    print("5. Exit")

    choice = int(input("Enter your choice: "))

    # View products
    if choice == 1:
        print("\n----- PRODUCTS -----")
        for number, details in products.items():
            print(number, details[0], "- ₹", details[1])

    # Add to cart
    elif choice == 2:
        print("\n----- PRODUCTS -----")
        for number, details in products.items():
            print(number, details[0], "- ₹", details[1])

        product = int(input("Enter product number: "))
        quantity = int(input("Enter quantity: "))

        if product in products and quantity > 0:
            cart[product] = cart.get(product, 0) + quantity
            print("Product added to cart!")
        else:
            print("Invalid product or quantity.")

    # View cart
    elif choice == 3:
        print("\n----- YOUR CART -----")

        if not cart:
            print("Cart is empty.")
        else:
            total = 0

            for product, quantity in cart.items():
                name = products[product][0]
                price = products[product][1]
                amount = price * quantity

                print(name, "x", quantity, "=", "₹", amount)
                total += amount

            print("--------------------")
            print("Total = ₹", total)

    # Checkout
    elif choice == 4:
        if not cart:
            print("Cart is empty.")
        else:
            total = 0

            print("\n===== BILL =====")

            for product, quantity in cart.items():
                name = products[product][0]
                price = products[product][1]
                amount = price * quantity

                print(name, "x", quantity, "=", "₹", amount)
                total += amount

            print("--------------------")
            print("Total Amount = ₹", total)

            name = input("Enter your name: ")
            address = input("Enter your address: ")

            print("\nOrder placed successfully!")
            print("Customer:", name)
            print("Address:", address)
            print("Amount Paid: ₹", total)
            print("Thank you for shopping!")

            cart.clear()

    # Exit
    elif choice == 5:
        print("Thank you! Visit again.")
        break

    else:
        print("Invalid choice. Please try again.")
