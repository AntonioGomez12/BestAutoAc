<template>
    <nav class="navbar">
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
    name: 'NavigationBar',
  };
  </script>
  
  <style>
  /* Add your CSS styles for the navigation bar here */
  .navbar {
    display: flex;
    width: 100%;
    height: 20%;
    position: fixed;
    top: 0;
    left: 0;
    background-color: #333;
    align-items: flex-end;
    color: #fff;
  }
  
  .nav-links {
    position: bottom;
    list-style: none;
    padding: 0;
    margin: 0;
  }
  
  .nav-links li {
    display: inline-block;
    margin: 0 10px;
  }
  
  .nav-links li a {
    color: #fff;
    text-decoration: none;
  }
  
  .nav-links li a:hover {
    color: #ddd;
  }
  </style>
  