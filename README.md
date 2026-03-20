# thm-missing-person-osint
TryHackMe Missing Person OSINT Challenge Writeup (Hints Only)



TryHackMe – Missing Person (OSINT) Writeup

This is a classic OSINT challenge. Hint: social media platforms are very important here.

Overall Strategy

You have:

Image 1 → Restaurant (Mexican place)

Image 2 → MotoGP circuit

Message clue → DJ + cave + after party

Your job is to extract metadata, visual clues, and online traces.


===================================================
Task 1: Analyze the MotoGP Image (Location Identification)
What you see:
<img width="1920" height="1080" alt="SS1 task 1location" src="https://github.com/user-attachments/assets/3b04d284-d9b0-4a0e-ad13-658568e7c6a0" />

“PERTAMINA” sign

Race track

Motorcycle (MotoGP)

Tools to use:

Google Images (Reverse Search)

What to do:

Upload the MotoGP image to Google Images

Try keywords:

Pertamina MotoGP circuit

Pertamina track location

MotoGP Indonesia circuit



===================================================
Task 2: Find Event Date

Now that you know the circuit:
<img width="1920" height="1080" alt="SS task 2 date" src="https://github.com/user-attachments/assets/b46dc3db-d41a-47cb-860b-6e0222106f8f" />

Search:

Mandalika MotoGP 2025 date

This gives you the event date range.

Format required:

DD-DD/MM/YYYY


===================================================
Task 3: Restaurant Name

Use Google Images again.

The restaurant image gives strong visual clues.

Hint:

Identify cuisine style from decorations

Use reverse image search (crop the image for better results)

Combine with location from previous questions


===================================================
Task 4: Photo Timestamp
Question:
<img width="1920" height="1080" alt="SS 3 exiftool food jpg" src="https://github.com/user-attachments/assets/0c157a78-28ca-4f29-ab88-6928d3aa9c83" />
<img width="1920" height="1080" alt="SS4 exiftool moto" src="https://github.com/user-attachments/assets/933d3ed6-0ef3-4e11-919f-0fb0c4fdd772" />

At what time was this photo taken?
Format: HH:MM:SS

Method: EXIF Data (Best and Fastest)

Images often contain hidden metadata called EXIF metadata.

This includes:

Date

Time

Camera

GPS (sometimes)

If using Kali Linux:

Run:

exiftool image.jpg
What to look for:
DateTimeOriginal : YYYY:MM:DD HH:MM:SS

Extract only:

HH:MM:SS
If not using Kali:

Use online tools:

Exif Viewer

Metadata2Go

Find:

DateTimeOriginal

CreateDate


===================================================
Task 5: Bar Location
Question:

What is the full address of the bar’s location?

What you know:

From the message:
“Went to this cool MotoGP after party… local DJ…”

Location is near the circuit

Event is MotoGP after party

Clue is a local DJ

Goal:

Find bar name, then full address.

Step 1: Use Social Media

Search:

Mandalika MotoGP party Lombok

Kuta Lombok DJ night MotoGP

What to look for:

Event posters

DJ names

Tagged bar locations

Step 2: Identify the Bar

Event posts will mention:

Bar name

DJ name

Step 3: Get Full Address

Search the bar on Google

Open in Maps

Copy full address exactly

Hint:

Focus on:

Kuta Lombok nightlife

Bars hosting MotoGP parties

Places with DJ events



===================================================
Task 6: DJ Name

Hint: You will get three DJs. One is correct. Verify using flag and location.

Hint 2: Check the bar’s official Instagram handle.

What you know:

Bar: Surfers' Bar (Kuta Lombok)

Event: MotoGP 2025

Context: After party

Clue: Local DJ

Step 1: Find Event Evidence

Search:

Surfers Bar Lombok MotoGP party DJ

MotoGP Lombok after party Surfers Bar DJ

Look for:

Instagram posts

Event posters

DJ lineups

Step 2: Use Instagram

Search Surfers Bar Lombok

Check posts and tagged posts

Focus on October 2025

Step 3: Identify the DJ

Look for:

DJ names

Tagged profiles

Event captions
Step 4: Verify Local DJ
Check DJ profile
Confirm location (Lombok/Indonesia)



===================================================
Task 7: Cave Identification
This was the most difficult part.
Question:
What cave does the DJ take tourists to?
What you have:
DJ identified
Instagram highlight: “thekebon”

Steps:

Search:
the kebon lombok
Identify the place:
A tourist or hospitality location
Connect:
This place is linked to tours
Search:
cave near the kebon lombok
Key Clues:
The cave is a popular tourist location
Near Kuta Lombok
Close to Mandalika
Frequently visited with guides
Appears in travel blogs and Google Maps
Note: There are only a few famous caves in the area. Narrow it down accordingly.



===================================================
Task 8: Phone Number
Question:
What number did the DJ list for his tour business?
Format: Full number, no country code

What you know:
DJ
Instagram
Google Maps link

Step 1: Check Instagram Bio
Look for:
Phone number
WhatsApp link
Contact info

Step 2: Check Google Maps
Open link from bio
Scroll for contact info

Important:
Do not include country code (+62)
No spaces
No dashes

Final Hint:
Use Facebook.
Search using cave name + DJ
Find the official Facebook page related to the tour business
Extract phone number from there

Conclusion
This challenge shows how small pieces of information can be connected using OSINT techniques.

Key takeaway:
Follow the chain — image → location → social media → business → contact info.
