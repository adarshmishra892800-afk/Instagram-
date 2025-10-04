
<!-- Basic free SMM panel starter template (HTML + Firebase) --><!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My Free SMM Panel</title>
  <script src="https://www.gstatic.com/firebasejs/10.5.2/firebase-app.js"></script>
  <script src="https://www.gstatic.com/firebasejs/10.5.2/firebase-auth.js"></script>
  <script src="https://www.gstatic.com/firebasejs/10.5.2/firebase-firestore.js"></script>
  <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
</head>
<body class="bg-gray-100">
  <div class="max-w-md mx-auto mt-10 p-6 bg-white rounded-2xl shadow-md">
    <h1 class="text-2xl font-bold text-center mb-4">🔥 My Free SMM Panel</h1><div id="authSection">
  <input id="email" placeholder="Email" class="border p-2 w-full mb-2" />
  <input id="password" type="password" placeholder="Password" class="border p-2 w-full mb-2" />
  <button id="loginBtn" class="bg-blue-500 text-white p-2 w-full rounded">Login / Sign Up</button>
</div>

<div id="orderSection" class="hidden">
  <h2 class="text-xl font-semibold mb-2">Place Order</h2>
  <input id="target" placeholder="Profile/Link" class="border p-2 w-full mb-2" />
  <input id="quantity" placeholder="Quantity" type="number" class="border p-2 w-full mb-2" />
  <select id="service" class="border p-2 w-full mb-2">
    <option value="followers">Instagram Followers</option>
    <option value="likes">Post Likes</option>
    <option value="views">Video Views</option>
  </select>
  <button id="orderBtn" class="bg-green-500 text-white p-2 w-full rounded">Submit Order</button>

  <div id="status" class="mt-4 text-sm text-gray-600"></div>
  <button id="logoutBtn" class="mt-4 bg-red-500 text-white p-2 w-full rounded">Logout</button>
</div>

  </div>  <script>
    // --- Replace with your Firebase config ---
    const firebaseConfig = {
      apiKey: "YOUR_API_KEY",
      authDomain: "YOUR_PROJECT.firebaseapp.com",
      projectId: "YOUR_PROJECT",
      storageBucket: "YOUR_PROJECT.appspot.com",
      messagingSenderId: "YOUR_SENDER_ID",
      appId: "YOUR_APP_ID"
    };

    firebase.initializeApp(firebaseConfig);
    const auth = firebase.auth();
    const db = firebase.firestore();

    const email = document.getElementById('email');
    const password = document.getElementById('password');
    const loginBtn = document.getElementById('loginBtn');
    const logoutBtn = document.getElementById('logoutBtn');
    const authSection = document.getElementById('authSection');
    const orderSection = document.getElementById('orderSection');
    const target = document.getElementById('target');
    const quantity = document.getElementById('quantity');
    const service = document.getElementById('service');
    const orderBtn = document.getElementById('orderBtn');
    const statusBox = document.getElementById('status');

    loginBtn.onclick
