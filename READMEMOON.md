'''
agent zero should be able to execute the code
- has built in search too too
- works with openai and anthropic
- need to have docker desktop
- The whole behavior is defined by a system prompt in the prompts/agent.system.md file. Change this prompt and change the framework dramatically.
- dspy may be helpful for optimizing chat prompt w/ api 

https://github.com/frdel/agent-zero
'''

- models temperatures are 0-1 with 0 being the most factual and the 1 being the most creative... play with this on the main.py to see how it do for our tasks
- e to leave


prompt
Agent 0, I've confirmed that all necessary files and folders are in your current working directory. I want you to loop through the strategies in the 'strategies' folder and backtest each one using backtesting.py. Use the data file 'BTC-USD-1h-2020-1-01T00_00.csv' for the backtest. You can use pandas_ta or talib for indicators, or numpy and pandas as needed. Debug the backtests as necessary to ensure they execute correctly. For each strategy, output the stats as a .txt file in the 'stats' folder. follow mmy steps precisely. 1. find the first text based strategy in the strategy folder, this will be a written strategy that you will then turn into code and debug. 2. debug and run the code to get the stats back from backtesting.py 3. place the stats in the stats folder. here is the data to use /Users/md/Dropbox/dev/github/agent-zero/work_dir/BTC-USD-1h-2020-1-01T00_00.csv 4. place the finished python backtest code in this folder: /Users/md/Dropbox/dev/github/agent-zero/work_dir/debugged_bt so i can play with the code 5. never use placeholders for the indicators. if you dont know how to create a specific indicator, then search the web if needed and create it yourself.

 The 'strategies' folder, 'BTC-USD-1h-2020-1-01T00_00.csv' file, and 'stats' folder are all present here. i have a folder of strategies i want you to loop through and then backtest using backtesting.py, you will need to debug the backtests and get them to a point where they can execute and print out the stats of the backtest before moving on to the next strategy in the folder here: /Users/md/Dropbox/dev/github/agent-zero/strategies here is the data to use for the backtest data: /Users/md/Dropbox/dev/github/agent-zero/BTC-USD-1h-2020-1-01T00_00.csv use backtesting.py, feel free to use pandas_ta or talib for indicators, or numpy and pandas. output the stats as a .txt for each and every strategy here: /Users/md/Dropbox/dev/github/agent-zero/stats


 below i have written a trading strategy for you to backtest with backtesting.py here is the data to use: 'BTC-USD-1h-2020-1-01T00_00.csv' 
 step 1 - read in the strategy below
 step 2 - code a backtest using backtesting.py and if needed use talib or pandas_ta
 step 3 - debug the backtest and once it runs, output the stats into the stats folder
 step 4 - output the working code into the debugged_bt


 RSI Momentum Trend Trading Strategy Instructions

1. **Indicator Setup**:
   - Add 'RSI Momentum Trend' indicator by Tac 88.
   - Customize the indicator:
     - On the input tab, set 'negative' to 35.
     - On the visual settings, disable 'show momentum'.
   - Add 'Support and Resistance Levels' indicator by Lux Algo.
   - Customize the indicator:
     - On the style tab, set resistance color to green, support color to red.
     - Disable unnecessary visual options.

2. **Conditions for Long Position (Buy)**:
   - Identify a resistance level (green horizontal line).
   - Wait for the price to break and close above the resistance level without the wick having touched it previously.
   - Confirm that the 'RSI Momentum Trend' indicator's ribbon is colored green (bullish trend).
   - Entry: Execute a long position when both conditions are satisfied.
   - Stop Loss: Set below the most recent swing low.
   - Take Profit: Set at two times the risk (risk-reward ratio of 1:2).

3. **Conditions for Short Position (Sell)**:
   - Identify a support level (red horizontal line).
   - Wait for the price to break and close below the support level without the wick having touched it previously.
   - Confirm that the 'RSI Momentum Trend' indicator's ribbon is colored red (bearish trend).
   - Entry: Execute a short position when both conditions are satisfied.
   - Stop Loss: Set above the most recent swing high.
   - Take Profit: Set at two times the risk (risk-reward ratio of 1:2).

4. **Additional Considerations:** 
   - Ensure there is sufficient volume to support the identified trend prior to taking a position. A separate volume indicator may be added to confirm trend strength.

5. **Trade Management**:
   - Let the trade run until either the take profit or stop loss is hit.
   - Do not micromanage the trade; trust the indicators and setup conditions.

6. **Backtesting Parameters**:
   - Time Frame: 15-minute chart.
   - Instrument: GBP/JPY (extend to other instruments if desired).
   - Historical period: Define the historical period (e.g., past 5 years).
   - Commissions and spreads: Include realistic trading costs to ensure the strategy's profitability is accurate.
   - Risk management: Define the risk per trade (e.g., 1% of account balance).

7. **Evaluation Metrics**:
   - Total return and return percentage.
   - Profit factor (gross profit divided by gross loss).
   - Maximum drawdown.
   - Win rate and loss rate.
   - Average gain per winning trade versus average loss per losing trade.
   - Number of trades executed.

The AI designated to code the backtest should incorporate these instructions accurately, ensuring that all entry and exit conditions are coded as specified and that all additional considerations regarding volumes and trade management are taken into account. Furthermore, detailed trade logs should be maintained to help evaluate the strategy's performance based on the metrics highlighted.