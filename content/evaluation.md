## Evaluation
{:#evaluation}

The proposed architectures and implementations are evaluated by doing a user study.
The user experience is evaluated by asking participants to use the FormGenerator and FormRenderer apps to create and fill out forms.
Users were provided with a scenario explaining what they were supposed to do with the app.

The feedback received from these users was that the FormGenerator app was easy to use, especially because of the drag-and-drop functionality.
However, the feedback also showed that bindings and other Linked Data concepts still confuse users.
This is still required knowledge to use the app, which should not be the case.
The users building a SHACL form noted that the "min count" and "max count" for a field were confusing to them because they did not know what they meant.
Overall, the feedback on the FormGenerator app was positive and 6 out of the 8 technically proficient users were able to create the form without any issues besides the difficulties with the bindings.

The feedback that was received for the FormRenderer app from all the 11 users, with and without a technical background, was that the app is straightforward to use, easy to use, and clear.
They were all able to fill out the form without any issues.
Someone noticed that when filling out a form described using SHACL, they expected a multi-line text field to be used for the review field instead of a single-line text field.
However, the SHACL vocabulary does not allow one to define a multi-line text field.
Furthermore, one person noted that it was unclear what the Subject URI was for, and even though for people without that knowledge there is always at least one valid suggestion that can be used, it can be confusing because they do not know what to choose.
Besides that, the users did not notice that the app was using Solid and Linked Data behind the scenes and this is exactly the goal of the FormRenderer app.
People were also unaware that schema alignment tasks were being performed behind the scenes.
