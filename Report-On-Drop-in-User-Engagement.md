# Report-On-Drop-in_User_Engagement
A short case study investigating a drop in user engagement featuring a faux dataset of Yammer's user database from Mode Analytics. https://community.modeanalytics.com/sql/tutorial/a-drop-in-user-engagement/

## Making a list of hypothesis
After brainstorming, I came up with a short list of possible reasons for a change in user engagement
1. Holiday/News - people away from work would potentially be talking about their work less on Yammer
2. Marketing campaign drop off - There could potentially be a drop off in the mailing efforts.
3. Changing features/bugs - major changes or issues could be driving users off the platform.
4. Bot activity

### Holidays/News
Relatively easy to check, refering to a calendar and a few newsfeeds shows that there were no significant 
holidays or news events that could have distracted users from engagement. Time to move to the next possibility. 

### Marketing campaign drop off
To check this, the yammer_emails database looks like the best bet. Here we can look at the activity of email 
actions grouped by week and action. 

https://modeanalytics.com/homobabies/reports/cb411396c671

At first glance this data confirms my suspicions; the week of interest (2014-07-28) shows a drop off in total clickthroughs immediately
 after ,meaning users are opening links from the weekly email digest less. However, while the rate of the other events remain the same, 
 there is also an increase in total digests sent. This probably means an increase in the total userbase while there is simultaneously 
 a dip in the user engagement. If this is the case, then the dip in engagement might be attributed to a drop in older user engagement while
 regular growth continues to rise as usual. Let's investigate by first looking at the rate of events contributing to total user engagement.
 
 https://modeanalytics.com/homobabies/reports/71a740306b02
 
 As suspected, there is a clear drop in most engagement activities, while the create_user event is actually rising steadily. This definitely
 points to a problem with older users engaging less. Let's chart the activites of users based on what quarter of the year they signed up. 
