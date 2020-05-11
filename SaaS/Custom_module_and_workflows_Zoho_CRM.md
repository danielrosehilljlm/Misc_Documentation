## How to: create a custom module in Zoho CRM to send clients work

I’ve written a few posts about CRMs in my blog and about how, for many years, I was spoiled for functionality by hosting my own implementation of Vtiger CRM.

More recently, I belatedly joined the cloud-hosted CRM world.

And while I would be lying if I said that I don’t still have paranoid misgivings about what might happen if Zoho or any other cloud provider vanished off the face of the earth one day (or, more likely, dramatically changed its terms of services — or lost my data), I can’t deny that the functionality comfortably exceeds that found in the open source world.

![](/images/31.png)

One feature which I’ve always “built” into CRMs I have self-hosted is the ability to track articles I write for clients as projects within the CRM — and to send out automated update notifications as I indicate that they are in progress, have been finished, etc.

I imagine that this is a fairly routine use case but also that most freelancers would see this as overkill. Personally, I like scalability and even at the 10 account point, sending out emails for every status update tends to get tricky.

Obviously, while I want to send updates, I don’t want to annoy my clients with too many notifications.

So I generally configure the automations to only run when a project has been initiated and completed; the other statuses I create are for internal tracking only and won’t trigger the workflows.
Let me explain how I set this up.

(Screenshots and Zoho CRM functionality as described at the date of writing only)

## 1: Create a custom ‘Article’ Module

In retrospect ‘Projects’ might have been a better and more generic title, but I was working on an article that I wanted to track when I decided to give setting this up a go.

From the main setup menu, select ‘Modules and Fields’ from under ‘Customization’:

![](/images/32.png)

Then, simply click on the button to create a new module.

The asterisks will flag this as user-created — compared to the default modules built in to the CRM:

![](/images/33.png)


Your first port of call will be the field editor.
Here, you can add all the picklists and conditions that you’ll require for tracking this type of item.

This is how I set up my module:

![](/images/35.png)

It includes fields that associate the article with:

- A current status
- A current version
- A billing cycle

It also has room for a download link and expected delivery date which I can populate when the project is finished and hide in the status update templates.

‘Suppress client no.’ is abbreviated from ‘suppress client notifications.’ (Whenever I’m building CRM automations, I like to create a sort of ‘kill switch’ and then build that into the workflow logic.)
To create a connection to an Account / Contact record, or any other module in the CRM, you’ll want to firstly add in a ‘Lookup’ field:

![](/images/36.png)

Then you’ll want to map which Contact/Account this relates to.

And then give this module a title in the related list. You can also make the lookup required — or allow entries in this module to be freestanding.

![](/images/37.png)

I made one additional customization beyond the default Zoho configuration.

For every client I onboard, I set up an email group with all the points of contact. And I created a custom email field for this address. This is the ‘point of contact’ email that I associate with the record in my invoicing platform.

![](/images/38.png)

I still create all points of contacts in the conventional way in Zoho and associate them with this account record.

But this custom field for the account management email is the one I will be building into my workflows.

## 2: Build Workflow Rule

I chose to set up three workflow rules for project deliveries, again using ‘article’ as a sort of generic shorthand for shorter writing projects:

![](/images/41.png)

These are:

- Article status update: sends for articles statuses that are not system capture (default) or delivered.
- New delivery date: used to advise clients of delays in expected delivery date.
- File delivery: used to confirm that the project has been finished and provide a download link.

I built my workflow logic like this:


![](/images/42.png)

When I was creating the picklist for ‘Current Status’ I added just about every conceivable stage a shorter written project could be at from ‘Brief Received’ to ‘Draft 1: Feedback Received’ and so on.

But I also set its default value to be ‘System Capture’. This is so that I can quickly add projects that haven’t been initiated to the CRM yet without triggering any workflows:

![](/images/43.png)

Note that I also added the ‘suppress system notifications’ as an AND logic condition.

If you’re the Professional tier, you might also want to make this a date-based workflow and configure it to only run during business hours.

## 3: Create Email Template for Workflow

Finally, I set up an email template to go to the client when the status has been updated to an intermediate status but not when the project is marked ‘delivered’. Because I add myself to all the account management groups, I didn’t need to configure my address as an additional email — although that is also an option.

I expect that most people wouldn’t bother clicking into the status update emails, so I included all the essential information in the subject line itself:

![](/images/44.png)

In English, that should read (for example): “Update: Article X is: in progress.”

I then added my fields and wrapped this text into a template:

![](/images/45.png)

And I added a custom field as the link itself so that I don’t show the download link as a URL but rather embed it with a hyperlink on the ‘clicking here’ text:

![](/images/46.png)

Now, all I need to do to mark an article as finished and send it to my client is update the field from a dropdown:

![](/images/47.png)

Which will send this to my client:

![](/images/48.png)

Additionally, I now have a module called ‘Articles’ in my CRM where I can see all current articles that I am working on.

I edited the default columns to make the information more useful:

![](/images/49.png)

I can simply click on each piece and send all project updates to the clients without having to ever send a manual email.

(Many thanks to Michael Trow, President of Alderbest Solutions who kindly provided me with guidance on the Zoho Community forums that set me off in the right direction.)




