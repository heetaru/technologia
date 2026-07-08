# MARCI

## Overview

MARCI is an intelligent university and faculty recommendation platform designed to help students make one of the most important decisions of their lives. By combining a modern web interface with an integrated AI assistant, MARCI simplifies the search process, allowing users to discover, filter, and save academic programs that truly fit their goals.

## Features

* **AI Assistant:** A built-in ChatGPT-powered advisor that understands user preferences and suggests the best matching faculties in real time.
* **Smart Filtering:** Effortlessly filter academic programs by degree type (Bachelor, Master, PhD, etc.) and country.
* **User Accounts & Favorites:** Students can create profiles, log in securely, and save their favorite faculties for quick access later.
* **Faculty Registration System:** A comprehensive multi-step workflow for universities to list their programs, upload galleries, and define tuition fees, durations, and start dates.
* **Dynamic UI with Theming:** A responsive, clean interface built with Tailwind CSS and daisyUI, featuring instant switching between various color themes (light, dark, corporate, forest, etc.).

## Technologies

* **Backend:** Python, Django 5.2
* **Frontend:** HTML5, JavaScript (AJAX), Tailwind CSS, daisyUI
* **Database:** SQLite
* **AI Integration:** OpenAI API (gpt-4o-mini)

## Architecture

MARCI follows a monolithic architecture built on top of the Django framework. The backend manages data models for students, faculties, degrees, and media, while handling
user authentication and routing. The frontend is powered by Django templates layered with Tailwind CSS for styling. To provide a seamless user experience, vanilla
JavaScript is used to handle asynchronous AJAX requests, allowing users to toggle favorite faculties and chat with the AI assistant without reloading the page.
The OpenAI logic is securely encapsulated on the server, maintaining state and chat history in the database.

## API

While MARCI primarily uses server-rendered HTML, it implements custom
asynchronous endpoints to handle dynamic features:

  * POST /ajax/save-faculty/ — Toggles the saved/liked status of a specific
    faculty for the logged-in student.
  * POST /chat/ — Processes user messages, interacts with the OpenAI API, saves
    conversation history, and dynamically updates the chat UI.
