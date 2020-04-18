---
layout: post
title: How Datadog Saved My Wedding
image: /images/wedding_post/results.png
---

Ok, the title is a bit exaggerated but the story is still true… With 9 months to go to my upcoming wedding, my beautiful fiancée was in full planning mode. Venue = booked, photographer = booked, florist = booked, her dress = bought. The next item on the list : the perfect pair of shoes. She had her heart set on the exact pair she wanted, her bridesmaids had all swooned over them, they matched the dress perfectly (or so she tells me!). There was only one problem: they were out of stock in her size!

As a doting husband-to-be, I took it upon myself to make sure she would be happy. I contacted several shops, emailed customer support, even phoned their HQ! No joy.

Then, one afternoon at work, the thought came to me - how could Datadog help solve my problems? The answer - the then recently announced [Synthetic Browser Checks](https://www.datadoghq.com/blog/browser-tests/){:target="blank"}.

The idea was simple - set up a Browser Check on the shoe website to check at regular intervals the status reported for her specific shoe size and to alert me when that dreaded “Out of Stock” message disappeared.

**Creating the Browser Check**  
Datadog Browser Tests allow the user to record any journey on a website to test/monitor a workflow.

Thanks to the built in Web Recorder I could configure via the GUI, with no coding required, the steps required for my check.

First - Click on the shoe size 36.5  
Second - Include an Assertion that would test an element’s content to test if the button included “SOLD OUT”.

![image](/images/wedding_post/test.png)

Next I waited for the first check to make sure the flow recorded properly and worked.

![image](/images/wedding_post/results.png)

**Waiting for the Monitor to trigger**  

Later that very evening, to my amazement the check triggered a failure! The site was showing that the “SOLD OUT” button was no longer there, meaning it had been replaced with the “Add to Basket” button instead!

![image](/images/wedding_post/email.png)

Unfortunately - I wasn’t checking my emails at 21:39!!! When I came in to work the next morning and noticed it, I immediately checked the Datadog UI and sure enough the test was still failing, meaning they were still available:

![image](/images/wedding_post/failure.png)

I then jumped to action and made the purchase, as you can see from the below, after I made my purchase (around 08:16), by the time my check ran again (just before 09:00) it resolved back to the “OK” state - meaning they were out of stock again! I’d managed to grab the only pair that had become available!

![image](/images/wedding_post/uptime.png)
