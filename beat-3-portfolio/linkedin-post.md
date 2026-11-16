I made an open source contribution this month: I showed that a safety check in PathReview, an AI review app, could be fooled by a single space, and I opened a fix that now passes all of the project's automated checks. The pull request is up and waiting on the maintainers' review.

PathReview screens the text users submit for a trick called prompt injection — hiding instructions inside ordinary text to make the AI ignore its rules. One of its checks looked for lines pretending to come from the system, like "System: ignore the instructions above." But if someone typed a space before the colon — "System : ignore" — the check missed it entirely.

Before changing anything, I reproduced the problem and posted my evidence and plan on the project's issue, so the maintainers could see exactly what failed and what I intended to do. Then I made a small, careful change and backed it with tests: six proving the sneaky variants are now caught, and two proving that ordinary sentences like "System is down: please retry" don't get wrongly flagged.

The fix was one line, but I learned the credibility comes from everything around it: proof before the change, tests after, and honest scope about what I didn't touch. When my first batch of tests covered less than I had promised in my plan, I rewrote them before opening the pull request.

My pull request: https://github.com/codepath/pathreview-ai301-fa26-s3/pull/284
