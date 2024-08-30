
## Cat API Project with Beego and JavaScript
This project implements a web application that interacts with The Cat API using Beego for the backend and JavaScript for frontend interactions. The application features four main sections: Voting, Breeds, Favorites and Voted.


## Table of Contents
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [API Endpoints](#api-endpoints)
- [Authentication](#authentication)
- [Project Structure](#project-structure)
- [API Integration](#api-integration)
- [Contributing](#contributing)
## Features
#### Voting Section
- Displays random cat images fetched from The Cat API.
- Allows users to upvote or downvote images.
- Enables users to add images to their favorites.
#### Breeds Sectio
- Provides a search bar with breed options fetched from the Breeds API.
- Displays breed-specific images and information upon selection.
- Shows breed details including name, origin, and Wikipedia link.
#### Favorites Section
- Displays images that users have added to their favorites.
- Retrieves favorite images from the favorites API.
- User can remove images from the favorites API.
#### Voted Section
- Displays images that users have voted from votes API.
- Retrieves voted images from the votes API.


## Prerequisites

- Go 
- Beego framework
#### Tech Stack

- Backend: Beego
- Frontend interaction : vanilla JavaScript
- API: The Cat API

## Installation

#### 1.Clone the repository:
``` bash 
git clone https://github.com/samayunPathan/Beego-assignment-W3.git
```
#### 2.Go project directory
``` bash
cd Beego-assignment-W3
```
#### 3.Install Go dependencies:
```bash
go mod tidy
```



#### 4.Configuration

Create a conf/app.conf file in your Beego project root.
Add your Cat API key to the configuration file:
```bash
appname = cat-api-project
httpport = 8080
runmode = dev
copyrequestbody = true
catApiKey = "your api key"

```

#### 5.Running the Application

- Start the Beego server:
```bash
bee run
```
Open your browser and navigate to http://localhost:8080(or the port specified in your Beego configuration).


## API Endpoints

#### The Cat API Base URL
This API interacts with The Cat API. The base URL for The Cat API is:

`https://api.thecatapi.com/v1`
### Endpoints

### GET /breeds

Fetches all cat breeds

**Response :**  
- Array of breed objects


### GET /random-cat

Fetches a random cat image

**Response:**

- Cat object with image URL


### GET /breed-images/:breed_id

Fetches images for a specific breed

**Response:**
- Array of cat objects with image URLs


### POST /favorite

Adds a cat to favorites

** Request body:**

`{"image_id": image_id,
"sub_id":   "demo-samayun"}`

**Response:**
- Favorite object


### GET /favorites

Fetches all favorited cats

**Response:**

- Array of favorite objects


### DELETE /favorites/delete/:favorite_id

Removes a cat from favorites

**Response:**
- Status code 200 on success


### POST /vote

Votes on a cat image

**Request body:**

	`{"image_id":"image_id","sub_id": "demo-samayun","value":voteValue}`

**Response:**

- Vote object


### GET /votes

Fetches all votes

**Response:**
- Array of vote objects or message if no votes found



## Authentication
> [!NOTE]
The Cat API key is managed server-side in this implementation. Requests to The Cat API include the API key as a query parameter or header, depending on the endpoint.

## Project Structure
```

Copycat-api-project/
├── conf/
│   └── app.conf
├── controllers/
│    └── default.go
│   
├── models/
│   └── cat.go
├── routers/
│   └── router.go
├── static/
│   └── js/
│   |   └── main.js
|   └── css/
│       └── style.css
├── views/
│    └── index.tpl
│   
├── main.go
└── README.md
```
## API Integration
The project uses Go channels for API calls to The Cat API. This allows for efficient, concurrent handling of requests.
## Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

