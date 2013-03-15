VA Log entry v13.02.18

Pages changed:
/admin/students/state/logVA.html

Description:
Adds VA specific validation to discipline logs. If problems are found,
error messages are displayed next to the associated field. The form
cannot be submitted until the errors are corrected.

Compatibility:
Windows 7: IE8, Firefox 12, and Chrome 18.
Ubuntu 12.04: Chrome 18, Firefox 12.
Mac OSX: Someone let me know!

Behavior:
If the logtype is discipline, and there is a VA incident number, perform the
following validation:

Manual entry of the incident number is disabled if the "multiStudent" checkbox
	is not checked, or if "FA2" is not chosen for an offense code.
There must be an incident number if a required offense code is chosen.
There must be an incident number if a sanction code other than 99 is chosen.
There must be a primary incident code.
The incident codes cannot be duplicates.
There cannot be a secondary code without a primary.
There cannot be a tertiary code without a secondary.
There must be a firearm count for firearm related offense codes.
There must be a non-firearms count for non-firearm related weapons codes.
There must be a sanction code.
There must be a sanction code of 4, 5, or 7 for specific offense codes.
Days suspended must be between 1 and 10 for short-term suspension.
Days suspended must be greater than 10 for long-term suspension.
Days suspended must be 365 for expulsion.
Days suspended must be > 0 for sanction code 01.
Days suspended must be 0 for non-OSS sanction codes.
There must be a victim count for specific offense codes.
There must be a time code.
Law enforcement must be "Yes" for specific offense codes.

Changelog:
----------------------13.02.21------------------------
-Fixed: Non-Firearms validation reading wrong input.

----------------------13.02.18------------------------
-Fixed: You are now able to submit a discipline log entry with no state information completed.

----------------------13.02.18------------------------
Version A:
-Bug Squashing: Added code to allow logs other than Discipline to be entered (don't
	validate anything except discipline!).
-Fixed: Incident Number storage. Changed method of preventing manual incident number
	entry. Changed from "disabled" property to "readonly" attribute.
	Was preventing incident number from being submitted with form.

-Changed: ALL validation code has been rewritten using jQuery.
-Removed: customlogentry.html: No longer required to be customized.
-Fixed: Double click prevention now works!
-Added: Merged latest state/CRDC fields. Validation only on state fields.

----------------------12.10.04------------------------

-Added: Checkbox for "VA_Change_Placement" "SPED IEP Change in placement".
-Changed: Wording on "SEP IEP Change in Placement" sanction code. Retired for 11-12 year.
	Left in for legacy log entries.

----------------------12.05.25------------------------

-Added: Disabled manual entry of incident number unless certain conditions are met.
-Changed: Reworked code for use in PowerSchool 7.2 - Disabled PowerSchool
	Loading dialog on submit. Would not go away if validation failed.
	I will try to work this out in a future release.
-Changed: If there is a sanction code other than 99, you must enter an incident number.
-Changed: Victims must be blank if the code does not require a victim count.

----------------------12.05.16------------------------

-Added: Various codes to the victim count validation.

----------------------12.05.14------------------------

-Added: Requires Days suspended for sanction code 01.

-----------------------12.05--------------------------

-Added: Hidden divs around form inputs for displaying errors.
-Added: Javascript validation at bottom of page.
-REMOVED: All Pearson validation from page. Incompatible.
-Replaced: The freeform input of offense codes with select dropdowns.

