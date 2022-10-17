[Music] welcome to the sei podcast series a production of the carnegie mellon

university software engineering institute the sei is a federally funded research and development center sponsored by the

u.s department of defense a transcript of today's podcast is posted on the sei website at sei.cmu.edu

podcasts welcome to the sei podcast series my name is jonathan spring and i'm a senior

vulnerability researcher here at the sei cert division today i'm joined by two illustrious colleagues dr grace lewis

principal researcher and lead of the tactical and ai enabled systems initiative here at the sei

and dr ipek watskaya technical director of the engineering intelligence software systems directorate also here at the sei

today uh we're here to discuss their research in software engineering for machine learning welcome to you both

thank you thanks great so grace epec can we start with telling our listeners a little bit about

yourselves and what brought you here to the sei sure i can i can start my name is grace

lewis i came to the sei hard to believe it but 20 years ago

after completing my master in software engineering at carnegie mellon university i joined as an as an engineer meaning

that i was a software developer on several projects that were ongoing uh very quickly i learned that my passion

was really the research i mean i like engineering but my passion was really the research side so after that i got a

phd in computer science from from the freya university in amsterdam and now

with the sei i lead an initiative like you said called test tactical and ai enabled systems

where we conduct applied research and development in three focus areas one is uh tactical edge systems the second is

software engineering for ai systems and the third is the intersection of the two meaning how do you how do you do ai

at the edge great thanks epec how about yourself well thanks for having us uh ipagoskaya

and i came to the sei longer than i actually can admit to myself at around 2006 this was right

after i completed my phd at carnegie mellon university in a field called computational design that was applying

software engineering to design professionals and to architecture

and design tasks but i was very passionate about software and its research and ever since i joined the sei

my focus has been on software architecture and combining software architecture practices and applying it

with organizations my current research is focused on understanding how to manage technical

debt again with which builds on architecture and software architecture principles and also with working with

grace and our other teams on understanding what software engineering for ai enabled systems look like

so um thanks i know building on both of those pieces of work for ml systems youtube recently uh wrote a blog post

exploring uh software engineering and ml and characterizing what you call mismatch in ml systems

um so how does this problem of mismatch come up with machine learning and like how does it

can you describe the sort of entry point for the problem for why we why we care about it yeah sure

so the the the origin of mismatch is that when you think about how machine learning systems are built they're built

by three different types of teams you have data scientists or machine learning engineers they're building machine learning models then that model is

typically passed on to a software engineering team for integration into a larger system and then the system itself is kind of

passed on to an operations team that now is in charge of operating and monitoring the system as a whole the problem is

that if you look at how these teams are composed very different people very different backgrounds very different

vocabulary and in the end also very different like system concerns so what happens is that these teams because they

also operate independently unfortunately tend to make assumptions about what the other parts of the of the teams and the

in the systems we're doing and that is what leads to mismatch so basically mismatch is a problem that occurs

because of an incorrect assumption made in isolation by one of these teams and

in addition to that if we we found that you can trace the

the cause of the mismatch to something that some piece of information that should have been shared between

stakeholders and if and if it would have been shared it would have avoided that problem great so i i'm sure that misaligned

assumptions are not totally new but epec could you talk a little bit about how the

mismatch sort of shows up from traditional software engineering and how that gets maybe worse in machine learning

systems of course and as you've identified mismatch is not new to software engineering systems and

actually any engineering system it's really the assumptions that different parties make and how you communicate

those assumptions what's different is in the software engineering systems we have techniques that we actually anticipate

and we've kind of safeguarded with it what has been catching a lot of the organizations who are developing now ml

enable systems unprepared is the data scientist the new set of technical stakeholders that are

joining the development of these systems first of all maybe making different assumptions their techniques are

different the way they measure success or how the elements that they develop like the ml models are developed

behave are different and these models go through so many different stages that software engineers may not always

appreciate so putting that together there are actually new categories of mismatch or mismatch assumptions that

occur and also maybe opportunities to safeguard the systems both with automation or other techniques

and that was the observation that we made and that's how the research started yeah of course so i want to you know i

think that we'll want to talk to what we might recommend people can do to safeguard against different kinds of

mismatch but it's clear that we need to know what they are before we can safeguard against them um so can you tell us a little bit about

how you would go about methodologically sort of characterizing the new kinds of mismatch and maybe also interesting

places where you've identified the sort of the same mismatch as maybe more impactful but like how would we go about studying this

uh let me get started the approach we took was an empirical approach there were some uh observations we had

started to make based on the organizations we worked with things we read our research and whatnot but we

stepped back and said okay what does a mismatch really look like and do these mismatch appear same way from a data

scientist perspective from a software engineer perspective from an operations individual perspective so

we interviewed individuals across the board that included a combination of these different expertise levels and we

collected their examples and then uh we also supplemented that information with things that have been written there are

quite a number of actually papers now coming out from experiences microsoft google and some of these organizations

who are doing it and there are examples there as well so and as a result there were about 140 examples of mismatch that

we've collected and then we went about with a characterization or exercise to see whether there are some categories

that are emerging and that kind of started snowballing the research great so um

so i think that that's a really great example of sort of mixed methods sort of i guess social science and general

research which is super important and i think underused um to understand at least the security side of things i'm

not as expert in software engineering but is that also something that maybe people need to do

more of for software engineering i i would say so so it like like epec

said and like you said it is definitely a mixed method study so in one part of it was understanding

from real practitioners what does a mismatch look like or even like that was a hypothesis that we had right but is

this is this real does this match really happen right so that was the part of the interviews that we also validated with a

survey but in parallel to that just as epec said we said you know what

mismatch has occurred in the past there are lots of kinds of mismatch let's look at what the literature says and maybe

maybe are there best practices out there already for these types of systems and so we conducted what is called a

multi-vocal literature study where you look not only at the at the white literature which is the academic literature but you look at the at the

gray literature which is basically what comes up when you when you google something right so like more informal

blog posts and the the advantage of that is that you get the academic perspective but you also get the industry

perspective because those are the folks that are writing the the you know the great literature and so then after that what we did was a basically a mapping

right we said okay we know that all these mismatches exist which one of these best practices can we

map to those mismatches and then we ended up with a really really nice matrix and then at the end what happened

is that all that information that should have been shared we codified it into a set of descriptors they're machine

readable and so these descriptors are descriptors or parts of the system so this is how

you describe your trained model this is how you describe your raw data this is how you describe your training data this is how you describe your operational

environment because that way that information now is it is explicit it's it's shared and the the goal of making

the machine readable is that our next steps are really to really build tooling around this have people build tooling

around these descriptors so yes absolutely totally agree and part of the approach also helps

us as well as the practitioners and researchers identify there's a

some categories of mismatch or that will actually emerge because the field is new you don't know some of the things you

don't know and eventually those will fall in place but others are actually enduring challenges that we need to

really more research on and this kind of an approach allows us to separate okay some of these will eventually go away by

themselves because the practices will be learned by all these individuals there are other safeguards that are already

out there that people will start employing others and we've identified some of these like for example testing

being one that really requires more research from different individuals to actually advance the field and make

these machine readable district descriptors define them identify more of them develop your automation and all the

good stuff that comes with it yeah so epec you mentioned testing there as if that's sort of a simple and one thing

right but because of all of these different areas of mismatches like there are different testing that's needed for maybe each of

the pairing so i imagine that there's some mismatch that are between data scientists and engineers some mismatch

between data scientists and ops right some between ops and engineers right and so

are there different tests sort of on each of those axes and like how do we go about making sure that the right people

learn about the right tests absolutely and uh that's actually why we're going to do

continuing work in this area because the work we did just scratched the surface we

and this happened coincidentally at the time when we were working with some other uh some organizations who happen

to have challenges in what does it mean to test an ml model while it's being developed by data scientists what does

it mean to test that model when it's actually part of the system and what it's deployed are there techniques that

are already applied by software engineers that are used which is there there are techniques that data

scientists use but it seems to be more of a art rather than a science in terms of how some of these organizations are

going about that so that's actually what we're going to do we'll be doing next you're right there are mismatches that

we can safeguard there are some again obvious methods that could be used but there's also gaps that we need to

identify yeah so do more work on grace i don't know if the more interesting part for our listeners is

the things that we can fix easily or the things that are going to be super hard to fix and might we might be stuck with for a while

um but maybe do you want to talk about maybe the good news first sure and then the bad news

right so so that so here's the here's the good news the good news is that uh

at a small scale we were able to validate our our findings we were able to validate that you know mismatch exist

yes this is very important to share to avoid that mismatch so the the the good thing is that for many of those

mismatches there's not really a rule that says this value has to equal this value for many mismatches just just

share the information so for example when you hand data to a to a data scientist tell them more about it where

did you collect it how did you collect it at what time was it i mean like just just basic information or you know where

did you get it from um when this when the model is operational how fast is the data going to be coming

into this into this model so a lot of them i would say about 70 of them were really just

sharing information um for others we did have to we did have to build rules so for example um

when it when a data scientist is building a a model it is it is a good

idea if that data scientist has has some information on you know what is that what are the competing resources that are required to serve the model but then

you can have there you can have a formula right meaning resources and operations have to be greater than

resources required for running the model um so so yeah so the good news is that a lot of it is simply a lot of it is

really simply information sharing uh for a lot of them there are kind of simple rules but there are areas that are that

are still very difficult so um the number one cause of mismatch uh in our interviews was was testing

it was really testing because we we don't really know how to test these types of systems and for example from

the data scientist perspective when they say yes we tested the model it basically means we evaluated the model and the

model has the expected accuracy that that we were targeting for a data scientist that is what means

testing for a software engineer it's like have you done unit testing have you done and so the data science is like oh

unit test i'm not sure i know what that is um so so part of the the work that we're going to be doing next is really

is really building on that because that's what we saw there was like the biggest gap so for example how can we

through tooling how can we help data scientists build unit tests something that they're just i mean it's nothing wrong it's just that they weren't

trained with that yeah um from from a software engineer perspective what does it mean to integrate a a

machine learning modeling and what does integration testing look like so so yeah so that i guess the bad news although

you could say it's good news is there's there's so much work to be done thanks grace i think that the different

testing stuff is really interesting one of the things i'm was curious about reading your work

is whether like the security side of these things falls under operations

so like i've been doing some thinking about how to manage vulnerabilities in ml enabled systems

which is sort of an operations problem but the security community has sort of different testing

you know like fuzzing or symbolic execution or whatever sort of program verification stuff

similarly to do something similar to what unit tests are doing but looking for sort of a different objective

right um how do you think we can communicate those sorts of tests i know

that this isn't exactly what you did your research on but can can we sort of integrate all of that into the testing

that we need to bring together with the mismatches so i think there are opportunities with

the mismatch and the descriptors both from a testing perspective but there were other

categories of mismatches that we've identified like for example the mismatch between development environment and operational environment would also

provide opportunities to safeguard and catch for some of the issues that you're talking about i would not probably lay

them all on testing but testing definitely will create uh opportunities to catch some of those

yeah and also and also i would say that that some of the some of the let's call it security testing is testing that

we've been doing you know forever and ever and ever for example validate your inputs and that is not a common practice

in in in the data science community right um but it's a very common practice in the security in the software

engineering community so really it's it's really looking at what is what is out there and and providing those tools

that people that are not aware of of of what you need to do to make us to make a secure system

yeah so epec can you talk a little bit more about the mismatch between the development environment and the

production environment that you mentioned briefly there so some of the examples that we came

across were for example when the ml models were being developed and so happen both in the data science

aspect on the software engineering aspect the environment that they were collecting the data running the model

and whatnot was different from the actual operational environment this was a huge resource consumption

assumptions mismatch sometimes it works sometimes it doesn't but that created a lot of failures for some of the uh

organizations that we talked to and this is i think something that could easily both be checked as well as automated

because these things are uh you can there are attributes for these that actually can be up front or in an

iterative way identified and brought back into the environment okay so

can you uh what is the i don't i know it's hard to briefly summarize the whole data life cycle

but can you give us some highlights on where some of those those data life

cycle mismatches show up absolutely absolutely so so uh kind of like from from a data life

cycle right you know so you start out with raw data the raw data gets processed and you can you come up with

with training data and evaluation data right and then uh eventually the model gets put into production and now you're

dealing with with operational data or production data right so so there are there are lots of opportunities for for

mismatch not only not only just related to the data but also again related to the

different categories so for example a data scientist gets raw data

we heard it over and over again the data scientists saying that somebody just tosses them a piece of data and says go

do some data science so this just just go and do something tell me something about this data and it's like

okay what problem are you trying to solve how will you know that the problem is being solved so from that perspective there

are mismatches between the between the the expectations like from a product owner of what the what

the model of what a model could do and what you actually can can do with

that data if that if that makes any sense so there are definitely mismatches there mismatches between between let's say

raw data and training data usually occur because there's not enough information about the

raw data sure you give me the raw data and you know it's field 52 fields 53

field 73 and on the data side i'm looking at this i'm like i have no idea what field 53 is it might

be it might be that i may able to tell you something interesting about field 53 but unless i have more context i really

can't give you a good good good solution and then further on okay you have a trained model everything is great but

what happens usually when a data a data science team trains a model

you're given the data in some let's call it static format right it's in a database it's in a data file it's in

some data source when that model is put into production the data is not coming from a static

data source right it's coming from a from a data stream it's coming from user input it's coming from another thing and again for the the data and science if

the data science team doesn't know like operations like how that what are the data rates it's not only the data

science team but the software engineering team is not going to be able to say yes this model is performing well but more not not so much from an

accuracy perspective but from a from a performance perspective like you know running producing inferences in a in an

appropriate amount of time so i i hope that answers your question but those are some of the mismatches related to data

that we found yeah thanks grace i think that that is a good summary of the whole life cycle

from you know data collection through forming hypothesis and a model and moving that into production and the

stuff that can happen i i hear you know some of this is

essentially good scientific practice generally like have a question

like have a question you're trying to answer like have us have a success criteria

where you know whether you've answered it or not like understand how it's going to change your model of the world or what you want to learn from it and why

you care about it um so like i know that epec you've been involved in

that more generally in software engineering like through the journal that you're

chief editor editor of and all of this like you have a lot of different perspectives on this so it boils down to codification of best

practices there's a very important aspect of the ml mismatch work that is codification of the best

practices some of these are experience engineers experienced data scientists already do know

but it's really based on their experience once you codify especially when you can codify and represent them

as a descriptor and provide some form of ability to check regardless of who's doing it that's really when you baseline

some of these avoidable problems secure that's really where it's what it boils down to and that's probably what is

transferring from software engineering and software engineering for machine learning that's really how software engineering has improved over the

decades and i think that information is transferring and that's the approach we brought to the project as well

so epec that's really good um understanding of codification

so what are some of the remaining challenges for deploying operating and sustaining ml enabled systems

so one of the things i mean there are large industry organizations that are actually

have been using ml models and ai techniques as part of their software

they do it because they have resources they and some of the software that they

produce are not as mission critical one of the things i think especially for our stakeholders within the dod and more

mission critical safety critical domains sustainment and maintaining these systems will actually going to probably

pose new challenges we don't know what we don't know there yet we're mostly focused on the

best use of algorithms development algorithms making sure that we improve the precision their decision making

capability ethics bias privacy all these good things that are actually involved in developing ml enabled systems but

once i think these systems are out there in the field we'll start seeing some of their sustainment and deployment

challenges we'll see how we'll actually be able to upgrade some of the work we're doing in ml mismatch will

definitely contribute to that but there's more work to be done in terms of how we monitor them how we scale them

how we architect for them those are all i think going to be things that we'll learn more as we have more

experience coming from the field as well that's great so um grace can you talk a little bit about

how those challenges that epec just mentioned might inform your future work or the future work of our colleagues

here at the sei yeah so so absolutely so one of one of the things that first of all we have

upcoming work uh in addition to building tooling around mismatch detection like we said before we're really focusing on

on testing because that's a big issue on providing support for testing for for not only for data scientists but also

for software engineers and even operations folks um in addition to that uh as

as people that have followed the sei for many years especially our software architecture work uh we have a big

emphasis of on quality attributes you know understanding a system through its quality attributes what does security mean for a system what does scalability

mean for a system and all the leds you can you can think of and one big quality attribute that is not new

but i really think it's going to be key for these types of systems is monitorability just because if you think

of the model i mean the model just it's it it only knows what it what it what it knows what it knew at training if it

starts seeing new data it's not going to perform well um it might be that the environment itself changes and so now

the predictions are are somewhat different so being able to develop systems that have monitorability built

in so that you can tell that something is different in the system i think that's going to be a it is is going to

be a big challenge like epec said as systems are deployed and it's something that we were definitely very interested

in given like i said or our quality attribute focus i just think that's one of those quality attributes that is going to that is going to emerge another

another uh type of quality attribute is that you know we we talk we talk about ethics a lot right you know in ai and

ethics that's a bad i know that's a big theme but what does ethics mean from a quality

attribute perspective like how do i build a system that shows that it is ethical how do i say

this design is more ethical than this other design so it's it's understanding those new

requirements and quality attributes that come from this field i think that's also a very interesting area of research that

we would like to explore and we have efforts going on in all those areas in addition to those that

grace mentioned understanding how to move these into operations there's all the new work

coming in ml ops but there are missing parts of the life cycle and that actually meets

well with the monitorability how do you actually provide some of the information to the operations as well as data

scientists throughout the life cycles thanks grace thanks epec i have uh you

know a number of topics that i know that we could spin off to on those two things that you just

said um you know what is ethics from a quality attributes point of view is an amazing

question that i think we could probably talk about for another hour um

but before before we go too far off into something like that um

i think it's important to understand you know what we can transfer to practice sort of right now

out of what we already know um so for our listeners that are software

engineers or machine learning engineers or operations people who are getting engaged with an ml system

like what resources are available to those listeners to sort of do a little bit better right now okay so part one of

this research project which was which was under uh characterizing and and uh understanding mismatch uh was presented

in an sei webinar so i would definitely start there it's available on the sci website just go to the sei website uh

search for software engineering for machine learning uh under the webinar series um now the paper that describes the

methodology more in detail was recently uh delivered and published at a at a brand new xc 2021 workshop on ai

engineering called wayne w a i n 2021 and a preprint of that paper is

available on archive um it's called characterizing and detecting mismatched nml enabled systems um so obviously you

can you can look on archive for that and finally the replication package for part one of the of the study if you're

interested in seeing the actual data and what the mismatches were it's available on github on

github.com uh forward slash g a lewis forward slash ml dash dash mismatch and

the plan is to very soon epic and i are working on that is to upload the replication package for part two which

is also going to include the the resulting descriptors which i think are the are the main outcome of this project

and i think that's what that's going to bring you know it's our belief that it's going to bring a lot of benefit especially to practitioners in the field

that's great and we'll definitely have links to all of those resources in the show notes so our listeners don't have to sort of rewind and scribble that down

so everyone can go to the show notes and you'll find links to all of those wonderful resources that grace just mentioned um epec is there anything else

that you think our listeners should know right now about what they could maybe do a little bit better sort of with what we have available right now so i think the

sci puts out some of the results of the early work out there i would encourage

uh listeners to visit our website and blog regularly there are also other things

that have been published you mentioned iop software there was a special issue focusing on ai

effect and there were some interesting papers that relate to what we've done we published 11 practices for ai

engineering i think those resources could also be starting points for uh practitioners or researchers who are

starting to think about uh applying software engineering to ml engineering and

enabled systems as well as thinking about ai engineering yeah that 11 good practices document is definitely a good

place to start and in addition in addition uh recently

sci has published the three pillars of ai engineering which include robust and secure ai scalable ai and human machine

teaming i think those are also available and they are good resources to get started great

so grace epec thank you so much for taking your time to talk with us today

and thank you to all the listeners for joining us um we'll have links to all of the various things that we've mentioned

during the podcast in the show notes and grace epec thank you very much

thanks for joining us this episode is available where you download podcasts including soundcloud stitcher tune in

radio google podcasts and apple podcasts it is also available on the sei website

at sei.cmu podcasts and the seis youtube channel

this copyrighted work is made available through the software engineering institute a federally funded research

and development center sponsored by the u.s department of defense for more information about the sei and this work

please visit www.sei.cmu.edu

as always if you have any questions please don't hesitate to email us at info sei.cmu.edu

thank you [Music]