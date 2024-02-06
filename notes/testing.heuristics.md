---
id: 5cyocfv6s094wm6zbjxlo42
title: Heuristics
desc: ''
updated: 1692396122331
created: 1692221597645
---

As with all testing methods and techniques, a deep understanding of what they are, when to apply them, and of their strengths and weaknesses, are essential to be able to use them effectively. Heuristics are no different. You need to apply them knowingly, wisely and carefully. 

As a tester, you’re probably familiar with using heuristics to provide structure to create tests, to generate new test ideas and to explore the boundaries of a system, but have you heard of heuristic praxis? Praxis is what happens when testing theory is applied to testing practice; it's the gap between theory and practice. Theory without practice is hot air. Practice without theory is hollow. The best-equipped testers are those who are well informed and work in the praxis gap.

## Theory Behind Heuristics

Heuristics are simple, occur naturally in the human mind, and are used in everyday life. They’re so simple and ubiquitous that it can cause confusion. The reality is you can have a heuristic technique for almost anything and some will be unique to you.

### Study Of Heuristics

> "Heuristics are principles which reduce the complex tasks of assessing probabilities and predicting values to simpler judgmental operations" - Tversky and Kahneman

In simpler words, heuristics are cognitive shortcuts. We use them under conditions of uncertainty, often automatically without knowing using system thinking, to rapidly solve problems and make decisions. All heuristics are fallible. Under the availability heuristic, people tend to make decisions based on more recent information that is quickly called to mind and the solution you remember easily might not be the optimal solution. 

The unknowing use of any heuristic can lead to systematic errors in thinking known as biases. Biases can have a detrimental impact on you and your testing. For example, under the availability heuristic, if you used a tool successfully in your last few projects, you might want to use it in the next even when there are more suitable tools available.

Despite their fallible nature and the potential biases they cause, heuristics are very useful. It may be impossible or impractical to find the optimal solution to a problem. In these circumstances, we can use heuristics to find solutions that are *"good enough"* to achieve our immediate goal.

### Heuristic Evolution

Heuristics are thought to have been essential during human evolution. The use and development of heuristics are considered to be innate. Some are believed to be *hard-coded* into our brains, serving as adaptive survival mechanisms.

Today, heuristics are just as essential. Humans employ and develop them every day whenever we quickly make judgments or reach decisions without using all the information or computational abilities available to us. Some examples of everyday heuristic techniques that you may recognise are using a rule of thumb, making an educated guess, or following your intuition. Without such heuristics, we’d be unable to function effectively; everyday decisions and judgments would require an exhaustive cost-benefit analysis. 

## Testing With Heuristics

In the world of software testing, we can use heuristics to help us make decisions and solve problems while testing software. They can be particularly useful by offering us suggestions when we're unsure of how to start a testing project or have run out of ideas on what to do next.

Here are three well-known test heuristics used by software testers:

### 1. Goldilocks - Elisabeth Hendrickson

We are all familiar with the story of Goldilocks and the Three Bears, and the Goldilocks heuristic focuses on the concept of "too big, too small and just right" 

When considering the Goldilocks heuristic, testers could think about data entry fields and try testing with data entries that are too big, too small and with entries that are more "typical" for that field and context

### 2. RCRCRC - Karen N. Johnson

The mnemonic RCRCRC will help you remember key words for a test heuristic that could support you with regression testing. It stands for: 

* Recent: Any new code or features were added to your product
* Core: What essential or critical functions or features must continue to work
* Risky: What features or areas of code are inherently more risky, what features do i need to safeguard
* Configuration: What code is dependent on environment settings
* Repaired: What code has been changed to address defects and therefore may have created issues?
* Chronic: What seems to break often (chronically breaking or having issues)

### 3. FEW HICCUPPS - James Bach and Michael Bolton 

FEW HICCUPPS is a mnemonic which may help you remember key words for oracles that could support you with identifying problems in your product. These oracles are particularly useful when a specification is missing or contains inadequate information. It stands for 

* Familiar
* Explainability
* World
* History
* Image
* Comparable product
* Claims
* User Expectations
* Product
* Purpose
* Standards
* Statutes

### More Well-Known Heuristics

Those were just three of many test heuristics that have been shared within the testing community. Del Dewar has kindly collated numerous mnemonics of test heuristics from multiple sources and placed them in this handy mind map.

Note: as many well-known test heuristics use mnemonics, it’s a common misconception to think that heuristics must have a mnemonic or that they’re the same thing. They’re not. Heuristics don’t require a mnemonic, they’ve just been developed this way to aid with memory recall. You can find plenty of well-known test heuristics that aren’t mnemonics in the Test Heuristics Cheat Sheet.

Extra note: A mnemonic is a type of heuristic; they act as a cognitive shortcut to help solve the problem of memory recall. A cheat sheet is a type of heuristic too. Also, a mind map is a type of heuristic… we could go on. Remember, a heuristic can be almost anything. Anything, that acts as a cognitive shortcut in helping you make decisions or solve problems but is not guaranteed to do so and could lead to biases.

Personal Software Testing Heuristics
If you are a practising tester, you will be using your own heuristics - whether you are aware of it or not. This is partly because the use and development of heuristics are intuitive and innate. But, also because everything testers do in software testing could be considered a heuristic. From all the test techniques we use to the next test ideas we come up with during exploratory testing; they’re all born out of cognitive shortcuts that aid us in quickly making decisions and solving problems.

As a tester, you may have a routine that you follow before you start testing, such as opening particular applications. You do this because your experience tells you that you may need them during your testing and that having them open from the start will help you solve the problem of losing your focus mid testing to open them.

It can be hard to identify your own personal heuristics, after all, we often unconsciously develop them based on our experiences using system 1 thinking. The best method to spot them and pull them into system 2 is to reflect upon your actions during and after every testing session. Regular reflection on your testing activities can help you identify patterns in your behaviour and potentially help you identify your personal testing heuristics. These reflections can also help you identify biases.

Heuristic Praxis Gap
A praxis gap occurs when there is an inadequate understanding of the relation between theory and practice. And in the context of test heuristics, a praxis gap happens most frequently when well-known software testing heuristics are routinely applied to test software with little to no thought as to whether the chosen heuristic is helping the tester solve their problems, or make suitable decisions.

Heuristic praxis gaps can also arise when practising testers develop effective heuristics without realising it. You may be wondering where’s the issue here? But, without awareness, testers are unable to justify their decisions and are open to the biases heuristics can cause. Sadder still, many awesome test heuristics are not shared with the testing community that could help advance our profession.

Finally, a heuristic praxis gap can happen when a tester understands the theory behind a heuristic but is unaware of how to apply it effectively to their testing practice.

Filling the Gap
Praxis only happens when theory is applied to practice. To fill the gap you must learn the theory behind heuristics, learn some well-known test heuristics and practice applying them thoughtfully. 

To learn the theory, read blogs and books on heuristics, watch talks and have discussions with other software testers on when and how to apply them. Have these discussions in person, on forums, on slack, social media, wherever. The more people you talk to the better.

Once you’ve learnt all about heuristics, it’s time to practice applying them in different contexts. Importantly, you should reflect upon their efficacy; what worked, what didn’t and why. If a heuristic is not working for you, try another, modify it or make your own.

Modify Heuristics
Don’t be afraid to skip parts of a well-known test heuristic that’s not quite working for you. You might not get value from using a heuristic in its entirety, so go ahead and just use part of it. Use what works for you in your context and drop what doesn’t.

Another option is to add to a heuristic. For example, you may forget the words for RCRCRC. Richard Bradshaw does this regularly and mentions ‘Revenue’ as one, it isn’t one, but nevertheless, it’s provided him with lots of test ideas in the past. Revenue encourages him to think about the parts of a system that generate the business revenue, no revenue, no business. So, for him, RCRCRC has become RCRCRCR. 

Even the creators of well-known heuristics change them, FEW HICCUPS started out as just HICCUPS, then Michael Bolton added the FEW to it. So if the creators are changing them, why not create your own oracles that focus on consistency criteria? Michael even encourages you to.

You can get really creative when you start mixing heuristics. John Stevenson introduced this idea at TestBash Brighton with his fantastic talk on breaking model fatigue. John encourages us to SCAMPER existing models; Substitute, Combine, Adapt, Modify, Put to another use, Eliminate and Reverse them. Try experimenting with different combinations and alterations of well-known test heuristics and see what brings you value. 

Note: Models are a type of heuristic, they’re a method of trying to solve the problem of making complicated or abstract things simpler and easier to understand.

Make Your Own
The first step in realising and developing your own test heuristics is to identify where you are already using them. This is a very difficult process. We’re used to explaining what we’re doing, but we find the why significantly harder to articulate, but the ‘why’ is where the heuristics are hiding. Here are a few methods we can use to reveal them.

Reflection
Reflecting on your testing activities can often reveal patterns, those patterns are probably the result of applying heuristics. Reflecting regularly during and after every test session will increase your chances of identifying heuristics. For example, you could spend a few minutes after each testing session asking yourself “why did I do the tests that I did?” and, “why did I do them in that order?” Taking good testing notes can aid you with reflection, you may spot patterns as you are taking them and when you review them.

Verbalising
Another way to identify and make your own heuristics is to verbalise your testing activities to others. The process of verbalisation encourages reflection, as you search for the words to share and think about explaining what you’re doing or have done. When discussing decisions with others we often reveal subtleties we were not aware of and make new connections between thoughts and ideas when we’re describing them. You can verbalise your testing activities and decisions with a team member, perhaps in a testing debrief session or during a pairing session. Alternatively, you could verbalise them to yourself using the rubber duck heuristic. 

Teaching
Teaching is where Richard Bradshaw has had the most joy in realising his own heuristics. To teach others well, you need to fully understand your own actions when practising the subject being taught. This means lots of thought and reflection on your testing practice to identify what needs to be taught and even more importantly on how to teach it. Working out how to teach testing knowledge and skills is where Richard has created and shared most of his own heuristics to aid his teaching. For example, the SACRED model was designed to teach people about automated check design and TRIMS was created to encourage people to think about their automation strategy.

Putting Theory Into Practice
Heuristics are powerful, even more so when you’re fully aware of them, understand them and can apply them thoughtfully during your testing sessions. In other words, heuristics are most powerful when you use heuristic praxis.

After practising using different heuristics in different contexts, you will develop great judgement to know which heuristic to apply and when. From reflecting deeply on your testing practice through note-taking and verbalisation you will be able to modify existing heuristics to better suit your needs and perhaps even identify your own.

We encourage you to go ahead and change well-known test heuristics and to develop your own. We would love to hear your stories on remixed and new heuristics on The Club.

