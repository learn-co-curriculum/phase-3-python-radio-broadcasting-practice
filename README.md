# Object Relations Practice - Radio Broadcasting

For this assignment, you will be working with a Radio Broadcasting domain.

We have three models: `Station`, `Program`, and `Broadcast`.

For our purposes, a `Station` has many `Broadcasts`, a `Program` has many `Broadcasts`, and `Broadcast` belong to both `Station` and `Program`.

`Station` - `Program` is a many to many relationship.

**Note**: You should draw your domain on paper or on a whiteboard _before you start coding_. Remember to identify a single source of truth for your data.

## Topics

- Classes and Instances
- Class and Instance Methods
- Variable Scope
- Object Relationships
- lists and list Methods

## Instructions

To get started, run `pipenv install` while inside of this directory.

Build out all of the methods listed in the deliverables. The methods are listed in a suggested order, but you can feel free to tackle the ones you think are easiest. Be careful: some of the later methods rely on earlier ones.

**Remember!** This code challenge does not have tests. You cannot run `pytest`. You'll need to create your own sample instances so that you can try out your code on your own. Make sure your relationships and methods work in the console before submitting.

We've provided you with a tool that you can use to test your code. To use it, run `python tools/debug.py` from the command line. This will start a `ipdb` session with your classes defined. You can test out the methods that you write here. You can add code to the `tools/debug.py` file to define variables and create sample instances of your objects.

Writing error-free code is more important than completing all of the deliverables listed - prioritize writing methods that work over writing more methods that don't work. You should test your code in the console as you write.

Similarly, messy code that works is better than clean code that doesn't. First, prioritize getting things working. Then, if there is time at the end, refactor your code to adhere to best practices. When you encounter duplicated logic, extract it into a shared helper method.

**Before you submit!** Save and run your code to verify that it works as you expect. If you have any methods that are not working yet, feel free to leave comments describing your progress.

## Deliverables

Write the following methods in the classes in the files provided. Feel free to build out any helper methods if needed.

### Initializers, Readers, and Writers

#### Station

- `Station __init__(self, title)`
  - A Station is initialized with a title as a string and title length must be at least 3 characters.
  - A title **cannot** be changed after it is initialized.
- `Station title()`
  - Returns the title of the station

#### Program

- `Program __init__(self, title, category,description)`
  - A program is initialized with a title as a string, a category as a string, and a description as a string.  Title length must be at least 3 characters.
  - The title,category, and description of the program **can** be changed after being initialized.
- `Program title()`
  - Returns the title of the program
- `Program category()`
  - Returns the category of the program
- `Program description()`
  - Returns the description of the program

#### Broadcast

- `Broadcast __init__(self, program,station, time)`
  - A Broadcast is initialized with a program as a Program instance, a station as a Station instance, and a time as a string.
- `Broadcast program()`
  - Returns the program for that given broadcast
- `Broadcast station()`
  - Returns the station for that given broadcast
- `Broadcast time()`
  - Returns the time for that given broadcast

### Object Relationship Methods

#### Broadcast

- `Broadcast station()`
  - Returns the station for that given broadcast
- `Broadcast program()`
  - Returns the program for that given broadcast

#### Station

- `Station broadcasts()`
  - Returns a list of Broadcast instances for the station
- `Station programs()`
  - Returns a **unique** list of Program instances for the station

#### Program

- `Program stations()`
  - Returns a **unique** list of Station instances that are scheduled to broadcast the program

- `Program broadcast_times(station)`
  - Returns a list of strings of the times the program is scheduled to be broadcasted on a particular radio station

### Associations and Aggregate Methods

#### Station

- `Station schedule_broadcast(program, time)`
  - Given a program (as Program instance) and a time (as a string), creates a new Broadcast instance and associates it with that station and that program.
- `Station most_popular_program()`
  - Returns the program that gets broadcasted the most frequently with the given radio station
- `Station program_types()`
  - Returns a **unique** list of strings of the types of programs that gets broadcasted on the given radio station.

#### Program

- `Program loyal_station()`
  - Returns the radio station that broadcasts the program the most frequently

  ## Bonus Deliverable
  #### Station
  - In addition to needing to have a minimum of 3 characters, `Station` title can only have alphanumeric characters


# phase-3-python-radio-broadcasting-practice
