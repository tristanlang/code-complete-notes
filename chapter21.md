### Chapter 21: Collaborative Construction

#### 21.1 Overview of Collaborative Development Practices
* The primary purpose of collaborative construction is to improve software quality
* Pair programming reduces development time by 45%
* Formal reviews have a massive effect on development time

#### 21.2 Pair Programming
* One developer codes and the other watches for mistakes, thinks strategically about how the code is being written, and makes sure the right code is being written
* The person without the keyboard should be an active participant in the programming
* Rotate pairs and work assignments regularly
* The readability and understandability of the code tends to rise to the level of the best programmer on the team
* Pairs tend to write code faster and with fewer errors

#### 21.3 Formal Inspections
* Focus is on defect detection, not correction
* Distinct roles are assigned to all participants
  * Moderator: keeps the inspection moving along to be productive, but slowly enough to find the most errors possible
  * Author: the person who wrote the code plays a minor role, to ensure that the design or code speaks for itself
    * Author is assigned the job of making it clearer if it is unclear
  * Reviewer: anyone who has a direct interest in the design or code who is not the author
    * Usually finds defects during preparation and considerably more during the discussion during inspection
  * Scribe: records errors that are detected and the assignments of action items
  * Management: should not be involved because these reviews should be strictly technical
* Minimum of 3 people for an inspection: moderator, author, reviewer
* Maximum of 6 people

##### General Procedure for an Inspection
* Planning
  * moderator decides who will review the material and when and where the inspection meeting will occur
  * moderator then distributes the design or code and a checklist that focuses the attention of the inspectors
* Overview
  * design or code should speak for itself; the overview shouldn’t speak for it
* Preparation
  * each reviewer works alone to scrutinize the design and code for errors
  * Use the checklist to stimulate the review
* Inspection Meeting
  * The moderator chooses someone other than the author to paraphrase the design or read the code 
  * All logic is explained, including each branch of each logical structure 
  * Scribe records errors as they are detected
  * Discussion of an error stops as soon as it is detected
  * The author should acknowledge each alleged defect and move on 
  * Don't discuss solutions to the defects
  * Meeting generally should last no more than 2 hours
* Inspection Report
  * Moderator produces an inspection report that lists each defect, its type, and severity
  * Serves as a checklist that ensures all defects will be corrected
  * This will be helpful when explaining to management the efficacy of inspections since you can refer to time spent and number of errors found
* Rework
  * Moderator assigns defects to someone, usually the author
* Follow-Up
  * Depending on the number of errors found and the sever- ity of those errors, you might follow up by having the reviewers reinspect the entire work product, having the reviewers reinspect only the fixes, or allowing the author to complete the fixes without any follow-up
* Third-Hour Meeting
  * Optional meeting after inspection ends to allow parties interested to discuss solutions

#### 21.4 Other Kinds of Collaborative Development Practices
* Walk through
  * Differs from inspection because it is usually hosted and moderated by the author
  * Usually 30-60 minutes
  * Still focuses on error detection not correction
  * Less effective than formal inspection because if you're going through the trouble of having a meeting, you may as well use the most effective error detection structure
  * Inspections are more focused
* Code reading
  * Read source code and look for errors
  * Usually involves 2+ people reading code independently and meeting with the author to discuss it
  * Between 1000-10,000 lines of code
  * Discussion meeting focuses on problems found, not going line by line through the code
  * Focuses more on the individual reading than the meeting, as compared with walk throughs 
* Dog and pony shows
  * Product demo with customer
  * May include code review
