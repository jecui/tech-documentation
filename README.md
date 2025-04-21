# Stocks Simulator

Welcome to Stocks Simulator! Thank you for taking the time to explore this project. Continue reading below for information on how to run the program, its features, design, and more.

![GUI Screenshot](https://github.com/jecui/tech-documentation/blob/main/GUI%20Screenshot.png)

## 📑 Table of Contents

1. [Table of Contents](#-table-of-contents)
2. [Overview and Purpose](#-overview-and-purpose) 
3. [Features](#-features) 
4. [Getting Started](#-getting-started)
5. [Design](#-design)
6. [Language and Frameworks](#-language-and-frameworks)
7. [Changelog](#-changelog)
8. [Project Status and Objectives](#-project-status-and-objectives)
9. [Collaborators](#-collaborators)
## 🧭 Overview and Purpose

Stocks Simulator is a tool designed to simulate real-world stock trading by allowing users to create, manage, and analyze personalized stock portfolios using actual market data. It was developed to demonstrate core Object-Oriented Design (OOD) principles through an interactive application.

By interacting with this program, users can:
* "Buy" and "sell" stock on any past or current date,
* Explore how portfolios evolve over time,
* Experiment with different trading strategies, and
* Analyze stock performance and trends

Stocks Simulator ensures data persistence and offline access through file management. Portfolios and fetched API data are fully persistent. The application is integrated with the AlphaVantage API to pull real-time stock information and store it for later use, ensuring both interactivity and reliability. 

## ✨ Features

### ⚡ Personal Portfolio Simulation
- Create, save, and retrieve multiple portfolios with shares of stock(s), even when the program has been restarted.
- Simulate the buying and selling of stock in portfolios on a specified date.
- Rebalance a specified portfolio on a specified date using custom weights.
### ⚡ Real Data Calculations
- Determine the value, composition, and distribution of a specified portfolio on a specific date.
- Calculates gain, loss, or maintenance of a stock in a specified period of time.
- Calculates the x-day moving average of a stock for a specified day.
- Determines which days are "x-day crossover days" (when the closing price for a day is greater than the x-day moving average for that day) for a stock over a specified period of time.
- Plot a bar chart that illustrates the performance of a given stock or existing portfolio over a given time frame.
- Supports any stock available in the AlphaVantage API.
- Data can be accessed even when the program has been restarted or there is no internet connection.
#### Notes:
- Sell transactions must be done on a date after all buy transactions.
- Calculating gain/loss, x-day moving average, x-day crossover days, buying and selling stock, and rebalancing does NOT support or use holidays and weekends.
- Determining value, composition, and distribution and plotting a bar chart DOES support holidays and weekends.
- Downloaded data only support dates up to the non-weekend or non-holiday date before or on the day it was downloaded on.

## 🚀 Getting Started

1. Download this project or clone it through GitHub.
2. Create a new folder anywhere and move just the `res` folder inside.
3. Take the `Assignment.jar`  file out of the `res` folder but keep it in the folder you just created.
4. Open your machine's command terminal.
5. Navigate to your newly created folder in the terminal and enter the command: 
```shell
java -jar Assignment.jar
```
6. To access the text version* of the program, enter instead:
```shell
java -jar Assignment.jar -text
```

The program should now start.

## 📐 Design

The design used in this program follows the Model-View-Controller (MVC) design pattern.

<details> 
  <summary><i>What is MVC?</i></summary> 
MVC is a way of organizing code in programs so that different parts of the program have clear roles.

<ul>
<li>The <b>Model</b> handles the data and logic.</li>
<li> The <b>View</b> handles what the user sees.</li>
<li>The <b>Controller</b> handles user input and connects the Model and View.</li>
</ul>
</details>

There are 3 version of this program and all versions **build upon the previous** as required by the class assignments and project description. Feel free to take your time exploring how this program is visually layered and designed in the diagram below, as well as how the numerous classes and interfaces relate.

![Design Diagram](https://github.com/jecui/tech-documentation/blob/main/Design%20Diagram.png)

_Click on the diagram for better quality if needed._

Every class has been thoroughly tested.

<details> 
  <summary><i>What are classes and interfaces?</i></summary> 
<ul> 
<li>A <b>class</b> defines how something works and what it can do. It includes all the details; the data it holds and the actions it can perform. </li>
<li>An <b>interface</b> just defines a set of actions something must be able to do. It doesn’t say how those actions work, only that they must exist. </li>
</ul>
</details>

<details> 
  <summary><i>What is an API?</i></summary>An <b>API</b> (Application Programming Interface) is a set of protocols and tools that allow different software applications to communicate and interact with each other, enabling them to request and exchange data or services.
</details>

## 🧪 Language and Frameworks
The following are the languages and frameworks involved in the development of this program:
- Java
- JUnit
- Java Swing

## 📝 Changelog

For those with programming experience:
### 🔧 Changes in Version 2.0
- Enabled extensibility by changing select private methods and fields to `protected`, allowing subclasses to build upon existing functionality.
- Refactored `StocksController` to separate command processing into helper methods, improving clarity and maintainability.
- Modified `StocksData`:
	*  Changed the API constant into a `protected` method to support alternate API keys for subclasses like `PortStocksData`.
	* Introduced a `protected` URL field to make switching data sources easier in the future.
- Updated the data model:
    - Replaced the `Model` field in `StocksController` with a `PortModel` instance, enabling support for portfolio-specific features.
    - Changed the `shares` field from `int` to `double` to support partial shares (e.g., from rebalancing), improving the realism of transactions.
- Improved file-based portfolio logic by adding a `String` field to the `getTickers` method in `Portfolio`, enabling date-sensitive stock retrieval.
### 🔧 Changes in Version 3.0
- Reduced method coupling:
    - Removed `Scanner` arguments from controller methods.
    - Stored the `Scanner` as a field for more flexibility and cleaner interfaces.
- Improved user interaction:
    - Based on Version 1.0 feedback, updated the menu behavior so it reappears automatically after each command or error, making the interface more intuitive and responsive.

## 📌 Project Status and Objectives
Please be aware that this project is currently inactive, and no additional updates are planned, as it has fulfilled the following objectives:

- Simulate stock trading by creating, managing, and analyzing personalized stock portfolios.
- Enable buying and selling of stock on specified dates to model real-world trading scenarios.
- Rebalance portfolios using custom weights on specified dates.
- Use real stock data from the AlphaVantage API for real-time trading simulations and offline data access.
- Calculate portfolio value, composition, and distribution on specific dates.
- Track gain, loss, and maintenance of stocks over specified time periods.
- Implement moving averages and crossover days to analyze stock trends and performance.
- Support portfolio analysis and chart plotting for visualizing stock and portfolio performance.
- Ensure data persistence for portfolios and fetched stock data through file management.
- Adhere to MVC design pattern.
- Allow extensibility for future updates and modifications.

## 🤝 Collaborators
This program was designed and implemented by Harry Duong and Jennifer Cui.
