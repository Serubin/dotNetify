<p align="center"><img width="400px" src="http://dotnetify.net/content/images/dotnetify-logo.png"></p>

![alt build](https://ci.appveyor.com/api/projects/status/github/dsuryd/dotnetify?svg=true)
[![npm version](https://badge.fury.io/js/dotnetify.svg)](https://badge.fury.io/js/dotnetify)
[![NuGet](https://img.shields.io/nuget/v/DotNetify.SignalR.svg?style=flat-square)](https://www.nuget.org/packages/DotNetify.SignalR/) [![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2FSerubin%2FdotNetify.svg?type=shield)](https://app.fossa.com/projects/git%2Bgithub.com%2FSerubin%2FdotNetify?ref=badge_shield)


DotNetify is a free, open source project that lets you create real-time, reactive, cross-platform apps with [React](https://facebook.github.io/react/), [React Native](https://facebook.github.io/react-native/), [Vue](https://vuejs.org) or [Knockout](http://knockoutjs.com) front-end on C# .NET back-end via WebSocket (SignalR). 

## What's New

* v3.6: [release notes](https://github.com/dsuryd/dotNetify/releases/tag/v3.6)
* v3.5: Multi-hub support, web API + local modes - [release notes](https://github.com/dsuryd/dotNetify/releases/tag/v3.5).

<div/>

* Check out [**DotNetify-Pulse**](https://github.com/dsuryd/dotnetify-pulse), customizable realtime monitoring for .NET Core services.
* **DotNetify-Elements** is out! <a href="http://dotnetify.net/elements">See documentation and live demo.</a> 
* React SPA template for ASP.NET Core 2.x - [github](https://github.com/dsuryd/dotnetify-react-demo-vs2017/tree/master/ReactTemplate).

## Features

* Simple and lightweight - no heavy client-side framework, no REST APIs.
* Reactive back-end MVVM architecture on either .NET Core or .NET Framework.
* Built-in real-time across WebSocket with SignalR.
* Support local (client-side only) and Web API modes.
* Full support for single-page apps, including deep-linked, nested routing and token-based authentication.
* Powerful back-end infrastructure, including dependency injection, WebSocket request/response pipelines, and modern tooling.

## Documentation

Documentation and live demo can be found at [https://dotnetify.net](http://dotnetify.net).

[Usage with .NET Core 3.0](https://github.com/dsuryd/dotNetify/issues/159#issuecomment-547691063)

## Code Examples

* React example: [dotnetify-react-demo-vs2017](https://github.com/dsuryd/dotnetify-react-demo-vs2017).   
* React Native example: [dotnetify-react-native-demo](https://github.com/dsuryd/dotnetify-react-native-demo).
* Other examples: [demo github repo]([https://github.com/dsuryd/dotNetify/tree/master/Demo]).


## Installation

*$ npm install dotnetify --save*

ASP.NET Core:

*PM> Install-Package DotNetify.Core*  
*PM> Install-Package DotNetify.SignalR*  

ASP.NET Framework:

*PM> Install-Package DotNetify.Core*  
*PM> Install-Package DotNetify.SignalR.Owin*  

Read the website on how to configure your project.

## License
Licensed under the Apache License, Version 2.0.


[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2FSerubin%2FdotNetify.svg?type=large)](https://app.fossa.com/projects/git%2Bgithub.com%2FSerubin%2FdotNetify?ref=badge_large)

## Contributing
All contribution is welcome: star this project, let others know about it, report issues, submit pull requests!

_Logo design by [area55git](https://github.com/area55git)._