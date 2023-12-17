# A Monte Carlo Simulation to Compare the TCO of ICEV & BEV for Gojek Driver

This script is designed to model the cost and revenue of operating electric vehicles (EVs) under different scenarios. The primary focus is on two types of electric vehicles: "Beat Street" and "Viar New Q1." The model covers various aspects, including fuel costs, maintenance costs, replacement costs, purchase costs, taxes, and revenues.

## Table of Contents

- [Introduction](#introduction)
- [Setup](#setup)
- [Dependencies](#dependencies)
- [Modeling Components](#modeling-components)
  - [Fuel Cost](#fuel-cost)
  - [Replacement Cost](#replacement-cost)
  - [Maintenance Cost](#maintenance-cost)
  - [Purchase Cost](#purchase-cost)
  - [Vehicle Tax](#vehicle-tax)
  - [CO2 Tax](#co2-tax)
  - [Revenue](#revenue)
  - [Resale Revenue](#resale-revenue)
- [NPV and Replication](#npv-and-replication)
- [Usage](#usage)

## Introduction

The script aims to simulate and analyze the total cost of owning and operating electric vehicles over a specified period. It considers different scenarios and parameters, allowing users to understand the financial aspects of electric vehicle ownership.

## Setup

Before running the script, make sure to set up the necessary parameters at the beginning of the script. These parameters include the simulation period (`y`), distances for different scenarios (`d1_dod`, `d2_dod`, `d3_dod`, `d4_dod`), work time (`W_hd`, `W_dw`, `W_dm`, `W_dy`), service costs, battery specifications, fuel prices, vehicle prices, tax rates, CO2 tax, and customer-related earnings.

## Dependencies

To run the script, you need to install the required Python packages. You can do this by executing the following command:

```bash
pip install fitter
```

## Modeling Components

### Fuel Cost

The script models the fuel cost for both gas and electricity, considering different distribution tests. It uses statistical distributions to simulate the consumption and returns of gas and electricity.

### Replacement Cost

The replacement cost is modeled based on the Viar New Q1 vehicle. The script considers the proportion of energy usage and calculates the replacement cost accordingly, taking into account the battery's maximum charge.

### Maintenance Cost

The maintenance cost is modeled for both "Beat Street" and "Viar New Q1." The number of services is determined based on the distance covered, and the cost is calculated accordingly.

### Purchase Cost

The script models the purchase cost for both vehicle types. It provides flexibility for users to input different prices for each vehicle.

### Vehicle Tax

Vehicle tax is calculated based on the purchase price and the specified tax rates for each vehicle type.

### CO2 Tax

CO2 tax is modeled considering the distance covered and predefined CO2-related parameters.

### Revenue

The script models the revenue generated by the vehicles, taking into account availability, potential revenue, and other factors. It uses statistical distributions to simulate the number of customers and their average distance.

### Resale Revenue

The resale revenue is modeled for both "Beat Street" and "Viar New Q1." It considers a linear regression model based on the simulation period.

## NPV and Replication

The script includes functions for calculating the Net Present Value (NPV) of cash flows and conducting replications to assess the model's robustness. It allows users to analyze the NPV per distance traveled over multiple replications.

## Usage

To use the script, update the parameters at the beginning of the file to match your specific scenario. Then, run the script using a Python interpreter. Review the results and analyze the generated plots to understand the financial implications of electric vehicle ownership under the specified conditions.

## Modeling Components

### Fuel Cost

The script models the fuel cost for both gas and electricity, considering different distribution tests. It uses statistical distributions to simulate the consumption and returns of gas and electricity.

#### Gas Fuel Cost Formula
\[ C_{\text{{gas}}} = \text{{gas\_price}} \times \text{{gas\_consumption\_distribution}} \]

#### Electricity Fuel Cost Formula
\[ C_{\text{{electricity}}} = \text{{electricity\_price}} \times \text{{electricity\_consumption\_distribution}} \]

### Replacement Cost

The replacement cost is modeled based on the Viar New Q1 vehicle. The script considers the proportion of energy usage and calculates the replacement cost accordingly, taking into account the battery's maximum charge.

#### Replacement Cost Formula
\[ C_{\text{{replacement}}} = \left( \frac{{\text{{energy\_usage\_proportion}}}}{{\text{{battery\_max\_charge}}}} \right) \times \text{{vehicle\_price}} \]

### Maintenance Cost

The maintenance cost is modeled for both "Beat Street" and "Viar New Q1." The number of services is determined based on the distance covered, and the cost is calculated accordingly.

#### Maintenance Cost Formula
\[ C_{\text{{maintenance}}} = \text{{service\_cost\_per\_distance}} \times \text{{distance\_covered}} \]

### Purchase Cost

The script models the purchase cost for both vehicle types. It provides flexibility for users to input different prices for each vehicle.

#### Purchase Cost Formula
\[ C_{\text{{purchase}}} = \text{{vehicle\_price}} \]

### Vehicle Tax

Vehicle tax is calculated based on the purchase price and the specified tax rates for each vehicle type.

#### Vehicle Tax Formula
\[ C_{\text{{vehicle\_tax}}} = \text{{purchase\_price}} \times \text{{tax\_rate}} \]

### CO2 Tax

CO2 tax is modeled considering the distance covered and predefined CO2-related parameters.

#### CO2 Tax Formula
\[ C_{\text{{CO2\_tax}}} = \text{{CO2\_emission\_rate}} \times \text{{distance\_covered}} \]

### Revenue

The script models the revenue generated by the vehicles, taking into account availability, potential revenue, and other factors. It uses statistical distributions to simulate the number of customers and their average distance.

#### Revenue Formula
\[ C_{\text{{revenue}}} = \text{{availability}} \times \text{{potential\_revenue\_distribution}} \]

### Resale Revenue

The resale revenue is modeled for both "Beat Street" and "Viar New Q1." It considers a linear regression model based on the simulation period.

#### Resale Revenue Formula
\[ C_{\text{{resale\_revenue}}} = \text{{resale\_price\_intercept}} + (\text{{resale\_price\_slope}} \times \text{{simulation\_period}}) \]


