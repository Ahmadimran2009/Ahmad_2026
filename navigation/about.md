---
layout: page
title: country generator
permalink: /about/
---

Created by ahmad

# 🌍 Random Country Generator

Click the button below to get a random country!

<button onclick="generateRandomCountry()">Generate Country</button>

<p id="countryDisplay">Click the button to see a country.</p>

<script>
  // Array of country names
  const countries = [
    'United States', 'Canada', 'Brazil', 'United Kingdom', 'Germany', 
    'France', 'Italy', 'Australia', 'Japan', 'China', 'Pakistan', 'South Africa', 
    'Mexico', 'Argentina', 'Spain', 'Russia', 'Egypt', 'Thailand', 'Turkey', 
    'New Zealand', 'South Korea','Ireland'
  ];

  function generateRandomCountry() {
    // Generate a random index
    const randomIndex = Math.floor(Math.random() * countries.length);
    // Display the random country
    document.getElementById('countryDisplay').innerText = countries[randomIndex];
  }
</script>
