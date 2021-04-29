# Technological Mediation in Public Comment

## Admin

### Potential Publishing Targets

- [Journal of Quantitative Description: Digital Media](https://journalqd.org)

## Hypotheses

1. There is a difference in pro vs con overtime allowance in public comment.
2. Venue (In-person and online) mediates and removes or minimizes the difference in
   pro vs con public comment overtime allowance.

## Background

Prior to the COVID-19 pandemic, time limits on in-person public testimony largely was
"enforced" through mutual understanding between community member. Councilmembers and
representatives would tell commenters when they had gone over time and occasionaly
the clerk may mute the commenters microphone but it was very rare for commenters to
be _strictly_ stopped right at the time limit. Commonly, public testimony would
go over time by a few seconds and this was generally allowed as long as it wasn't
multiple of time over the allowance.

In this way there was a common overtime allowance.

During the COVID-19 pandemic, all public testimony became virtual using conferencing
technology to carry out meetings and public comment. The difference however is that
the clerk was provided a much easier way to stop public comment through the ability
to mute any specific participant. Commonly, the moment or soon after public testimony
went overtime, the individual was muted, thus stopping their testimony entirely.

## Work Plans

1. Determine and codify the rules of public commenting
2. Find violations of rules and document how enforcement takes place
3. Determine measurement system (features) that can be applied uniformly to
   different venues to create dataset with
4. Generate features and analyze to prove there is a casual determinant

End result of this should be:
A dataset showing lengths of time of comments and rule violation enforcement across
both periods (online and offline). Then, to show that by controlling for other
confounding variables that the new forum (online) results in a dampening of
one viewpoint or another.

### Example Dataset

| event_id              | legislation_id        | legislation_file_uri              | testimony_id                                                                | testimony_file_uri                | testimony_content                              | testimony_environment | position_label | allowed_duration | real_duration | legislation_decision_result | meeting_chair_decision | overtime_allowance | enforcement_type                    | enforcement_serverity        |
| --------------------- | --------------------- | --------------------------------- | --------------------------------------------------------------------------- | --------------------------------- | ---------------------------------------------- | --------------------- | -------------- | ---------------- | ------------- | --------------------------- | ---------------------- | ------------------ | ----------------------------------- | ---------------------------- |
| (metadata, generated) | (metadata, generated) | (metadata, archived cdp file uri) | (metadata, generated, a unique id for all sentences for a public commenter) | (metadata, archived cdp file uri) | "I am here to speak in favor of this bill..."  | remote-audio          | pro            | 120              | 123           | pass                        | approve                | 3                  | (None, muted, removed, or arrested) | (mapping of type to numeric) |
| (metadata, generated) | (metadata, generated) | (metadata, archived cdp file uri) | (metadata, generated, a unique id for all sentences for a public commenter) | (metadata, archived cdp file uri) | "I am speaking against the passage of bill..." | local                 | con            | 120              | 149           | pass                        | approve                | 29                 | (None, muted, removed, or arrested) | (mapping of type to numeric) |

#### Dataset Comments

It would be useful to extract features from the audio as, an assumption would be that if a person's testimony was yelling, regardless of commenters `position_label`, they are likely to be violation enforced earlier, or the severity of their violation may be harsher.

Adding `allowed_duration` and `real_duration` for each testimony is useful as there are common occurances of people "yielding their time" to other commenters.

To track in-person vs. remote testimony we can use the `testimony_environment` column which will only support "local", "remote-audio", and "remote-video" options. In doing so, we can limit the amount of variables while also understanding if there are overtime allowance bias specific to the environment.

Finally, keeping `legislation_decision_result` and `meeting_chair_decision` as there is likely bias in which comments are allowed overtime based off of the pre-planned "general understanding of bill passage." (I.E. it is common for legislation in Seattle to only make it to Full Council if it will be passed.)

#### Dataset Construction

In most cases, annotating the `position_label` would hopefully not be too difficult as many legislative bodies keep record of public commenters and their commenting position. We could either ask for that information, or, pull from an API.

It may be useful however to see if we can create a classifier to apply to data (which is likely faster and scales better) than waiting for a Clerk to return back to us and annotating a dataset like this would be relatively quick and easy.

Most everything else in this dataset can be computed or directly pulled from existing CDP resources.

## Addtional Comments

Be observant and additional look into if during the technology intervention
(of using the mute) public officials were systematically allowing overtime
allowances for certain bills and / or viewpoints.

## Relevant Articles, News, and References

- [Arkansas House Hearing on Transgender Youth Bill, Father Arrested for Overtime](https://web.archive.org/web/20210429000235/https://www.lgbtqnation.com/2021/04/concerned-father-arrested-peacefully-testifying-arkansas-trans-health-care-ban/)
- [Arkansas House Hearing on Transgender Youth Bill, Full Video](https://www.arkansashouse.org/watch-live) _2021.03.09 House Public Health, Welfare and Labor Committee, HB1570_
- [Crosscut: Washington State Goes Fully Remote for Testimony](https://crosscut.com/politics/2020/11/how-wa-legislature-plans-go-remote-during-covid-19)
