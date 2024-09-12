# Next.js and Django Chart Dashboard

## Overview

This project is a web application that displays a dashboard with multiple charts (Candlestick, Line, Bar, and Pie charts) using a Next.js frontend and a Django API backend. The frontend dynamically fetches chart data from the backend and renders it using charting libraries.

### Frontend:
- **Next.js**: A React framework for server-side rendering and generating static websites.
- **SWR**: A React hook for remote data fetching.
- **Chart.js**: A JavaScript library for creating charts.
- **React Chart.js 2**: A React wrapper for Chart.js.
- **Fetch**: HTTP clients to fetch data from the Django API (depending on your implementation).

### Backend:
- **Django**: A Python web framework for building the API.
- **Django REST Framework**: A toolkit to create web APIs in Django.

## Table of Contents
- [Overview](#overview)
- [Setup Instructions](#setup-instructions)
  - [Backend (Django)](#backend-django)
  - [Frontend (Next.js)](#frontend-nextjs)
- [Thought Process](#thought-process)

## Setup Instructions

### Prerequisites
- Node.js (v14+)
- Python (v3.8+)

### Backend (Django)

1. **Clone the Repository**:
    git clone https://github.com/takehome.git
    cd takehome/backend

2. **Create a Virtual Environment**:
    python3 -m venv venv
    source venv/bin/activate

3. **Install Dependencies:**:
    pip install -r requirements.txt

4. **Run the Django Server:**:
    python manage.py runserver


5. **Navigate to the Frontend Directory:**:
    cd ../front

6. **Install Dependencies:**:
    npm install

7. **Run the Next.js Development Server:**:
    npm run dev


### Running with Docker (Optional)
1. Build Docker Image:
    docker-compose up --build

2. Start the Application:
    docker-compose up

3. Start Django server:
    cd takehome/back
    python manage.py runserver


## Thought Process
The approach was to create a simple but robust full-stack application integrating modern frontend and backend technologies:

### Backend:
I set up the backend first, Django was used for the backend API so I tried to capitalize on its simplicity in creating APIs using the Django REST Framework. The API serves hardcoded chart data which I coded in views.py. There is some remnants of code left from api.py which is a resulted from me learning fullstack coding from online. It's not pretty but it's simple and pretty robust.

### Frontend:
I then implemented the front end. In this proces I found that I liked working with Next.js even though I had only mostly worked with React, its server-side rendering and react features made it fairly easy to use, though I ended having to do some client side rendering in the end, it's definitely something I could improve on in the future. 

I used SWR for fetching, the page is designed to load the data when it opens, which should be fine for this project. 

For the chart visuals I used Chart.js with React Chart.js and plotly. I used Chart.js for the line, bar, and pie charts, since I had used them before. However I struggled a lot with getting the candlestick chart to work. I first tried using financial charts, but it wouldn't cooperate and I ended up having to use react and plotly, unfortunately making the candlestick graph a bit of an eyesore.

I have looked into using typescript, but I ran into an issue with the fetcher. In the interest of time, I decided to opt for building a Docker for easier integration, as opposed to refactoring the code for typescript. I also did not implement tests or use redux, I will look into how to build those in the future.