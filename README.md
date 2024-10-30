# Itinershary API

Welcome to the Itinershary API repository! This API allows users to create, update, and delete itineraries via HTTP requests. All actions are authenticated using a secure access token.

## Table of Contents

- [Overview](#overview)
- [Sign Up](#sign-up)
- [Billing](#billing)
- [API rate limit](#api-rate-limitation)
- [Authentication](#authentication)
- [API Endpoints](#endpoint-create-an-itinerary)
  - [Create Itinerary](#endpoint-create-an-itinerary)
  - [Upload Image](#endpoint-upload-image)
  - [Delete Itinerary](#endpoint-delete-itinerary)
- [Filing Issues](#filing-issues)
- [Communication](#communication)
- [Contributing](#contributing)
- [License](#license)

## Overview

The Itinershary API provides a straightforward interface for managing itineraries. It supports the creation of interactive itineraries event by event, allowing you to set event location, description, time, and additional media. Users can easily manage itineraries through simple HTTP requests.


## Sign Up
Sign up for an Itinershary account [here](https://itinershary.net/account/register).
By signing up you agree to our [terms and conditions](https://itinershary.net/documentation/documentation.html#terms-and-conditions-of-use) as well as our [privacy policy](https://itinershary.net/privacy_policy.html).

## Billing
Itinershary API usage is free of charge as part of an active enterprise or premium Itinershary subscription.

## API rate limitation
The Itinershary API is rate limited to protect our servers. The default rate limitation of 10 requests per minute can be lifted. Please [contect us](mailto:support@itinershary.net) to increase this rate limitation.

## Authentication
Authenticate with our API endpoints through passing your secret token as HTTP POST parameter with each request.

You can activate API access and create a secret token through your [accounts page](https://itinershary.net/profile), when logged in with your Itinershary account.

## Endpoint Create an itinerary
Use this endpoint in your application to create a new itinerary. The itinerary will be created without event images. Those can be uploaded after the itinerary has been created, through the [image upload endpoint](#itinershary-api-endpoint-upload-image).

```html
https://itinershary.net/api/create_itinerary_api
```
### Required and optional parameters

| POST Parameter  | Description | Type |
| ------------- | ------------- |------------- |
| secret_token  | Create a secret token through your [accounts page](https://itinershary.net/profile) |`String`|
| email | Email address that the Itinershary account was created with.|`String`|
| json_config |  Configuration of the Itinerary to create. See [configuration section](#itinershary-api-configuration) for details.|`String`|
| api_key | To update an existing itinerary, provide the itinerary ID, as the `api_key` (optional)|`String`|


### API Response
The response when querying the Itinershary API is of type `application/json`.

| Response element  | Description | 
| ------------- | ------------- |
| error  | **True** - An error occurred, **False** - no error| 
| error_msg  | **Successful** - No error, request served as expected, **api_key** - The ID identifying the newly created itinerary., **Exceeded request limit** - Rate limit of account reached.,  **Required parameter is missing!** - A required API parameter is missing in your request., **Invalid Input!** - Your input parameters contain characters that are not allowed.| 

## Endpoint Upload Image
Use this endpoint in your application to upload an image for an existing itinerary event. If an image already exists for the specific itinerary event, it will be replaced.

```html
https://itinershary.net/api/image_upload_api
```
### Required and optional parameters

| POST Parameter  | Description | Type |
| ------------- | ------------- |------------- |
| secret_token  | Create a secret token through your [accounts page](https://itinershary.net/profile) |`String`|
| email | Email address that the Itinershary account was created with.|`String`|
| image |  (optional) A base64 encoded image (`data:image/jpeg;base64,/9j/4AAQSkZJR...`). If the image parameter is not submitted and an image exists for the specified event, the existing image will be deleted. The image size may not exceed 5MB. |`String`|
| api_key | To update an existing itinerary, provide the itinerary ID, as the `api_key` |`String`|
| step | The 0-based event count of your itinerary. e.g. `1` refers to the second event in your itinerary. |`Integer`|


### API Response
The response when querying the Itinershary API is of type `application/json`.

| Response element  | Description | 
| ------------- | ------------- |
| error  | **True** - An error occurred, **False** - no error| 
| error_msg  | **Successful** - No error, request served as expected, **Image too large** - The image is too large and was not accepted., **Exceeded request limit** - Rate limit of account reached.,  **Required parameter is missing!** - A required API parameter is missing in your request., **Invalid Input!** - Your input parameters contain characters that are not allowed.| 


## Endpoint Delete Itinerary
Use this endpoint in your application to delete an existing itinerary.

```html
https://itinershary.net/api/delete_itinerary_api
```
### Required and optional parameters

| POST Parameter  | Description | Type |
| ------------- | ------------- |------------- |
| secret_token  | Create a secret token through your [accounts page](https://itinershary.net/profile) |`String`|
| email | Email address that the Itinershary account was created with.|`String`|
| api_key | To delete an existing itinerary, provide the itinerary ID, as the `api_key` |`String`|



### API Response
The response when querying the Itinershary API is of type `application/json`.

| Response element  | Description | 
| ------------- | ------------- |
| error  | **True** - An error occurred, **False** - no error| 
| error_msg  | **Successful** - No error, request served as expected, **Exceeded request limit** - Rate limit of account reached.,  **Required parameter is missing!** - A required API parameter is missing in your request., **Invalid Input!** - Your input parameters contain characters that are not allowed.| 


## Filing Issues

If you encounter any problems while using the Itinershary API, please open an issue in this repository. Provide as much detail as possible about the issue you’re experiencing, including request details and any error messages.

## Communication

For general inquiries, feedback, or suggestions, feel free to reach out to the Itinershary engineering team through this repository. We value your input and aim to improve the API based on user experiences.

## Contributing

While this repository primarily serves to file issues, we welcome any suggestions or contributions to improve API functionality. Please adhere to best practices and ensure your contributions align with our vision for Itinershary.

## License

To use Itinershary, please register for an Itinershary account and buy a software license.  (See our [pricing](https://itinershary.net/pricing.html)).
