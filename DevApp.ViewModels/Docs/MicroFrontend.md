## Micro-Frontend

Micro-frontend is a technique that decomposes an otherwise monolithic web application into smaller, isolated, and independently deployable sub-applications.  Each sub-application provides a subset of the UI, which will then be stitched together by a light orchestrator to present a single, cohesive front-end to its users.

While this technique does increase development complexity and brings its own challenges, many large organizations find merits to this approach, as it allows them to better scale their development and deployment process across autonomous, geographically-dispersed teams.

There are many different ways in implementing micro-frontend. What dotNetify proposes is closely aligned to the microservices approach, where aspects of functionality is encapsulated within independent web services (dotNetify on ASP.NET Core applications), each with its own build process and deployment pipeline.  The domain-driven design approach can be employed here on deciding how to slice the problem domain into these distinct services.

The entry to the application is provided by a portal service that performs the front-end orchestration.  That process involves discovering the services, then dynamically loading the static UI script bundles from the running web services, instantiating and composing their root UI components into a single-page application with client-side routing (can be provided by dotNetify), and redirecting the network traffic to appropriate service ports.  

The portal service also takes care of the authentication and authorization for the services, i.e. communicate with an identity server to generate security tokens, then inject the tokens through request interception.  In production environment, we want to put these services behind an API gateway to secure them and expose just a single entry point into the system.

Below is the diagram depicting the architecture:
[inset]

A simple reference implementation covering the application layer of this architecture is provided in the nuget:
```
dotnet new -i dotnetify.react.template

dotnet new dotnetify-mfe -o MyApp

// To run the app, follow the instructions in README.md
```

App Services

Each app service is built from ASP.NET Core application that's been configured to build the UI scripts with Webpack on compile time (dev build on `dotnet run`, prod build on `dotnet publish`).  The main script that serves as the Webpack's entry point is designed to expose the root UI component as a native Web Component, instead of the normal mounting to a DOM tag.   This will allow the portal service later on to create the application's root component at will as a framework-agnostic HTML element and mount it anywhere it likes.

Here is a sample implementation of the main script.  For React, you can use the function provided by dotNetify-Elements to wrap your React component in a HTML Web Component:

```
import { createWebComponent } from 'dotnetify-elements/web-components/core';
import MyApp from './components/MyApp';

const elementName = 'my-app';
createWebComponent(TodoList, elementName);

export default document.createElement(elementName);
```
