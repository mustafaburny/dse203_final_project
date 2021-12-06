DSE 203 Final Project - Winter 2021
===================================

Dataset Overview
----------------

This repository contains data extracted from Reddit via the pushshift.io API (https://github.com/pushshift/api). It
contains Reddit posts (a.k.a. submissions) and Reddit comments from 17 finance/investing sub-reddits that mention any of
75 large Information Technology companies from the S&P 500 (see `Companies.xlsx` for the exact list of companies).

Specifically, the data consists of two parts:

1. `top_submissions`: Most popular Reddit posts (submissions) that mention the companies of interest in the post title
   and/or body.
2. `top_comments`: Highest-scoring Reddit comments that mention the companies of interest in the comment body.

The data was extracted using the following parameters:

- Date Range = January 2020 to December 2021 (23 months)
- Subreddits: 
  ```python
  SUBREDDITS_TO_EXTRACT = (
      # Sources:
      #  - https://thehiveindex.com/topics/investing/platform/reddit/
      #  - https://www.investopedia.com/reddit-top-investing-and-trading-communities-5189322
      'stocks',
      'wallstreetbets',
      'pennystocks',
      'investing',
      'Wallstreetbetsnew',
      'StockMarket',
      'options',
      'RobinHood',
      'RobinHoodPennyStocks',
      'weedstocks',
      'smallstreetbets',
      'SecurityAnalysis',
      'CanadianInvestor',
      'SPACs',
      'InvestmentClub',
      'ValueInvesting',
      'investing_discussion',
      'stonks',
      'shroomstocks',
  )
  ```

The data was extracted as follows:

1. `top_submissions`: For each of the 75 companies, and for each month, the 500 most popular (i.e. with the most
   comments) Reddit posts that mentioned the company were extracted from all sub-reddits.
2. `top_comments`: For each of the 75 companies, and for each month, the 1,500 highest-scoring Reddit comments that
   mentioned the company were extracted from all sub-reddits.

See the Jupyter notebook `Download Top Reddit Post Details.ipynb` for the code. The dataset is available in
`notebooks/top_submissions_and_comments`.
