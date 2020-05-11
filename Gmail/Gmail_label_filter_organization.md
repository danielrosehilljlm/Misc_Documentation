## Gmail Organization System for Managing Bills 

I’ve just finished my bi-annual cloud-to-cloud backup process (if you missed the excitement, check out my post here).

In the process of archiving old emails and files to S3 (itself a nice hack — see here) I decided that I may as well make sure that my expenses for this and last year are ready for my accountant when it’s time to do my tax return in a few months. Because trying to fish through a year’s worth of receipts and invoices on a 24 hour deadline is never any fun. (And yes, these are the kind of fun activities the self-employed get up to when work lets off for a day).

Thankfully, having at least your fixed bills nicely organized in Gmail makes that process much easier.

The following utilities are Israel-specific but you can use this same workflow to organize and archive your utility bills wherever you are in the world — whether, like mine, they are partially tax-deductible and you need them for your business or whether you just like keeping your data well-organized on the cloud.
Here’s the system I’ve been using for years.

## Opt In To Digital Invoices For Every Service That You Use

First things first, you want to make sure that you’re signed up for digital invoices for absolutely every service that offers it.

If you’re using a G Suite account with just one address — and you’ve set that up as a catchall — then you can be even more clever and register all bills to send to: bills@yourdomain.com.
If you’re just on regular Gmail then you can use this little known hack to create an additional “address” for filtering purposes. Simply append the plus sign and some text to your email. So you can create:
```
myaddress+bills@gmail.com
```

Then you can create a filter like this with the “from” field as a wildcard.

Replace the “to” field with either your spoofed Gmail address as above or the bills@ address that will route through the catchall system:

![](/images/11.png)

And automatically forward all mail to that address into your ‘bills’ label:

![](/images/12.png)

The exact options for receiving bills by email varies by utility, of course. But these days most do. It also cuts down on needless paper use and is good for the planet.

## Organize Your Utility Bills Into Sub-labels

I kind of skipped a step ahead.

Firstly, you’ll want to create a Gmail label for bills.

I would put that at the root level of my Gmail:

![](/images/13.png)

Next, you’ll want to populate sub-labels for every utility whose bills you receive by email.

Mine looks like this:

![](/images/14.png)

## Create Gmail Filters to Automatically Route Sending Addresses Into Folders

As soon as you begin receiving your invoices by email, you’ll need to start paying attention to the sending address that is automatically dispatching the bill as well as the subject line used in the template. This is so that you can create filters that will capture and route only those emails into the right folders.

Of course, you could simply add the whole domain with a wildcard like this:

![](/images/15.png)

But by doing so you would probably end up inadvertently capturing non-billing related items such as company newsletters and correspondence with customer services.

Instead, I look for the sending address that is specifically used to send customer invoices:

![](/images/16.png)

Most bills that are automatically sent by email follow a predictable format in the subject line or body text (usually both). If you want to be even more precise you can incorporate both these and the sending address into your Gmail filter.

Let’s look at an example.

Above is an example of the electricity bills which I receive by email. The bill is attached as a PDF and paid by direct debit. So once a folder automatically fills itself I can just go through it once a year and pull down the PDFs and then upload them as a batch into my expenses system. (There are far more sophisticated ways of automatically tracking expenses than this, I realize; but our choice of online banking environments and accounting programs in Israel — at least those that are compliant with the demands of the tax authorities — are limited).

### Demonstration 

For this bill I would filter based upon two concurrent variables:

Sender: noreplys@iec.co.il
Subject: “מספר חשבון חוזה” and לתקופה
This is the Gmail filter as I would set it up:

![](/images/17.png)

The filter automatically scoops up all the emails matching this search in my inbox (billing is bi-monthly and I only signed up for e-invoices at the start of this year).

Make sure to click the “also apply filter” box if you want to group existing messages in your inbox into your newly created folder. In the future, the rule should route the messages automatically.

![](/images/18.png)

Caveats:

- You may need to tweak your filters from time to time as the utilities change their CRM templates and/or sending address.
- Therefore, it’s sometimes more sensible to apply less exact filters. E.g. a wildcard sender from the company domain with “Bill”, or equivalent, in subject line.

## Some common search strings

I’ve been using this system for a number of years to filter and organize my incoming bills — as well as lot of other communications — automatically.

I find that bundling the capturing of these expenses into my accounting system at yearly (or twice yearly) intervals is the most effective strategy.

Here are a couple of filters that work at the time of writing.

If you’re also using these service providers it might save you a couple of minutes:

### Golan Telecom (phone service)
From: noreply@golantelecom.co.il
Subject: “חשבונית גולן טלקום” (make sure to use the apostrophes to run an exact search match).

### HaGihon (water supplier)
From: hagihon@printernet.co.il
Subject: חשבונית

### Macabbi (health fund)
From: do_not_reply@maccabi4u.org.il
Subject: “חשבון חודשי”

### Partner (internet)
From: Thankyou@partner.net.il
Subject: “אני החשבונית שלך”
