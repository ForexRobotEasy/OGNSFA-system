# OGNSFA System ReadMe

This ReadMe file provides an overview of the OGNSFA System code. 

## Program Information

- Program Name: OGNSFA System
- Developer's Site: [forexroboteasy.com](https://forexroboteasy.com/)
- Development Name: Forex Robot Easy Team

## Libraries Used

The following libraries are included in the code:
- Trade.mqh
- Neuro.mqh

## Constants

The following constants are defined in the code:
- MIN_DEPOSIT: Minimum deposit required for the OGNSFA System (set to 5000)
- CURRENCY_PAIRS: Number of currency pairs for trading (set to 7)

## Global Variables

The code initializes two global variables:
- trade: An instance of the CTrade class for trading operations
- neuro: An instance of the CNeuro class for neural network analysis

## Initialization Function

The `OnInit()` function is responsible for initializing the OGNSFA System. It performs the following tasks:
- Checks if the account balance meets the minimum deposit requirement. If not, it prints an error message and terminates the expert advisor.
- Loads neural networks for analysis using the `LoadNetworks()` method of the `neuro` object.
- Sets the currency pairs for trading using the `SetCurrencyPairs()` method of the `trade` object.
- Sets cent account compatibility using the `SetCentAccount()` method of the `trade` object.
- Sets trading time customization using the `SetTradingTime()` method of the `trade` object.
- Sets broker spread optimization using the `SetSpreadOptimization()` method of the `trade` object.
- Prints a success message indicating that the OGNSFA System has been initialized successfully.

## Tick Function

The `OnTick()` function is called on each tick and handles trading decisions based on neural network analysis. It performs the following tasks:
- Retrieves market data for analysis using the `CopyRates()` function.
- Analyzes the market data using neural networks by calling the `Predict()` method of the `neuro` object.
- Makes trading decisions based on the prediction. If the prediction is greater than 0.5, it calls the `Buy()` method of the `trade` object. If the prediction is less than -0.5, it calls the `Sell()` method of the `trade` object.
- Manages open trades by calling the `ManageTrades()` method of the `trade` object.
- Manages the account balance by calling the `ManageAccountBalance()` method of the `trade` object.

## Deinitialization Function

The `OnDeinit()` function is called when the expert advisor is terminated. It performs the following tasks:
- Closes any open trades by calling the `CloseAllTrades()` method of the `trade` object.
- Prints a termination message indicating that the OGNSFA System has been terminated.

## Product Description

The OGNSFA System is a neural network-based expert advisor designed for forex trading. It utilizes neural networks to analyze market data and make trading decisions. The system is capable of trading multiple currency pairs and is compatible with cent accounts. It also allows customization of trading time and includes broker spread optimization.

Please note that ForexRobotEasy is not the official developer of this product. This code serves as a sample that can work as described in the official product. For detailed reviews and trading results of this product, please visit the [OGNSFA System Review](https://forexroboteasy.com/forex-robot-review/ognsfa-system-review-neural-network-forex-ea/) on the Forex Robot Easy website. To find the official developer of this product, please use MQL5.
