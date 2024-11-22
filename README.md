# Zapier-Lead-Scoring-Workflow
# Zapier Lead Scoring Workflow

## Overview
This repository contains a guide and resources to implement a lead scoring system using Zapier, Google Forms, Google Sheets, and Gmail.

## Features
- Automatically capture leads from Google Forms.
- Assign scores based on custom criteria.
- Filter high-scoring leads and send personalized emails.
- Track low-scoring leads for nurturing campaigns.

## Setup Instructions
1. Create a Google Form with the following fields:
   - Company Size
   - Budget
   - Industry
   - Urgency
2. Set up a Google Sheet for lead tracking (template included).
3. Configure the Zapier workflow as outlined in this guide.

## Resources
- [Google Sheet Template](.[/GoogleSheet-Template.xlsx](https://docs.google.com/spreadsheets/d/1WQ8CcqqpHhmGe9qvvp_K4yrbcVXF5slefSRwgssdkr8/edit?usp=sharing))
- https://docs.google.com/spreadsheets/d/1zUO6D8UUAZ0FAGL1JEoyBCdbvFJbCHVpQM__Nnptp30/edit?usp=sharing
- https://docs.google.com/forms/d/1aijjilxvR8z7uK9NbcfyAmWs_9kp80m0BAzb0xm8MqA/prefill
- Screenshots:
  Solution for TechNova Solutions' Lead Management Workflow Challenge
Here’s a detailed step-by-step guide to implementing the solution using Zapier and the free tools mentioned.
________________________________________
Preparation Steps
1.	Set Up Google Form:
o	Create a form with the required fields: Company Size, Annual Budget, Industry, Urgency of Need, and optionally, a Comments field.
o	Link the form to a Google Sheets spreadsheet to collect responses.
2.	Set Up Zapier:
o	Create a Zapier account (free plan if within limits).
o	Connect necessary apps: Google Forms, Google Sheets, Gmail, and Google Calendar.
________________________________________
Implementation: Task 1
Step 1: Trigger for New Form Submission
1.	Create a New Zap: 
o	Trigger: Google Forms → New Response in Spreadsheet.
o	Select the Google Sheet linked to your Google Form.
Step 2: Calculate Lead Score
1.	Add a Zapier Formatter Action: 
o	Action Event: Numbers → Perform Math Operation.
o	Use the scoring logic to assign points based on responses. Example: 
	Create separate Formatter steps to translate responses (e.g., "201-1000 employees" = 30 points).
	Sum these scores in another Formatter step.
Step 3: Add Lead to Spreadsheet
1.	Add a Google Sheets Action: 
o	Action Event: Create Spreadsheet Row.
o	Select the destination Google Sheet.
o	Include lead details and calculated score.
Step 4: Conditional Welcome Email or Nurturing
1.	Add a Filter Action: 
o	Condition: Lead Score > 70.
o	If true: 
	Gmail Action → Send Email.
o	If false: 
	Google Sheets Action → Add to "Nurturing Campaign" spreadsheet.
________________________________________
Implementation: Task 2
1. Handle Incomplete Data
1.	Add a Filter Action: 
o	Condition: Check if all required fields are filled.
o	If false: 
	Gmail Action → Send an email to the lead requesting missing information.
	Add to an "Incomplete Leads" Google Sheet.
2. Ensure High-Value Leads Are Managed
1.	Add another Filter Action: 
o	Condition: Lead Score > 90.
o	If true: 
	Slack Action (or Gmail) → Notify the sales manager.
3. Handle Time Zones
1.	Modify the Google Form to include a Time Zone field.
2.	Add a Formatter Action: 
o	Parse the time zone and convert scheduling data.
3.	Add a Google Calendar Action: 
o	Action Event: Create Detailed Event.
o	Schedule a follow-up call or meeting in the lead’s time zone.
________________________________________
Implementation: Task 3
1. Assign Leads to Sales Reps
1.	Add a Google Sheets Lookup Action: 
o	Track assigned reps in a separate sheet.
o	Use a "Round Robin" system: 
	Use a formula to rotate assignments or leverage Zapier’s Formatter to determine the next rep.
2. Extract Keywords from Comments
1.	Add a Formatter Action: 
o	Action Event: Text → Extract Pattern or Split Text.
o	Extract specific keywords (e.g., "integration," "support") from the Comments field.
3. Automate Follow-Ups
1.	Add a Google Calendar Action: 
o	Create an event based on the urgency field: 
	Immediate: Schedule a reminder for today.
	Short-term: Schedule for 1 week.
	Medium-term: Schedule for 1 month.
	Long-term: Schedule for 3 months.
________________________________________
Testing and Deployment
1.	Test each Zap to ensure it works as expected.
2.	Monitor the Zap history to verify tasks are being processed correctly.
3.	Share the workflow with the TechNova team.
________________________________________
Recording a Video Explanation
1.	Use a screen recording tool like Loom, OBS Studio, or Screencastify.
2.	Walk through: 
o	The Zapier workflows.
o	The logic in the Google Sheets for scoring and assignments.
o	How follow-ups are scheduled in Google Calendar.
________________________________________

Adding Screenshots for reference
        
![image](https://github.com/user-attachments/assets/5fae638a-0b6e-48e7-a218-e3c1e1f616e3)
![image](https://github.com/user-attachments/assets/e20deb44-6307-41f4-8351-e79ad8aca223)
![image](https://github.com/user-attachments/assets/aa5b6ce1-fde9-425d-8c19-341734dbefda)
![image](https://github.com/user-attachments/assets/3bd464db-31af-41a2-9a84-2cb93fc57753)
![image](https://github.com/user-attachments/assets/2589d706-53f0-447c-9235-5cc8523f7744)
![image](https://github.com/user-attachments/assets/89fab8a1-d4ad-4f3d-90ff-23664509f090)
![image](https://github.com/user-attachments/assets/921be5f8-3d97-41c8-b9eb-13324e90ef82)
![image](https://github.com/user-attachments/assets/c69488b1-1c13-4b74-ac41-bd031898f9bb)
![image](https://github.com/user-attachments/assets/154d95aa-3596-4b59-95cc-dd0457d5f8be)


## License
This project is licensed under [MIT License](./LICENSE).
