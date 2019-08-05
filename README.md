# 10 Years of Crowdfunding on Kickstarter - A Data Exploration
### by Marie-Luise Klaus | 20/07/2019, Berlin, Germany

This exploratory data analysis is dedicated to the 10th anniversary of the crowdfunding platform Kickstarter in April 2019. 
The main goal is to analyse current trends and determine possible factors contributing to the success of a campaign. 

Throughout the course of this notebook, I will have two main questions in mind. Based on our data:

**1) Is it still worth the effort to finance your project on Kickstarter since crowdfunding has become mainstream?**  
**2) What determines the success of a crowdfunding campaign on Kickstarter?**

### Project
This project includes the following files:  
1) Crowdfunding Data Wrangling files (jupyter notebook, html, pdf)  
2) Crowdfunding Data Exploration files (jupyter notebook, html, pdf)  
3) Slide Deck for the presenation of findings (jupyter notebook, html, pdf)  
4) Raw data, master data files (kickstarter_master1-4.csv), a collectio  of historic USD exchange rates  

# Dataset
## Assessment and Cleaning

The Kickstarter data set was gathered in April 2019 from an automated web scraping service called web robots. They have been publishing monthly data of all ongoing and completed Kickstarter projects and released it to the public in the form of csv files on their website. 

https://webrobots.io/kickstarter-datasets/

I extensively assessed the data set, which included 210,088 project observations with 37 project features each at first. The assessment revealed multiple quality and tidiness issues. For example, I found 27 tsd. duplicated projects and severe inconsistencies in currency conversions. Therefore, I took a programmatic approach to clean the data. To a great part, I had to break up insufficiently extracted JSON strings and store them as separate data points. After the wrangling processes, I ended up with 182,823 clean project entries with 32 project features.

One of the main problems of this data set was the missing documentation provided by the source. There was no information given about the project features, nor how the data was scraped or generated. To improve comprehention and to rule out erroneous information, I collated the data set with Kickstarter's project archive, which is unrestrictedly accessible online. 
On the positive side, I did not encounter any inconsistencies during the wrangling and analysis processes. However, I cannot guarantee the validity and completeness of the data and take no liability for misinterpretation of the results due to the lack of documentation. 

Finally, I stored the clean data in csv files. Due to Github's file size limitations, I broke up the files in four. 

## The Structure of The Data

The clean dataset contains information on 10 years of Kickstarter projects; from Kickstarter's launch in April 2009 to mid-April 2019. In the focus of my analysis were all completed projects up until Kickstarter's anniversary in April 2019. This left me with 169,661 project observations.

As for the features of this dataset, there are 22 variables that have been selected for analysis. We got quantitative variables like the funding goal or the final pledges, several time-related variables and qualitative data, like project categories, names and project statuses.

### Main Feature of Interest
The main feature that I will explore is the **status** of a project. It depicts whether the crowdfunding was successful or failed.

### Supporting Features
Undoubtedly, there are many different factors that may affect the success or failure of a crowdfunding campaign. In the course of this data set, I suspect the following factors to be most influential on the project:

- the amount of the initial funding goal: goal hist usd
- the amount pledged: pledged hist usd
- the number of backers: backers count
- the promotional support provided by Kickstarter: featured
- project categories: category, subcategory, comb cat
- the dates of the project's launch and deadline: launched at, deadline
- the duration period of funding: duration
- the location of a project: country, loc type.

# Key Insights of Findings
## 1) Is it still worth the effort to finance your project on Kickstarter since crowdfunding has become mainstream?

**The short answer: yes, chances today are better than ever.**   
In spite of increasing project numbers and therefore higher competition, there were never more campaigns ending successfully than today. Also, the pledges collected for each successful project have been staying on a relatively stable niveau.

**The number of monthly crowdfunding campaigns has been growing since 2018.**    
After a rather slow growth in the first 5 years after Kickstarter's launch, we found extreme boosts in crowdfunding activities in August 2014 and March/April 2015. The number of campaigns literally exploded. Project counts settled down thereafter. Nevertheless, with roughly 2,000 projects each month, the number of campaigns ending each month kept on a high level in the following 5 years up until today. Most importantly, we discovered increasing numbers of campaigns since 2018.

**In 2018, 63.5% of campaigns were successful.**    
With the hype of Kickstarter in late 2014, we found an abnormal high percentage of projects failed. 61% flopped. During the years of recession the likelihood to fail minimally exceeded success rates. 51% of projects failed. By the beginning of 2018, Kickstarter turned success and failure rates upside down. On average, 63.5% of completed campaigns had the chance to succeed. Actually, the record of successful campaigns was only recently, in March 2019. Chances to win were 74%!

**Funding goals have become lower, but the collected financial backing has been stable.**   
I noticed a trend of declining funding goals of successful projects since 2017. While successful projects achieved goals of roughly USD 3,100 between 2014 - 2016, creators today usually aimed for USD 500 less.  
Surprisingly, the overall financial backing per project has been relatively constant since 2014. In the 10 years period, creators on average creators raised a median of USD 4,825. The good news: as of 2018 creators were able to expect a median of USD 5,371.

**Today, supporters tend to pledge smaller amounts.**  
The money each supporter spent on incentives has been declining lately, creators had to attract a higher number of supporters to collect the same amount of funding. In 2018, successful projects on average collected USD 7 less per backer than in the record year of 2016. This may be a negative development for some creators, but it may also be a strategic chance for business starters to increase their reach, funding or customer numbers.   

**Growing supporter numbers compensated for increased competition among creators.**  
We would expect the recent increase of competing projects, lower funding goals and the tendency to pledge greedier to negatively impact campaigns. However, with Kickstarter becoming mainstream, the number of people who supported a project has been increasing stronger than the number of active campaigns. While a lack of supporters caused severe failure rates during the hype years, the backer/project ratio has been increasing since 2015. Therefore, success rates and the overall funding capacity has been stabilizing. In October 2018, there was even a record median of 72 backers supporting each project. 

**Better chances to be promoted by Kickstarter.**  
In spite of growing campaign numbers, Kickstarter promotes a higher percentage of projects on their landing page (and possibly social channels) since the beginning of 2018. Today, more than 60% of all fundings are spotlighted on Kickstarter's channels. The proportion of unsupported projects has been decreasing from 55% in the hype years to only 27% today.   

Additionally, more projects than ever are additionally picked by staff to be awarded the "Projects We Love" badge as the proportion of fully supported projects has kept constant at at rate of 10%.

# 2) What determines the success of a crowdfunding campaign on Kickstarter?

To determine whether a campaign was considered successful or not, we looked into two main factors: first, the general chance to successfully end a campaign, and second, the amount of funding that was ultimately collected. 
When creators decide on a goal, they generally have to ponder whether to maximize their chances to successfully end a campaign or to generate the maximum funding possible. Both targets oppose each other diametrically. Because of Kickstarter's all-or-nothing-approach, raising the goal typically decreases the chances to succeed, yet creators risk insufficient funding by aiming for low goals.

**The lower the goal the better.**  
If creators want to keep at least a 50% chance, it appears to be advisable to stay below a benchmark of USD 10,000, leaving all other effects aside. On average goals below 5,000 had a chance above 60%. Very risk-averse creators may even stick goals below USD 1,500. 

**Successful projects realize an average surplus of 17.5% above goal** 
The surplus creators realize depends on the goal chosen. For goals under USD 3,000 the surplus rate describes a curve of exponential decay. The lower the goal chosen the higher was the surplus rate. Low goal projects typically realized a surplus of 34%, whereas goals between USD 1,5 k to 13 made a median surplus of 11-12%. 

Creators seeking funding above USD 18 k, were able to count on increasing surplus rates. In particular, goals from 45 k up to 113 k realized a median surplus of 25.6%. Yet, the surplus rates become less reliable as the volatility of pledges increases.

**It is highly unlikely to successfully collect funding beyond USD 100k.**  
Creators seeking high funding may consider alternative investment possibilities to Kickstarter. 3 quarters of successful goals were below USD 9,600 anyways.  The success chances of projects between USD 65 k to 113 k were only 20%. For even higher goals, success chances draw closer to zero.

**Kickstarter's promotion support is extremely relevant for success.**  
In 10 years, strictly projects that were supported by Kickstarter succeeded. Since 2018, on average, 54% of projects were spotlighted on Kickstarter's landing page (and optionally on Kickstarter's social media channels). 11% of completed projects were fully supported. Meaning,they got picked by staff and were awarded the "Projects We Love" badge.  

All crowdfundings that were not announced on Kickstarter's landing page failed. This includes a few campaigns that got the "Projects We Love" badge, but were not spotlighted in any way. 

Being fully featured by Kickstarter also drove the total collected funding. Projects which received the 'Projects We Love' badge in addition to being spotlighted on the landing page, had more than a double of supporters, which resulted in 2 to 2.5 times higher funding compared to campaigns that were only spotlighted. 

Generally, Kickstarter tends to support projects of lower goals. Spotlighted projects on average sought a goal of USD 3,400. Creators who intend to collect higher funding should aim for the badge in addition to being featured on the website. Fully supported projects realized a median goal of USD 7,100.

**Kickstarter is a platform to fund creative projects with comparatively low financial requirements.**  
Creative projects and categories attributed to lower commercial potential seem to most common and highly successful.
Written work and comics dominate the top categories. Fictional & nonfictional publishing projects, children's books and comic books all ended in success. Tabletop games clearly win the race of projects with the highest success rates.

**Tech and food projects are most likely to fail.** 
Due to their high financial requirements, gadgets, hard- and software, web projects all had low chances of success, although being among the most popular categories. In addition to technology ventures, I found 3 food subcategories among the ventures with the lowest chances: small batch, drinks and restaurants. Higher failure rates do not necessarily imply that Kickstarter is generally a bad place for such kind of projects. On the positive side, once successful, tech campaigns generate the highest median pledges of plus USD 22 k. 

**Universal category names are more likely to succeed.**
The top chances in popular project categories show a tendency to not have subcategories. Publishing, comics, film & video, art and music performed generally well they were communicated universally, instead of niche topics.

**The Funding Duration is 30 days. Period.***
We cannot affirm that a higher funding duration is rewarded by higher success rates. No matter if a campaign was successful or failed, the median period was generally 30 days. Overall, success chances were highest around 30 days.  
 
The average funding durations appear to be a little longer when the goals were higher. Successful goals under USD 1,500 had a mean funding duration of 28 days. Successful very high goal projects between USD 13,194 to 65,064 on average ran a week longer (35 days).

**The time of the year matters.**  
The time of the year on average affected the general success chances, investor counts and collected funding. Considering all factors, I found the best chances in December. Generally, October to December and April to July were the most promising months to run a campaign. January to March performed suboptimally. 

November was the safest bet for every creator whose primary goal was to end a campaign successfully. Those creators should avoid running a campaign in January since success rates were roughly 10% lower. Creators who seek high funding had the best chances in December or June and should avoid the January to March.

**Nailed it!**  
I identified the most valuable project categories by depicting pledges against success rates. Accordingly, the most valuable campaigns were:  

1) Technology projects without defined subcategory,   
2) Product Design projects and   
3) Documentary films.   

In contrast, the following projects had low funding potential:   

1) mobile games,   
2) Hip-Hop music and  
3) generally journalistic projects.

# Installation
### Install python3 and packages using conda package manager
    
    $ conda install pandas numpy python=3.6 matplotlib seaborn

### Intall iPython

    $ conda install -c anaconda ipython

### Install nbextensions and enable Python Markdown from the Jupyter nbextensions dashboard 
 
    $ conda install -c conda-forge jupyter_contrib_nbextensions 
    $ jupyter contrib nbextension install --user

 ### Install further packages using pip package manager
 
    $ pip install requests jsonschema
    
### Install Jupyter Notebook
You can find the installation documentation for the
[Jupyter platform, on ReadTheDocs](https://jupyter.readthedocs.io/en/latest/install.html).
The documentation for advanced usage of Jupyter notebook can be found
[here](https://jupyter-notebook.readthedocs.io/en/latest/).

For a local installation, make sure you have
[pip installed](https://pip.readthedocs.io/en/stable/installing/) and run:

    $ pip install notebook

## Usage - Running Jupyter notebook
### Running in a local installation

Launch with:

    $ jupyter notebook
    
### Running in a remote installation

You need some configuration before starting Jupyter notebook remotely. See [Running a notebook server](http://jupyter-notebook.readthedocs.io/en/stable/public_server.html).
