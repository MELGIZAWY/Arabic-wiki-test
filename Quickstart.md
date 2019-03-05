# Gunbot Quickstart Guide

This guide describes the essential steps to get up and running with Gunbot, using the built-in GUI.


>If you prefer running Gunbot without the GUI, you need to edit the `config.js` file with a text editor to get started. This is the only configuration file for Gunbot that requires any modification. The config.js file is where you add your exchange keys, edit your bot settings, strategies and add trading pairs. Config.js and the GUI are not mutually exclusive: if you edit your settings through the the GUI these will be detected automatically and config.js will be updated accordingly. 
>
>[[Detailed information about all configuration options|Gunbot settings]] 


> **Contents:**
>
> 1. [Download Gunbot](#1-download-gunbot)
> 2. [Installation](#2-unpack--install)
> 3. [Connect to an exchange](#3-connect-to-an-exchange)
> 4. [Configure a trading strategy](#4-configure-a-trading-strategy)
> 5. [Add trading pairs](#5-add-trading-pairs)
> 6. [Start trading](#6-start-trading)
> 7. [Making changes](#7-making-changes)




## 1. Download Gunbot

Download your copy of Gunbot: 

Gunbot Standard edition and higher: https://github.com/GuntharDeNiro/BTCT/releases

Gunbot Starter edition: https://github.com/GuntharDeNiro/Gunthy/releases/





## 2. Unpack & install 

Gunbot has an easy installation process: you only need to unpack the zip file to a new folder. 

Instructions per operating system:

- [[Windows installation|Windows installation]]
- [[Mac OSX installation|Mac OSX installation]]
- [[Linux installation|Linux installation]]
- [[ARM installation|ARM Installation]]

After installing, you can login to the GUI by opening `localhost:5000` in a browser on the same system (modern browsers recommended, preferably Chrome or Firefox).




## 3. Connect to an exchange

To be able to trade, you need to enter the exchange [[API key|api]] and secret. To enter these in the Gunbot GUI, go to **Settings > Trading > Exchanges**.

![exchange-keys](https://user-images.githubusercontent.com/2372008/52206416-707ef380-287a-11e9-8f93-881abdbe9e5b.png)


Select your exchange and fill in all the fields for this exchange.

- **Master Key:** the API key registered to be used with Gunbot. This key may have read only access as long as you use a different Key for actual trading.
- **Master Secret:** The API secret for the Master Key.
- **Key:** The API key used for trading, can be the same as Master Key. This key must exist in the same exchange account as the Master Key.
- **Secret:** The API secret for the Key.
- **Delay:** The delay factor (in seconds) for processing pairs on this exchange. Setting this to 10 should work in almost all cases, you can lower it later to speed up pair processing after you've verified that everything works.


#### Register API keys to GUNTHY wallet (optional)

Manage your own API keys by registering a GUNTHY wallet address. After the initial key registration you will be able to update the API keys used for Gunbot any time you like, at no cost.


Read more about [[managing API keys|API key management]].



## 4. Configure a trading strategy

Before you start trading with Gunbot you'll need to configure a trading strategy to later assign to a trading pair. Do this, go to **Settings > Strategies > Strategy Configurator**.

![image](https://user-images.githubusercontent.com/2372008/51757361-724ef700-20c3-11e9-8690-3b957b96a75b.png)


The easiest option to begin with, and learn how Gunbot works, is with the [Emotionless:](Emotionless) strategy. Make sure that the [balance settings](Emotionless#balance-settings) reflect the amount of base currency Gunbot is allowed to use for each buy order and that the correct trading fees are set.


[[Detailed information about Gunbot strategies|About Gunbot strategies]]



## 5. Add trading pairs

Add one or more trading pairs and assign them the strategy you configured in the previous step. To do so, go to **Settings > Trading > Trading Pairs**.

![image](https://user-images.githubusercontent.com/2372008/51761865-792f3700-20ce-11e9-8a4e-ba331b806136.png)

[[Read about how trading pairs work in Gunbot|Gunbot-settings#pairs]]



## 6. Start trading

To start trading the configured pairs, click on the **START BOT CORE** button on the **Settings** page. 

![image](https://user-images.githubusercontent.com/2372008/51761890-8ea46100-20ce-11e9-90ea-4eb69773d510.png)

To monitor your Gunbot, go to the **Dashboard**. It can take a small moment for data to appear on the dashboard after starting the bot core. Refresh the dashboard after a few seconds if it's empty at first.

Make sure to keep the computer Gunbot runs on powered on. It will not be able to trade when the computer is off or in sleep/hibernation mode. You can safely close the browser and Gunbot will continue to run in the background.



## 7. Making changes

When you want to make any changes such as adding a new trading pair, all changes are queued and will take effect once you hit the **SAVE CHANGES** button.


[[Read more about working with the Gunbot GUI|Using-Gunbot-GUI]]







