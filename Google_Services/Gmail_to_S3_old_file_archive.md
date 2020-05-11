## How To: Save Gsuite and Gmail Storage Space by Archiving Old Emails and Files To AWS S3

![](/images/51.png)

As well as taking backups of my desktop and cloud services, another really cool tech practice I’m into* is periodically cleaning up my inbox and cloud-hosted filesystem.

My inbox seems to be getting progressively busier and more cluttered these days, so I’m trying to up the frequency of these clean-outs to once every three months rather than my hitherto annual swoop.

I’ve just closed up a long project with a client.

So I thought that this was a good opportunity to demonstrate — and document — my current methodology.

Here’s how I do it.

## 1: Batch All Projects / Clients Into Gmail Labels — And Set Filters to Direct Inbound Mail

The first step is to make sure that every unique project — or client you’re working with — has its own label in G Suite.

![](/images/52.png)

I’m pretty insane about this and have set up labels — and corresponding rules — for just about every conceivable purpose.

E.g.:

- I a label for my utilities (“Bills”) and under that sub-labels for power, my cellphone plan, my water bill, and my healthcare provider.
- I have a label for my IFTTT “it’s going to rain today” notifications and another for correspondence from my accountant.

![](/images/53.png)

So, if you’re also a freelancer / small business owner, set up labels for your clients. (I have mine sub-divided into current clients, past clients, and prospective clients).

Next, I create Gmail filters to automatically route inbound messages to the correct folder.

Generally, the easiest way to do this is to filter by sending address, but you can also:

- Filter by unique text strings in the subject line. The “exact match” Boolean operator is useful for this purpose.
- Filter by text strings in the body text.

HaGihon delivers water to my apartment in Jerusalem. And they send their e-bills from the domain printernet.co.il.

So, I create a filter to route all email from that address into the Gmail label I created for water bills.

The asterisks (*) symbol denotes a wildcard — so email from any other address at that domain will also route to the folder:

![](/images/54.png)

![](/images/55.png)

I typically also tick the “Never send it to spam” box — because I know it’s not spam and I need to see it — so I can “whitelist” the domain and prevent it getting caught up in my spam folder.

And I tick the “also apply filter to X matching messages” box in order to get all existing messages from that sender into the folder.

If this were a client, then I would also want to capture all the outbound (sent email) in the label I just created, again making sure that I apply a wildcard operator.

So I would create a filter in the opposite direction — just swap ‘me’ for your email:

![](/images/56.png)

## 2: Create A Label for Archiving And Nest Old Labels There

Next, I set up label called ‘For Archiving’.

I’ve nested this under another label called ‘System’.

![](/images/57.png)

Let’s say I wrap up a project with a client.

I don’t really need or want to have all the back and forth with my point of contact cluttering up my inbox.

So I’ll archive that label in my S3 bucket.

For the purpose of this demo, I batched a few emails I don’t need under a label called ‘Demo Old Client’.

![](/images/58.png)

I then moved the label under ‘For Archiving’.

![](/images/59.png)

Now I want to initiate a Google Takeaway — but only capture the label that I want to archive.

Firstly, deselect all GSuite services other than Mail.

![](/images/510.png)

- Click on ‘All Mail data included’.
- And unselect “Include all messages in mail”.

![](/images/511.png)

(FYI: despite this, the UI will still automatically select some folders that you probably don’t want to delete. So be sure to deselect these if you want to keep them.)

![](/images/512.png)

Just tick the old clients that you want to archive and click OK:

![](/images/513.png)

Unless all these messages come with large attachments, email is pretty light. So the download link shouldn’t take more than a few seconds to generate.

The few folders I decided to export came to just 8 MB:

![](/images/514.png)

In AWS S3, I created a bucked called archivedemail.

After downloading the Takeaway, you’ll want to unzip the archive and navigate a few folders into the directory to find the actual label archives.

These end with the file extension .mbox.

![](/images/515.png)

![](/images/516.png)

And that’s basically it.

I then select Glacier as the storage class because it’s unlikely that I will ever need to access the correspondence again:

![](/images/517.png)

Now that the emails are safely archived, I can delete all the messages from the labels in G Suite.

![](/images/518.png)

