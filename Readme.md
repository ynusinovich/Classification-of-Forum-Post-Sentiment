# Project 3: Web APIs & NLP

## Problem Statement
I’m a data scientist for a data science startup. We’ve been hired by Reddit to train a model that will identify whether libertarian users on Reddit lean towards supporting Republicans or Democrats. The Republican and Democrat organizations will pay Reddit for this data in order to market ads that will win over libertarian voters before the election.

## Executive Summary
As you're well aware, the United States of America has two major parties, the Republicans, which are considered conservative, and the Democrats, which are considered liberal. The parties each need to sway voters who are undecided or third-party in order towin the election. The biggest third-party in the United States is the Libertarians. Their views are based on maximizing individual freedoms and limiting the role of government, so their views can lean conservative (e.g., decreasing welfare) or liberal (e.g., legalization of cannabis).<br><br>
Reddit has hired our startup to figure out whether the users of the libertarian subreddit are liberal or conservative, based on their comments. They will sell this data to the Republican and Democrat organizations so that they can market ads towards the conservative-leaning libertarians and the liberal-leaning libertarians, respectively, to win them over in key battleground states.<br><br>
The initial model to classifiy libertarian posts as liberal or conservative has been a success:
- The model correctly recognizes comments from liberals and conservatives among self-identified libertarians 70% of the time.<br><br>
- Guessing conservative based on the majority would be correct 54% of the time.<br><br>
- Liberal, conservative, and libertarian commenters have characteristic words:
    - Liberal: 'yet', 'fucked', 'days', 'death', 'different', 'donald', 'easy', 'economy', 'elections', 'entire', 'fine', 'fox', 'full', 'white', 'given', 'god', 'gop', 'guns', 'hate', 'healthcare'
    - Conservative: '[new] york', 'gets', 'dying', 'each', 'essential', 'except', 'experts', 'face', 'family', 'fauci', 'fever', 'force', 'global', 'willing', 'god', 'goes', 'guys', 'hell', 'higher', 'hospital'
    - Libertarian: 'italy', 'paid', 'worst', 'gouging', 'data', 'deal', 'demand', 'distancing', 'doctor', 'effective', 'essential', 'false', 'goes', 'gun', 'grocery', 'lower', 'haven'[t]', 'her', 'idiot', 'idiots'<br>

Targeting advertisements towards libertarian users based on their comments will be more effective than paying for random advertisements, especially when combined with a user's location data.<br>

With more funding, our company will pay for more computing power and data, and further refine the model for Reddit. Some possible improvements include:
- Add far-right and far-left subreddit comment data for training the model.
- Tune more components of the model, such as the maximum number of filler words that the model considers.
- Crowd-source data on political slant by comment for the training dataset, instead of assuming that self-identified conservatives and liberals are conservative and liberal, respectively.


## Contents
- Goal
- Import Comments from Subreddits and Save Relevant Data
- Data Cleaning
- Create Variables
- Run Classification Models with Hyperparameter Tuning
- Create and Score Labeled Test Dataset
- Run the Model on the Libertarian Subreddit
- Analyze Libertarian Subreddit Users
- Examine Most Common Words in Each Subreddit
- Summary and Further Research


## Data Dictionary

|Feature|Type|Description|
|---|---|---|
|**subreddit**|string|The forum within Reddit where the comments were posted.<br>In this case r/politics (left-wing), r/conservative (right-wing), or r/libertarian (sometimes left-leaning and sometimes right-leaning).|
|**subreddit_id**|string|The unique label corresponding to each subreddit.|
|**author**|string|The Reddit username of the person who logged in and wrote the comment.|
|**author_fullname**|string|The unique label corresponding to each username.|
|**author_flair_text**|string|A label that the moderators of a subreddit gave to a user. This flair only displays when the user comments on that subreddit.|
|**body**|string|The full text of the comment. Only the words, numbers, and domain names (e.g., Fox.com or NYTimes.com) are extracted for this model.|
