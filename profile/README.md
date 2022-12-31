# CSB Open API
> Built by students for students

A most certainly helpful tool for a most certainly competitive student.

- CSB Open API is a tool which works on top of the [CSB Engage](https://cambridgeschoolportal.engagehosted.com/) API to provide helpful insights and statistics
unachievable with the stock engage engine. CSB Open API **must not** be mistaken for a tool used for harassing or bullying pupils.

- CSB Open API is purely a passion project as much as it is a utility project. It was never made with any intent of discrediting people and must be used
for personal use **ONLY**.

## FAQ
### Are the results of CSB Open API achieved by *hacking*?
TL;DR: NO

Hacking is a very serious offense and most certainly a very hard skill to master. Even though I (Patrick Arvatu) would love to know the craft of hacking
I am simply miles away from *hacking* something. As the surprise of most of people (me included) Engage publicly displays marks of students by default
hence the spark of ideas needed to bring this project to life.

Engage clearly has the idea of privacy implemented in their services, but kept the privacy of marks limited by, what I can mostly see, *choice*.
Although I havent worked at or seen the insides of engage I have studied the api quite a bit before starting this project. Here are some examples of privacy
being opted on/off:

> ⚠️ Keep in mind that a valid engage session token is needed to preform any of these requests.

#### Privacy OFF:
Request made: POST https://cambridgeschoolportal.engagehosted.com/Services/ReportCommentServices.asmx/RenderPupilMarksheet

> This is the location of marks on the engage server ^

Body of the request: (simplified)
```json
{
  "academicYear": "...",
  "columnList": "...",
  "pupilIDs": "592"
}
```
Now I want to bring your attention to the `pupilIDs` field (which is populated with my pupil ID). I want you to notice that it is a plain number, this plain
number along side other information which I wont dive into, is basically the key to: your grades, name, year and subjects, which isnt necessarily private
information, at least in the eyes of engage.

I proceeded to send many requests to this endpoint with incremental ids till I got the name and IDs of around 1000 people, which again isnt any private
information or hacking, it is just me using publicly available data.

#### Privacy ON:
Request made: POST https://cambridgeschoolportal.engagehosted.com/Services/PupilDetailsServices.asmx/RenderSimpleSection

Body of the request:
```json
{
  "encryptedPupilID": "I am not sharing this :)",
  "sectionType": "whatever"
}
```
I want you to notice now that, the `pupilIDs` field changed to `encryptedPupilID` and so did my willingness to publicly show my encryptedPupilID.
If someone is in possesion of your encryptedPupilID they can see: your adress, age and final report cards (which arent accesible in CSB Open API). Moreover
as suggested by the name, the pupil ID is encrypted, this is also why you shouldnt worry that any of the information listed above being breached. Now
if the information was breached then the action would be classified as hacking!

The question is why did engage make the marks/grades public, as of that I cant answer and your concern should be taken elsewhere. Ultimatelly the decision
was in the hands of the developers/employees of engage on what to make public/private and the marks were made public.

**CSB Open API isnt made by hacking, its made by the manipulation of open data!**

### Can I help with the project?
Sure! We are very excited to welcome anyone with potential value on the team!
To apply/get details go to: https://discord.gg/EmPArQuWfe

### Can anyone see my grades?
No, not anyone can just download the software and see your grades. When CSB Open API is started up, it checks for a valid Engage auth token. What this means
is that to access the public data, you need to have a valid engage account/login, hence you need to be in the school. Keep in mind that the Engage auth token
expires so if you share your token to anyone they will have limited access before the token expires.

# Maintainers:
- [Patrick Adrian Arvatu](https://github.com/Lambels)
