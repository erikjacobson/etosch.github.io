---
layout: post
title: 'Surveys : A History'
date: 2014-03-04 16:23:27.000000000 -05:00
type: post
published: true
status: publish
categories:
- Research
tags:
- surveyman
meta:
  _edit_last: '20775'
author:
  login: etosch
  email: etosch@cns.umass.edu
  display_name: Emma Tosch
  first_name: Emma
  last_name: Tosch
---
# What *is* a survey?

Everyone has seen a survey -- we've all had the customer satisfaction pop-up on a webpage, or have been asked by a college student PIRG worker to answer some questions about the environment. We tend to think of surveys as a series of questions designed to gauge opinion on a topic. Sometimes the answers are drawn from a pre-specific list of options (e.g. the so-called [Likert Scales](http://en.wikipedia.org/wiki/Likert_scale); sometimes the response is free-form.

What distinguishes surveys from other, similar [instruments](http://www.census.gov/srd/papers/pdf/rsm2006-13.pdf) is that surveys (a) typically return a distribution of valid responses, and (b) surveys are observational.

Or rather, surveys are *supposed* to be observational. That is, surveys are meant to [reveal preferences](http://www.uvm.edu/~dguber/POLS234/articles/zaller_feldman.pdf) or underlying assumptions, behaviors, etc. and not sway the respondent to answer in one way or another. There are some similar-looking instruments that are not meant to be observational. Some of these instruments fall under the umbrella of what's called an "experiment" in the statistics literature.

# Why surveys?

Perhaps in the future we won't have a need for surveys anymore -- [all of our data will be floating around on the web, free to anyone who wants to analyze it](http://andrewgelman.com/2014/03/01/moving-era-private-data-public-analyses-one-public-data-private-analyses-just-learned-cautious-data-missing-may-cautiou/). If, after all, surveys are really about observational studies, we should be able to just apply some clustering, learn a model, do some k-fold validation, etc.

There are many problems when attempting to just use data available in the wild. First of all, though we may be in the era of "big data," there are plenty of cases where the specific data you want is sparse. A worse situation is when the sparsity can be characterized by a [Zipfian distribution](http://en.wikipedia.org/wiki/Zipf's_law) - depending upon how you set up your study and what your prior information is, it's possible that you will never sample from the tail of this distribution and may never know that it is sparse. This leads us to a second problem with simply mining data : we cannot control the conditions under which the data is obtained. When conducting a survey, researchers typically use [probability sampling](http://en.wikipedia.org/wiki/Survey_sampling#Probability_sampling) (the popularity of [convenience sampling](http://en.wikipedia.org/wiki/Sampling_(statistics)#Accidental_sampling) for web surveys will be discussed in a later post). This allows them to adequately estimate the denominator and estimate error due to people opting out of the survey (so-called "unit nonresponse").

Finally, conducting a survey explicitly, rather than mining data gives the researcher a more complete view of the context of the survey. As we will discuss later, understanding context is critical and can lead to unpredictable responses.

# A brief history of survey modes

While simple surveys such as a census have been around for <a href="http://en.wikipedia.org/wiki/Census#Egypt">thousands of years</a>, the customer satisfaction or politic survey of today is a more recent development. Market research and political forecasting are products of capitalism and require access to resources to conduct and make use of surveys. Survey research is intrinsically tied to the technologies used to conduct that research and the statistical methodologies that are available and understood gat the time the survey is conducted. Before mail service, a survey would have to have been conducted in person. Although random sampling is a very old idea, it was not until <a href="http://en.wikipedia.org/wiki/Laplace#Inductive_probability">Laplace</a> that tight bounds were calculated on the number of samples needed to estimate a parameter of a population.

Centralized mail service helped lower the cost of conducting surveys. The response time for surveys was lowered with widespread adoption of telephones. Mail and telephone surveys dominated survey modes in the latter half of the 20th century. Since landline telephones are associated with an address, these now-traditional survey modes relied on accurate demographic information. The introduction of the World Wide Web and increasingly wide-spread use of cellular phones prompted survey designers to reconsider traditional instruments in favor of ones better suited to growing technologies. 

A <a href="http://schonlau.net/publication/02fieldmethods.pdf">2002 paper from the RAND corporation</a> describes growing interest among researchers about using the Web to conduct surveys. The paper addresses the assertion that internet surveys have higher response rates than traditional mail or telephone surveys. They found this to not be the case, except for technologically savvy populations (e.g. employees of Bell Labs). However, they noted that the web is only going to become more pervasive and they recommended that survey designers keep the web in mind.

The RAND paper describes web surveys not as web forms, but simply as online-distributed paper surveys. The surveys were sent over email, in a model that exactly mirrors mail surveys. They noted that spam could be an issue over time and specifically stated that it was possible that the populations with higher response rates to emailed surveys were those who may have had a lower junk-to-relevant mail ratio for email than for snail mail.

The view of web surveys from twelve years ago predated "web 2.0". It also predated the widespread use of cellular phones. Six years ago Pew Research published <a href="http://www.pewresearch.org/2007/06/19/how-serious-is-pollings-cellonly-problem/">an article</a> on the growing proportion of cell-phone-only households. They found that this population still only comprised a small proportion of the total US population, and so for polls that targeted the entire US population, unit nonresponse from cell phone users could be explained by typical error estimates. However, cell phone users were found to have a distinct population profile from the total US population. Therefore, any stratified sampling needed to take cell phone users more seriously.

# Why Web Surveys?
As technology changes, the mode used to collect survey information changes. Clearly the rising use of smart phones makes web surveys increasing attractive for researchers.

On top of the obvious appeal of being able to reach more people, web surveys afford researchers unique advantages that other modes do not allow, or are prohibitively expensive to implement. Web surveys do not require people to administer them (while many organizations use automated calling services for phone surveys, the is still an associated cost for the service, as well as <a href="http://lifehacker.com/why-you-should-hang-up-immediately-when-you-get-a-roboc-1269375265">growing discontent for robocalls</a> (okay, that still supports argument one).

Web surveys allow for rapid design modification, cheap pilot studies, and (what we believe to be most important) the ability to control for known problems in survey design. What problems could there be, other than not being able to reach people? Consider the dominant view of survey design:

<blockquote><p>
The goal is to present a uniform stimulus to respondents so that their responses are comparable. Research showing that small changes in question wording or order can substantially affect responses has reinforced the assumption that questions must be asked exactly as worded, and in the same order, to produce comparable data. (<a href="http://www.census.gov/srd/papers/pdf/rsm2006-13.pdf">Martin 2006 </a>)
</p></blockquote>
<p>We believe that this view -- this static view -- of survey design leads to overly complicated models and cumbersome statistical analyses that arise solely from only being able to perform post-hoc data analysis. Our view is that, since there are so many variables that may affect the outcome of a particular survey response, we should not try to control for everything, since <em>controlling for everything is impossible</em>. Instead, we randomize aspects of the instrument over a population, promote a "debug phase" akin to pilot studies, and encourage easy replication experiments. If we can reduce known biases in survey design to noise, we can perform more robust analyses. Now what do more robust analyses give us? Better science! Who wouldn't want that? </p>
