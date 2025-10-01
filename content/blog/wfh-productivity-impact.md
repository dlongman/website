---
date: "2020-06-13"
omit_header_text: true
title: "Working from home and its impact on productivity"
featured_image: ""
tags:
  - Productivity
  - Ways of Working
  - Power BI
---

## The world of work has changed

The impact of the Coronavirus pandemic has meant that millions of people have been forced to work from home – with many having to make this adjustment at very short notice.

The Office for National Statistics says that 49% of UK workers reported working from home at some point in the seven days to 14 June 2020. The fact that so many people have now had this experience is likely to lead to a major change in working practices in the future.

Many experts believe that there will now be a permanent shift to more working from home. This is because the experience of home working has demonstrated to businesses and their employees the range of benefits that it can bring.

Working from home can allow people to work smarter and to achieve more with their time and resources, as well as achieve a better work-life balance. Staff can avoid the need for commuting and the stress associated with it, freeing up more time and energy to be invested in productive work.

These factors can improve staff morale and lead to better staff retention and loyalty.

There is certainly evidence building to prove the case that home working can enhance productivity.
A [survey](https://www.airtasker.com/blog/the-benefits-of-working-from-home/) by Airtasker in the USA found that remote employees work more. On average, remote employees worked 1.4 more days every month, or almost 17 more days every year, than those who worked in an office. Meanwhile, [research](https://www.researchgate.net/publication/256051553_Does_Working_from_Home_Work_Evidence_from_a_Chinese_Experiment) from the Quarterly Journal of Economics shows that home working can boost productivity by 13%.

On the other hand, working in an office can have important benefits too. The value of face to face communications and a sense of personal connection is enormous and this can be an important contributor to staff motivation. Simple things such as shared whiteboards can be surprisingly helpful. There is also the ‘buzz’ of the office, which is impossible to replicate in a virtual environment. Even random chats at the water cooler can spark ideas and identify new opportunities or solutions.

Agile was originally designed around the premise of co-located teams and so it is quite a change for an Agile company to experience working in a completely different way.

## How has working from home affected Headforwards?

At Headforwards, we have always had our teams located together, in order to make the most of team collaboration. In fact, we had been concerned that lack of face to face communication with working from home might make us less effective. This was the situation until 23rd March 2020 when our entire company, like many UK based businesses, needed to start working from home full-time.

As we adjusted to this new world, a client asked a pertinent question: _‘Has working from home impacted our productivity?’_

Our impression was that working from home was going well. Teams had adapted to the new working practices, communication was very good, and our feeling was that we were delivering at least as much as before lockdown. After all, we were used to working remotely with our clients, so this was just an extension of that practice. But could we prove it? Could we use the data we have to measure our productivity and use that as an ongoing indicator of our performance?

This led to much internal discussion on the best measures to use. We wanted something easy to capture and also easy to explain to anyone who looked at the reports but also indicative of the value we were delivering. We ultimately settled on simply measuring the number of user stories the teams delivered over time.
User stories are an integral part of our agile approach. The purpose of them is to encourage the team to focus on the value of the requirement. They are expressed from the point of view of the user and explain the reason for the functionality and the benefit it will bring. Our teams are used to focusing on delivering the most valuable stories first, so we were comfortable that using the number of stories completed was a good proxy for measuring productivity.

Since we use Azure DevOps to keep track of all the teams’ backlogs, we had a few reporting options available to us. We decided to build reports using Microsoft’s Power BI platform which had good integrations with Azure DevOps and enabled us to easily extend our reporting to pull in additional datasets and make the reports available to people who do not use Azure DevOps often.

We created an Analytics View in Azure DevOps that retrieved a historical summary of all our teams work since the start of 2019. This let us see every change to a story’s status over time and was the basis of our historical reporting. Using Power BI measures, we calculated the average number of stories that we completed each month during 2019 and used this as a comparison with 2020 data.

![Completed Stories by Month 2019-2020](/images/completed-stories-by-month.png)

This showed that we have a significant amount of monthly volatility with the number of stories that the teams completed each month. Looking at the data from the start of 2019 there does not appear to be a clear yearly trend, although January and August do appear to be lower than other months.

We also compared the number of stories completed by quarter rather than by month. This showed similar volatility, but trends were less obvious.

![Completed Stories by Quarter Chart](/images/completed-stories-by-quarter.png)

Both views suggested that the work completed during lockdown was within our expected levels of volatility. After a surprisingly strong March, our delivery levels settled to a similar level to 2019. This indicated that the lockdown had not negatively impacted our delivery productivity.

While we were building high level reporting, we compared our 2020 data to the equivalent month in 2019 to see if that highlighted any areas for concern.

![Completed Stories by Month 2020 compared to 2019](/images/completed-stories-by-month-vs-2019.png)

This suggests that we may be very slightly less productive during Q2 than we were during Q2 2019. However, the difference is very small and during Q1 we delivered noticeably more than Q1 2019. It is not uncommon for teams to have a slight dip in their output after periods of higher than normal delivery, so this was not a concern for us.

In summary, using Power BI and data already within our backlog management system, we quickly created a report that gave us confidence that the very different working arrangements during Q2 2020 have not had a significant impact on our delivery.

## Looking to the future

Like businesses across the country, we have now had an enforced ‘test’ of working from home, from which we have learnt a great deal.

We want to explore making more long-term remote working options available to staff in future but without losing the collaborative benefits of office working. It may be that the ideal solution is a mix of working environments, building on the respective benefits of both.

We have a simple system in place that will enable us to closely monitor our productivity into the future – wherever our teams are located.
