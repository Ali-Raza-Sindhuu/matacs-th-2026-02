# AI Proposal Triage - Design Write-up

# 1 >> AI vs Rules:

I would use AI in my workflow to speed up tasks that would take more time to handle using traditional code, such as extracting facts and important requirements from proposals. Every contractor writes their proposal differently, so AI can analyze the text and extract the required information more easily.
Secondly, I would use AI to explain the final scores in simple language because writing fixed rules to generate human-readable explanations for different situations would require more code.
For mandatory requirements, I would use code to check whether the information extracted by AI meets the required conditions. Code would also verify the evidence, calculate scores, and rank proposals based on those scores. I chose code for these tasks because they require accuracy and consistency, while AI-generated results may sometimes vary.
Finally, the award decision would be made by a human reviewer. The purpose of our system is to analyze each company's proposal, highlight its experience and achievements, and help the reviewer make an informed decision.

# 2 >> Consistency and Explainability:

I would use predefined formulas in code to make the scoring consistent across all proposals, so the calculation process remains the same for every contractor. If we use AI for scoring instead, the results may vary even when evaluating the same proposal.
To make the results explainable, I would use a table to show all the information extracted by AI from each proposal, along with the supporting evidence, scoring formulas, calculated scores, and final rankings. This would help the reviewer understand how each contractor received their score and why they ranked in that position.
I would also save the verified extracted data and criteria so that scoring the same proposals again would produce the same results.

# 3 >>  Human in the Loop:

I would add a human review step so that the reviewer can check whether the information extracted by AI is correct or not. If the reviewer finds any incorrect information, they can edit the extracted data or override the results with a valid reason.
I would also maintain an audit log to keep track of all changes made in the system. It would store the reviewer's name, date and time, previous and updated values, and the reason for each change. The system would also record the criteria used, calculated scores, and final decision.
This would help us understand who made changes and why. The final award decision would always remain with the human reviewer.

# 4 >> Changing Criteria:

I would store the previous results and recalculate the scores using the newly updated criteria and weights. The system would keep both the old and new results so that the reviewer can compare them and understand what changed, where the differences occurred, and why.
I would also maintain different versions of the criteria so that previous results are not lost. If the required information is already extracted, the system can reuse it without calling AI again. However, if a new criterion requires additional information, AI would extract that information from the original proposal.

# 5 >> Risks and Safeguards:

One major risk is that AI could make mistakes while extracting facts or important information required for scoring. Another risk is that a human reviewer might accidentally enter incorrect information while correcting the extracted data. Repeated AI calls could also increase costs, especially when the admin frequently changes the evaluation criteria.
To prevent these issues, I would first identify the information required by the selected criteria and then use AI to extract only the relevant facts from each proposal.
For verification, I would show the AI-extracted information alongside the original proposal, highlighting the section where each fact was found. This would allow the reviewer to compare the information and correct any mistakes. I would also validate manual changes before saving them.
To reduce API costs, I would limit unnecessary AI calls and store the extracted information so it can be reused when criteria or weights change. AI would only be called again if additional information needed to be extracted.
I would also treat proposal content as untrusted data and flag any instructions attempting to manipulate the AI or influence the ranking.