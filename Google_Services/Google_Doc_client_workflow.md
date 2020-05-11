## A Way To (Comfortably) Work With Clients in Google Docs

![](/images/71.png)

Have you ever been working on a Google Doc for a client only to feel a lump in your throat the moment they — and their client — both make an unexpected appearance in the live view late in the night?

Although I’ve been using Gdocs since …. well… a long, long time, it still makes me uneasy when I’m working on a document with my client just kind of sitting there watching me work (at least that’s what it feels like).

I get it.

They’re not actually looking over your shoulder. Or at least I hope they’re not (awkward truth: very occasionally they actually are!).

But unlike bosses that physically look over your shoulder, you can never tell exactly where your client’s eyes are while you’re scribbling.

You only know where their cursor is currently situated.

That, and the remoteness of it make it …. just kind of creepy.

The problem is that, for the most part, I think that Google Docs are great. As a Linux user, I also like the fact that Google Docs is cloud-hosted and thus operating system agnostic. No more LibreOffice— Word formatting disasters. And I also like to work with clients on the platforms they are most comfortable using wherever possible.

However, a recent straw-pool among freelancing friends also showed that many (if not the majority of freelancers) share my uneasiness with raw, real-time editing in Google Docs. Ie, most freelancers are little bit weirded out by their clients being able to observe them working in real time.

So, when I recently onboarded a couple of clients that were Google Docs-centric type of accounts I went about devising a little system to attempt to please all parties.
So far, so good.

And it even helps keep version control in better check which is important if you cap these in your fee structure.

Here’s what I do.

## 1: Set up “shared”and “not shared” folders

Firstly, I set up all my client accounts are based on a template file structure — whether I’m working with them primarily in Google or through another cloud system. (I have a two-way sync running between Gdocs and my main cloud provider so it doesn’t make much difference to me. To do this, check out Multcloud.com).

Mine currently looks like this:

![](/images/72.png)

Then, within articles, I set up two sub-folders: “Shared” and “Not Shared”:

![](/images/73.png)

Remember the custom module which I built in Zoho CRM for sending drafts to clients? If not, check out the link to the left. It’s easy to set up and works really nicely.
I keep track of revisions in it and capture the Google Doc link there:

![](/images/74.png)

## 2: Share the “Shared” fold with your client(s)

The rest of the system is pretty straightforward.

But, to be thorough, let me explain its moving parts.

Firstly, I either transfer ownership of the “shared” sub-folder to my client so that he/she can share it around internally.

Or (this, I think, is the best approach, particularly when working with large clients), I share the link with anybody at the client’s organization who has the link:

![](/images/75.png)

Finally, you can turn on link sharing for “anybody with the link.”

![](/images/76.png)

Sometimes, clients specifically ask for this.

If the document is being reviewed and edited by various organizations (think agency plus client), and not all of them are on G-Suite, then this can be the easiest and quickest way to make sure that everybody that needs the resource can get it.

As you can elevate to the anybody to the link “can organize, add, and edit” permission, you can also give your client the ability to configure additional individual sharing permissions.
Of course, from a security and data protection standpoint, it’s also the riskiest. The document won’t be indexed by search engines, but there’s still a risk that a third party could access the link as there is no protection whatsoever around access — all it takes is for somebody to accidentally include the link in an email for unintended recipients to gain access. So I don’t recommend using it to share sensitive projects or documents with clients.

If you need to use open link sharing, do so with caution and consider making the share link ephemeral (configuring it to expire after a certain time period).

## 3: Work on drafts in the unshared folder

I will then work on the first draft of my article within the unshared folder:

![](/images/77.png)

## 4: When Finished, Move The Draft Over

And then, when the draft is ready to show to my client, I will simply move it into the shared folder.

I also make sure to note the version in the title by appending VX to the title:

![](/images/78.png)

And then, when it’s done, I move the file over.

I’m showing this process on the browser UI, but it’s equally straightforward if you’re using a desktop sync client.

![](/images/79.png)

You can simply drop your client an email to let them know that the first draft is ready.

I usually prefer to use the “Email collaborators” function and just drop in a message there. And I always choose the “send a copy to myself” option just for record-keeping purposes:

![](/images/710.png)

Bear in mind that your client may already be using something like Google Drive File Stream and get a notification that a new file has arrived for them.

Alternatively, you could use something like Zapier to create a Google Drive -> email Zap and automatically notify your client when a new file is ready for their attention.

If you’re doing this, you should know that Zapier cannot recurse into subfolders on Google Drive. So you can’t do what I do and create date/month based sub-folders within the “shared” folder.
If I don’t have a personalized message to relay through email / the email collaborators function I simply use the CRM module I created to notify the client through a workflow:

![](/images/711.png)

## 5: Let Your Client Collect Feedback

From a workflow perspective, this encourages your client to collect feedback within a specific time-frame.

I let my clients take the lead on this.

There’s usually some deadline that the client is adhering to — so the feedback should come aggregated by a predictable date.This works a lot better than what I call “stream of consciousness” feedback that is relayed by multiple parties at irregular intervals — and it’s never quite clear when it’s safe to begin working again.
When my client is done working on my V1 (if it’s an agency, that might involve sharing the folder with the end-client and collecting their feedback), then they simply let me know that it’s ready for me to take back to production.

## 6: Copy Version With Feedback To Unshared Folder and Annotate it ‘V2’

I then copy the document back to my “draft” / working folder and notify my client that the V2 is in progress — although they won’t have access to the share link until it’s ready for their attention again.

I update the document title to annotate it with V2. This is both for version control and billing purposes — I need to keep track of what draft is currently being circulated as (under my fee structure) revisions beyond V2 usually accrue extra charges. (If you want to know why, see my freelance pricing guide).

![](/images/712.png)

To get the workflow right, you need to make sure that you:

- Check the option to copy comments and suggestions. There’s another option to “include resolved comments and suggestions” which is unticked by default. To be safe and ensure that I’m not missing anything, I tick this box also.
- Uncheck the option to “share it with the same people.” If you don’t, this will just mean that the document gets re-shared with your client — despite the fact that it’s now nested in the unshared folder which only you and/or your internal resources should have access to.
- Copy over your client’s comments and suggestions so that you can work on resolving them.

## 7: Enjoy Less Stressful Google Doc Editing!

As I mentioned, this workflow has proven surprisingly successful so far.

From my perspective, it allows me to aggregate comments and then work on them in one shot without having to worry about the client (or additional points of contacts) making changes to text I’ve just edited. If you’re in software, think of it as a Google Docs way of avoiding merge conflicts.

It also makes it easy to keep control of revision rounds and encourages clients to collect all edits and then send them in one shot.
If there are multiple stakeholders involved in an editing process, at different organizations, trust me when I say that this can be a huge time-saver.
Some clients might hate this system and adamantly refuse to work with it.

Depending on how uncomfortable you find working live with clients in Google Docs this may or may not be a deal-breaker for you.

During the course of my straw poll, several freelancing friends said that they would expressly refuse to work with a client who insisted on peering into their work in real time. If you’re in a strong bargaining position, you can try enforce terms that suit you. But that, of course, is not always the case.

Use the above methodology to make working with clients over Google Docs a less stressful experience!

