## EIPIP Meeting 60 Notes
## Meeting Date/Time: Wednesday, Jul 13, 2022 , AT 14:00 UTC
## Meeting Duration: 1 hour
## [GitHub Agenda Page](https://github.com/ethereum-cat-herders/EIPIP/issues/153)
## [Audio/Video of the meeting](https://www.youtube.com/watch?v=OlKWquEmJms)
## Moderator: Pooja Ranjan
## Notes: Darkfire-rain

# Action items
Action Item | Description
---|---
**60.0** | No action from Ethereum DevOps will be taken. 
**60.1** | In absence of an EIP author of a proposal, a champinon may create a new proposal, add the content of the existing proposal with a new number. 
**60.2** | Victor may pursue the idea of "Placeholder author" by making a PR of a template for EIP-1
**60.3** | FEM may add a template for "discussion-to" link. EIP-1 can be updated with the FEM template link.
**60.4** | Issue #156 - create a new proposal with changes suggested for EIP-4906
**60.5** | Issue #157 Pooja will add the discussion to the next meeting. User is suggested to split that issue into two. (1) the licensing issue and (2) should we lint people's code

# 0.Travis CI issue. A proposal to migrate to GitHub Actions.

**Pooja:** [welcome](https://www.youtube.com/watch?v=OlKWquEmJms&t=0s) everyone to eipip meeting 60. we have pretty packed agenda this time before we get into the usual discussion the first item actually the item number zero here is about the travis ci issue as we know that there is an ongoing issue that was reported yesterday by micah and we have communicated it to team the ethereum devops team it was reported that it is fixed but apparently it wasn't i know pandapip1 created a pull request  which is kind of related so anyone from here may would like to provide a summary and where we are on the resolution 

**Gavin:** [so](https://www.youtube.com/watch?v=OlKWquEmJms&t=38) i think that the get her back actions is in fact working perfectly the problem is for some reason i'm pretty sure that travis ci is still trying to include itself as a required check and i think that probably has to be fixed by someone with admin access for the repository

**Pooja:** [well](https://www.youtube.com/watch?v=OlKWquEmJms&t=66) that's good because when i was interacting with the team they reported to me something similar to that and their last response was it looks like when it cancelled  someone was removed that needs to be re-added so if i understand correctly it was travis that was accidentally removed when you were trying to fix the issue sorry the question is for you oh my god

**Micah:** [not](https://www.youtube.com/watch?v=OlKWquEmJms&t=83) accidentally removed it was moved intentionally and why do you think that it's still being required like i'm looking at apr here and i don't see travis in the required checks list 

**Gavin:** well i'm looking at this pr right here that i recently made and travis is in fact in the required checks

**Micah:** [i](https://www.youtube.com/watch?v=OlKWquEmJms&t=131) don't see travis in that required checklist see the auto merge continuous integration rerun bot auto merge bot continuous integration continuous integration i see it in there so it's in the web hooks so if you're go tohooks you can see notify travis ci i think that is how it is finding that there is a travis ci connection like that's how github is noticing that is watching and so if we remove that web hook i think that it will stop asking travis are there anything pending for use for this it's my guess

**Gavin:** it might also be in the connections of ethereum but i'm not sure about that i deactivated it so we'll see removed it from the web hooks

**Lightclient:** [i](https://www.youtube.com/watch?v=OlKWquEmJms&t=216) didn't remove it yet i just deactivated it i don't see that as an option i only see delete at the oh now it's gone did you think that the word delete was deactivate no no no no it definitely it was like there's a check box at the bottom active and i unchecked it and so then i called it deactivate even though

**Micah:** [it](https://www.youtube.com/watch?v=OlKWquEmJms&t=241) didn't say deactivate oh i see yeah it's gone now so good job wait did you delete it no i was about to and then it's perhaps it would be better to just delete it i mean it was now intentionally or not it's gone so let's go refresh the pages okay i'm kicking kicking this 52-42 see if this  still asks for travis still shows is required well  commit something else before it rechecks okay well we can figure this out i think the assuming the github actions work properly i don't think we need to just we need to fix travis like we should just get rid of it and so we need to figure out how to actually get rid of travis and then we can just iterate on the github actions if there's problems with it 

**Pooja**: so  would there be anything required for devops team to maybe look into it or is it something that can be done by  the admin access that we have within the team 

**Micah**: i think we're okay dealing with it for now

 **Pooja**:  sounds good thank you so  

# 1. Regarding old EIPs that don't conform to current standards. Ref discussion

**Pooja:** [moving](https://www.youtube.com/watch?v=OlKWquEmJms&t=346) on to the first item listed here for today's discussion that is regarding all eips that don't conform to the current standards basically this is related to a new linting part which is under progress  there are some comments that is added  in the link provided in the agenda so sam wilson  if he you may like to maybe talk about the new part and the proposed approaches for automatic validation here

**Sam:** yeah sure so it's covers everything that eep v does but it has better line reporting information and a few other checks i'm just finishing up like a github action for it and we should be able to get rid of eipv and add this instead yeah that's got it so 

**Pooja:** i see there are three proposals for handling this i wonder if anyone has any specific oh

**Sam:** oh about like yeah we're going with the files that changed in a particular pr that's the the easiest well it's not the easiest but it's it's not too bad to implement and that's i think what micah wanted so it works out 

**Pooja:** awesome thank you we are moving  pretty fast on items today so far okay

**Micah:** i i think i fixed it it was under branch protection i still had a reference to travis ci and so i have removed travis ci and i have added eip validator html proofer and code spell as required  checks for the branch merging

**Pooja** yay thank you 

# 2 Moving proposal in absence of author. Ref: Comment

**Pooja:** [all](https://www.youtube.com/watch?v=OlKWquEmJms&t=471) right  moving to item number two that is about moving proposals and absence of author like this is a known issue that sometimes authors are not around to push the proposal we created the stagnant part to mark them as a stagnant and wait for the author to come back if they would like to pursue with that particular proposal however in some cases there are new people  who are interested to pursue that proposal they reached us on ech discord to learn about the process as how they can be added to the proposal and champion the proposal micah responded to that that was good i believe it is helpful too for a few authors to be added but i have a follow-up question on that actually too number one assuming that the proposal is in stagnant status how can we make sure that the original proposal may never come alive or move forward as we proceed with an alternate one and the other part of it is like if the proposal isn't in stagnant and the author is still not around to respond what solution do we have instead of waiting for the proposal to be eventually marked as a stagnant for a new champion to maybe take over the proposal 

**Micah:** so are you saying if the author of a stagnant  eip wants to permanently terminate it how do they do that is that what you're asking for the first question oh no

**Pooja:** [ah](https://www.youtube.com/watch?v=OlKWquEmJms&t=589) no i'm sorry that is not my question let me try to rephrase it if there is a proposal which is in stagnant status but an author of another proposal who is using this first proposal as requires for his new proposal wants to pursue the old proposal bring it out of a stagnant and they're not getting any response one solution that was suggested that that was suggested was create a new proposal it is fine but how do we make sure that the proposal which was left in its statement is never moved ahead you can't

**Micah:** we don't like if if two people want to do compete on basic what is functionally the same proposal they can historically we haven't found that be a problem like people tend to want to collaborate and so i'm not too worried about this but if like you had one person that couldn't reach the original author and so they decided to spin up a copy and push that forward through and they they're now the author and it's totally fine but then if later you know like a year later or something the other guy comes back and wants to push his stagnant through we'll let him the editors almost certainly will tell him hey someone else is already pursuing this maybe you should work with them and again historically we've always gotten people to work together and so i'm not too worried about the situation but theoretically if they wanted they could run that proposal totally separate and even if they're identical we'd allow it presumably just as a matter of process but again i would strongly encourage anyone in that situation to work together rather than

**Pooja:** [that](https://www.youtube.com/watch?v=OlKWquEmJms&t=657) is a good resolution probably for the stagnant status  yeah victor i see your hand raised 

**Victor**: yeah  i've seen some of the stagnant  proposals were actually already implemented and widely adopted and for example like some of the ones that it was proposal proposed by open zeppelin i'm curious like  for the editor group one thoughts on this type of stagnant draft it's basically the original author created an erc proposal and then also use it in some of the their own tools and now get widely adopted they don't might they might not have time to finalize it but it actually it was kind of de facto standard like what is your guidance on these so we've had this club a number of times in the past and what i usually tell people is you have a few options one if you don't have the time to update it but someone else does then you can just add them as an author

**Micah:** [and](https://www.youtube.com/watch?v=OlKWquEmJms&t=719) all you have to do in that case is just a single approval it's like so let's say you have person a has created an e eip and it goes to stagnant and person b would like to see that go to final so there's someone out there  person b can submit a pr that moves it out of stagnant and adds themselves as an author and then the original author person a can then just approve that and then from then on person b can take the proposal all the way through to final and that's one option and that's the one i generally recommend like if you've got a situation where an author doesn't have time or doesn't care to push it through but someone else does i generally encourage that one because it's it's the smoothest and cleanest path forward the other option is as mentioned before you can spin up a competing proposal that's basically identical but actually with the only changes the author and then push that one through again i it's much better if you can just get the original author to sign off on adding you as a co-author and then you push it through but if they just absolutely can't be reached which happens sometimes people like disappear entirely from the world it seems in that situation then yeah you'd have to spin up a competing proposal and push it through

**Pooja:**  there is this one particular situation which is similar to what victor was trying to explain here except the case here is the proposal is not in stagnant though it should have been because it is very old proposal but we we tried to reach out to author in between and he made certain efforts to maybe push but he again stopped and then now there is another proposal 2400 which is being discussed in url uri meeting and we are recommending  the author to maybe push that proposal because that seems to be a very good proposal which is actually helpful for many wallet developers but he is stuck because one eip831 which is not in stagnant is in draft status and author is not approachable so what is the solution

**Micah:** so the solution if you can't get a hold of the author would be to spin up a new eip and then depend on that one and push that one through to final so um so basically you'd say hey i like this idea um but again the thing to keep in mind is like from a process standpoint eips that are in draft or stagnant or whatever are basically ideas there may be good ideas and they're on their on track to eventually become like an actual adopted standard but until they make it to final they're not standard yet they're they're just ideas or drafts as you as you will like someone's working on something to try to standardize it but because they're mutable they're not really good for being standard you want something that's immutable to be a standard you don't want your standard changing to every every six months when you know an author happens to show up and edit things and so for that reason the right thing to do here is if you're depending on something that is draft and it's just not moving forward whatsoever and you can't get ahold of the author you can't convince them to add you as a co-author you can't get them to update it you can't get them push it through then create a basically copy the ap give it a new number or we'll assign a new number i should say and then add yourself as the author instead of the old one and then then you can push that through to final and then you can depend on that and so now you have something that's actually mutable that you're depending on rather than depending on something mutable

**Pooja**: one concern that he flagged here is like it is highly likely that there could be many other proposals who may have used proposal 831 in its current format 

 **Micah**:  yeah people do bad things on the internet all the time we can't stop them like i mean people did this with the erc20 and it was a mess 

**Micah:** [Like](https://www.youtube.com/watch?v=OlKWquEmJms&t=938) people started implementing the erc20 when it was in draft and then what ended up happening is the roc 20 eventually did get moved to final but because everybody had implemented it before while it was still in draft phase it ended up with a bunch of problems that everybody who was working on they acknowledged like hey these are all really big problems we should not do this this is a bad design but because everybody went out and adopted it while it was still in the draft phase we just had that we ended up just for compatibility reasons finalizing it as  in its bad form and now we're stuck with terrible erc20 tokens everywhere like and it sucks and the in a perfect world people will wait to adopt standards until they're actually immutable and discussed and people have worked through the issues they won't be like hey that's a good idea that someone just had let me go implement my entire system on top of it like they would stop think through talk about it discuss iterate and then eventually build systems on top of it of course we don't live in a perfect world of rainbows and ponies and so sometimes like in the situation if you've got a bunch of people implementing this thing even if it's not a good idea like as as design like it has design flaws sometimes it is necessary to push it through with those design claws and in this case you could do that as a separate eip so you can just again copy the ip new ap number new author push it through to final with all of its warts and bugs and everything like that just so you're backwards compatible with everybody who implemented the earlier version  it sucks i'm not a fan of it but it's sometimes necessary yeah i don't have a great answer for you there i'm also wondering if it might be

**Gavin:** [good](https://www.youtube.com/watch?v=OlKWquEmJms&t=1040) to if uh if any eip is stagnant for a certain period of time say the arbitrary six months uh chosen earlier um if other people might be able to add themselves as if we might be able to make a kind of a pathway for people to add themselves as an author and then kind of adopt that eip 

**Micah**: yeah we  talked about this back when we talked about you know making stagnant a thing um i think the general concern is is we're really loath to take over someone else's thing like kind of without their permission which is why you know we won't add authors against the authors without permission from the author and because sometimes there are eips that someone will write up a draft for and they'll sit on for six months and they'll come back and and work on it in fact i think greg here has a couple of ips that you know went went stagnant for a while and then he came back worked on them and we're i'm very hesitant to tell people hey you have six months to to get this done or iterate or we're taking it from you um i'd rather just say hey you know this is your thing you can work on it take your time whatever speed that is and for some people that's slow some people that's very fast um and if someone wants to try to race you they can do a competing vip but they can't take yours so i'm hesitant i'm not hardcore against it like if everyone else here says yes we should definitely allow people to take over eips after some time period i probably won't die on this hill um just my personal thoughts 

**Gavin**: how about for example maybe like something that like an author can add that says if for some reason i like to lose interest in this and just let it get the stagnant then other people may decide to have themselves an author

**Sam**: so that's just putting tim as an author i think that's the uh the standard 

**Greg**: how many times has this actually happened really how many times has this actually happened 

**Pooja**: at least one i can remember 

**Greg**: what only one so we deal with the case by case the creative commons license is so loose that you know there's nothing enforceable there it's just etiquette

**Greg:** [um](https://www.youtube.com/watch?v=OlKWquEmJms&t=1170) generally it's you add yourself as an author and you keep going and if the champion doesn't like it like micah says um or you copy huge bits of it and start over

**Micah**: i think the thing that that is desired by some of the people is they want the number so if you have like eip123 and then it goes stagnant but it is a becomes well-known eip-123 people don't want to then do copy of the eip123 which is now eip you know 7032 and then work on that they want to iterate on eip123 because that's well known and everybody you know is familiar with it and that's the one that i'm i'm uncomfortable
 
**Greg**:  it's a creative commons license it's a creative commons license i i don't know it's 
 
**Micah**: yeah so the content i agree through entirely greg that someone can just copy the content and talk to the ap the question is is can you take over that specific eip number four no they 
 
 **Greg**: you shouldn't take over the number you're you're a new champion you've taken over but it's going to involve in the champions new direction so it's totally appropriate it gets a new number and your desire to keep the old number is you know tough but the odds are you know nobody wants my proposal they've taken the ideas and thrown them into new proposals you know um i've got a pr to take a few paragraphs and ideas out of 615 and and put it into the new proposal and we may or may not do that it's people cooperate on this stuff it's just we're worrying way too much and stuff that is not likely to happen that we can deal with when it happens um it's you know we waste too much time creating procedures for things that may never happen anyway

**Pooja:** i may uh disagree a little bit here because i think uh we have created a lot of new process and it turned out to be helpful for managing it but again this is something that we will keep coming up with new challenges and that we would like to discuss anyway i see victor do you want to add something here 

**Zanan** i i want to say that i i feel very warm and and careful as a head as a like eip author  seeing this whole group of editors being very kind not to take people's eip numbers and trying to be nice and and not not like influenced or like missing things  over people's will but i as a eip author i've sometimes come to the situation where like i might be busy in the future and might not even be connected  in some way let's say a car hit me and i wonder i i i wonder if if we can have a middle ground let's say find a a check box in the template to begin with saying like if i enacted on this vip for the for for longer than six months or a year then  you don't have to add an editor's  editor as as the author but like i'm giving authors editors the approval to allow other people to step up if they shown sufficient significant interest i wonder if that's something you can you want to consider 

**Micah:** [i](https://www.youtube.com/watch?v=OlKWquEmJms&t=1200) think the the jokes i made earlier about making tim a co-author is something along those lines actually does work and so in the past for example peter from the guest team had some eips he had authored but he was frustrated with the ip process and didn't want to push through the final and so he just all he did was approve the pr to add tim as a co-author and then tim took everything through the final and so one can imagine kind of if we wanted to formalize that and i suggest we do formalize it but if we want to formalize that we could have you know some placeholder author that is used to indicate that you know like maybe maybe one of the editors or several of the editors if you put down you know sam matt and micah on as co-authors then it's kind of a signal in some way or maybe you put down a certain bot or something name just as a signal to say i'm okay if someone else takes this over like and in fact i have some eips like this where i have have them in stagnant i would love it if someone takes them over in fact i actively advocate yes we should standardize tim in eip1 in fact now some of my ap statement eips i actively advocate in multiple forums and whatnot please someone take this over and so being able to have that apply even after you know i'm hit by a car would be nice and so i don't need to actually be around to approve whoever does 

**Greg:** [decide](https://www.youtube.com/watch?v=OlKWquEmJms&t=1500) to take over yeah in favor of the idea i don't have any problem with the idea how to integrate that into a process i'm a little less clear i think that's the only thing i was having some sort of placeholder author that's kind of well known as if this author is in your author line it means that if your eip goes stagnant someone can take it over and you're okay with it we don't need a dead author policy that's a horrible tragedy that we'll deal with when the time comes hope it doesn't ever come well so the problem is we don't know if the author is dead or just  taking  hiatus or on vacation we're just you know we'll deal with it when it happens but it's best it's best that we just set a new if we really can't find the author if we can't find the author or have reason to believe the authors potentially going to cut you know just

**Micah:** don't take the author's number without permission  unless we know the author's gone and in some consensus just go you know john's gonna take it over and keep the same number that's that's what the dead person would have wanted whatever y'all will deal with the tragedy when it happens right so hopefully whatever does we have so for all we know this tragedy may have happened several times there are many eips that have authors that have disappeared off the street i don't know where they're at they're possibly dead and it's very possible they would have liked someone to take over their thing after they're gone and that's what 
**Greg**: nobody is suggesting nobody is bound to this decision later anyway we're you know we could write this down but when it happens people are going to do what seems best in the situation i don't

**Micah:** well so how do you propose we handle all of the stagnant eips that people would like to take over right now where we have no ability to get in contact with the author they might be dead we don't know how many we don't have a way for the builders to pre-order 

**Greg**: how many of those do we have 

**Micah**: uh we've got a handful um i'd say less than a dozen maybe but that order of magnitude so like you know 

**Greg**: okay that's a lot how many are erc's how many are core 

**Micah**: i think mostly ercs there are a couple of core eips i think that have disappeared but i think those ones have been since handled uh like uh past the ideas 

**Greg**: Core are more delicate um i just don't we need to work with those particular people we don't need to chat with each other about a general policy we really need it's work but we need to work with the people to come up with the best resolution for each situation but i would say that the general preference is you know add yourself as an author to a new eip

**Greg:** i think the president's long been since said that other than the primary author other people are simply needing knowledge for their contribution they may or may not still support um the eip uh in some cases they oppose eip but don't want to have their name removed so um just take it over and give it a new number and if that creates some confusion it we can deal with that that's a preference and we can go against a preference if we think it's best it's just

**Micah**:  so how do you propose we deal with situation victor's saying or he's got an eip and he wants to make it clear that if he disappears he would like someone else to be able to take over that eip specifically like how should we you know record this or track this or maybe 
 
**Greg**: he can stick he can put it in his last will and test on it 
 
**Gavin**: or we could stick it in the preamble it went into their notes of this meeting and we archived the notes so i don't i don't see a problem um 
 
**Micah**: so i mean yes what you just described would work um i feel like like if that's our process i'm fine with

**Micah:** [that](https://www.youtube.com/watch?v=OlKWquEmJms&t=1773) uh it feels like the process would be simpler if we just had a **placeholder author** that the person can put in rather than requiring the person show up the EIPIP meeting and bring it up and you know 

**Greg**: no i'm just saying when a person asks you know we say have you tried hard to find the author and if the answer is yes and there can't be a hard and fast rule there um it's always **an option to just take a proposal add yourself as author under a new number that's the preferred option if you can't find the author and if the author doesn't want if the new author doesn't want to do it for some reason we consider those reasons** i don't think there's many cases of that you know for many reasons it can't just be rejected out of hand 

**Victor**: so i think um one thing you could do victor um to bypass this whole um debate that greg and i are having would be add several other people and as long as you guys aren't all on the same plane at the same time when it crashes um someone will still be around to approve someone else taking it over and you can add you know some people that you know will uh support a future takeover if you disappear and that way we don't need many processes and you know if something happens to you you've got several other authors that can accept a replacement 

**Greg**: generally you're lucky if anybody wants to champion it 

**Micah**: i have a bunch of eips that i wish someone would

**Victor**: I can chime in, I think you answered tim's question why not just make copy of it. i feel like for just speaking of myself or whoever cares about the content of the eip more than uh the num the the glorious number um i think authors  can be less caring about like someone else taking the number rather than like people just make make a copy and claim themselves as they author even though that cc0 definitely is not like restricting that and they know that but authors i think care about their work being used or not so in respecting that uh i think it's it's slightly better for from me as a personal uh feeling that uh if i can just sign off and say hey uh i'm okay someone take off and then but i also i also wonder if it's a good idea to just put some render uh editor as a placeholder author because of the the title of author actually mean something for people like you you guys are all authors yourself as well right when you put the author in the in the subject of the of the paper it really means something so maybe either we can say uh have a separate like a trusted editor or something like that um that has the approval  to edit um and and remove authors if they need to or um we can just i think for me it's simply just like a check box that i'm signing off for the resume and editor group to to to have someone else take off if they see fit so  **i can further pursue this idea by making a pr of a template for eip1** and we can i don't want to like hijack too much time of this meeting which pooja says already very packed but i appreciate you guys or he listened to me on this idea 
 
 **Micah**: yeah so as far as further discussion um oftentimes just creating a pr against the ip1 is a good way to incite discussion so make your proposed change and then all of the editors will pile on and say whether you like we don't like it and then eventually it'll get rejected or approved and this works particularly well if it's a very simple change like if you want to add a line to the header or something um the effort there you know is very low to uh for you to do create that pr and then it gives us a place to discuss and iterate um so if you're up for and you want to continue this discussion um i'd say that probably the next step 
 
 **Victor**: sounds good thank you and before that i'll just write it to my personal leading will 
 
 **Micah**: yeah if if a lawyer contacts me and asked me to validate a death certificate and associate it with the github handle i'll tell them uh yeah no i'm not gonna well actually github has a process that 
 
 **Gavin**: actually allows you to transfer your account to another github account in case of your death if you're checking yourself 
 
 **Micah**: okay yeah do that i guess

**Pooja:** [sounds](https://www.youtube.com/watch?v=OlKWquEmJms&t=1980) good all right it looks like we had a lot of good discussion plus fun discussion here i i wanted to quickly respond to one point of Greg which i find uh a fair here like we should not allow any other author to take their eip number once they have submitted and has been merged as draft in the eip repository which i think is not going to be a case in any case because if someone is trying to rewrite the eip that would not contain the same history because they that is not being merged on the same um PR number so anyway they would be getting a new number um so yeah i think that would resolve uh the main issue and otherwise i believe we have a handful of other solutions to deal with certain situation in here. so i wanted to check on this issue because uh the author reached out to me like what would be the next best step um so i'm gonna suggest him to maybe come up with the own proposal and try to push that proposal in order to push the original proposal he wanted to move it towards final and i'm gonna ask him to hang out on eip editor's channel for any question concern and any road blocker if he finds on the way thank you for this discussion 

# 3. The future of eip process after the merge

**Pooja**:  moving on to the next item listed here on the agenda that is about the future of eip process after the merge so in the past few meetings we discussed about the core eip process which we may expect after the march and i was talking to an act who is currently leading the nft working group and she is also looking into some of the erc is related to nft and she is concerned about the process on that i would like you to maybe share about your thoughts concern on this topic and then we can probably discuss how do we see it 

**Anett** okay thank you so much for giving me a word uh so regarding the eipip template i just share it to the agenda document the hackmd document which i discussed the with greg um on like how we should do like what kind of template we should have for magicians forum in order so people can share an eip still farm but without complicating copy pasting the full eyepiece itself uh so my idea is to i mean i talked to greg with this um so it should have like tl;dr of the eip itself eip motivation and specification and additional links to any sources or implementation or anything like that i can post link here as well um and um so yeah so that's the template um so others will have easier job or like it should be like easier to share EIPs on the forum and so it can be discussed and that's pretty much it i mean we've been also talking with um some people in the nft standard working group regarding the eip4007 or 4907 or something i think um and there has been many comments regarding that but i push it to the outer so they maybe edit the eip tiles and add more texts in a different languages and i mean there are like bunch of um links which i can share later on but that's probably on eip authors itself and that's pretty much what i wanted to share i'm going to start going with you guys for the hacking document 

**Pooja** thank you um just to provide some more context here it was reported to the group that sometimes when we are recommending people to create an issue thread on fellowship of ethereum magician they are pasting the entire content of eip and that's why this is a proposed template which we are hoping to have it on fellowship of ethereum magicians so they get the guideline of how they should initiate a discussion on that forum and do not end up pasting the entire proposal so uh that was on it. coming back to uh the point that we were trying to bring it here about the eip process my general understanding is the eip process after the merge will not be affected for erc or any other category of proposals other than the core eip which we will be probably discussing in this meeting today or if if we get time yeah any other different thought do do we see any changes coming up for erc category proposal in future considering the present proposals that we have on table  

**Greg:** i like seeing the whole eip pasted in if that's what they want to do that's what's ready uh

**Micah:** [so](https://www.youtube.com/watch?v=OlKWquEmJms&t=2400) i have no problem with creating a template for over on the fm forums that contain some standardized thing just to help people along i generally am okay with people doing what they want for their post if they already have a draft eip then i do weekly prefer that they don't just paste in the whole eip because then it ends up out of sync with the eip itself over time and i'd rather than paste a link to the eip oh but if they if they're starting with no aap and they just have an idea and they want to iterate then i think like greg said the full ap is fine or partially ap i would also be okay with pretty much anything so oh basically my stance is is if you guys think this would be useful i have no problem with it i think the strong advice is make it clear to initiate discussion with but a template or just examples whatever but yeah it's it's up to the author and we have enough to do without policing the authors have we verified that we can that  discourse does support templated topics like can we actually create a template that integrates with this course that was going to be my next question yes yeah like having having a template that is just like a file somewhere i'm my concern would just be that no one would look at it like we already have this problem with the ip1 right no one actually looks to eap one they generally just copy another eip and so if they happen to copy an old eap that doesn't match the current format then they use that if they copy a new ap they use that if fem or discourse supports like when you click the new button it asks you hey do you want to use this template then people might actually use it and it's probably worth it it might be worth the effort to give some give authors like a hint hey this is a good template to use give it a try whereas if we can't actually do that then i would be hesitant to spend time you know designing and polishing a template if no one ends up using it isn't that what the eip template in the root of the erp's repository is supposed to be it is anyone uses it except for i think me i think i'm the only person that actually creates their ips for that template that's exactly the problem right is that if it's not part of the new pr flow then people what was that kevin oh i use that too okay so there's two of us that use it i think it's  from an author perspective most authors only have one or two proposals like the majority of them other than them being very familiar with the process so yeah so maybe using lintor is the lean tool or  the travis which you discussed just now  to to help guide people so that they can automatically be reminded of using them or make sure they conform all right yeah please go ahead greg that comes at the stage where you're

**Greg:** actually creating the draft that this is the stage where you're just starting a discussion on on the magicians i like to people off to offer help to people you know but i want to make it easy to start things there i don't want to discourage it at all if i had to imagine my ideal scenario it would be when you're on the  discourse forums you click new and it asks you like for the one of the first things to ask you is like what topic you want to do until you choose eip discussion and then when you chose the eip discussion again this is ideal world i don't think it's possible when you chose that i would say hey would you like to use this template or would you like to freeform and the user can choose the author can choose to free form if they want or they can choose to use the template and they'd fill it out and to give them some hints and say hey here's some useful things for a new aip idea but like i said i definitely want to encourage and make it easy for people and i don't want to take away their power to do freeform stuff either so you click new a very simple bit of markdown gets dropped in like you know here's the summary and put in something else afterwards and if they don't like it they delete it and keep going yeah maybe i'll be really fine with that you know just just some markdown with some advice in between just as simple as possible but useful it's so easy to just delete it and easy enough to tell them that they have every right to delete it i don't know it's just we're making this too hard yeah if that's possible so i think next steps is someone find out can we add a template to like greg described you know where you when you click new it pre-fills some stuff you can just quickly delete if you don't like it

**Micah:** if that's possible then someone can iterate on that if that's not possible then just keep in mind like i don't want to say okay so so gavin says it is possible so whoever wants to take that i have no problem so if you you can even slow down i'm sorry it can even drop in a link to eip1 please read this is there not already one i think there's currently no template in on the forum it's like when you go to new new forum topic it's just a blank slate so we are actually just suggesting go to fellowship of ethereum magician maybe we can update that link directly leading to the template where it suggests how to properly write it the first draft well that's good so 

**Greg:**  well that's good so  **[we](https://www.youtube.com/watch?v=OlKWquEmJms&t=2803) want a button that says new eip and it opens up the topic with some minimal instructions um and fill in the blanks and um the author can take it from there** and this will encourage them to go read eip1 and use the template if they haven't already um i like that

**Pooja**:  yeah i hope that that is going to be very helpful all right we have just 10 minutes left um i see a lot of issues there i mean like the topics to be covered let me try to bring some of them quickly 
 
 # 4.  From GitHub Issue
 ### a. Include a copy of RFC 822 and RFC 2119 in EIP-1's assets folder
 [number](https://www.youtube.com/watch?v=OlKWquEmJms&t=2803s) four from github issue um this is about um some conflict include a copy of rfc 822 and rfc2119 i have added the issue link here probably there are some discussion i guess initiated by pandapip1  
 
**Micah**:  i have no problem 

**Gavin**: sorry i didn't catch which one the issue was oh is this including the rfcs well i obviously don't have any issue with it 

**Micah**: yeah that one

**Sam**:  so i'm in favor of adding two one one nine um i'm not sure if we're allowed to add the other one 
 
 **Micah**: what is the other one then why would we not me is that a different licensing yeah so 2119 explicitly says distribution of this memo is unlimited which according to their faq means that you can just redistribute it however you want um whereas the other one i think was 822 or something like that doesn't include that note so they don't give legal guidance on whether they're allowed to we're allowed to redistribute it or not 
 
 **Micah**: i interpret don't give leave bill guidance as do whatever you want but i don't know what the rest of you do no one tells me explicitly i can't do it i'm gonna do it 
 
 **Gavin**: also worst case they tell us take it down and we take it down 
 
 **Sam**: very true yeah 
 
 **Micah**: so i'm okay with approving that pr if no one else feels comfortable approving that pr um you know what so if someone created this pr i would have no problem approving it as long as no one rejected it if someone actually rejects it then i will respect that in further discussion uh do we put them in the assets directory for eip1 or do they go somewhere else 
 **Gavin**: Assets directory for EIP-1.
 
  **Sam** yeah perfect okay 
  
  **Micah** that's what i would do 
  
  ### b. [EIP-4907](https://eips.ethereum.org/EIPS/eip-4907) has inconsistencies with Requires (EIP-721), can it be updated?
 **Pooja** cool point number b here is for eip4907 that has inconsistencies which requires ip721 so here is the thing in the proposal 4907 um that has been moved to final it suggests that it requires eip721 as mandatory but the proposal has some inconsistencies with the required proposal 721. i'm dropping the link to the proposal here 
 
 **Micah**: does anyone know the technical history behind this 
 
 **Gavin**: so from what i gather uh the thing that's similar to the owner of in erp 721 uh in eip721 owner of if token id doesn't exist then it reverts but in the this eip4907 the equivalent for effective user uh does not actually refer it just returns the zero address instead and uh and basically it'd be nice if they both reverted 
 
 **Macah**: uh sure but so so if there's a final yeah so if it's final and like like having final eips that suck is pretty normal um and we have pretty strict policy that you know if your specification is final you've not changed the specification like my general way to phrase this is if someone implemented the eip before the change it must still be completely compliant after the change like you cannot have any possible implementation that becomes non-compliant due to this change and if understanding correctly this change would make something that was previously compliant now non-compliant so therefore they need a new eip 
 
 **Gavin** yeah i just suggest sticking a new eip with that change in perhaps it could i'd say it'd probably be had to be merged in this review i'm not sure if it'd be allowed to be merged in this last call that might be a bit too ambitious but i wouldn't be entirely opposed to that
 
**Micah**:  i generally prefer people go through the process draft review last call final though i also don't care how fast i go through that process the main reason is is uh i just having to go through those steps there are some people that only pay attention on certain steps and so you skip a step you skip a set of people to pay attention like for example for ercs i will glance once at an erc when it's in draft and i will glance once when it goes into the last call and i ignore everything else and so if you skip one or more steps then i will not see it and so i like to at least go through the process but again it can be quick like you can just do submit it as a draft get it merged immediately submit to review as soon as that's merged merge it immediately send it submit it as last call merge it um and then wait for two weeks and submit to final like i don't expect anyone to take a certain amount of time besides the last call step
 **Pooja**: i would agree that is generally a good practice here to start from draft and move it fast if that proposal is in good shape and people are accepting it the way it is probably **i can add that as a comment so if the user who has uh suggested this change or has pointed it out maybe want to create a new proposal** 
 
 ### c. Reference implementations aren't linted prior check-in or when marked as final
 **Pooja**: point number c 4c here is reference implementation aren't linted prior checking when marked as final i see this is um by a user tim  and i have seen some comment left by pandapip um anyone would like to summarize or is there any final decision on this issue 
 
 **Gavin**: so i think it's still very much debatable i would say that they should be all cc0 unless there is a good reason for them not to be for example the rfc's obviously we can't stick it cc0 um but i'd also suggest maybe having to have editor approval to have something that is non cc0.

**Micah:** a similar note that is license for a reference implementation discussion so on this 157 issue there's two separate things one is should we require everything to be a certain license or not and two should we lint people's code i'm pretty against linking people's code because i want authors to have autonomy to write their code how they want and if you want to do curly braces on next line with you know vertical alignment and using spaces then that's your choice and i don't want to try to enforce on anyone else any particular this is mainly because i don't want editors to be taking philosophical positions on things at all possible so that's the one thing i'm fairly

**Pooja:** against that one the licensing one is more separate more complicated we do need to resolve that because right now we don't have consistency and we should decide you know what licenses are people allowed to include as part of their eip i'm pretty strongly in favor of everything should be cc0 like the ipsc 0 and that means everything the eip you can't get out of this cc0 license by just moving all your content over to an asset file like i think that's not an appropriate way to bypass the cc0 licensing but i know not everybody agrees with me on this and so i do think we need more discussion yeah i think the other side of it is i think we should allow other licenses in the assets directory like cc0 isn't even an osi approved license so yeah it's because osi is dumb they have a pretty good reason for it i think it explicitly does not grant patents where you know the unlicensed or some of the other cc0s licenses do yeah sure but neither does mit and i believe mit is no no exactly yes mit doesn't mention patents at all whereas cc0 explicitly does not grant patents and they were concerned about that why would we want people have patents over eips we don't know it means that you can get pen the fear is patent trolls so someone comes in licensed something with cc0 but it includes a patent infringing code and then someone else will then use that code because it stacy zero license and then the patent 

**Micah:**  and then the patent [troll](https://www.youtube.com/watch?v=OlKWquEmJms&t=3360) will come show up and sue the person for using their patented stuff. it's the most ridiculous thing ever and the fact that this is an issue in the world makes me want to fast forward my plans to murder all of humanity 

**Sam**: yeah so anyways like i just think we should allow other licenses in cc0 i'm totally fine with like the default being cc0 only and if somebody wants something else like somebody has i mean somebody has to prove it anyways but yeah 

**Victor**: can we have like people have like in in wikipedia the content licenses cc by shop and you can license it with other license so you people can cite your content with either one can we make cc buy as one required license and and then if they want to license it in any other ways they can declare that we also license it under other forms so if you know you if you worry about patents we happen to also license it with this this license so you can use it how's that

 **Micah**:  i would be okay with that i don't think that addresses the problem that people have i think the problem people have is they want to include in their assets directory code that is already code that someone else wrote that they are copying as part of their eip usually it's open zeppelin so opens up i think license everything they do is mit and so they want to copy that mit code drop it in the assets directory and then use it in their reference implementation but they can't re-license that as cc0 because they don't have the rights to do
 
  **Victor**:  so this specific case i think it's impossible to avoid it that right people can always propose something and then put it there even though it can be put assumingly  influencing other people's patent who don't necessarily are the authors right 
  
  **Micah**: people can definitely lie and we just assume that everybody's telling the truth in this case because that gives us legal protection i think is the general idea like if  if someone steals someone else's code what's in the github repository then a patent troll comes around generally the person who put it there is the person who's in trouble and if as long as they like if they claimed that this is non-patented but it was that's not true then they're the ones that are in trouble and so the ultimately like we just need them from a legal standpoint presumably we need them to make a declaration that this is x and that's enough whether that declaration is true or not doesn't actually matter we just need them to you know effectively claim make a claim somewhere and 
  
 **Victor**: yeah i wonder if that that is achieved by a license or another the thing i'm concerned about is having people allowing people to use some license that's actually restricted of distribution of the content 
 
 **Micah**: yeah and that's why i prefer cc0 only like i want everything like i want to say someone goes and reads an eip and that includes all aspects of the eip including the 

specification section and the assets etc i want them to be comfortable that they can use that however they want like they don't need to worry the fact that cc0 doesn't give patent protection yes that's a concern and i mean 

**Greg**: we are not lawyers

 **Micah**:  well maybe i am, in the past life; 
 
 **Greg**: no i mean really
 
  **Sam**:  you're entirely right greg like we only have like a very very surface level knowledge of any of this stuff 
  
**Micah**:   so i mean so i spoke with lawyers in this and they also only have service level knowledge of this stuff i wouldn't give them too much credit a big part of the problem is is most of these theoretical cases have never actually been tried in court and so everybody is guessing including the lawyers and the lawyers i guess you know with you know presumably history and background and knowledge of precedent and court cases and how courts have decided in the past but like there's no actual strong president that says most of this stuff the patent stuff i think actually has been tried in court and so

[that](https://www.youtube.com/watch?v=OlKWquEmJms&t=6058)  is concerning i don't know if anyone's actually patent trolled cc0 before but people have patent trolled before like that is a thing that people have done 

**Greg**: i would just say i had thought we always did stick with cc0 so it's unfortunate if anything landed in assets otherwise and if it it can't be made cc0 then it should be linked to rather than copied assets and then i don't i don't see the link out to something as anything like the same force as actual inclusion and but it would be good if that if the foundation wanted to hire a lawyer and if anything ever happened then you just point and say you know this this lawyer said it was okay we tried to do the right thing and that helps otherwise you know just pick a restrictive policy and be about it and quit worrying

 **Micah**: I am not a fan 
 
 **Pooja**: so if i have to maybe put it for the not writers do we have any consensus on this or we are still continuing discussion
 
  **Micah**: No
  
 **Pooja**: okay then probably i will **add it to the next meeting** and try to see what more for and against points do we have to consider yeah think there's one thing we can do let's split that  issue or **suggest to tim to split that issue into two so one is the licensing issue and that is the entire discussion separately is should we lint people's code and i think those two can be handled in isolation for each other and they may have very different resolutions**
 
**Pooja**:  is it something that is recommended to be done on  ef devops channel or do you want it to be there on either side he has  so 

**micah**: right now he has on ethereum cat herders eipip he has an issue number 157 is linked from the agenda apparently that has two bullet points i think this should actually be split into two separate issues the discussions can remain separate 

**Pooja:** [i'm](https://www.youtube.com/watch?v=OlKWquEmJms&t=3807) sorry for a moment i forgot that we are talking about the other team i was thinking that you are talking to timbeiko my bad anyway okay fine  definitely i'm gonna add this  as what we have  taken out from this meeting and if we have two separate issues we can continue discussing on that 
well we are past six minutes from the meeting and  t**here were many other points that we wanted to discuss i hope to bring them up in the next meeting** thank you all for joining us today and yeah i hope to see you in two weeks but if there are something that we need to be addressing it on higher priority we can probably bring into Discord cat herders EIP editors channel and we can see if we come to a faster solution over there.
 thanks again see you all in two weeks have a good one everyone. see you too! 


# Attendees
* Pooja
* Zanan
* Greg
* Anett
* Micah
* Sam
* Lightclient
* Tim
* Gavin
* Pooja


