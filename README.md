# Investigating-Drop-in-User-Engagement
A short case study investigating a drop in user engagement featuring a faux dataset of Yammer's user database from Mode Analytics.
https://community.modeanalytics.com/sql/tutorial/a-drop-in-user-engagement/

### Investigating a Drop in User Engagement
Before starting, be sure to read the overview to learn a bit about Yammer as a company.

Yammer’s Analysts are responsible for triaging product and business problems as they come up. In many cases, these problems surface through key metric dashboards that execs and managers check daily.

### The problem

You show up to work Tuesday morning, September 2, 2014. The head of the Product team walks over to your desk and asks you what you think about the latest activity on the user engagement dashboards. You fire them up, and something immediately jumps out:

https://modeanalytics.com/modeanalytics/reports/cbb8c291ee96/runs/7925c979521e/viz/cfcdb6b78885

The above chart shows the number of engaged users each week. Yammer defines engagement as having made some type of server call by interacting with the product (shown in the data as events of type “engagement”). Any point in this chart can be interpreted as “the number of users who logged at least one engagement event during the week starting on that date.”

You are responsible for determining what caused the dip at the end of the chart shown above and, if appropriate, recommending solutions for the problem.

### Getting oriented

Before you even touch the data, come up with a list of possible causes for the dip in retention shown in the chart above. Make a list and determine the order in which you will check them. Make sure to note how you will test each hypothesis. Think carefully about the criteria you use to order them and write down the criteria as well.

Also, make sure you understand what the above chart shows and does not show.

If you want to check your list of possible causes against ours, read the first part of the answer key.

### Digging in

Once you have an ordered list of possible problems, it’s time to investigate.

For this problem, you will need to use four tables. The tables names and column definitions are listed below—click a table name to view information about that table. Note: this data is fake and was generated for the purpose of this case study. It is similar in structure to Yammer’s actual data, but for privacy and security reasons it is not real.


Table 1: Users

Table 2: Events

Table 3: Email Events

Table 4: Rollup Periods

### Making a recommendation

Start to work your way through your list of hypotheses in order to determine the source of the drop in engagement. As you explore, make sure to save your work. It may be helpful to start with the code that produces the above query, which you can find by clicking the link in the footer of the chart and navigating to the “query” tab.

### Answer the following questions:

Do the answers to any of your original hypotheses lead you to further questions?
If so, what are they and how will you test them?
If they are questions that you can’t answer using data alone, how would you go about answering them (hypothetically, assuming you actually worked at this company)?
What seems like the most likely cause of the engagement dip?
What, if anything, should the company do in response?

