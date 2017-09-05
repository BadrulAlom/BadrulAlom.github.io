---
layout: default
---


# Applications of machine learning in Corporate Finance
<br>
Google 'machine learning corporate finance' and you'll get articles such as [this](http://www.huffingtonpost.com/entry/cfos-embrace-machine-learning-to-move-beyond-the-spreadsheet_us_59132f94e4b0e070cad70aad) and [this](http://www.digitalistmag.com/finance/2017/03/15/machine-learning-in-finance-4-ways-cfos-can-unlock-value-04962169) which on the surface seems to promise answers to the question of how one applies machine learning in corporate finance, but when you read into the details they offer nothing more than rules based automation, a data warehouse (both useful just not 'machine learning'), or pithy statements such as 'Instead of manually reviewing months of spreadsheets, self-learning algorithms can find patterns and solutions in data to make decisions easily' without explaining how exactly this is possible. 

With that in mind I sat down to do my own analysis of the opportunities machine learning can bring to corporate finance by donninng my recenty regained academic hat and performing a literature review.

## Predicting corporate bankruptcy

There is quite a lot of academic research on predicting corporate bankruptcy out there such as [this one](http://www.sciencedirect.com/science/article/pii/S0957417404001526) in which Support Vector machines and 23 financial ratioss were found to be effective in predicting bankruptcy to an 83% accuracy. The researchers do warn that the problem is domain specific, and other research shows results of 53%, but more [advanced techniques](https://www.hindawi.com/journals/ddns/2015/294930/) are continually being developed. 

Banks will already have been using machine learning to asses the risk rating of a company based on ratios, but what would be interesting is whether non-traditional sources of data such as news reports and sentiment analysis can better refine these models.

## Detecting financial restatements

In this [2017 paper](http://www.sciencedirect.com/science/article/pii/S0957417417305687) the authors perform robust research into whether both fraudelent and unintentional financial restatements can be predicted. They find that Decision Trees and Neural nets perform well with an accuracy measure in the 65-70% range. Such models would could be used by auditors and investors to flag up companies that have a greater risk of financial restatement.

## Valuing intangible assets

In this [paper](http://www.sciencedirect.com.libproxy.ucl.ac.uk/science/article/pii/S0925231215015003) the authors set about trying to build an intangible assets classifier that tries to predict whether a companies intangible assets are either high or low value. The value itself is derived from this formula *Q=(Market value of common stock + Book value of preferred stock) / Book value of total assets*. They find that a k-means + bagging based Decision Tree ensemble (say that three times fast) gave the best results. 

With intangible assets being seen as the explaining the gap between market-value and book-value of an organization, models that can form an objective view of the intangible value of an organization can help investors have a better view of a companies worth.

## Dynamic Pricing

Price optimization has been a business challenge for many years but there is now an increasing shift to machine-learning led dynamic pricing models, such as discussed in this [research](http://www.sciencedirect.com/science/article/pii/S187705091401309X). Dynamic pricing is already becoming a feature of the travel industry and is used by [Starwoods](https://www.cio.com/article/3070384/analytics/starwood-taps-machine-learning-to-dynamically-price-hotel-rooms.html), Expedia and [Travelocity](https://www.quora.com/What-dynamic-pricing-algorithms-use-Travelocity-and-other-travel-sites) and supermarkets are not getting in on the [act](https://www.theguardian.com/technology/2017/jun/04/surge-pricing-comes-to-the-supermarket-dynamic-personal-data). 

Going forward, periodic decision-making of prices changes will increasingly be replaced by real-time price decisions made by machines.

## Business Forecasting

Business forecasting is a critical function for most CFOs. Often there are lots internal and external variables that can impact forecasts, and simply asking the business to submit forecasts can lead to a culture of "playing by the numbers". Machine learning can play a vital role in providing objective forecasts, based on analysis of financial ratios as well as other internal/external variables. Machine learning models applied to business forecasting is described in [this paper](http://www.sciencedirect.com/science/article/pii/S0957417413000158) and [this paper](https://arxiv.org/abs/1701.06624). Furthermore a machine learning model that that continually update itself based on daily data could provide not just an up-to-date forecast, but also highlight trends early on through seeing how the forecasts change over a period of days or weeks.

Going forward we should expect machine learning to be the right-hand-machine of every CFO, continually analyzing the numbers as they come in and prociding them with daily refreshed predictions to pore over.

