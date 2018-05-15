# Scraper ProfitTrailer Settings

Welcome to the home of "Scraper" - a tiny bundle of "lean & mean" settings for ProfitTrailer 1 & 2 to scalp/scrape off of little chart swings in altcoins without bagging up!

So far I have had the PT1 version running for over 70 days with only two multiday bag occurences (holding a coin over night, the bot not really making any % for that day) and averaging in a net profit of about 0.8% daily.

__NOTE:__ This is on Binance, which the settings are mainly aimed for/tested with - using BNB for fees the real fees are considerably lower then what PT assumes, so rather then relying on the profits PT reports, check and protocol your TCV/TPV or exchange balance daily!

After being quite disappointed with the stock and other settings around beginning of the year and constantly having to sell bags at a loss, running with a simple LOWBB buy and HIGHBB sell strat, I set out for some long and heavy backtesting & simulation sessions on TradingView and also a lot of trial & error with PT itself, trying to understand how exactly it was behaving and how the trailing worked - what its big shortcomings and to be honest failings are.
So these settings are the result of spending a lot of time & effort on testing.

__The goal of these settings / my strategy:__ avoid bags as much as possible, rather be fine with regular little profits than ending up with bags! (compounding interest)

As soon as you have a bag that you can't get out of anymore - in my opinion once it goes below -20% to -25% it's "gone" - and have to sell at a loss, the bot has failed completely imho and it's not worth running it that way!

Because I don't really like messy and/or randomly thrown together settings that seem almost arbitrary without any reasoning, I documented here what each setting does and what the idea behind it is:

**1) The main buy strat** is EMAGAIN with a negative buy value to buy into dips based on 5min candle size, on ProfitTrailer 2 this is supported by a second buy trigger RSI on 15min candle size to have a better buy point from the get go. Also to note are the indicators, these have been fine tuned by heavy backtesting on TradingView, as has the trailing.

__NOTE:__ The way DCA is required to work and the whole strat is set up requires the max pairs to be limited to 2-3 while the initial buy in is set as a percentage to scale, however for **higher balances** (>1 BTC) you should probably double max_trading_pairs and half initial_cost_percentage, for really high balances it might work best to split them over multiple accounts/bot instances.

**2) The sell strat** is just a simple GAIN but with a very tiny minimum profit value - one of the key elements to bag up less, as often we will buy only into tiny swings. Once we start forcing PT to wait for those tripple digit profits (you wish) we will often force it into holding an altcoin for a pretty long time. During that whole time the chance of anything happening (altcoin tanking, market tanking etc.) will go up exponentially - so we try to avoid that and will be happy with every little % we can accumulate.

The same reasoning stands behind NO TRAILING on PT1, as PT1 does not have any timeouts (sadly) for trailing so in turn we quite often "miss" a good sell opportunity, trailing/lingering forever and end up with the same problem I just outlined.

__NOTE:__ For ProfitTrailer2 trailing is enabled and will give better daily profit numbers - PT2 has the abbility to "timeout" the trailing using the take_profit settings, so we are still able to trail with the uptrend a little bit, but if it lingers on for too long we will take what we can get and get out! (**only works with PT 2.0.4 and higher, as take_profit was completely broken before that!**)

**3) DCA** is another important tool in this strat, in Scraper it's set up pretty "tight" to double up quite rapidly. The reasoning behind it is to use it - especially with PT1s flawed buy options - to advance/improve the initial buy point. So we use quite a tiny amount of our balance for initial buy and then quickly improve on our initial position by buying in after it dipped a little further, so we can get out as quickly as possible with a little bit of profit. (remember, we don't want to overstay our welcome)

This is still work in progress though, I'm currently working on implementing settings with PTMagic to maybe use stoploss/panicsell in case a coin or the market really tanks. As long as the ratio of this happening is in our favour we could still come out on the positive side.

**4) The whitelist** used in these settings is the result of a 2 months run on Binance beginning of 2018 without a whitelist and analyzing the sales log for which coins gave the best profits and weeding out the ones that resulted in more DCA without giving a lot of profit (or even bags). I try to update this regularly or maybe replace it with a PTMagic "auto whitelist".

**5) Possible Buy List Trend filtering** imho is one of the most important settings besides the whitelist to avoid bags, it has been introduced only now in PT2 - if you are using PTFeeder or PTMagic it might not be required if you have a tight setup. But I like to run PT without any additional overhead/addons on my server, so the trend filter has helped a lot to avoid buying into coins when they are either tanking too much or are at the top of a pump/moon cycle. ;)

**6) Possible Buy List Max Spread filtering** is the last of a number of "protective layers" these settings employ to save you from bags. I have set them very very narrow on purpose, the idea being pretty simple: especially when looking at a dip/downtrend (as we are buying into those mainly) it is usually the case that the spread (difference between ask and bid prices in the orderbook) is quite high (=volatile) when we are still on a "downwards slope" and we don't want to buy too early before reaching the "bottom" of the dip. A tight max spread helps a lot with this - for DCA i set it even tighter as it is supposed to counteract my "tight" DCA in cases when we have a more violent downward dip, so the DCA doesn't double down immediately when triggered but more towards the coming dip.


```
If Scraper works for you and you like to support further tweaking/backtesting, feel free to tip:

LTC ➔ LUYTeXwcUNRvcReQkhvcyBN6wUQHqJTH46
ETH ➔ 0xea55c8a453899d5E587d264b195A2EeF8BABF763
BTC ➔ 35PtGJtwxw45E4tV2aAXcdyp4YacZv3Mgf
BCH ➔ qpe2h667sndntd0da4szp9fj4huscnjjugga2ejmju
```
