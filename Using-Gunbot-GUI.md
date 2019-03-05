# Using Gunbot GUI

Gunbot GUI is a browser based interface for Gunbot. You can completely manage Gunbot settings through the GUI, as well as monitor your trades and trading performance. 

The GUI can be accessed from the local system Gunbot runs on, or from machines outside your local network when your firewall allows for external traffic.

> While the GUI allows for every kind of configuration change, advanced users can also manually edit <code>config.js</code> and use Gunbot GUI for monitoring. Every setting change made in the GUI is reflected in <code>config.js</code> and vice versa. 


> **Contents:**
>
> 1. [Connect to exchanges](#connect-to-exchanges)
> 2. [Starting and stopping the bot core](#starting-and-stopping-the-bot-core)
> 3. [Bot settings](#bot-settings)
> 4. [Telegram notification settings](#telegram-notification-settings)
> 5. [TradingView add-on settings](#tradingview-add-on-settings)
> 6. [Strategy configurator](#strategy-configurator)
> 7. [Trading pairs](#trading-pairs)
> 8. [Dashboard](#dashboard)
> 9. [Charts](#charts)



## Connect to exchanges

On **Settings > Trading > Exchanges** you can manage your exchange connections. 

![exchange-keys](https://user-images.githubusercontent.com/2372008/52206416-707ef380-287a-11e9-8f93-881abdbe9e5b.png)

You can use Gunbot to trade on multiple exchange simultaneously. Trading pairs for the connected exchange are processed in parallel.

To connect to a new exchange, select your exchange and fill in all the fields for this exchange.

- **Master Key:** the API key registered to be used with Gunbot. This key may have read only access as long as you use a different Key for actual trading.
- **Master Secret:** The API secret for the Master Key.
- **Key:** The API key used for trading, can be the same as Master Key. This key must exist in the same exchange account as the Master Key.
- **Secret:** The API secret for the Key.
- **Delay:** The delay factor (in seconds) for processing pairs on this exchange. Setting this to 10 should work in almost all cases, you can lower it later to speed up pair processing after you've verified that everything works.


#### Register API keys to GUNTHY wallet (optional)

Manage your own API keys by registering a GUNTHY wallet address. After the initial key registration you will be able to update the API keys used for Gunbot any time you like, at no cost.


Read more about [[managing API keys|API key management]].





## Starting and stopping the bot core

Use the **Start bot core** button on the **Settings** page to start trading. A few seconds after starting the bot core you can start monitoring Gunbot on the dashboard. If you have changed any settings, click the **Save changes** button to review and confirm your changes before they are applied. 


![image](https://user-images.githubusercontent.com/2372008/51904004-d45a7580-23bd-11e9-99e2-6460114659b0.png)




## Bot settings

On **Settings > Preferences > Bot Settings** you can modify settings for the bot core. These settings are global and affect every running trading pair.

![image](https://user-images.githubusercontent.com/2372008/51828387-c63c2480-22eb-11e9-9c9c-8d5fff91be52.png)


[[Detailed documentation for bot settings|Gunbot-settings#bot-settings]]



## Telegram notification settings

Gunbot can send notifications via Telegram for each trade it places. You can enable this on **Settings > Preferences > Telegram**.

![telegram-settings](https://user-images.githubusercontent.com/2372008/51828436-e53ab680-22eb-11e9-91f0-d0a96bba89bb.png)

[[Detailed documentation and instructions for creating a Telegram bot|Gunbot-settings#telegram-settings-part-of-bot-section]]

Please be aware that you cannot run two Gunbot instances using the same Telegram bot.

## TradingView add-on settings

The TradingView add-on can be used to let Gunbot execute trading alerts sent by tradingview.com via email. 

You'll need to connect Gunbot to an IMAP mailserver to listen to incoming emails from TradingView.

On **Settings > Preferences > Imap Listener** you can connect to your mailserver. 

![image](https://user-images.githubusercontent.com/2372008/51828771-9a6d6e80-22ec-11e9-8953-db6aee776c52.png)

As soon as the IMAP listener is enabled, Gunbot will only process incoming alerts from TradingView that arrive in the connected mailbox.

[[Detailed documentation for the IMAP listener|Gunbot-settings#imap-listener-settings-for-tradingview-plugin]]

To configure how incoming alerts are handled, go to **Settings > Preferences > TradingView**.

![image](https://user-images.githubusercontent.com/2372008/51828827-b3761f80-22ec-11e9-914a-35aa96a2891b.png)

[[Detailed documentation for the TradingView add-on|TradingView]]


## Strategy configurator

A strategy in Gunbot is a collection of settings that can be assigned to one or more trading pairs. These pairs will then trade according to the assigned settings.

On **Settings > Strategies > Strategy Configurator** you can view and modify strategy presets, or create your own custom strategies.

### Create a new strategy

![image](https://user-images.githubusercontent.com/2372008/51828870-d1dc1b00-22ec-11e9-977d-a4f978b7c8ad.png)


Set a nickname for your strategy (this can be anything you want), and select the main methods for buying and selling. Hit the **Create** button to save the new strategy.

### Modify an existing strategy

Click on a strategy nickname to edit its settings. 

![image](https://user-images.githubusercontent.com/2372008/51828922-e9b39f00-22ec-11e9-8953-f98f5832a8d3.png)


Make sure to read up on [[Gunbot strategies|About-Gunbot-strategies]] before you start trading. 

On the strategy pages you can find detailed explanations for each buy and sell method, as well as documentation for all available strategy parameters.


## Trading pairs

To configure which trading pairs Gunbot should trade, go to **Settings > Trading > Trading Pairs**.

### Manage trading pairs

![add-pair](https://user-images.githubusercontent.com/2372008/51829027-15368980-22ed-11e9-9fab-9d65fd081fb2.png)


Gunbot uses a standardized format for entering trading pairs, this allows you to use the same syntax for all exchanges you might use. 

The format is: BASECOIN-QUOTECOIN, where the base coin is the one used to buy another asset.

[[More information about pair names|Gunbot-settings#pairs]]

To start trading on a new pair, just enter the pair name, pick the exchange and strategy and hit the **Add** button. 

When you want to temporarily stop trading a pair, use the **Enabled** toggle to disable the pair.

### Override settings

Overrides are pair specific settings, overruling the assigned strategy. 

![image](https://user-images.githubusercontent.com/2372008/51829158-4b740900-22ed-11e9-9788-fe27db2d6df3.png)

You can use this, for example, to set a different <code>TRADING_LIMIT</code> for a specific pair. 

When adding overrides, make sure to enter the exact parameter names as listed on the [[Gunbot strategies|About-Gunbot-strategies]] pages. 



## Dashboard

The dashboard shows information on all of your exchange accounts that Gunbot is connected with and is actively processing trading pairs on.

![dashboard](https://user-images.githubusercontent.com/2372008/52167539-aefe9c00-271c-11e9-9f1e-5be6b1d224e4.png)

### Portfolio value

The portfolio value shows the value of your complete portfolio in various base currencies. This includes all pairs on exchange accounts that Gunbot is actively trading on - pairs that are not set in Gunbot are not reflected in the portfolio value.

### Wallet balances

Under wallet balances you get an overview of all your holdings for your exchange accounts that Gunbot is connected with and is actively processing trading pairs on. This includes balances for coins you are not currently trading.

### Recent trades

The recent trades overview shows a complete list of recent trades for all exchange accounts that Gunbot is actively trading on. 

### Pair summary

The pair summaries show the most important info for each active trading pair. For example:
- recent activity
- targets
- a real time chart


## Charts

The charts page shows a detailed overview for each active trading pair, this includes a lot of the data Gunbot works with. 

![image](https://user-images.githubusercontent.com/2372008/51828069-0ea71280-22eb-11e9-9968-2f2055c495e2.png)

Charts are shown in realtime by default, as soon as you start moving around in a chart it is no longer automatically updated. Click the yellow **Realtime** dot to reset the chart to it's default settings.


### Core checks

Core checks give information about the current status of a trading pair. For example, this is where you an see if a pair is currently performing reversal trading.


[[More information about core checks|logs#trading-checks]]

### Trailing details

When you use any kind of trailing, this is where you can see the current trailing limits. 



Every kind of trailing is always calculated, this is the reason you might see some data here for trailing types not currently in use. 

### Profit and loss statistics

On the **PNL** section you'll find per pair trading statistics for various timeframes and types of trading.


[[More details about profit and loss statistics|logs#profitloss]]

### Manual trading

You can place manual orders right from the charts page. 

Gunbot is designed with incidental manual trading in mind: when you buy multiple times, Gunbot will calculate the average bought price and uses that for calculating an exit point. When you manually sell all your balance for a coin, Gunbot will go into buying mode.

Be aware that settings for [[automatically canceling|Gunbot-settings#cancel_orders_enabled]] orders also apply to manually placed orders.









