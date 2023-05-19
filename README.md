Please read the entire document before proceeding

After installation go to C:\ShoonyaScalper\Shoonya Scalper

populate the cred.yml file with valid credentials

Lots to trade can be modified:
modify the lots list in settings.yml
Make sure indentation/spacing maintained in settings.yml file

![image](https://user-images.githubusercontent.com/42057975/218642555-5bf8e9f9-c404-4683-a0f0-95153e3a59e5.png)
You can change these settings:

SL Buffer:  negative value like -1 makes sure you offer to sell it at 1 point lesser than the SL trigger price. It improves the chance of order filling if the strike is illiquid.

Entry Buffer: If LMT is set as pricetype in settings.yml  you can use this to set the buffer. Negative value = BestBuy-EntryBuffer. If theLTP is 100 and the entry buffer is -1 then the LMT order is placed at 99.  pricetype: in settings.yml can be LMT or MKT.  MKT places market order and ignores the Entry Buffer setting.

SL Points: Stoploss in points. If set as 0 then SL and TSL features get disabled.
TSL Points:  Stoploss is trailed by x points. 
Target: Set the target in points. if the target is 20 and the entry price is 100, when the price reaches 120 trade gets closed.
Lock Points  (x) / Lock profit after (y): if the "lock profit after value" is more than 0 when ltp crosses y shift the sl to x points so you lock some profit. 
Example:
SL:20
TSL:1
Lock Profit After:10
Lock Profit at:5
LTP is 100. When the LTP reaches 110 instead of the SL being it at 90 it shifts the SL to 105. now 5 profit points are locked. Don't use this feature during high volatility. 

![image](https://user-images.githubusercontent.com/42057975/218644556-1f8a9c87-08e7-4207-b5ae-35b84507ff9b.png)

Here you can select the index, ATM offset, and lots(lots can be modified in settings.yml)
ATM offset updates every 15 secs based on the index move. -1 = ITM1 for both CE and PE. 1= OTM1 for both CE and PE
The long button places a CE order and the Short button places a PE order. The Straddle button creates a long straddle
Risk management Settings set in the panel above are considered for the trade and any changes made later only affect the new trade.

If you have multiple orders, you can close all of them by clicking on the exit all button and to cancel any open orders which were placed using LMT order can be canceled by clicking on the cancel all open orders button.

![image](https://user-images.githubusercontent.com/42057975/218645280-8e15fd1f-9136-4548-a439-52d576001ba2.png)

This panel shows all the open positions. You can select any open position, right-click on it and close it or you can shift the SL to cost+1(LTP should be higher than entry+1)

Important: 
TSL and relisting of open positions will not work if the app is restarted. 
Make sure to use a good internet connection or use this in a VPS env.

Telegram bot:

follow these links to understand how to create a Telegram bot and paste the id in cred.yml file
#https://medium.com/@ManHay_Hong/how-to-create-a-telegram-bot-and-send-messages-with-python-4cf314d9fa3e
#https://medium.com/@ganeshnagarvani/deploying-algorithmic-trading-strategy-part-3-telegram-updates-b22cd101a258

If you are not using Telegram bot clear the field like this
telegrambottoken : ''
telegrambotchatId : ''
Generate totp as shown in this video
https://www.youtube.com/watch?v=yJi3SuQc_Xk
