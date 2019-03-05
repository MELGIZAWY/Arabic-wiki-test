# Troubleshooting

When there is a problem that might need attention, Gunbot usually shows an error notification in the GUI. Some errors are only visible in the console window running Gunbot.

For troubleshooting purposes, recent [[logs|logs]] are stored in the /logs folder. After Gunbot is closed, logfiles can be read with a text editor like Notepad++.

This page describes common problems and their possible solutions.


> **Tips for troubleshooting**: always completely close Gunbot before trying to resolve a critical issue. Reboot your computer when you are unsure if you've completely closed Gunbot. When resolving an isse that might be related to API rate limiting, stop running Gunbot for at least 10 minutes before trying to solve the problem.


> **Contents:**
> 1. [Errors when starting Gunbot or Gunbot core](#errors-when-starting-gunbot-or-gunbot-core)
> 2. [Errors after successfully starting Gunbot](#errors-after-successfully-starting-gunbot)




## Errors when starting Gunbot or Gunbot core

The following errors are **critical** and will prevent trading, they indicate Gunbot could not properly start or connect to an exchange.

<hr>

> ### INVALID LICENSE FOR (exchange) Please contact your reseller!

**Reason:** master key is not registered

**Possible solutions:**

- Double check if your master key and secret are correct and do not start or end with a blank space
- Verify that you are running the correct edition of Gunbot (Lite or regular)
- If the problem persists: contact your reseller

<hr>

> ### Cannot access GUI anymore after an error keeps occuring in the console log

**Reason:** Config error preventing core to properly load

**Solution:**

- Set <code>start</code> false in the GUI section of config.js, with a text editor like Notepad++. Save the file and you should be able to connect to the GUI again.

<hr>

> ### "Object object"

**Reason:** various

**Possible solutions:**

- Upgrade to the latest available release.
- Make sure all pairs on the exchange showing the error are correct. Try testing with just a single BTC-LTC pair.
- Make sure that both <code>MIN_VOLUME_TO_SELL</code> and <code>MIN_VOLUME_TO_BUY</code> are set to at least the minimum allowed trade size at your exchange.
- When trading fiat pairs like USDT-x, make sure that <code>MIN_VOLUME_TO_SELL</code>, <code>MIN_VOLUME_TO_BUY</code> and <code>TRADING_LIMIT</code> are set to round number without decimals.

<hr>

> ### INVALID RESPONSE FROM LICENSE SERVER

**Reason:** Usually a network issue

**Possible solutions:**

* Try a wired internet connection
* Restart your router and/or flush your DNS cache 

<hr>

> ### Error: bind EADDRINUSE null:5000

**Reason:** Other process is already using the specified port number

**Possible solutions:**

* Restart your computer
* When other software requires using any of the ports needed for Gunbot, change the ports Gunbot uses in the config.js file

<hr>

> ### Unable to connect to (exchange)

**Reason:** Various

**Possible solutions:**

- Double check if your master key and secret are correct and do not start or end with a blank space
- Check if your system clock is synced with an internet time server. [Tool for Windows](http://www.timesynctool.com/) / [https://www.howtogeek.com/tips/how-to-sync-your-linux-server-time-with-network-time-servers-ntp/ Info for Linux]
- Make sure both a valid master key and key are present in your config
- Make sure your pairs actually exist on the exchange and conform to Gunbot pair syntax
- Make sure all Gunbot files were correctly unzipped
- Make sure the IMAP listener is disabled (when not using the TradingView add-on)
- Try a wired internet connection
- Restart your router and/or flush your DNS cache

<hr>

> ### SSL_ERROR_RX_RECORD_TOO_LONG

**Reason:** https not enabled

**Possible solutions:**

* Enable <code>https</code> in the config.js file
* Visit Gunbot via http, instead of https 

<hr>

> ### Repeated messages about loading exchanges and config

**Reason:** Problem with one or your pairs

**Possible solutions:**

- Check the syntax of your trading pairs. Pair syntax is case sensitive
- Verify that the trading pairs actually exist on the exchange

<hr>

> ### toLowerCase of undefined

**Reason:** API issue

**Possible solutions:**

- Verify you downloaded the correct Gunbot edition (Lite or RT)
- Make sure your API key is activated on CEX
- Make sure you filled in your CEX ClientID

<hr>

> ### error: Invalid signature

**Reason:** API issue

**Possible solutions:**

- Make sure your API key is activated on CEX
- Make sure you filled in your CEX ClientID

<hr>

> ### Please add the exchange credentials for (exchange) under Exchanges

**Reason:** API details missing

**Possible solutions:**

- Make sure that you have entered all required API details for every connected exchange 

<hr>

> ### Error: Cannot find module '...Gunbot-master\gui\node_modules\sqlite3\lib\binding\...\node_sqlite3.node'

**Reason:** Essential files not found

**Possible solutions:**

- Make sure that you have unzipped all files from the Gunbot release package before starting Gunbot


<hr>



## Errors after successfully starting Gunbot

The following orders can prevent trading when occuring very often. When any of these errors only occur intermittently, there is usually no issue that needs solving.

<hr>

> ### Received broken open orders info: retrying again

**Reason:** Exchange did not send requested order data

**Possible solutions:**

- Ensure proper internet connectivity
- Increase exchange delay

<hr>

> ### Received empty balance: retrying again

**Reason:** Exchange did not send requested balance data

**Possible solutions:**

- Ensure proper internet connectivity
- Increase exchange delay
- Wait until the exchange finishes maintenance

<hr>

> ### Fetching OHLC again

**Reason:** There is not enough trading volume to receive the number of requested candles

**Possible solutions:**

- Try a different setting for <code>PERIOD</code>
- Try other trading pairs with more volume

<hr>

> ### Received empty order book: retrying again

**Reason:** Exchange did not send requested order book data

**Possible solutions:**

- Ensure proper internet connectivity
- Increase exchange delay
- Wait until the exchange finishes maintenance

<hr>

> ### Portfolio value chart shows strange peaks

**Reason:** Known issue

**Possible solutions:**

- None. Expect better portfolio value calculation in v11.

<hr>

> ### WARNING: BUY order from more than 30 days ago.

**Reason:** Bought price for asset is unknown

**Possible solutions:**

- Add <code>BOUGHT_PRICE</code> as an override for your pair. Remove after the following sell order.

<hr>

> ### TypeError: Cannot read property askprice of undefined

**Reason:** Problem with one or your pairs 

**Possible solutions:**

- Check if all of the pairs in your setup actually exist on your exchange and conform to Gunbot pair syntax (BASE-QUOTE)
- Wait until the exchange finishes maintenance

<hr>

> ### Poloniex: 422

**Reason:** Exceeding API rate limit 

**Possible solution:**

- Increase the exchange delay for Poloniex.

<hr>

> ### Bitfinex: nonce is too small

**Reason:** Exceeding API rate limit 

**Possible solution:**

- Increase the exchange delay for Bitfinex.

<hr>









