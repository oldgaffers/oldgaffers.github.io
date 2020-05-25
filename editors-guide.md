# Guide for Editors

This is a work-in-progress

## The Editing Process

The editing process has been designed to allow anyone to submit new or amended data and
pictures for a boat but nothing is committed to the register until an editor has approved it.

## Adding a boat

New boats are added by clicking on the link on the boat browser. This opens up a form (on Jotform.com)
which takes the user step-by-step through the process.

When a boat form is submitted an email is sent to the boat register editors with three buttons:

  + a button to commit the changes to the register.
  + a button to edit the data before creating a new entry
  + a button to merge this data with an existing registry entry (this isn't implemented yet)

Pressing the commit button creates a new entry in the register. If the form contains pictures a new SmugMug gallery is
automatically created and the pictures are uploaded to it. Editors may want to crop and/or straighten these pictures. N.B. we will need editors to authenticate as the link could get lost and abused.

Pressing the edit button launches the form again with the data populated from the previous submission and
allows the editor to make changes to the data. Submitting the form sends another email to the editor who
is then likely to use the first button.

Pressing the merge button will do one of two things - we haven't decided yet:

  1. open up a version of the form which lets the editor pick a boat to merge the data with and steps through allowing the editor to chose the current or proposed data or to merge and edit text fields.
  1. send an email back to the person who submitted the form asking them to re-submit the data using the update process and suggesting a boat to update.

## Updating a boat

Boats are updated by clicking on the add data button on the boat detail page. This opens up the same form as the new boat process but with the fields filled in with the current data. The remaining process is the same.

it is possible in future that when a logged in editor uses the update process the changes will automatically be committed to the database without the email approval process.

## Using the image gallery

TODO

## Ownership data

TODO

## Adding Builders and Designers

TODO

## Fleets

TODO

## Updating the pick-lists

This is done in the Hasura console at https://api-oga.herokuapp.com
