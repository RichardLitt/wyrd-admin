*      Person  
 * The user. Can become complex. Eventually: profiles, team membership, etc. 
*      Agent
 * When you need confirmation form a certain person - that can be modelled as a class. May be later down the road. 
*      TimeSpan
 * Similar to instant, takes care of time-zone information, task independent. Possible repeated. 
*      Resource
 * Abstraction for time, people, things you need for a specific task. 
*      Goal
 * Goals are high-level - you may not know how to achieve. These are currently _projects_ in Wired In. Can be embedded. 
*      Plan
 * Common sense knowledge of how to achieve a task. If you have a goal for learning python, the plan is to read the documentation, for instance. Motivated by theory of scripts and human behaviour. 
*      Task
 * Subtasks, various tasks, projects, etc.  
*      State
 * Subtype of goal, but don't have to be. 'Have a flat'
*      Event
 * Subtype of event, but not necessarily. 'Buy potatoes.' Events enable states...?
*      Deadline
 * Uses an instant. Soft or hard. 
*      [Penalty]
*      Instant
 * A specific time. 
*      Scheduler
 * Main processor for scheduling the class. Can be done in different ways. 
*      WorkSlot
 * A timespan that is specific to each task. From start() to end(), basically. 
*      Day
*      WorkDay
*      WeekendDay
* Focus
 * Attribute of workslot, user-decided.
* Contentment
 * Attribute of workslot, user-decided.
* Comment
 * Can be longer than 140 characters...
* Holiday
* Thursday
 * Time which is set aside for non-work. Attribute of day, timespan? Possibly also subclass of day. Could be a special kind of empty task. 
* DeadHours
 * Basically the same as Thursday, but for hours and not days.
* Showtime (only show from 5pm on, for instance)
 * I don't want to see tasks if I don't have the appropriate trigger, or in advance of the time when I would have to do them (like going to a class). This should be a property of a task. 
* Timezone
* Worth
 * Property of task

And one more note -- enumerating useful classes is the smaller part. It
will  be  more  work  to  design  protocols  for  their  relations  and
interactions  (including  relations  such  as:  Person  is-a  Resource,
TimeSpan  is-a  Resource,  Goal  can  be  a  State  or  an  Event;  and
interactions such as: when a Goal  is  created,  it  tries  to  suggest
a suitable Plan; or Scheduler looks at a set of  Tasks  and  Resources,
and then returns an ordered list of some of the Tasks).

Notes
------

* Should alert you when you have too many tasks
* Shouldn't show more than one or two tasks at a time
* Wyrd In needs to organise the tasks
* If deadlines will be missed, the user is warned. 
* Should be able to computer actual work time that you can do, and how much you'll be able to manage in a given time. 