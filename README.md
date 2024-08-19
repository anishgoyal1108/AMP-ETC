# Electronic Trading Challenge Trading Bots

![](https://eco-cdn.iqpc.com/eco/images/partners/8wKbGOn7mj9kADeHdoPImckCLhMcJjimFUN14Jnk.png)

## Authors
- Anish Goyal [@anishgoyal1108](https://github.com/anishgoyal1108)
- Archita Singh [@architasingh0825](https://github.com/architasingh0825)

## Introduction
Jane Street Capital Group hosts a summer program called the Academy of Math and Programming (AMP), where participants engage in the inaugural Electronic Trading Challenge (ETC). The competition involves a central server where various bots operate in the backend, buying and selling securities. All trades are publicly available on a digital exchange and are printed in real time. The challenge requires participants to interact with the REST API, according to provided specifications, to make trades with these bots and maximize profits. The boilerplate code provided by Jane Street allowed us to focus on developing and refining our trading algorithms.

### Types of Securities:
- **BOND**
- **ETFs:** GS, MS, WFC, XLF
- **ADRs:** VALE and VALBZ

## Strategies We Considered

### Pennying
Pennying is a trading strategy that involves placing orders slightly better than the best bid or ask to gain priority in trade execution. This approach was challenging to implement effectively due to the fast-paced nature of the competition and the need to constantly update bids and asks in response to market conditions.

### Arbitrage
ETFs presented significant arbitrage opportunities, as the bots generally traded within a threshold close to the average of all stocks. A $100 conversion fee allowed us to convert 3 BOND, 2 GS, 3 MS, and 2 WFC into 10 XLF shares, creating potential for profitable arbitrage. We leveraged this by closely monitoring price discrepancies between the ETFs and their underlying assets.

### Buying Below Fair Value for Bonds
Bonds had a fixed fair value of $1000, which made this strategy straightforward. We focused on buying bonds below their fair value and selling them at a slightly higher price. This method was simple yet effective (especially in the beginning when most teams weren't set up yet), as it allowed us to profit from predictable price movements.

## How We Did
We performed well during the early and middle stages of the competition, primarily using two bots: a simple BOND bot that capitalized on buying low and selling high, and an arbitrage bot for the three liquid ETFs (GS, MS, and WFC) that used the averages of the first five trades of each ETF to approximate the fair value and buy below those approximations. Toward the end, Anish attempted to implement a random moving average bot that trained itself to improve over time. However, this strategy did not yield significant profits, partly because the algorithm buys too much of each security at the start of the round.

## An Open Letter to Future AMPers
If you are preparing to enter the ETC, be aware that the challenge is a race against time. It is crucial to thoroughly understand every aspect of the competition—from how the exchange operates, to how orders are placed, to how market feeds are read and parsed.

The key to success lies in your ability to adapt quickly and learn the mechanics of trading on the fly. Here are a few tips:

1. **Develop a Mental Model of Trading:** Understand the fundamentals of how trading works, as this will guide your strategies and decision-making processes.

2. **Be Creative and Experiment:** Don't be afraid to try new things. No matter how good a strategy seems in theory, the only thing that matters is whether it works in practice. Iterate quickly, develop new ideas, and test them thoroughly.

**NOTE:** During our competition, the testing servers were broken for approximately 80% of the time. If you have access to a testing environment, make sure to test your algorithms thoroughly before deploying them to production.

Lastly, don't take the challenge too seriously. Take some risks, enjoy the process, and have fun!

