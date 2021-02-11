---
title: 'Conditions'
media_order: ''
published: true
taxonomy:
    category:
        - docs
slug: conditions
twitterenable: true
twittercardoptions: summary
articleenabled: false
orgaenabled: false
orga:
    ratingValue: 2.5
orgaratingenabled: false
personenabled: false
facebookenable: true
---

---------------------
## Conditions

Campaign conditions are used to execute different actions based on a contact's data.  For example, a condition can be configured to execute an action if a contact has an email or does something else if they do not.

A condition has two paths that are denoted by the red and green points.

 - Actions attached to the green point ![](green-point.png) of a condition are considered as positive status points. The status condition path is executed as a result of the condition at the end of the delay set (trigger, delay or specific date).

 - Actions attached to the red point ![](red-point.png)of a condition are considered as negative status points. This path is executed as a result of negative status for the condition at the end of the delay set (trigger, delay or specific date).

 Here are the different conditions that Mautic offers in the Campaign builder:

 | Condition        | Description  | 
| :------------- | :----------: |
|**Contact campaigns**| Checks if the contact is a member of another campaign|
|**Contact device**|Checks if the contact has interacted <br> with your campaign from a specific device <br>type, brand, or OS|
|**Contact field value**| Checks if the information matches the selected criteria on the contact record, the contact’s primary company, or UTM tags|
|**Contact owner**| Checks if the selected user is assigned <br> as the contact’s owner|
|**Contact segments**| Checks if the contact is a member of <br>selected segments|
|**Contact tags**|Checks if specified tags are on the contact record|
|**Form field value**|Checks if values submitted for a <br>selected field on a selected form <br>matches specified criteria|
|**Has active notification**|Checks if an active web notification <br> is being sent to the contact|
|**Has valid email address**|Checks if the contact’s email address has a <br>valid syntax, that is, name@domain.com without spaces, other invalid characters, formats.|
|
The delay you set is ran before checking the condition no matter the delay you add on the connected actions. It will not wait the delay on the connected action to check the status of the condition to qualify the contact into the positive or negative path of the condition. <This sounds very convoluted. Need to understand and rewrite.>

### Using a custom date field to trigger a campaign

In the condition based on a contact field value, select the required date field. Then select **date** as the operator and select the required value from the drop-down list.

>**Note**: In the **Anniversary** option, you can only enter the day and month values.

Since campaign conditions are evaluated immediately, if the date in the field matches the condition, then the positive action is executed.  If the date doesn’t match, the negative action is executed. The contact does not wait for the condition to be true.

In order to run campaigns based on a particular date where a contact may or may not be "included" today:
- create a segment with a filter where the date field = TODAY.
- initiate the campaign based on that segment.
- as contacts move in and out of the segment, the campaign will run.
- you can elimiate the condition since the segment is changing daily.

This will NOT work for the Anniversary option.

If a contact appears again at a later date in that segment because the value of the date has changed, then the contact will go through the campaign only once and hence will NOT be included in the campaign again.