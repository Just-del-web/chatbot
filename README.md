# Juts-Chatbot

Juts-Chatbot is a Node.js-based chatbot application designed for a restaurant ordering system. It allows users to interact with the bot to place orders, view the menu, check order history, and make payments via Paystack.

## Features

- **Interactive Chatbot**: Users can interact with the bot to place orders and manage their orders.
- **Dynamic Menu**: Displays a menu of available food items.
- **Order Management**:
  - Place orders.
  - View current orders.
  - View order history.
  - Cancel orders.
- **Payment Integration**: Integrated with Paystack for secure online payments.
- **Session Management**: Tracks user sessions using `express-session`.

---

## Technologies Used

- **Node.js**: Backend runtime environment.
- **Express.js**: Web framework for handling HTTP requests.
- **Socket.IO**: Real-time communication between the client and server.
- **Axios**: For making HTTP requests to the Paystack API.
- **Paystack**: Payment gateway integration.
- **dotenv**: For managing environment variables.
- **LocalTunnel/ngrok**: For exposing the local server to the internet during development.

---

## Installation

### Prerequisites
- Node.js installed on your system.
- A Paystack account for payment integration.

### Steps
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/juts-chatbot.git
   cd juts-chatbot

2.  npm install

3. Create a .env file in the root directory and add the following:
PORT=5000
HOST=localhost
PAYSTACK_SECRET_KEY=your_paystack_secret_key
CALLBACK_URL=https://your-public-url/paystack/callback

4. Start the server:
node app.js

5. Expose your local server to the internet using a tunneling service like ngrok or LocalTunnel:

ngrok http 5000

Usage
Commands
1: View the menu.
97: View your current order.
98: View your order history.
99: Checkout and make payment.
0: Cancel your order.
Payment Flow
1. Place an order by selecting items from the menu.
2. Checkout by entering 99.
3. The bot will provide a Paystack payment link.
4. Complete the payment on Paystack's secure page.
5. The bot will confirm the payment status.

PROJECT STRUCTURE
Juts-chatbot/
├── [app.js](http://_vscodecontentref_/1)              # Main application file
├── [package.json](http://_vscodecontentref_/2)        # Project metadata and dependencies
├── .env                # Environment variables
├── public/             # Static files (if any)
├── [README.md](http://_vscodecontentref_/3)           # Project documentation

API Integration
Paystack Payment Initialization
Endpoint: https://api.paystack.co/transaction/initialize
Method: POST
Headers: <vscode_annotation details='%5B%7B%22title%22%3A%22hardcoded-credentials%22%2C%22description%22%3A%22Embedding%20credentials%20in%20source%20code%20risks%20unauthorized%20access%22%7D%5D'> -</vscode_annotation> Authorization: Bearer <PAYSTACK_SECRET_KEY>
Content-Type: application/json

.Body
{
  "email": "user@example.com",
  "amount": 5000,
  "callback_url": "https://your-public-url/paystack/callback"
}

Paystack Payment Verification
Endpoint: https://api.paystack.co/transaction/verify/:reference
Method: GET
Headers:
Authorization: Bearer <PAYSTACK_SECRET_KEY>

Known Issues
Callback URL: Ensure the callback URL is publicly accessible (e.g., using ngrok or LocalTunnel).
Session Persistence: Sessions are cleared on user disconnection. Modify the code if persistent sessions are required.

Future Improvements
Add user authentication for better session management.
Improve error handling for edge cases.
Add support for multiple payment gateways.
Enhance the UI for better user experience.

License
This project is licensed under the MIT License. See the LICENSE file for details.

Acknowledgments
Node.js
Express.js
Socket.IO
Paystack
ngrok
