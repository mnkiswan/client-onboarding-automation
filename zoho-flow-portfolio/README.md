# Zoho Flow Automation Portfolio

Five Zoho Flow automations built on Zoho CRM, Zoho Forms, Zoho Writer, Zoho Projects and Zoho Bookings. Each one removes a manual handoff that small service businesses usually run by hand: lead intake, quoting, meeting follow-up and task creation.

## 1. Client Onboarding Automation

Trigger: Zoho Forms "Form entry submitted" (realtime).

Steps: create the account in Zoho CRM, create or update the contact, create a deal, merge a welcome document in Zoho Writer and email it, then create a task list and several tasks or subtasks in Zoho Projects. A Decision step routes the work by client segment (Enterprise, Group, or Default). Errors on the CRM steps go to an "Error alert task" branch.

Why it matters: every new client gets the same records, welcome document and kickoff tasks, with no one re-typing intake data. Onboarding is faster and the first impression is consistent. It has 11 executions with 10 successes and 1 failure, so the error branch has already been exercised.

## 2. FlowOps 2 - AI Lead Triage

Trigger: Zoho CRM "New lead".

Steps: a custom function called `triageLead` scores the lead, then the lead record is updated in Zoho CRM with the result.

Why it matters: sales reps stop reading every inbound lead to decide priority. Strong leads surface first, and weak leads stop taking up time. This is the AI lead management idea in its first working form. The custom function is where the classification logic lives.

## 3. FlowOps 3 - Quote and Sign

Trigger: Zoho CRM "Entry created or updated".

Steps: an If/else condition checks the record. When it is true, a document is sent through Zoho Writer.

Why it matters: a quote or document goes out the moment a deal reaches the right stage, so deals do not stall waiting for someone to send paperwork.

## 4. Kickoff Booked Sync

Trigger: Zoho Bookings "Appointment booked".

Steps: fetch the contact in Zoho CRM, then update the matching CRM module entry with the booking.

Why it matters: a booked kickoff call is written back to the CRM automatically, so the sales record always matches the calendar.

## 5. Kickoff Booking Reminder

Trigger: Zoho Forms "Form entry submitted".

Steps: a Delay step, then fetch the contact in Zoho CRM, then a Decision step. If no condition matches, the Default branch runs. The matched branch sends an email template.

Why it matters: clients get a reminder without anyone remembering to send it, which reduces no-shows and missed kickoff calls.
