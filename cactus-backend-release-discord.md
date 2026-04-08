
#v0.2.11 backend release#

Chore: All websocket logs are marked as debug right now
Fix: cascading fixture deletion issues with config updates
Feat: store staff and org viewer should not see sales data
Feat: update user language

@QA Team let me know when I can push these to staging
shuning.chRole icon, Staff — 26/3/2026, 3:48 PM
deployed on cactus-backend-prod-1.lookingglassprotocol.com
@QA Team
Julia SRole icon, Staff — 26/3/2026, 3:59 PM
okay, for more clarity here
Ticket related: https://auki.atlassian.net/browse/CSA-806
should be tested on Kiki domain which moved to staging but still pointing to cactus-backend-prod-1.lookingglassprotocol.com
shuning.chRole icon, Staff — 26/3/2026, 4:00 PM
the error is gone in last cronjob, nice job @JDYaske
Image
more logs
Image
JDYaskeRole icon, Staff — 26/3/2026, 4:09 PM
Yeah that means it's working. We can remove the logs if they are too spammy though
shuning.chRole icon, Staff — 26/3/2026, 4:09 PM
yes, it is better to change to debug and also there is one log probably printed by printf instead of log.Infof
JDYaskeRole icon, Staff — 26/3/2026, 4:11 PM
Should I just change it on the branch?
shuning.chRole icon, Staff — 26/3/2026, 4:11 PM
lets change on release/v0.2.11 branch
JDYaskeRole icon, Staff — 26/3/2026, 4:11 PM
Yeah sorry thats what I meant
Ok I changed them from info to debug, and removed the dbg log
Julia SRole icon, Staff — 27/3/2026, 2:20 PM
store staff and org viewer should not see sales data - works!
Image
ArtRole icon, Staff — 30/3/2026, 11:47 AM
For this feature "Feat: store staff and org viewer should not see sales data", is this a flag that can be turned on/off per backend?
shuning.chRole icon, Staff — 30/3/2026, 2:06 PM
it is true for all backends, no feature flag
shuning.chRole icon, Staff — 1/4/2026, 2:20 PM
@QA Team how's going with the test?
ArtRole icon, Staff — 1/4/2026, 2:21 PM
The blocking of sales and unit sold for staff is working
but we can't verify the others bec of the issue with kiki org
@shuning.ch deploy this version as well on the cactus staging backend
shuning.chRole icon, Staff — 1/4/2026, 2:23 PM
i dont think those issues are related to where kiki org is
ArtRole icon, Staff — 1/4/2026, 2:23 PM
I mean for regression testing
shuning.chRole icon, Staff — 1/4/2026, 2:24 PM
like, Feat: update user language and Fix: cascading fixture deletion issues with config updates
the kiki store only matters when cactus web needs to display pointclouds
ArtRole icon, Staff — 1/4/2026, 2:24 PM
cos I can't test using Kiki Org since I can't calibrate
So I'd like to have the version on the cactus backend staging to check the end to end not only the changes
shuning.chRole icon, Staff — 1/4/2026, 2:25 PM
can't calibrate sounds like a new problem
ArtRole icon, Staff — 1/4/2026, 2:26 PM
I think this is the one that Julia raised last time
Failed to fetch data 
shuning.chRole icon, Staff — 1/4/2026, 2:26 PM
that is the problem of failing to load pointclouds, as long as that feature is disabled, it can be ignored
staging-0 upgraded to that version
ArtRole icon, Staff — 1/4/2026, 2:49 PM
Update user language is not working after changing either from mobile or web
Image
shuning.chRole icon, Staff — 1/4/2026, 2:52 PM
which endpoint does it call? and what is the request
ArtRole icon, Staff — 1/4/2026, 2:59 PM
I can't find any logs from grafana for the profile update since update profile can only be done in mobile app
But the web language change is from joystick
I tried via the new API method PUT, with changes on the name but no changes on language
Image
Image
shuning.chRole icon, Staff — 1/4/2026, 3:03 PM
the new one is a patch
not put
put doesnt have the option to update language
Image
ArtRole icon, Staff — 1/4/2026, 3:05 PM
Ugh I hate cache. My swagger still showing the previous version
let me try again
Working via API
Image
ArtRole icon, Staff — 1/4/2026, 3:24 PM
@shuning.ch the language should change based on what was sent via patch yeah?
shuning.chRole icon, Staff — 1/4/2026, 3:25 PM
yes
ArtRole icon, Staff — 1/4/2026, 3:25 PM
Ok so it's not working
Image
ArtRole icon, Staff — 1/4/2026, 3:25 PM
This one it's because I was already on JP language
shuning.chRole icon, Staff — 1/4/2026, 3:25 PM
is frontend using this endpoint?😂
ArtRole icon, Staff — 1/4/2026, 3:25 PM
That's my next question
if it's already implemented
Most likely not
since the change on mobile did not change the language
and language via web is still fetching joystick
shuning.chRole icon, Staff — 1/4/2026, 4:11 PM
so, is 0.2.11 ready?
ArtRole icon, Staff — 1/4/2026, 4:44 PM
Not yet, still need to do regression on previous app version
shuning.chRole icon, Staff — 1/4/2026, 4:48 PM
is it something you can do without using kiki?
ArtRole icon, Staff — 1/4/2026, 4:48 PM
Yes
shuning.chRole icon, Staff — 1/4/2026, 4:48 PM
ArtRole icon, Staff — 1/4/2026, 4:49 PM
I'll do this one on the QA staging backend. The one that is updated earlier
But after I check the open data set first
shuning.chRole icon, Staff — 1/4/2026, 4:50 PM
no rush
ArtRole icon, Staff — 1/4/2026, 4:50 PM
We will probably have this backend released first if everything goes well with regression since the app/web versions have issues and Louis is currently out
This one we can target after easter
ArtRole icon, Staff — 1/4/2026, 5:03 PM
Shuning can you remind me what’s the cascading fixture deletion with config updates?
shuning.chRole icon, Staff — 1/4/2026, 5:04 PM
⁠v0.2.11 backend release⁠
ArtRole icon, Staff — 1/4/2026, 5:37 PM
✅ Chore: All websocket logs are marked as debug right now
✅ Fix: cascading fixture deletion issues with config updates
✅ Feat: store staff and org viewer should not see sales data
✅ Feat: update user language
Validated all changes and working
shuning.chRole icon, Staff — 1/4/2026, 5:38 PM
thanks a lot
ArtRole icon, Staff — 1/4/2026, 5:38 PM
Notes:
Update user language is code ready only. Front end still need to implement the changes
Current update profile still makes use of the old API
shuning.chRole icon, Staff — 2/4/2026, 11:45 AM
@Art  please give me an approval on https://github.com/matterless/cactus-backend/pull/94 then I will make a release of v0.2.11
ArtRole icon, Staff — 2/4/2026, 11:47 AM
Release to prod?
shuning.chRole icon, Staff — 2/4/2026, 11:47 AM
yes
ArtRole icon, Staff — 2/4/2026, 11:47 AM
Let's do M1
ArtRole icon, Staff — 2/4/2026, 5:27 PM
Approved
shuning.chRole icon, Staff — 11:28 AM
v0.2.11 released

