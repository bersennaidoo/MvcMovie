# Movie App Microsoft DOT NET Tutorial

## Description
Tracks the activities of movie lovers

## Badges

## Visuals

## Installation

    1. Install dotnet8 sdk includes (cli and runtime)

## Usage

    1. Clone repo and cd into MvcMovie
    2. dotnet restore to update packages
    3. dotnet run to run app and add,delete,edit movies
## Notes
If you on linux you out of luck for generating scaffolding for the Movie Model because visual studio
is not supported on linux.

Alternate solution is dotnet-aspnet-codegenerator below are the instructions to perform:

    1. dotnet tool install -g dotnet-aspnet-codegenerator

    2. dotnet tool install --global dotnet-ef

    3. Create your dotnet project dotnet new mvc -o MvcMovie and cd into MvcMovie

    4. Install required packages to generate scaffolding

        4.1 dotnet add package Microsoft.EntityFrameworkCore.Design

        4.2 dotnet add package Microsoft.EntityFrameworkCore.Tools

        4.3 dotnet add package Microsoft.VisualStudio.Web.CodeGeneration.Design

        4.4 dotnet add package Npgsql.EntityFrameworkCore.PostgreSQL

    5. Create your Movie Model as per tutorial and run the below command and options, 
       I have changed the tutorial database to Postgresql.

    6. dotnet aspnet-codegenerator controller -name MoviesController \
       -m Movie -dc MvcMovie.Data.MvcMovieContext -namespace MvcMovie.Controllers \
        -outDir Controllers -dbProvider postgres

    7. dotnet ef migrations add InitialCreate

    8. dotnet ef database update
    
    9. In your Program.cs file add this only if using Postgresql 
       "AppContext.SetSwitch("Npgsql.EnableLegacyTimestampBehavior", true);" 
        below this "var builder = WebApplication.CreateBuilder(args);", to enable legacy time support for postgresql.

    10. dotnet run 

    11. Continue with tutorial.

## Support

## Roadmap

## Contributing

## Authors and acknowledgment
Bersen Naidoo

## License

## Project status
WIP

