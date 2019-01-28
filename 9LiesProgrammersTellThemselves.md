LINK:http://www.infoworld.com/article/3184495/application-development/9-lies-programmers-tell-themselves.html

# 9 lies programmers tell themselves

## Confidence in our power over machines also makes us guilty of hoping to bend reality to our code

Programmers have pride with good reason. No one else has the power to reach into a database and change reality. The more the world relies on computers to define how the world works, the more powerful coders become.

Alas, pride goeth before the fall. The power we share is very real,but it’s far from absolute and it’s often hollow. In fact, it may always be hollow because there is no perfect piece of code. Sometimes we cross our fingers and set limits because computers make mistakes. Computers too can be fallible, which we all know from too much firsthand experience.

Of course, many problems stem from assumptions we programmers make that simply aren’t correct. They’re usually sort of true some of the time, but that’s not the same as being true all of the time. As Mark Twain supposedly said, “It ain’t what you don’t know that gets you into trouble. It’s what you know for sure that just ain’t so.”
Kevin Deldycke’s GitHub-hosted list of falsehoods that programmers believe is a good example of how disconnected cyberspace can be from reality. It’s a compendium that will only grow as others contribute their war stories. Consider it a good kick in the pants itemizing a thousand examples that say, in essence, “Remember, Caesar, thou art mortal.”

My favorite may be the list of falsehoods about phone numbers. If you think that saving a phone number for a person is as simple as putting seven or maybe 10 digits in a database, you’re mistaken. That works until it doesn’t because there are country codes, abandoned numbers, and more than a dozen gotchas that make it hard to do a good job keeping a list of phone numbers. Is it any wonder that there’s a smug smile of satisfaction on the faces of the Luddites who keep their phone lists in a little black book?

Here are a number of false beliefs that we programmers often pretend are quite true.

## 1. - Questions have one answer

The database table is filled with columns, and each column has an entry or it doesn’t. It’s either full or null. What’s so hard about matching up an answer for every question?

Alas, sometimes there is more than one answer, then the table starts to fail. Maybe a person has more than one telephone number or a second weekend home. Database designers figured out some of the solutions to this by creating one-to-many and many-to-one mappings that can store multiple answers. Some of the more modern NoSQL solutions use a “document” model that lumps together all of the possible answers with different tags in one big soup.

These solutions are better, but even they have limits. Sometimes answers are valid only for a short window of time. A parking spot may be legal except during rush hour between 4 p.m. and 6 p.m.
If you think it’s enough to add one slot to the table to handle a window for each day, remember that sometimes there are several exceptions like 7 a.m. to 9 a.m. and 4 p.m. to 6 p.m. But don’t keep track of the time of day simply because the parking rules are often different on weekends, but then the definition of weekends changes. Parking is free in the District of Columbia on Sundays—but not Saturdays. Federal holidays are different too, and so are local ones.

Those are times only. The list of potential exceptions goes on and on making it impossible to imagine that a database will ever model reality by storing the absolute and final answer for any question no matter how simple.

## 2. - Null is acceptable

Sometimes I think that half of the Java code I write is checking to see whether a pointer is null. When I’m feeling aggressive, I try to draw a perimeter around my library and test for null only at the entry methods, those locations where the API is open to the rest of the code. That simplifies things for a bit, but eventually I want to reach into the library and use a small method that’s sitting there. Oops. Now it needs to test for nullity and the perimeter has been breached. So much for building a wall.

Figuring out how to handle this issue is a big problem for modern language design. The clever way some languages use a question mark to check for nullity helps, but it doesn’t get rid of the issue. Null simply makes object-oriented programming much more confusing and prolix.

## 3. - Human relationships can be codified

When gay marriage was legalized, one smart database administrator recognized that this was much bigger than the Y2K problem, which had almost paralyzed the country by asking the programmers to go back and add two new digits to the year. To solve this, the DBA considered how to handle the challenge with 14 progressively more accommodating database schema, each more elaborate than the last. In the end, he concluded, “Perhaps the simplest solution would be to ban marriage outright.”

But tracking who is married to whom is only the beginning. Imagine you’re building a database table for a school for determining which adult can pick up a kid after school or maybe make a decision about administering aspirin. Sure, the birth mother is easy, but what about the stepparents? What about the step older sibling who’s back from college break and definitely remembers meeting the kid at their parents’ wedding last summer, at least before the bar opened?

You might be tempted to pull a Facebook and punt with an “it’s 
complicated” entry, but you can’t. These are legal questions that can produce lawsuits if the code isn’t accurate. By “accurate,” I mean conforms to the law, and we all know how accurate Congress can be when writing laws. But forget about blaming Washington. The kid needs aspirin. What will your database say?

## 4. ”Unicode” stands for universal communication

There’s an earnest committee that meets frequently trying to decide which emojis should be included in the definitive list of glyphs that define human communication. They also toss aside certain emoji, effectively denying someone’s feelings.
The explosion in memes shows how futile this process can be. If the world finds emojis too limiting, spurring them to turn to mixing text with photos of cultural icons, how can any list of emojis be adequate?

Then there’s the problem of emoji fonts. What looks cute and cuddly in one font can look dastardly and suspect in another. You can choose the cute emoji, and your phone will dutifully send the Unicode bytes to your friend with a different brand phone and a different font that will render the bytes with the dastardly version of the emoji. Oops.

## 5. Numbers are accurate

As I type this, snow is falling across the Sierras from one of the biggest storms in some time. When I looked at the weather today, it looks sunny and cool, a perfect day for skiing. But some of the slopes are closed. Why? The new snow might bring avalanches, and the slopes can’t be opened until the crew clears the danger with explosives.

The basic numbers from the weather report (temperature, cloud cover, humidity) don’t capture some of the special details. Avalanche scientists have more complicated models that do a good job of predicting when the snow will tumble, but the reality is that numbers tell only part of the story. This is why the ski companies send out teams to trigger potential avalanches just in case.

The computer industry’s infatuation with numbers has only gotten deeper as the buzzwords “big data” get more popular. The hard disks are filled with trillions of numbers, so there should be algorithms that can extract something intelligent from all of these numbers.

In reality, numbers tell only very specific things. They’re often quite useful, but they’re far from completely accurate.

## 6. Human language is consistent

One of the ways that developers punt is to put in a text field and let humans fill it with whatever they want. The open-ended comment sections are made for humans and rarely interpreted by algorithms, so they’re not part of the problem.

The real problem resides in structured fields with text. When my GPS wants me to choose a road named after a saint, it tells me to “turn onto Street Johns Road.” Road names with apostrophes also throw it for a loop. It’s common to see “St. John’s Road” spelled as “Saint Johns,” “St. Johns,” “Saint John’s,” and even the plural form: “Saint Johns.” The U.S. Post Office has a canonical list of addresses without extra characters, and it maintains an elaborate algorithm for converting any random address into the canonical form.

## 7. Time is consistent

It may feel like time keeps flowing at a constant rate—and it does,but that’s not the problem for computers. It’s the humans that mess up the rules and make a programmer’s life nasty. You may think there are 24 hours in every day, but you better not write your code assuming that will always be true. If someone takes off on the East Coast of the United States and lands on the West Coast,that day lasts 27 hours.

Time zones are only the beginning. Daylight saving time adds and subtracts hours, but on weekends that change from year to year. In 2000 in the United States, the shift occurred in April. This year, the country changed clocks on the second Sunday in March. In the meantime, Europe moves to “summer time” on the last Sunday in March.

If you think that’s the end of it, you might be a programmer tired of writing code. Arizona doesn’t go on daylight saving time at all. The Navajo Nation, however, is a big part of Arizona, and it does change its clocks because it’s independent and able to decide these things for itself. So it does.

That’s not the end. The Hopi Nation lies inside the Navajo Nation, and perhaps to assert its independence from the Navajo, it does not change its clocks.

But wait, there’s more. The Navajo have a block of land inside the Hopi Nation, making it much harder to use geographic coordinates to accurately track the time in Arizona alone. Please don’t ask about Indiana.

## 8. Files are consistent

It seems that merely remembering the data should be something a computer can do. We should be able to recover the bits even if the bits are filled with many logical, stylistic, orthographic, numerical, or other inconsistencies. Alas, we can’t even do that.
Whenever I ask my Mac to check the file system and fix mistakes, it invariably tells me about a long list of “permissions errors” that it dutifully repairs for me. How did the software get permission to change the permissions for access to my files if I didn’t give permission to do it? Don’t ask me.

The problems go deeper. About every six months, the built-in Mac backup software called Time Machine announces that the backup copy of everything has become corrupted and the only way to fix it is to rebuild the entire thing. Quick, though, before the main computer explodes and all the data is lost.

These are only two examples of how file systems don’t honor the compact between user (the person supplying the electricity) and the machine (desperate needer of electricity). Any programmer will tell you there are hundreds of other examples of situations where files don’t contain what we expect them to contain. Database companies are paid big bucks to make sure the data can be written in a consistent way. Even then, something goes wrong and the consultants get paid even more money to fix the tables that have gone south.

## 9. We’re in control

We like to believe that our instructions are telling the computer what to do and that arrogant pride is generally true except when it’s not.
What? Certainly that may not be true for the average nonprogramming saps, unwashed in the liniment of coding power, but not us, wizards of logic and arithmetic, right? Wrong. We’re all powerless beggars who are stuck taking whatever the machines give us. The operating system is in charge, and it may or may not let our code compute what it wants.

OK, what if we compile the Linux kernel from scratch and install only the code that we’ve vetted? Certainly we’re in control then.

Nope. The BIOS has first dibs over the computer, and it can surreptitiously make subtle and not-so-subtle changes in your code. If you’re running in the cloud, the hypervisor has even more power.

OK, what if we replace the BIOS with our own custom boot loader? You’re getting closer, but there’s still plenty of firmware buried inside your machine. Your disk drive, network card, and video card can all think for themselves, and they listen to their firmware first.

Even that little thumb drive has a built-in processor with its own code making its own decisions. All of these embedded processors have been caught harboring malware. The sad fact is that none of the transistors in that box under your desk report to you.