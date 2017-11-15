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
 points to a problem with older users engaging less. 

### Changing features/bugs
At this point I was just following evidence as it became apparent, but I'm going to go ahead and log the rest of this report under this hypothesis for reasons that will become apparent. At this point I had realized there was an issue with older users engagement dropoff. Let's chart the activites of users based on what quarter of the year they signed up to investigate this further.

https://modeanalytics.com/homobabies/reports/bae1534e0ad0

Strangely, it can be seen that activities for the last quarter of users (04-01-14) far outpaced the activites of all other quarters, which remained relatively constant, that is until the next quarter (6-30-14) during which the new quater user's activity began to grow while the 04-01-14 quarter users declined in activity. This was not obvious in the user engagement chart, because the activity of the newer users was offsetting the drop in activity by last-quarter users, and the change only became apparent in the week of 7-28-14 as the new quarter users began to drop in activity as well and could no longer offset the loses of last quarter engagement. 

Now if you recall, at the exact same time this is happening, there was a drop in email clickthroughs starting in the week of 7-28-14 as well. Since this drop was not accompanied by a drop in the email open rate, this drop is likely directly related to sudden decrease in user engagement. Let's then check the email actions of users grouped by what quater those users were added. 

https://modeanalytics.com/homobabies/reports/ab9e59f6569b

Not suprisingly, we see the exact same pattern as the user engagement events. What is more obvious in this chart however is that it seems each quarter of new users interacts with their emails exponentially more than older users, then begins to fall as the new quarter of users appears. This seems likely based on the fact that the older the user, the lower their interaction with emails. This was also the case in the events. The data here does not extend far enough to prove or deny this theory, but from what is visibile here we might deduce as much. 

So at this point it is apparent that the older the user is, the less engagement they have overall. This seems to point to a problem with user retention! What we don't yet know is why if normal growth usually outpaces loss of engagement from older users, then why the sudden drop in engagement in the week of 7-28-14? We do know it has something to do with email click throughs. This should be the next thing we investigate. Let's look at the email clickthrough rate based on what device the user is utilizing.

https://modeanalytics.com/homobabies/reports/ab9e59f6569b

Here we see more useful information! In the week of 7-28-14, there was a large drop in click throughs by users who used mobile devices like phones and tablets, but not users on computers. Bingo!

## Possible Solution
Based on all the information we collected, it seems like the older the user, the lower their engagement, and that newer user's engagement tends to outpace the loss in engagement from older users. However, in this particular instance, the loss in engagement outpaced newer user's engagement, and coincided with a reduction in email click throughs by all users on phones and tablets. I would suspect that this might have something to do with a change in optimization of emails for mobile users, but at this point this is only speculation, and with this information one would likely approach other departments to see what recent changes have been rolled out. 

