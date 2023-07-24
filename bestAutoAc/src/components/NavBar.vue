<template>
    <nav class="navbar">
      <div class="logo">
        <img src="@/assets/logo.jpeg" alt="Logo" />
      </div>
      <ul class="nav-links">
        <!-- Replace the links below with the appropriate routes or URLs -->
        <li><a href="/">Home</a></li>
        <li><a href="/about">About</a></li>
        <li><a href="/contact">Contact</a></li>
      </ul>
    </nav>
  </template>
  
  <script>
  export default {
    name: "NavigationBar",
  };
  </script>
  
  <style>
  /* Add your CSS styles for the navigation bar here */
  .navbar {
    display: flex;
    width: 100%;
    height: 17.5%; /* Set the height of the navigation bar */
    position: relative;
    top: 0;
    left: 0;
    background-color:white;
    color: #fff;
  }
  
  .logo {
    width: 25%; /* Set the width to 25% of the navigation bar width */
    height: auto; /* Set the height to the same as the navigation bar */
  }
  
  .logo img {
    width: 100%; /* Make the image fill the entire width of the logo container */
    height: auto; /* Let the height adjust proportionally */
  }
  
  .nav-links {
    flex: 1;
    display: flex;
    justify-content: flex-start;
    list-style: none;
    padding: 0;
    margin: 0;
  }
  
  .nav-links li {
    display: inline-block;
    margin: 0 10px;
  }
  
  .nav-links li a {
    color: black;
    text-decoration: none;
  }
  
  .nav-links li a:hover {
    color: black;
  }
  </style>
  