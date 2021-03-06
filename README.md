# The RA Helper

## Summary

My initial idea was to make some sort of texting application to help RAs (resident
advisors) better communicate with the residents they're responsible for. I myself have
never been an RA at Vanderbilt, but I have many friends that are. I can imagine that
they run into many issues trying to communicate with 30+ students regularly 
throughout a semester. So, that was the main driving force behind this idea: to create
software that would help RAs and residents communicate more effectively. 

I have a few goals for the application: a way for residents to notify their RAs of
an emergency quickly, a way for RAs to send their residents information regarding
house/floor events, and a way for residents to get quick information regarding helpful
resources on campus like the Career Center and Writing Center.

Overall, I think some of these goals are a bit challenging but definitely all within
reach of being accomplished. With the answer to my interview questions, I hope to get
a little more insight as to what challenges RAs face and how software could overcome
some of those challenges.

## Who Was Interviewed

Interviewed:
- 1st response = current Commons RA
- 2nd response = former Commons RA
- 3rd response = current main campus RA

## Questions

1. When and why did you first decide to become an RA?
2. What types of responsibilities do/did you have as an RA that other
   Vanderbilt employees don't have?
3. How do/did you get in contact with your residents?
4. Do/did you find it easy to get in contact with your residents? 
5. What resources on campus would you like your residents to know about and 
   have easy access to?
6. Do/did you find it easy to notify your residents of upcoming house events,
   floor meetings, etc.?
7. Is/was there any aspect of being an RA that you found unexpected? (i.e.
   something you had to do as an RA that you didn't expect when you first signed up?)
8. Have you ever had to handle an emergency situation with one of your residents?
   If so, how did you handle it? 
9. What aspects about being an RA do/did you enjoy?
10. In your opinion, what's the hardest part about being an RA?

# Answers:

## Question 1: 
"I decided to become a RA in the middle of my freshman year because I wanted to 
be a mentor to incoming first-year students and help get them connected on campus. 
I also liked the opportunity to have my housing covered."

"My freshman year RAs took me and some other international students out for bbq 
on my second night in America and I immediately knew that this was something I was 
interested in: a leadership role where the main focus was on personal relationships."

"I knew I wanted to be an RA after connecting so well my RA from Freshman year. She 
made my Freshman year so much more fulfilling than I thought it would be and made 
my transition into Vanderbilt feel like I was going to a second home."

## Requirements
The responses of this question tell me that my application should be the most 
accessible to first-years. As the common trend suggests that most students decide to 
become an RA their Freshman year, the application should do its best to appeal to that
population of Vanderbilt. To me, that means the application should have special feautres 
for first-years and reply with specific information if a student types a string like 
"first-year", "1st-year", "freshman", etc.
   
## Development Approach
Using the parser in our current framework, it seems doable that the application could
search for one or all of the strings I mentioned above and and reply with other 
information like the location of Commons, the different Commons houses, etc. 

...

## Question 2:
"I am responsible for getting to know around 45 residents on my floor, and while I 
am not expected to be fully engaged 24/7, my responsibilities range all over the 
place as anytime I am in the building I may have a conversation with a resident 
or respond to a request or question from a resident. At any moment's notice, I may 
be helping a resident."

"Personal crisis care. RAs are first responders to many tragic events. We're often 
the first people on the scene with overdoses or suicide attempts, arriving even before 
the police." 

"I'm responsible for lots of logistical things like doing regular room checks to 
make sure that students are still living in the domrs they're assigned to. In a general 
sense, my responsiblities vary case by case though." 

## Requirements
The answers to this question varied a lot, so it's difficult to identify what 
requirements could be made based on the responses. But, I do think that their respones
point to a need of a sort of database or list of residents for each RA that they
could access easily. That way, maybe if the application reads the name of a certain
resident, it could quickly pull up their information if an RA needed to know what
he/she is affiliated with on campus.
   
## Development Approach
For now, I think the best way would be to simply write out a list of names in a text
document and import that into the application to parse and edit as it pleases. I 
would probably set it up as the first name listed is the RA and names 2 through x are
the names of the residents. 

...

## Question 3:
"I use a GroupMe to communicate to residents about house events like our weekly 
Sutherland Social. I also will give them invitations by hand for invite-only events 
like our Sutherland Cafecitos. I will also sit in the common area and make an effort 
to greet and chat with those who come by. If I have specific requests, I might text 
residents individually."

"I saw them in person quite frequently because we would all hang out in the common 
room together. I would text them individually, but we also had a groupme for the 
whole floor."

"Typically I just use Groupme to send a quick message to all of the residents on my
floor. But if I need to get in contact with a specific resident, I usually send him
or her a quick text."

## Requirements
Based on the fact that most if not all RAs use GroupMe to communicate, I think the
application can take inspiration from it and allow RAs to either message their 
residents as a group or as individuals.
   
## Development Approach
For now, I will develop the application to work between just 1 RA and 1 resident, but
I would hope in future versions that it would be able to work between more than 2
people individually.

...

## Question 4:
"Sometimes. Some residents I rarely see around so it is hard to get to know them. 
Sometimes residents are not responsive to texts. Most residents do not say anything 
in the GroupMe and some probably do not check the GroupMe. I am usually able to reach 
most residents by individual text though."

"Yes, and they would also initiate getting in contact with me."

"Sometimes Groupme can be glitchy, so not all the time, but for the most part yes."

## Requirements
I think implementing read receipts in some form would be the best way of getting 
rid of the ambiguity RAs experience when they send messages to their residents.
   
## Development Approach
This doesn't seem like a feature that could be implemented through Clojure, so I would
try to implement it in a later version with another tool.

...

## Question 5:
"Hank Ingram front desk, Tech Hub, Center of Student Wellbeing, Student Health Center, 
UCC, Project Safe, IICC, and possibly more I'm forgetting."

"The wellness center. It's a great resource for anyone and shouldn't be seen as a 
place to go to only when you're going through stress."

"Student Health Center, Career Center, Writing Center, University Counciling Center."

## Requirements
It seems that a common trend among the responses was that RAs feel that students should
know more about resources like the Student Health Center and the University Councling 
Center. My first responder mentioned other good resources like the Tech Hub. I think
this calls for the application to allow students easy access to this type of information
like each resource's website.
   
## Development Approach
I think using our framework's definiton of a website URL, we can easily do the same
for the websites of the resources listed above. Then if a resident types a keyword into
the application, we can have the parser search for the keyword and return a URL to the
respective resource (i.e. typing "UCC" will text back the URL to the UCC to the resident)

...

## Question 6:
"It's easy to post the message in the GroupMe and write it on the whiteboard in the 
common area, but I don't know who is getting what messages and who's actually reading 
the messages. I don't know if people plan on coming to events but when the event happens 
they don't feel like going anymore, or if people plan on coming to events but when the 
time comes they forget it's happening, or if people just don't plan on coming to events."

"Yes for the most part."

"Yes, I'm pretty sure my most of residents at least know about every floor event 
when I post about them in the Groupme, but Groupme doesn't have read receipts so it's 
hard to tell who's seen the post and who hasn't."

## Requirements
Since the responses claimed that it's easy to notify residents of events, I believe
the application should follow that trend. I was thinking that the application could
receive a keyword or string and it would send the user a list of all house events
happening that week.
   
## Development Approach
I think this would be implemented in a similar fashion to the office-hours definition
used in previous assignments. In a map that was updated weekly, I could put a list
of house events and the information for them while the key for each of these events
was an integer or string representing a date (i.e. "10-5-18")
...

## Question 7:
"There are certain responsibilities like preparing door decs and bulletin boards that 
I didn't expect. Also, there are many small miscellaneous things that pop up that I 
don't plan for, like requests for residents for this and that."

"Yes. Most of my work had very little to do with interacting with residents which came 
as quite a surprise to me. There's a great amount of admin we had to do. In fact, 
admin and event planning is such a large part of the job that I know many RAs who were 
greatly disliked or even hated by their residents yet were held in high regard and often 
promoted to the HR position because they were good at administrative duties and other 
roles that didn't involve personal interaction. Resed is quite out of touch with what 
residents actually want in an RA."

"I was a bit suprised to see how difficult it is to create community on my floor. We
have things like events and meetings where I get to see some of my floor, but I've found
that it's pretty hard to get everyone together even once in a semester."

## Requirements
Since the answers to this question varied greatly, it's difficult to identify a 
reasonable requirement. But based on the second response, it seems like there's a 
great deal of administrative/logistical work to be done. I think eventually in a more 
final version, this application could have a dual interface set up where it lists 
an RAs logistical responsibilities as well as the last time they interacted via
text with his or her residents.
   
## Development Approach
I think implementing the second part of the above requirement could be possible with
a map. If that map was updated regularly with date and time information, it could let
the RA know when the last time they communicated with a resident was. This could be
a first step into helping RAs connect more regularly with their residents.

...

## Question 8:
"Yes, one of my residents was passed out, so I worked through the appropriate chain 
of command, contacting the RA on duty and they contacted the AC on duty, and we ended 
up contacting VUPD for a medical transport."

"Yes. I called to inform the Area Coordinator and also called the police. That would 
be my general approach to the handful of emergencies I dealt with."

"Yes, I called VUPD and the Area Coordinator almost immediately."

## Requirements
Judging by the fact that each of these RAs has had to deal with an emergency situation,
I think implementing a feautre with quick contact to the hospital and VUPD would be
useful.
   
## Development Approach
In a more final version of the application I would have the RA or resident be able to
send a message like "VUPD" and immediately send their location to the police, but for
now, I will similate an auto-response that would state something like "I have seen
you are in an emergency. Calling Vanderbilt Police Department now."

...

## Question 9:
"Getting to know my residents, the different things they're involved in on campus that 
I otherwise wouldn't know about, the different stories they have, their excitement and 
energy as first-years that keeps me going, seeing their growth over the year, working 
with my RA staff and laughing and spending time with them, better understanding event 
planning & getting to go off-campus to buy food for events. Being inspired by residents."

"I loved hanging out with my residents, especially those who didn't necessarily feel 
like they were a part of the floor community. I made some great relationships with them 
and feel like I made a difference in their first year experience."

"Even if I don't get to see my residents all the time, I love almost every interaction
I have with them. All of them are so unique and bring something different to Vanderbilt.
And if I didn't sign up to be an RA, I don't think I ever would've met some of the great
people I have."

## Requirements
I think the thing I got the most out of this question was that RAs truly do love spending
time with their residents. And while a text messaging application can't fully capture
that experience that RAs would love to have, it did help me narrow down what I wanted
the application's end goal to be.
   
## Development Approach
N/A

...

## Question 10:
"Feeling the burden of so many residents & not being able to connect with them as 
well as you'd like. Every time one of them doesn't say hi, or doesn't say hi 
enthusiastically, I feel too sensitive about it. Seeing the attendance of the weekly 
Sutherland Socials dwindle as people get more involved with their extracurricular 
involvements. Not being able to come home to upperclassmen friends. There are a lot 
of rewarding moments to being a RA, but sometimes those rewarding moments are few 
and far between."

"I felt that a lot of the work we did had no impact on the first-year experience and 
was therefore pointless. Logging meaningful conversations, creating bulletin boards 
and other similar activities felt like an unnecessary burden."

"It's really hard to know how my residents are really doing especially when it comes
to issues like mental health. As an RA, I feel like it's my responsibility to be there
for my residents when they struggle with something like that, but with the constant
busyness of Vanderbilt, it's really hard to find time to sit down and see how 
everyone is doing." 

## Requirements
The answers to this question similarly did not offer any tangible requirements or
development approaches, but it did help me sympathize with RAs better and
understand what areas they could use help in.
   
## Development Approach
N/A
