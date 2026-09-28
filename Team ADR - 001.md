# Team ADR - 001

One architecture decision record for one real decision your team has made.
You are each writing an ADR for your own solo app at IAP M4. This is the team version, and the difference matters: this one had to be agreed. An ADR that four people signed off on is a different artifact from one you wrote alone, and the alternatives section should show that more than one position was actually in the room.

What to submit
ADR-001 as markdown committed to the team repository, with context, the decision, alternatives considered, and consequences. Submit the repository URL or a direct link.
Django makes many decisions for you, which narrows the field but does not empty it. Where you put business logic, how you handle authentication, what your app boundaries are, whether you use the ORM directly or behind something — these are all live decisions inside a Django project.

### Context





### Alternatives
- One alternative taken was the web page indicating whether ‘’ Down’’ or ‘’Up’’. Such as a question ‘’ Is this web page down?’’’ and a check mark with either green or red or yellow. This alternative was not chosen because it provides limited information and does not explain the cause of an outage or incident updates. 

- The second alternative considered was a service status page similar to Steam's. Steam status pages can display a large amount of information about different services, such as population, multiple services, regional server status, server load, user activity, and graphs. However, this approach was not chosen because it includes more information and features than our project needs. 





### Consequences 






Rubric , Criterion , Pts

Context establishes the forces that made a decision necessary - 2

The decision is stated unambiguously - 2

At least two genuine alternatives, each with the reason it was not chosen - 3

Consequences name what is now harder, not only what is now easier - 2

Committed as markdown in the team repository - 1





