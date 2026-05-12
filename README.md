# Salon Lluvia Web Application
This is the **Angular** frontend portion for a local salon's website built to support online appointment scheduling, gallery browsing, and delivery of general business information. View the ASP.NET Core Web API backend portion [here](https://github.com/boros41/salonlluvia).

## Azure Deployment
This Angular project is deployed on **Microsoft Azure Static Web App** using:
-  **Angular**
-  **Angular Components**
-  **Angular Routing**
-  **Reactive Forms**
-  **Angular Validators**
-  **Angular HttpClient**
-  **Angular Material UI**

This deployment supports a public-facing business website for a local salon's operation.

## Appointment Scheduling Integration
Communicates with the ASP.NET Core Web API [backend](https://github.com/boros41/salonlluvia) using Angular's HttpClient for requests with the fetch API to receive and send data as JSON for the [Calendly REST API](https://developer.calendly.com/getting-started) in order to:
- Display only valid appointment dates
- Populate an Angular Material UI date picker component with available days
- Submit user input so the backend can validate and schedule their appointment

This helps the business provide a smoother booking experience and reach more clients.

## Authentication and Authorization
Client-side validation is used for a better user experience via Angular's built-in validators along with custom ones for emails and phone numbers. However, server side validation is performed on the ASP.NET Core Web API [backend](https://github.com/boros41/salonlluvia) and is the single source of truth. 

The following data is validated on the client:
- Phone number
- Email
- Appointment date
- Uploaded images (if the user is authorized)

This improves page responsiveness as data is validated on the client before making a server HTTP request.

## Cloud Image Storage
The gallery page makes an HTTP GET request via Angular's HttpClient to the [backend](https://github.com/boros41/salonlluvia) which integrates **Azure Blob Storage** with **Microsoft Entra ID** authentication to securely store and retrieve uploaded gallery images. If a user is authorized with the admin role, they may also upload images.

This enables:
- Secure cloud-based image storage
- Scalable media delivery
- Public gallery access for site visitors

## Gallery Page
Uses the [Masonry](https://masonry.desandro.com/) and [lightbox3](https://lokeshdhakar.com/projects/lightbox3/) JavaScript libraries to provide a responsive image viewing experience with the ability to filter images by gender, hairstyle, and hair color.

![Gallery page's masonry layout](https://i.imgur.com/Pkxvw9V.png)
![Gallery page's lightbox image popup](https://i.imgur.com/aualq6U.png)

## Appointment Page
Uses [Angular Meterial UI](https://material.angular.dev/) components to provide a form for clients to schedule appointments with the salon. Client-side validation is performed with Angular validators. The user's information is sent to the [backend](https://github.com/boros41/salonlluvia) where the appointment is created through the [Calendly REST API](https://developer.calendly.com/getting-started) after server-side validation. 

![Appointment page](https://i.imgur.com/mC2I6Wc.png)

## Project Highlights
- Angular frontend application deployed on **Microsoft Azure Static Web App**
- Real-world business website for a local salon
-  **Calendly API** integration for appointment automation
-  **Azure Blob Storage** with **Microsoft Entra ID** for secure image management
