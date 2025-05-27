---
title: "CDR-Reader"
description: "Telegram bot to learn about stocks"
date: 2020-05-10
---

{{< lead >}}
This project was done before this blog and most information is from memory
{{< /lead >}}


{{< keywordList >}}
{{< keyword icon="github" >}} [Github Repo](https://github.com/vdhorstnigel/StonksBot) {{< /keyword >}}
{{< keyword icon="telegram" >}} [Telegram bot link](https://t.me/IWannaHaveStonks_Bot) {{< /keyword >}}
{{< keyword icon = "code" >}} Python {{< /keyword >}}
{{< keyword icon = "code" >}} HTML {{< /keyword >}}
{{< keyword icon = "code" >}} mySQL {{< /keyword >}}
{{< /keywordList >}}


I initially created this bot to track the stock prices and to update me when prices change for the stocks that my sister bought for me. I was unable to view the stock profits as it was on her account and I did not have access to the broker. This bot is mostly depreciated now as I now have a proper broker.

I used python as the main language as I was learning python at the time. Numpy was used to read the data scraped from yahoo using Beatifulsoup4. I used mySQL as the database to store the stock, current price, profit, previous price and the percentage changed of the current vs previous price.

These are the commands supported

List of commands watch - /watch Tickername PriceofStock | If no price is written , the command will fail | if no ticker is written, the bot will send you a list of your current watchlist

unwatch - /unwatch Tickername | Removes stock from watchlist

price - /price Tickername | Get price for current stock

dividend - /dividend Tickername | /dividend CheckAllYourStockDividends(beta)

holding - /holding Tickername | Get holdings for an etf

gainers - /gainers | Top 10 Stock Gainers

losers - /losers | Top 10 Stock Losers

This was my first project and I learnt alot creating a very simple bot to automate tasks, I also learnt about html tags, divs and Xpath to scrape data. I also used a file to store the Telegram token. Looking back at the code now, it was very poorly done and can be significantly improved.