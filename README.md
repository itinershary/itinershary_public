# Itinershary API

Welcome to the Itinershary API repository! This API allows users to create, update, and delete itineraries via HTTP requests. All actions are authenticated using a secure access token.

## Table of Contents

- [Overview](#overview)
- [Getting Started](#getting-started)
- [Authentication](#authentication)
- [API Endpoints](#api-endpoints)
  - [Create Itinerary](#create-itinerary)
  - [Update Itinerary](#update-itinerary)
  - [Delete Itinerary](#delete-itinerary)
- [Filing Issues](#filing-issues)
- [Communication](#communication)
- [Contributing](#contributing)
- [License](#license)

## Overview

The Itinershary API provides a straightforward interface for managing itineraries. It supports the creation of interactive itineraries event by event, allowing you to set event location, description, time, and additional media. Users can easily manage itineraries through simple HTTP requests.

## Getting Started

To use the Itinershary API, you will need an access token for authentication. This token must be included in the headers of your HTTP requests.

## Authentication

Authentication is done using a secret access token. Include this token in the header of each request:

```
Authorization: Bearer YOUR_ACCESS_TOKEN
```

## API Endpoints

### Create Itinerary

`POST /itineraries`

Create a new itinerary.

**Request Body:**
```json
{
  "title": "Itinerary Title",
  "description": "Description of the itinerary",
  "events": [
    {
      "location": "Event Location",
      "description": "Event Description",
      "time": "YYYY-MM-DDTHH:mm:ssZ",
      "image": "Optional image URL or AI-generated image based on description"
    }
  ]
}
```

**Response:**
- Returns the created itinerary object.

### Update Itinerary

`PUT /itineraries/{id}`

Update an existing itinerary.

**Request Body:**
```json
{
  "title": "Updated Title",
  "description": "Updated Description",
  "events": [ /* Array of event updates */ ]
}
```

**Response:**
- Returns the updated itinerary object.

### Delete Itinerary

`DELETE /itineraries/{id}`

Delete an existing itinerary.

**Response:**
- Returns a success message upon deletion.

## Filing Issues

If you encounter any problems while using the Itinershary API, please open an issue in this repository. Provide as much detail as possible about the issue you’re experiencing, including request details and any error messages.

## Communication

For general inquiries, feedback, or suggestions, feel free to reach out to the Itinershary engineering team through this repository. We value your input and aim to improve the API based on user experiences.

## Contributing

While this repository primarily serves to file issues, we welcome any suggestions or contributions to improve API functionality. Please adhere to best practices and ensure your contributions align with our vision for Itinershary.

## License

To use Itinershary, please register for an Itinershary account and buy a software license.  (See our [pricing](https://itinershary.net/pricing.html)).
