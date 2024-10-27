# Self Hosting Feature Requests Service

***TLDR/To see a concise-ified version of this document produced using LLMs (chatGPT), see: [llm-feature-reqs-doc.md](./llm-feature-reqs-doc.md)***

### Introduction

After encountering that features.vote application earlier, I went to check out the various other tools that exist for gathering feature requests; and there are a lot of them. Partly because I intend on utilising similar software products myself in the future, but I also figured it may be helpful as a reference for anyone else in a similar position.

They’re all a bit pricey for a single individual running their own project though, you’re looking at ~\$350 a year for a fairly simple web application. Then again, the overheads associated with it being hosted and managed for you is probably what jacks the price up to that degree — and as I’m sure a lot of users of these products have a large amount of traffic flowing through them, that does provide some degree of justification.

Thus, I figured there must be some open-source tooling that you could self-host, as that would drastically reduce the cost associated with gathering user feedback (as you can offset the cost of the managed service agaisnt hosting the solution yourself, either on bare metal hardware if you already run a homelab with a decent fiber connection, or through a virtual cloud instance, such as EC2 on AWS or a droplet on DigitalOcean).

Whilst most SaaS product owners have likely already explored these avenues, I wanted to check these options out for myself and as such, I have created this document as a reference guide. Though, I have limited time. My findings are listed below.

### Findings

There are some self-hosted options worth potentially exploring, I found two ‘acceptable’ alternatives to managed & paid SaaS products, but they each have their own ‘problems’ associated with them.

1. clearflask.com — they politely ask for a license fee of $9 per month (even if you’re hosting their open-source project yourself), but they do essentially say that it’s not neccesary and you can simply deploy it yourself (since it is open-source). However, they use bunch of ‘old-school’ technology; and the application is (well) written in Java and is hosted using Tomcat. I mean, I don’t think I’ve come across Tomcat besides using it for a university project about nine years ago. There is also a large setup guide that provides the impression that there are a lot of dependencies and potential points of failure if something were to go wrong (this is simply a conclusion I arrived at through skimming the documentation). In conlusion, getting that set up would potentially be a pain point. In addition, forking and making changes would require familiarity with Java (for any backend changes) and the application backend is built professionally. As such, knowledge of design patterns and techniques such as dependency injection, generics, inheritance, abstract classes, interfaces and the like would be, at least, in-part required.

2. https://fider.io/ — completely open-source. Looks like a doddle to set-up; it’s essentially just deploying a docker container, configuring NGINX and grabbing an SSL certificate from LetsEncrypt. The only problem is the UX is a bit rubbish and it looks fairly terrible insofar as aestetics are concerned. Whilst there’s nothing stopping anyone from forking, making some UI changes; and then deploying it; their backend is written in Go (which may require some additional reading to get to grips with); but the front-end makes use of React, Typescript & SASS — so no issues there, per se.

3. https://usefeedback.vercel.app/ — This is a tool, more so for testimonial gathering, but could be utilised for gathering feedback privately. However, it is open source and built with: Next.js, TypeScript, Tailwind CSS, Prisma, Zod and Shadcn/ui, which most web developers should be pretty comfortable using. The project is not well known and is really quite a great find. As such, it would be possible to fork the project and modify the tool to provide an experience not dissimilar to https://features.vote/. Note: currently, I am the only individual who has starred and forked the project. This could be a great option to solving this issue; though it does require further investigation. https://github.com/jonathondilworth/use-feedback forked from https://github.com/Munadil16/use-feedback.

4. Tried looking into: https://github.com/nhsuk/user-feedback-form & https://github.com/nhsuk/user-feedback-store — absolutely shitshow of a project as far as I can tell, lot’s of vulnerabilities and I can’t even get the thing to run properly after about 25 minutes, all I could get was an empty modal to pop-up on the page. TODO: revisit.

5. An open-source Trello clone: https://github.com/plankanban/planka — Looks pretty good! But not entirely fit for the given use case.

6. You can essentially use GitHub discussions for feature requests, as is outlined by Feedbear: https://www.feedbear.com/blog/github-track-feature-request — but as they mention, it pretty much gate-keeps the experience to developers (kinda).

7. https://github.com/HugoGresse/open-feedback — I’ve had a quick look at their demo, looks fairly promising; but I don’t really have the time to explore it in anymore depth. TODO: come back to this.

### Comparing Findings with Required Criteria & features.vote

I didn’t really find anything else of value in the time I had (to do this quick bit of research) In terms of open-source projects that really satisfied the criteria; which, I would specify: should be minimal. In fact, the solution offered by https://features.vote/ is a good solution insofar as minimalism is concerned. It is reasonably priced; however, the product is unfinished and is not ‘battle-tested’. Plus, it’s not open-source, so I assume there hasn’t been much code review and it looks to be developed by a sole individual. In the absence of adopting professional testing practices: acceptance testing, unit testing and integration testing, it may be worth waiting a little while before paying for a license. Nevertheless, you can obtain a lifetime license for \$99 currently, which is a great price, assuming the product remains online for at least the next four or five years. 

I was supprised that there wasn’t many (easy to find and often reccomended) open-source tooling for an appropriate feature request tool (similar to https://features.vote), given the relative simplicity of such a project (as compared to many other open-source projects). Honestly, I found this to be quite odd. Given the time, this would certainly be a project I would be willing to work towards collaborating with others to produce, ideally with the intention of making it open-source. Sure, it’s monitisable, but then it becomes a business with paying customers; and you have to worry about commitments to those paying customers. It’s a much better practice to write software whilst collaborating with others who have a ‘shared vision’ (though, you can characterise this as a shared love for engineering — see Linus Torvalds on Vision in Open Source Software) and then simply hand off the parts that you find difficult to collaborators; and essentially produce a better piece of software as a working group, rather than working as an individual. Though, obviously, it is not as profitable — but typically, the money comes later. I think the experience is probably more valuable right now, for me at least.

Anyway, there are a couple of hosted solutions that looked pretty great, but these are paid solutions (note: whilst this document will be shared with others, it’s mainly a guide or reference for myself, as I intend on building my own software projects when I have time — and hopefully I can meaningfully contribute to other projects in the meantime, as I do not currently have the time to dedicate to focusing soley on my own project(s)):

* https://supahub.com/ — perfect, besides the lack of features until you hit $400 per year.
* featurefind.io — meh, it’s not too bad; but again — $290 per year.
* https://nolt.io/ — Nice, neat little web-app; but again, $350 a year is a bit steep.
* TODO: update this list, I reviewed at least four others, but need to revisit them.

### General Notes (train of thought) Prior to Conclusions

Given some degree of working capital, ~\$300 isn’t very much to pay for an annual license for tooling such as the aforementioned projects — for a serious software project. However, I wouldn’t neccesarily spend this before having done some initial research into the profitability of a proposed SaaS product (primarily interviews & surveys) — it should be validated — and ideally you’d want a brief outline for a business plan — just touching on the key aspects of marketing and monitisation. 

If you’re going to spend money on tooling to build out a serious project, you need to be able to justify those costs. In addition, it would be a good idea to set up a registered business (if one were serious about producing such a product) as you would be able to offset some costs as business expenseses (not to mention, the cost of living — as living whilst being self-employed is essentially a business expense). E.g. in the UK, we can claim VAT back on business purchases; but of course, we have to charge VAT on the sale of our products. More things are considered business expenses than you would think.

Anyway, that’s enough rambling; see conclusions.

### Conclusions

* I think it’s worth exploring: https://github.com/Munadil16/use-feedback as a tool for collecting testimonials at minimum. But from my fairly hastey review of the project, it could be used to collect feature requests; and given some modiciations, it could essentially be modified to provide an alternative to a tool such as https://features.vote/
* https://fider.io/ looked promising as an open-source (free) solution to gathering feature requests from non-technical users, however, it could probably use a little bit of a facelift, but is perfectly acceptable in its given form. I don’t believe deploying it would be much work at all. In fact, I could probably do it in my sleep (note to self: don’t speak too soon).
* GitHub Projects & GitHub discussions are the most appropriate tools for this use case, specifically for developers and esp. on any open-source projects.
* The paid tooling is the best, really — https://features.vote/ is probably the best value proposition IMHO. However, given some additional working capital, I would opt for either https://supahub.com/, featurefind.io or https://nolt.io/. https://supahub.com/ looks to be preferable, but would be the most expensive for all the additional bells and whistles. They each have their own strenghs and weaknessess.

### What would I do?

*(in rank order)*

I’d probably buy a license for https://features.vote/ as it looks like a promising project; and the developer is actively engaged in the project (since I’ve spoken with him directly, he was very quick to respond to a query via e-mail). In fact, I’d be happy to support that project and may even purchase a license for it given that it’s currently only $99 for a ‘forever-license’.

*Alternatively, if that didn’t work out:*

I’d probably implement https://github.com/Munadil16/use-feedback for a tool for collecting testimonialsl; and I would consider modifying it to fit the needs for collecting feature requests and publicly displaying a roadmap and the current request list.

*Alternatively, if that didn’t work out:*

I’d probably just deploy https://fider.io/ on a server runnning out of my own flat initially (and if the traffic started to increase, I’d migrate it over to a virtual instance). Personally, I wouldn’t even bother modifying the UI unless I was getting a lot of traffic. It does the job; and it’s free.

*Alternatively, if that didn’t work out:*

I would just purchase an annual license to https://supahub.com/ (most likely). Though I do like the other two alternatives too.

### Summary:

* https://features.vote/ — great little project; I like that it is in active development and believe it’s worth investing in getting setup.
* https://github.com/Munadil16/use-feedback — great little tool for a similar job to collecting feature requests (testimonials).
* https://fider.io/ — a fantastic, easy to deploy, free option.
* Paid alternatives:
    * https://supahub.com/
    *  https://featurefind.io
    *  https://nolt.io/

To see a concise-ified version of this document produced using LLMs (chatGPT), see: [llm-feature-reqs-doc.md](./llm-feature-reqs-doc.md)
