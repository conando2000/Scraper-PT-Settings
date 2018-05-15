# Scraper ProfitTrailer Settings

Welcome to the home of "Scraper"!
A tiny bundle of "lean & mean" settings for ProfitTrailer 1 & 2 to scalp/scrape off of little chart swings in altcoins without bagging up, which is of course not always possible so this is a work in progress. But so far I have had the PT1 version running for over 70 days with only two multiday bag occurences (holding a coin over night, the bot not really making any % for that day) and averaging in a net profit of about 0.8% daily.
__NOTE:__ This is on Binance, which the settings are mainly aimed for/tested with - using BNB for fees the real fees are considerably lower then what PT assumes, so rather then relying on the profits PT reports, check and protocol your TCV/TPV or exchange balance daily!

After being quite disappointed with the stock and other settings around beginning of the year and constantly having to sell big bags at a loss with a simple LOWBB buy and HIGHBB sell strategy I had running, I set out for some long and heavy backtesting/simulation sessions on TradingView and also a lot of trial & error with PT itself, trying to understand how exactly it was behaving and how the trailing worked (and what its big shortcomings and to be honest failings are). So these settings are the result of spending a lot of time & effort.
__The goal__ of these settings and my strategy is: __avoid bags as much as possible, rather be fine with regular little profits than ending up with bags__
As soon as you have a bag that you can't get out of anymore (in my opinion once it goes below -15% to -20% it's "gone" unless you throw a lot more funds at it) and have to sell at a loss, the bot has failed completely imho and it's not worth running that way!

**1) The main buy strat** is EMAGAIN with a negative buy value to buy into dips based on 5min candle size, on ProfitTrailer 2 this is supported by a second buy trigger RSI on 15min candle size to have a better buy point from the get go. Also to note are the indicators, these have been fine tuned by heavy backtesting on TradingView, as has the trailing.

**2) The sell strat** is just a simple GAIN but with a very tiny minimum profit value - one of the key elements to bag up less, as often we will buy only into tiny swings. Once we start forcing PT to wait for those tripple digit profits (you wish) we will often force it into holding an altcoin for a pretty long time. During that whole time the chance of anything happening (altcoin tanking, market tanking etc.) will go up exponentially - so we try to avoid that and will be happy with every little % we can accumulate.

The same reasoning stands behind NO TRAILING on PT1, as PT1 does not have any timeouts (sadly) for trailing so in turn we quite often "miss" a good sell opportunity and end up with the same problem I just outlined.

__NOTE:__ For ProfitTrailer2 trailing is enabled and will give better daily profit numbers - PT2 has the abbility to "timeout" the trailing using the take_profit setting, so we are still able to trail with the uptrend a little bit, but if it lingers on for too long we will take what we can get and get out!

**3) DCA**

**4) The whitelist**

**5) Possible Buy List Trend filtering**

**6) Possible Buy List Max Spread filtering**


If Scraper works for you and you like to support further tweaking/backtesting, feel free to tip:

LTC ➔ LUYTeXwcUNRvcReQkhvcyBN6wUQHqJTH46
ETH ➔ 0xea55c8a453899d5E587d264b195A2EeF8BABF763
BTC ➔ 35PtGJtwxw45E4tV2aAXcdyp4YacZv3Mgf
BCH ➔ qpe2h667sndntd0da4szp9fj4huscnjjugga2ejmju
