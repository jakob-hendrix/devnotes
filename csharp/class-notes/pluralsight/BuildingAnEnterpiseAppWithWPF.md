# Notes

## Course Description

Course: Building an Enterprise App with WPF, MVVM, and Entity Framework Code First

These are my notes for the class found at https://app.pluralsight.com/library/courses/wpf-mvvm-entity-framework-app/

## Steps

* build basic app
* refactor and extend for typical business usage
  * CRUD
  * validate input
  * handle different business relationships

## Architecture

* outline
  * N-tier and client-server architecture
    * N-tier - uses a middle layer to hold the logic, between the user and the database
    * client-server - the backend code exists along side the client code (UI)
* the app: friedn oragnized
  * plan layout
  * set up the solution

### The app's layout

* 3 projects
  * client (WPF)
    * MVVM - view, viemodel, data service
  * Models
    * Friend
  * Data Access
    * EF DBContext -> SQL Server
