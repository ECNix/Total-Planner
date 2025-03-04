# What is Total Planner?
Total Planner is an Android app which acts a weekly and monthly planner for the user. It allows the user to track a combination of events and tasks. I defined an event as time-boxed occurrence that happens once. A task is a deadline with 0 or more events associated with it. I describe this slightly more thoroughly in my description of data permanence later.

## UI Layout
It has four basic screens:
- Event creation screen
- Weekly view
- Monthly view
- Settings menu

### Event Creation Screen 
This screen lets the user enter a new event or task to add to their planner, which includes a name, description, start date and end date, and a color. It does input validation as the user enters it, which I would probably change now that I've improved as a programmer, so that the error messages only show up after the user tries to submit the information, not immediately after opening the window. This screen is the one which prompted me to write a series of JUnit tests for my date class which represented dates as strings so I could represent it easily in the front-end. It also allows the editing of already existing events.

### Weekly View
This screen shows the seven days of the week and 24 hours a day, with the events represented as carefully positioned interactable boxes within that schedule. It also shows a horizontal line for the current time of day in the same color as the app theme and a horizontal line in either red or the task color (depending on user settings) for deadlines. The user can also navigate to previous or future weeks.

### Monthly View
This screen (Using some algorithms I got from the farmer's almanac online to find the right number of rows and columns and on what day of the week the month starts) represents a calendar view of the month, with the date listed in the top left of each box and the events and deadlines taking place on that date listed inside it. Dates belonging to the previous or next month are in a slightly different color. Like the weekly view, the user can navigate to future or previous months. The goal was to imitate a normal online calendar you'd find anywhere, and I was please with my success in this endeavor.

### Settings Menu
The settings menu includes switches for things like whether to display the time in a 12-hour or 24-hour format, display task deadlines in read or their chosen color like their associated events, and whether to list the date as MM/dd/YYYY or dd/MM/YYYY. These each are implemented in the project and make use of data permanence.

## Data Layout
I wouldn't take my database class until the semester immediately following this Summer, so I had very little knowledge about how to implement data permanence. In addition, I had only begun my software engineering-specific education, so I hadn't been taught some software principles yet and certain methods of product planning which I would learn at Baylor later. This project prepared me for those classes far more than I anticipated.

### SQL Database
My database was simple. It was made of two tables: one for events and one for tasks. Events had an optional foreign key to a task ID to associate them as appropriate. Each table tracked color, the relevant times, the name, and the description. Looking back, I wonder about data reduncancy, but from a high level, I stand by my table layout. I was very proud to teach myself how foreign keys worked and all the relevant sql queries I needed to modify and pull from the database. I accomplished this using the Room API

### Settings
The settings are stored as key-value pairs using the datastore preferences provided by android. They are stored on the device as a form of permanent storage, making sure the behavior described by these settings persists even after restarting the app.

### MyDate
I thought it would be convenient to create my own class which represented a date in terms of strings so I could pass it directly to the elements of the front-end I made, as well as parse those values back out. I don't think I would do that today, preferring instead to keep it in terms of numbers, maybe use a dedicated date API I know how to use from Java if possible since Kotlin run on the JVM, maybe create a specific DateParser class to validate input. All the same, it was a neat little class to implement which required me to look up various farmer's almanac calculations to prove the feasibility of the date and figure out how to implement them on strings.

# Why is Total Planner?
I wanted to work over the Summer between my sophomore and junior year, but I wasn't as ready to live quite so independently as I was the following Summer. My compromise was to make a personal project that would provide a similar amount of experience. Initially, I was going to make a cross-platform app in C++ since I already knew the language, but after I discovered that deployment to Apple devices would require compilation on an Apple computer I didn't have, I decided to make an Android-specific app instead. This worked out perfectly, anyway. It required me to learn a new language, I found a wealth of information on the internet for how to use Android Studio, and the project gave me some experience with self sufficiency in work I value even today.

# What Would I Do Differently?
It took me a long time to start on this project, but once I started, I made excellent progress each day. In fact, I was surprised by how closely I managed to impelement my vision for the project, which I intentionally kept simple. However, I did write this when I was functionally a sophomore, and it doesn't run as well as I would like. If I were to revisit the project, I would see if I could handle the data more efficiently and have pages load faster. I was also daunted at the prospect of bit mapping back then, so I imported someone else's color wheel. While it works, I would love to implement my own so that I can integrate it better with the existing app, my color object, and allow the user to save colors they'd like to use across multiple events so as to better color code.

# What Did I Learn?
This project was completed between my sophomore and junior year of college, so I was sort of an upperclassman who hadn't taken any upper-level courses yet. There are a few notable technical skills I reaped as a result of this project, including:
- Android Development Skills
- Familiarity with the language Kotlin
- An introduction to database development and general data permanence
- How to build a project with Gradle

More valuable than that in certain respects are the personal skills and insights I gained from this project:
- Personal motivation/determination to complete a project
- An ability to manage my time to see that determination through
- The ability to plan a project that is both feasible and effective
