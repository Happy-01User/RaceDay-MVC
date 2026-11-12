# RaceDay-MVC
RaceDay application

#create RaceDay MVC Projects
# Configure MVC Api clienst session
add MVC Registration and login

# RaceDay - Programming 3 PoE

## Project Overview
RaceDay is a full-stack event management system for the South African road running, walking, and cycling community. It allows Organisers to create and manage events, and Participants to browse and enter events.

## User Roles
*   **Organiser:** Can create, edit, delete events. Can view enrolments and capture results.
*   **Participant:** Can browse upcoming events, enter an event, view their own enrolments, and view their results.

## Solution Structure
*   `RaceDay.Api`: ASP.NET Core Web API (Part 2).
*   `RaceDay.Contracts`: Shared DTOs.
*   `RaceDay.Mvc`: ASP.NET Core MVC Web Application (Part 3).
*   `RaceDay.Api.Tests`: Unit tests for the API.

## Prerequisites
*   .NET 8 SDK
*   SQL Server
*   Docker Desktop
*   Azure Storage Account

## How to Run Locally
1.  Update the connection string in `RaceDay.Api/appsettings.json` to point to your local SQL Server.
2.  Run the API: `dotnet run --project RaceDay.Api --urls http://localhost:5000`
3.  Run the MVC app: `dotnet run --project RaceDay.Mvc`
4.  Open the MVC app in your browser (usually `https://localhost:7XXX`).

## Azure Blob Storage Setup
1.  Create an Azure Storage Account.
2.  Copy the connection string into `RaceDay.Api/appsettings.json`.
3.  The API automatically creates the container `raceday-images` on first upload.

## Docker Setup
To run the MVC application in Docker (ensure the API is running on `http://localhost:5000` on your host machine):

**Build the image:**
```bash
docker build -f RaceDay.Mvc/Dockerfile -t raceday-mvc:part3 .
