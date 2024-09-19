---
layout: post
title: Ahmads blog!!!
description: click here to see my blog
type: issues
comments: True
---

# Ahmads blog
Hi, and welcome to my blog. Right now I have not done anything but enjoy this fun little thing I made.
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Animated Text</title>
    <style>
        body {
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            background-color: #282c34;
            color: #61dafb;
            font-family: 'Arial', sans-serif;
            text-align: center;
        }

        .animated-text {
            font-size: 2rem;
            font-weight: bold;
            animation: textAnimation 2s infinite;
        }

        @keyframes textAnimation {
            0% { opacity: 0; transform: translateY(-20px); }
            50% { opacity: 1; transform: translateY(0); }
            100% { opacity: 0; transform: translateY(20px); }
        }
    </style>
</head>
<body>
    <div class="animated-text">Hello, World!</div>
</body>
</html>


