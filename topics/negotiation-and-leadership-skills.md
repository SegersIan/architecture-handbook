# Negotiation and Leadership Skill

These are hard skills to obtain. This topic cannot make you an expert overnight, the techniques introduced here are a good starting point for gaining these important skills. The reason we cover these skills is because a Software Architect must understand the political climate of the enterprise and navigate the politics. 

Reason being that almost every decision will be challenged. Developers that think they know more than the architect on a particular part, other architect who think they have a better approach, or business stakeholders that consider your decision to be too expensive. Your goal is not to go to war, but to find the best outcomes for the organization.

## Negotiation and Facilitation
Costs can be a deal breaker. You might need to hone your story and understanding to justify the cost. Else you might need to find alternatives that work better cost wise. Usually it is not binary a negotiation, but a conversation to find common ground and work within its boundaries. Remember, it's always about trade-offs.

**GENERAL TIP: Leave your ego at the door**

### Negotiating with Business Stakeholders

* **TIP: Leverage the use of grammar and buzzwords to better understand the situation**
    * Don't ignore the buzzwords or nonsense grammar, these give tremendous insights on what the concerns are from the business stakeholders, this allows you to better understand the real concerns. You can also use the same grammar and buzzwords to ask follow-up questions.
        * "I needed it yesterday" : Time To Market matters.
        * "It must be lightening fast" : Performance matters.
        * "I want 8 nines availability" : Availability matters.
* **TIP: Gather as much information as possible before entering into a negotiation**
    * This allows to navigate the negotiation in a constructive dialog. If you know the stakeholder mentioned they want "8 nines", have a table ready with the uptime percentage and the downtime per year/day which can help the stakeholder reflect the difference between 3 and 8 nines. Help them understand what they're really asking.
    * Having information at your finger tips allows for a constructive dialog. Do make sure to steer it in such a way.
* **TIP: When all else fails, state things in terms of cost and time**
    * This should be a last resort, starting of with "that's too expensive" can start of a negotiation of the wrong foot.
    * Ideally cost and time are considered once an agreement is reached and if they are relevant.
* **TIP: Leverage the "divide and conquer" rule to qualify demands or requirements**
    * Break down the demands or requirements, or consider adjusting scope.
    * Maybe the 8 nines are only relevant for a part of the system.

### Negotiating with Other Architects
Between architects the seniority can be in the way (ego), competitiveness, too argumentive, and could easily get personal. Some tips to deal with such situations.

* **TIP: Always remember that demonstration defeats discussion**
    * Every situation is different, just "googling it" doesn't exist, so every system is different.
    * Run a comparison between the competing options and show the results. 

* **TIP: Avoid being too argumentive or letting things get too personal in a negotiation - calm leadership combined with clear and concise reasoning will always win a negotiation.**
    * If things get too heated, park the discussion and come back at it later when all parties have calmed down.

### Negotiating with Developers
Don't leverage your title as architect to tell others what to do. Work with them and gain respect. Development teams can feel disconnected from architecture or the architect. As a result they feal out of the loop with regard to decisions that impact them. This is the manifestation of the **Ivory Tower Anti-Pattern**.

* **TIP: When convincing developers to adopt an architecture decision or to do a specific task, provide a justification rather than "dictating from on high".**
    * Developers care about "why", they don't like to be "just told what to do", you (as an architect) probably doesn't like it either.
    * Use of language: Don't use compelling speech (e.g. "You MUST...")

* **TIP: If a developer disagrees with a decision, have them arrive at the solution on their own.**
    * Tell the developer take their choice if they can "show" or "validate" (don't say proof) that their options does tackle concerns.
    * Example: The team will use Framework X if they can show how to address the security requirements"
        * Either the developers fails to show/validate this, so they come to their own conclusion, so you win their buy-in. That's a win.
        * Either the developers succeeds to show/validate this, that is still a win, the architect learns also something new, and the original concerns are addressed, so Framework X DOES seem to be the better option.

## The Software Architect as a Leader

todo...

## Integrating with the Development Team

todo...

## Resources

* [Fundamentals of Software Architecture](https://fundamentalsofsoftwarearchitecture.com/) - Chapter 23