$$
z=\frac{ab+cd+ef+gh+ij+kl+mn+op+qr}{y}
$$

- H_0:  Both R and Python receive funding that is commensurate with the number of users
- H_1:  R receives greater funding than Python


$$
\begin{align*}
   H_0 & : \text{Both R and Python receive funding that is commensurate with the number of users}
   \\
   H_a & : \text{R receives greater funding than Python}
\end{align*}
$$

$$
H_0
$$


$$
\begin{hyp}[Test hypothesis] \label{hyp:0}This is my first hypothesis. \end{hyp}
$$


<p>
<img src="../assets/images/stem_women.png" width="99%" height="99%" />
</p>

There is a general understanding in the world of data and coding that the R community is impressively welcoming and inclusive of women.  Python does not necessarily have a reputation for being exclusive, but we do not often hear accolades of its inclusivity either.

In this article, I compare numbers of users in the R and Python communities.  I also compare statistics on the respective women's meetup organizations for each language:  R-Ladies and PyLadies.  



## What makes people think R is more inclusive, anyway?

### Open Source Contributions
  
[Scikit-learn](https://scikit-learn.org/stable/) is the machine learning library of Python.  There is only 1 woman in the [100 top contributors](https://scikit-learn.org/stable/about.html#citing-scikit-learn).

A study examining the [gender ratios of programmers](https://blog.revolutionanalytics.com/2016/06/programmers-gender.html) found that this is the breakdown of "Percent Female GitHub Contributors, by Language":  
- R:  **9.3%**
- Python : **2.0%**

While these stats are shockingly low for both groups, R has more than 4 times more female contributors than Python.


<p>
<img src="../assets/images/gh_contributions.png" width="99%" height="99%" />
</p>

### Conference Speakers

The New York R 2018 conference had 45% women speakers.  I don’t know of any Python conference that boasts that high a percentage. 

<p>
<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">45% of speakers are female 👍🏼<a href="https://twitter.com/NumFOCUS?ref_src=twsrc%5Etfw">@NumFOCUS</a> <a href="https://twitter.com/wimlds?ref_src=twsrc%5Etfw">@wimlds</a> <a href="https://twitter.com/hashtag/diversityawards?src=hash&amp;ref_src=twsrc%5Etfw">#diversityawards</a> <a href="https://twitter.com/hashtag/rstatsnyc?src=hash&amp;ref_src=twsrc%5Etfw">#rstatsnyc</a> <a href="https://t.co/UNbqBESRa4">https://t.co/UNbqBESRa4</a></p>&mdash; Reshama Shaikh (@reshamas) <a href="https://twitter.com/reshamas/status/987384241070616576?ref_src=twsrc%5Etfw">April 20, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
</p>

### Membership Numbers
Python is, by far, more widely used than R.  Both languages are popular for data science and analysis.  Python, however, is used widely by computer scientists, web developers (Django), software engineers, and many others.  According to the [2018 Stack Overflow Developer's Survey](https://insights.stackoverflow.com/survey/2018/#technology-programming-scripting-and-markup-languages), this is the breakdown of users:  
- R:  **6.1%**
- Python:  **38.8%**

These are the breakdowns for membership in the meetup groups:
- R-Ladies: **29.5K**
- PyLadies:  **36.5K**

Given that there are more than 6x the number of users of Python as compared to R (loose deduction from survey), we would expect the number of meetup members to be significantly greater.   But, the meetup population for PyLadies is **only 1.25x** greater than R-Ladies.   

### Amplification / Networking / Marketing on Twitter
R-Ladies has a designated twitter account to celebrate International Women's Day (IWD), [@rladies_iwd2018](https://twitter.com/rladies_iwd2018).  Last year, on IWD, I noticed blazing R-Ladies activity on Twitter. From March 7 to 8, 2018, they posted over 400 tweets highlighting women in R.  Here is one of those tweets:  
<p>
<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Another brilliant R-Lady! <a href="https://t.co/x1fhRE5U6Y">https://t.co/x1fhRE5U6Y</a> <a href="https://twitter.com/hashtag/rladies?src=hash&amp;ref_src=twsrc%5Etfw">#rladies</a> <a href="https://twitter.com/hashtag/iwd2018?src=hash&amp;ref_src=twsrc%5Etfw">#iwd2018</a> <a href="https://t.co/bd2Tksseib">pic.twitter.com/bd2Tksseib</a></p>&mdash; IWD 2018 featured R-Ladies (@rladies_iwd2018) <a href="https://twitter.com/rladies_iwd2018/status/972020099166212096?ref_src=twsrc%5Etfw">March 9, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
</p>

## How is the R community achieving inclusion at such a high rate?
How is the R community so successful and what can the Python community learn from the R community?

These are some feasible reasons for the R community's culture:
- Infrastructure (board vs no board)
- Foundational:  Underlying field of study (statistics vs computer science)
- Funding
- Scope
- Network
- Enthusiasm / Priority
- Prominent Male Supporters

### Infrastructure
PyLadies has no board.  I discovered via a deep Google search a [PyLadies Kit](https://media.readthedocs.org/pdf/pyladies-kit/latest/pyladies-kit.pdf) which I do not see linked on the [main Pyladies website](https://www.pyladies.com/):

>The global PyLadies community has no formal organization behind it; no board of directors, no appointed leadership.
We found that PyLadies growth and success stems from being decentralized and non-bureaucratic.
We do have a few point people that can answer and address general, or non-location specific PyLadies questions. If
you are not a local PyLadies leader, you may do so via our general email. If you are a local PyLadies leader, you may
email our organizers list (must be added to the mailing list first).

[R-Ladies Global](https://rladies.org/about-us/team/) has an active board.  I am an organizer for both Women in Machine Learning & Data Science (WiMLDS) and PyLadies.  As a board member of WiMLDS, I can say from personal experience that WiMLDS is better able to support our chapters with a board and designated leadership.  It is indeed challenging, since it is a volunteer position, but well worth the effort.  

The PyLadies website currently has [89 chapters listed](https://www.pyladies.com/locations/), but 17 of them are defunct, and that data has not been updated.  Determining how many active chapters and members was a tedious and manual process.  Comparatively, R-Ladies has a [central account](https://www.meetup.com/pro/rladies/) where it is easy to obtain the numbers.  Some of the PyLadies chapters are included in the [PSF account](https://www.meetup.com/pro/python-software-foundation-meetups/) which includes various Python user groups. 

### Foundational
Many R users have a background in statistics.  Membership in the American Statistical Association (ASA) is 53% women.  We can make a rough comparison to computer scientists.  The Association for Computing Machinery is the largest society of computer scientists.  [I have emailed ACM for percent female membership, and I am waiting for their response.]  

The proportion of women graduating with degrees in statistics (44%) is significantly greater than those graduating in computer science (19%).  The pipeline of R users and statisticians is rich with women as compared to computer science.  

<p>
<iframe width="750" height="500" src="https://datastudio.google.com/embed/reporting/1C8ouhyJ9WVyvGftSkkAhiEqAuWvksE5n/page/yr0c" frameborder="0" style="border:0" allowfullscreen></iframe>
</p>

<p>
<img src="../assets/images/cs_degrees.jpg" width="99%" height="99%" />
</p>

### Funding
This hypothesis has not been tested, because I do not have the data.  But, it could be a possible factor:  
- H_0:  Both R and Python receive funding that is commensurate with the number of users
- H_1:  R receives greater funding than Python

$$
\begin{align*}
\begin{hyp}[Test hypothesis] \label{hyp:0}This is my first hypothesis. \end{hyp}
\end{align*}
$$
  
  
$$
\begin{align*}
  \begin{hyp}[Test hypothesis] \label{hyp:a}This is my first hypothesis. \end{hyp}
  & \phi(x,y) = \phi \left(\sum_{i=1}^n x_ie_i, \sum_{j=1}^n y_je_j \right)
  = \sum_{i=1}^n \sum_{j=1}^n x_i y_j \phi(e_i, e_j) = \\

  & (x_1, \ldots, x_n) \left( \begin{array}{ccc}
      \phi(e_1, e_1) & \cdots & \phi(e_1, e_n) \\
      \vdots & \ddots & \vdots \\
      \phi(e_n, e_1) & \cdots & \phi(e_n, e_n)
    \end{array} \right)
  \left( \begin{array}{c}
      y_1 \\
      \vdots \\
      y_n
    \end{array} \right)
\end{align*}
$$

### Scope
R is used for statistical analysis and has about 10K CRAN packages.  Python has the ability to be deployed at scale and the Python Package Index ([PyPI](https://en.wikipedia.org/wiki/Python_Package_Index)) offers over 100K libraries.  The fact that R is statistically based with a specific focus makes it easier to manage.  As an analogy, it is much easier to know neighbors and shopkeepers in a small town than in a large city.  

### Network
The R-Ladies network is broad.  They have [120 chapters in 40 countries](https://www.meetup.com/pro/rladies/).  It’s easy to find R-Ladies (to speak at conferences).  There is an [R-Ladies directory form](https://rladies.org/r-ladies-directory-form/) which asks this question:   
> Could we list you as someone willing to speak about your relevant R topics/experience?

Here is the [complete R-Ladies list](https://rladies.org/ladies-complete-list/).  (Warning:  the website is *very slow* to load.)

As a comparison, PyLadies has 45 chapters in 19 countries which is surprisingly narrow given its user base.  

### Enthusiasm / Priority
R-Ladies are either more enthusiastic and/or more communicative.  There are many related twitter accounts:  
- [@WeAreRLadies](https://twitter.com/WeAreRLadies), 4700+ followers
- [@RCatLadies](https://twitter.com/RCatLadies) with this [#rcatladies](https://twitter.com/hashtag/rcatladies?src=hash)

### Prominent Male Supporters
The R community has prominent data scientists that are vocally supportive of women in the R community and R-Ladies:  

- [Hadley Wickham](https://twitter.com/hadleywickham), Chief Scientist at RStudio, Adjunct Professor
- [David Robinson](https://twitter.com/drob), Chief Data Scientist at DataCamp
- [Jared Lander](https://twitter.com/jaredlander), CDS of Lander Analytics / Organizer of NY Open Stats Meetup & NY R Conference
- [Nicholas Horton](https://twitter.com/askdrstats), Biostatistician and Professor at Amherst College
- [David Meza](https://twitter.com/davidmeza1), Chief Knowledge Architect at NASA
- [Noam Ross](https://twitter.com/noamross), Senior Research Scientist at EcoHealth / Editor at rOpenSci. 
- [Karthik Ram](https://twitter.com/_inundata), Data Scientist at Berkeley Institute for DS / Lead for rOpenSci project

## Table of Key Characteristics of R-Ladies and PyLadies
This table compares key details of R-Ladies and PyLadies, as well as Women in Machine Learning and Data Science (WiMLDS).  WiMLDS is included because it serves both populations in data science.

| Detail            | R-Ladies     | WiMLDS | PyLadies         |  
|-------------------|--------------|--------|------------------|
| Founded           | 2012         | 2013   | 2011             |   
| Users (a)         | 6.1%         |        | 38.8%            |
| Language          | R            |        | Python           |
| Sponsors          | R Consortium | none   | PSF (b)          |   
| Sponsor Followers | [5.9K](https://twitter.com/RConsortium)             |        | [223K](https://twitter.com/ThePSF) |
| Field of Study    | Statistics   |        | CS (c), others   |
| Board             | yes          | yes    | no               |
| Members           | 29,455       | 20,140 | 36,500           |
| Chapters          | 120          | 34     | 45               |
| Countries         | 40           | 17     | 19               |
| Slack Members     | 650          | 751    | 1515             |
| Twitter Followers | 8112         | 8376   | 10000            |
| Affiliated Conferences | ?       | none   | PyCon            |
| Other Conferences | Rstudio, useR!, NYR | none | PyData ?    |
| Language First Released |   1993 |         | 1990            |

Notes:  
- SO (a) = Stack Overflow Survey data
- PSF (b) = Python Software Foundation
- CS (c) = Computer Science


## What steps has the Python community taken?
The Python community has acknowledged the lack of diversity in speakers, open source contributors and working developers.  There are various organizations with initiatives to improve diversity.  

### Open Source Sprints

To increase the participation of women in open source, and specifically for scikit-learn, [Andreas Mueller](https://twitter.com/amuellerml) has organized open source sprints with [NYC Women in Machine Learning and Data Science](https://github.com/WiMLDS/nyc-2018-scikit-sprint).  While the event was a positive learning experience, the impact is undetermined, with 5 pull requests merged at the event, and two more merged post-sprint.  It will take a while to make a significant dent.  

[NumFOCUS DISC and Jupyter](https://github.com/sbrice/disc-sprint-nyc-2018) held a sprint in October 2018 to increase diversity in open source.  The impact of that sprint has not yet been published.

It is unclear how many open source sprints are being held and their impact.  That data is not being tracked by a single organization.  

### [Python Software Foundation](https://www.python.org/psf/) (PSF)
The Python Software Foundation manages the open source licensing of Python.  They also run PyCon as well as other Python conferences around the world.  They have a grants program for funding special projects.  PSF has [27 meetup groups](https://www.meetup.com/pro/python-software-foundation-meetups/) in 3 countries, totaling 46K members. 


#### [PyCon](https://us.pycon.org)

PyCon [2018](https://us.pycon.org/2018/about/) was held in Cleveland, Ohio this past May.  It is the national conference, sponsored by PSF, and is the largest annual gathering for the community using and developing the open-source Python programming language.   PyCon organizers reached out to women to encourage them to submit proposals and they also provided mentoring around the process.  The impact of this process is unknown.

### NumFOCUS

NumFOCUS was founded in 2012, and it supports and promotes open source scientific software (some examples: Numpy, Pandas and Jupyter).  Beginning in 2017, they began a [Diversity in Scientific Computing (DISC)](https://numfocus.org/programs/diversity-inclusion) committee whose aim is to increase diversity in the open source community.  

#### [PyData](https://pydata.org/)

PyData is an educational program of NumFOCUS which provides a forum for the international community of users and developers of data analysis tools to share ideas and learn from each other. They have a [community of meetup groups](https://www.meetup.com/pro/pydata/) with 100K members in 120 groups in 47 countries.  They host meetup events as well as yearly conferences.  There is no formal relationship between PyData and PyLadies.  It is unclear if there is a formal collaboration with the Python Software Foundation.  

### [Big Apple Py](https://bigapplepy.org/)

Big Apple Py is an organization which supports open source in New York City.  They organize the annual Python conference [PyGotham](https://2018.pygotham.org/).  They are a transparent and inclusive NYC organization which is committed to increasing diversity of speakers and attendees at PyGotham.  They offer NYC PyLadies a booth at the conference free of charge.  

### [Django Girls](https://djangogirls.org/)

## What more can the Python community do?



## What more can the Python community do?
1.  Create an official/unofficial "Board" for PyLadies
2.  Get more male allies
4.  Celebrate the wide scope of Python
    - Connect the Python communities
    - Connect women in Python with each other
5.  Grant proposal
6.  Increase PyLadies membership and track statistics
7.  Involve more women to be contributors to open source

Some of the following

### Action Items
Grant to do this, key endpoints:
Track number of women speakers at conferences and make goals for increasing those statistics
Collaboration between NumFOCUS, PSF and PyLadies


## Contact 
I welcome any updates or edits to this article.   I can be contacted via email at reshama@wimlds.org 

## References
- [Bachelor’s Degrees Earned by Women, by Major](https://www.aps.org/programs/education/statistics/womenmajors.cfm)
- [NSF Field of Degree: Women](https://www.nsf.gov/statistics/2017/nsf17310/digest/fod-women/)
- [Statistics We Still Have a Problem and We Need Your Help](https://statisticalrecipes.blogspot.com/2018/10/statistics-we-still-have-problem-and-we.html)
- [R vs Python:  Meta-review on Usability, Popularity, Pros & Cons, Jobs, and Salaries](https://www.stoodnt.com/blog/r-vs-python-metareview-usability-popularity-pros-cons-jobs-salaries/)
- [R vs Python for Data Science](https://www.kdnuggets.com/2015/05/r-vs-python-data-science.html)
- [Redmonk Language Rankings](https://blog.revolutionanalytics.com/popularity/)
- [2017 SAS, R, or Python Flash Survey Results](https://www.burtchworks.com/2017/06/19/2017-sas-r-python-flash-survey-results/)
- [Women a Growing Force in Statistics and Data Science, Reports Washington Post](https://thisisstatistics.org/women-a-growing-force-in-statistics-and-data-science-reports-washington-post/)
- [Women In Science, Technology, Engineering, And Mathematics (STEM)](https://www.catalyst.org/knowledge/women-science-technology-engineering-and-mathematics-stem)
- [AI is the Future, But Where are the women?](https://www.wired.com/story/artificial-intelligence-researchers-gender-imbalance/)
- [Gender Ratio of Programmers, by Language](https://blog.revolutionanalytics.com/2016/06/programmers-gender.html)
- [Inequality of underrepresnted groups in PyData leadership](http://nbviewer.jupyter.org/github/scopatz/nf-project-inequality/blob/9b83df3090c9b9b1b953d2905d428b71165ce607/nf-project-inequality.ipynb)


<a href="http://www.pewresearch.org/fact-tank/2018/01/09/7-facts-about-the-stem-workforce/ft_18-01-08_stemworkers_5/"><img width="615" height="642" src="http://www.pewresearch.org/wp-content/uploads/2018/01/FT_18.01.08_STEMworkers_5.png?w=415" class="attachment-large size-large" alt="Representation of women in STEM jobs varies widely" /></a>
