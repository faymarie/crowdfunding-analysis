# 10 Years of Crowdfunding on Kickstarter - A Data Exploration
### by Marie-Luise Klaus | 20/07/2019, Berlin, Germany

This exploratory data analysis is dedicated to the 10th anniversary of the crowdfunding platform Kickstarter in April 2019. 
The main goal is to analyse current trends and determine possible factors contributing to the success of a campaign. 

Throughout the course of this notebook, I will have two main questions in mind. Based on our data:

**1) Is it still worthwhile financing your project on Kickstarter, now that crowdfunding has become mainstream?**  
**2) What determines the success of a crowdfunding campaign on Kickstarter?**

### Project
This project includes the following files:  
1) Crowdfunding Data Wrangling files (jupyter notebook, html, pdf)  
2) Crowdfunding Data Exploration files (jupyter notebook, html, pdf)  
3) Slide Deck for the presentation of findings (jupyter notebook, html presentation, pdf)  
4) Raw data, master data files (kickstarter_master1-4.csv), a collection of historic USD exchange rates  

# Dataset
## Assessment and Cleaning

The Kickstarter data set was gathered in July 2019 from an automated web scraping service called Web Robots. They publish monthly data on all ongoing and completed Kickstarter projects and released it to the public in the form of csv files on their website. 

https://webrobots.io/kickstarter-datasets/

I extensively assessed the data set, which included 212,377 project observations with each one including 37 project features. The assessment revealed multiple quality and tidiness issues. For example, I found 27k duplicated projects and severe inconsistencies in currency conversions. Therefore, I took a programmatic approach to clean the data. For the majority, I had to break up insufficiently extracted JSON strings and store them as separate data points. After the wrangling processes, I ended up with 182,823 clean project entries with 32 project features.

One of the main problems of this data set was the missing documentation provided by the source. There was no information given about the project features, nor how the data was scraped or generated. To improve comprehension and to rule out erroneous information, I collated the data set with Kickstarter's project archive, which is accessible online without any restrictions. 
On the positive side, I did not encounter any inconsistencies during the wrangling and analysis processes. However, due to the lack of documentation, I cannot guarantee the validity and completeness of the data and take no liability for misinterpretation of the results due to the lack of documentation. 

Finally, I stored the clean data into csv files. Due to Github's file size limitations, I broke the files into four parts. 

## The Structure of The Data

The clean dataset contains information on 10 years of Kickstarter projects; from Kickstarter's launch in April 2009 to April 2019. The focus of my analysis was all completed projects up until Kickstarter's anniversary in April 2019. This left me with 165,452 project observations.

As for the features of this dataset, 24 variables were selected for analysis. The variables included quantitative variables such as the funding goal or the final pledges, several time-related variables and qualitative data, such as project categories, names and project status.

### Main Feature of Interest
The main feature that I will explore is the **status** of a project. It depicts whether the crowdfunding was a success or failure.

### Supporting Features
Undoubtedly, there are many different factors that may affect the success or failure of a crowdfunding campaign. In the course of this data set, I suspect the following factors will be the most influential on a project:

- the amount of the initial funding goal: goal hist usd
- the amount pledged: pledged hist usd
- the number of backers: backers count
- the promotional support provided by Kickstarter: featured
- project categories: category, subcategory, comb cat
- the dates of the project's launch and deadline: launched at, deadline
- the duration period of funding: duration
- the location of a project: country, loc type.

# Key Insights of Findings
## 1) Is it still worthwhile financing your project on Kickstarter, now that crowdfunding has become mainstream?

**The short answer: yes, chances today are better than ever.**   
In spite of increasing project numbers and therefore higher competition, there have never been more campaigns ending successfully than today. Also, the collected pledges for each successful project have been staying on a relatively stable level.

**The number of monthly crowdfunding campaigns has been growing again since 2018.**    
After a rather moderate growth in the first 5 years after Kickstarter's launch, crowdfunding activities exploded in August 2014 and again in March/April 2015. Project counts settled down thereafter. Nevertheless, with roughly 2k new projects each month, activities remained on a high level up until today. Since 2018, the number of campaigns ending each month has been increasing notably.

**In 2018, 63.5% of campaigns were successful.**    
With the hype of Kickstarter in late 2014, we found an abnormally high percentage of failed projects. 61% flopped. During the years of recession the likelihood of failing minimally exceeded the success rates. 51% of projects failed. By the beginning of 2018, Kickstarter turned success and failure rates upside down. On average, 63.5% of completed campaigns had the chance to succeed. Actually, the record for successful campaigns was set only recently, in March 2019. Chances of winning were 74%!

**Funding goals have become lower, but the total financial backing per project has been stable.**   
I noticed a trend of declining funding goals of successful projects since 2017. While successful projects realized goals of roughly USD 3,1k between 2014 - 2016, project creators today usually aim for USD 500 less.  
Surprisingly, the overall financial backing per project has been relatively constant since 2014. In the 10 year period, creators raised a median of USD 4,825. The good news: as of 2018 creators were able to expect a median of USD 5,371.

**Today, supporters pledge smaller amounts.**  
The money each supporter spent on rewards has been declining lately, creators had to attract a higher number of supporters to collect the same amount of funding. In 2018, successful projects on average collected USD 7 less per backer than in the record year of 2016. This may be a negative development for some creators, but it may also be a strategic chance for business starters to increase their reach, funding or customer numbers.   

**Growing supporter numbers compensated for increased competition among creators.**  
We would expect the recent increase in competing projects, lower funding goals and the tendency to pledge greedier to negatively impact campaigns. However, with Kickstarter becoming mainstream, the number of people who supported a project has been increasing at a faster rate than the number of active campaigns. While a lack of supporters caused severe failure rates during the hype years, the backer/project ratio has been increasing since 2015. Therefore, success rates and the overall funding capacity has been stabilizing. In October 2018, there was even a record median of 72 backers supporting each project. 

**Better chances to be promoted by Kickstarter.**  
Since early 2018 and despite the growing campaign numbers, Kickstarter has been promoting a higher percentage of projects on their landing page (and possibly social channels). Today, more than 60% of all fundings are spotlighted on Kickstarter's channels. The proportion of unsupported projects has decreased from 55% in the hype years to only 27% today.   

Additionally, more projects than ever are additionally picked by staff to be awarded the "Projects We Love" badge as the proportion of fully supported projects has kept constant at a rate of 10%.

# 2) What determines the success of a crowdfunding campaign on Kickstarter?

To determine whether a campaign was considered successful or not, we looked into two main factors: first,the general chance of successfully ending a campaign, and second, the amount of funding that was ultimately collected. 
When creators decide on a goal, they generally have to consider whether to maximize their chances to successfully end a campaign or to generate the maximum funding possible. Both targets oppose each other diametrically. Because of Kickstarter's all-or-nothing-approach, raising the goal typically decreases the chances to succeed, yet creators risk insufficient funding by aiming for low goals.

**The lower the goal the better.**  
If creators want to keep at least a 50% chance, it appears to be advisable to stay below a benchmark of USD 10k. On average goals below USD 5k had a greater than 60% chance of succeeding. Very risk-averse creators may even choose to stick to goals below USD 1,5k. 

**Successful projects realized an average surplus of 17% above goal** 
The surplus that creators realize depends on the goal that is chosen.  Roughly, the surplus rate above goal describes a u-form. For goals under USD 3k, the surplus rate descended exponentially. The lower the chosen goal the higher was the surplus rate. Low goal projects typically realized a surplus of 40%, whereas goals between USD 1,5k to 13k made a median surplus of 11-12%. 

Creators seeking funding above USD 18k, were able to count on increasing surplus rates. In particular, goals from 45k up to 114k realized a median surplus of 26%. However, the surplus rates become less reliable as the volatility of pledges increases.

**It is highly unlikely for projects to successfully collect funding beyond USD 100k.**  
Creators seeking high funding may consider alternative investment possibilities to Kickstarter. 3 quarters of successful goals were below USD 9,6k anyways. The success chances of projects between USD 65k to 113k were only 20%. For even higher goals, success chances draw closer to zero.

**Kickstarter's promotion support is extremely relevant for success.**  
In the last 10 years, only the projects that were supported by Kickstarter succeeded. Since 2018, on average, 54% of the projects were spotlighted on Kickstarter's landing page (and optionally on Kickstarter's social media channels). 10% of completed projects were fully supported. Meaning, they got picked by staff and were awarded the "Projects We Love" badge.  

Every crowdfundings that was not announced on Kickstarter's landing page failed. This includes a few campaigns that got the "Projects We Love" badge, but were not spotlighted in any way. 

Being fully featured by Kickstarter drove the total collected funding. Projects which received the 'Projects We Love' badge in addition to being spotlighted on the landing page, had more than a double the number of supporters, which resulted in 2 to 2.5 times higher funding compared to campaigns that were only spotlighted. 

Generally, Kickstarter's preference was to support projects with lower goals. Spotlighted projects on average sought a goal of USD 3.3k. Creators who intend to collect higher funding should aim for the badge in addition to being featured on the website. Fully supported projects realized a median goal of USD 7.1k.

**Kickstarter is a platform to fund creative projects with comparatively low financial requirements.**  
Creative projects and categories attributed to lower commercial potential seem to be most common and are highly successful.
Written work and comics dominate the top categories. Fiction & nonfiction publishing projects, children's books and comic books usually ended in success. Tabletop games clearly win the race of projects with the highest success rates.

**Tech and food projects are most likely to fail but realize the highest total funding.** 
Even though they are among the most popular categories, gadgets, hard- and software and web projects had low chances of success. In addition to technology ventures, I found 3 food subcategories among the ventures with the lowest chances: small batch, drinks and restaurants. We can attribute their high capital requirements to their poor success chances. It's important to say that higher failure rates do not necessarily imply that Kickstarter is generally a bad place for these types of projects. On the positive side, once successful, tech campaigns generated the highest median pledges of plus USD 22k. 

**Universal category names are more likely to succeed.**  
The top chances in popular project categories show a tendency to not have subcategories. Publishing, comics, film & video, art and music performed generally well if they were communicated universally, instead of niche topics.

**The funding furation is 30 days. Period.**
Although creators are free to choose their funding duration, it seems to be universally accepted to run a campaign within a period of roughly 30 days. It would seem natural to assume that a longer time frame would allow projects to increase their chances of success and collect higher funding. However, I found that longer durations are not rewarded with success. In fact, campaign periods ranging from 15 to 32 days were generally linked with the best chances.

The capital requirements may affect the chances of success though. The average funding durations appear to be prolonged when goals were higher. Successful goals under USD 1.5k had a mean funding duration of 28 days. Successful very high goal projects (USD 13k - 65k) were able to extend the funding duration by one week (35 days) without losing chances of success.

The second most popular period of 60 days turned out to be not advisable since it's associated with the lowest chances.

**The time of year matters.**  
The time of year affected the general success chances, investor counts and collected funding. Considering these factors, I found the best chances are in December. Generally, October to December and April to July are the most promising months to run a campaign. January to March performed suboptimally. 

November was the safest bet for every creator whose primary goal was to end a campaign successfully. Those creators should avoid running a campaign in January since success rates were roughly 10% lower. Creators who seek high funding had the best chances in December or June and should avoid January to March.

**The most valuable categories.**
I identified the most valuable project categories by depicting pledges against success rates. Accordingly, the most valuable campaigns were:

1) Design, in particular Product Design
2) Games, in particular Video Games and Tabletop Games
4) Fashion, in particular Apparel
3) Film & Video, in particular Documentaries & Narrative Films 

In contrast, the following popular project types were rather unsuccessful:   

1) Web Tech, Software and Apps  
2) Mobile Games  
3) Food Trucks  
4) Hip-Hop Music  

## Key Insights for Presentation

For the presentation, I will explore the points I discussed above in visualizations. By choosing the most meaningful plots I will explore my 2 research topics. By the end of each section, I will summarize my findings. The first summary comes to the conclusion that **Crowdfunding on Kickstarter has matured.**  
The second research topic will be summarized by **6 Rules for Success on Kickstarter**.

In contrast to the exploration, I omitted general descriptive statistics of Kickstarter.com and univariate plots of the investigated campaign features. Considering the complexity of my research topics, bivariate and multivariate plots were a better fit to visualize my findings. 

To answer whether it is still worthwhile to run a campaign on Kickstarter, I depicted the development of the main and supporting variables on a timeline. While doing so, I paid extra attention to the differences between successful campaigns and failed campaigns. To tell the story, I start by laying out how Kickstarter becoming mainstream may have negatively affected campaigns. Then, I argue that creators nowadays benefit from Kickstarter's popularity, more than they may suffer from increased competition.      

As for my second research question, I correlated project characteristics with one another and investigated the impact on success and the raised funding. As I have identified trends in project characteristics throughout the analysis of my first research topic, I considered the data from the latest years, usually 2018. I believe that the most current data describes best what determines the success of a campaign today.
I used lineplots, boxplots, scatterplots and barplots to visualize my findings. Ultimately, I was able to identify 6 general rules for running a campaign successfully. 

# References

1) Agrawal, Ajay; Catalini, Christian; Goldfarb, Avi (June 2013). "Some Simple Economics of Crowdfunding". NBER Working Paper No. 19133. doi:10.3386/w19133, https://www.nber.org/papers/w19133.pdf  
2) Wikipedia.org (July 2019): https://en.wikipedia.org/wiki/Crowdfunding  
3) Kickstarter.com, "How to start a project" (July 2019), https://www.kickstarter.com/learn?ref=nav  
4) Reviewed by Smith, Tim (last updated June 2019),  "Crowdfunding", https://www.investopedia.com/terms/c/crowdfunding.asp  
5) Barnett, Chance (May 2013), "Top 10 Crowdfunding Sites For Fundraising",  https://www.forbes.com/sites/chancebarnett/2013/05/08/top-10-crowdfunding-sites-for-fundraising/#1bfd6cfd3850  
6) Nguyen, Stacey (last updated May 2019), "The 8 best Crowdfunding Websites of 2019", https://www.thebalancesmb.com/best-crowdfunding-sites-4580494  
7) https://www.thebalancesmb.com/a-guide-what-is-crowdfunding-985100

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
