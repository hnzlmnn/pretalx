.. _changelog:

Release Notes
=============

- :release:`0.8.0 <2018-09-23>`
- :bug:`-`: When a submission was removed that contained an answered (multiple-) choice question, the selected answer option was removed, too.
- :bug:`501`: When a speaker held more than two talks, their related talks were not linked correctly.
- :bug:`505`: Custom CSS may now also include media queries.
- :bug:`500`: Display of times could be off in the static HTML export.
- :support:`-` The URLs for schedule exports have changed from /myevent/schedule/export?exporter=exportername to /myevent/schedule/export/exportername – if you have hardcoded links to schedule exporters, please update them accordingly.
- :feature:`213` A human-readable time until the CfP closes is now displayed next to the end time.
- :bug:`503` Not all current TLDs were used when processing markdown input to build links.
- :bug:`-`: The schedule import in the organiser backend never worked (while the manage command for administrators did work).
- :feature:`454`: As an organizer, it is now possible to send an email to all reviewers in the Compose Mail section.
- :feature:`492`: In exports, HTTP Etags are now supported to allow for more aggressive caching on clients.
- :bug:`-` If a review question was mandatory while submission questions were active, they would block the submission process.
- :feature:`-` Organisers can now also reset the password for the speakers they have access to.
- :bug:`488` The HTML export contained media files (not other content) from all conferences on an instance, instead of only the exported conference.
- :feature:`-` Present a public list of talks and a list of speakers.
- :bug:`478` The behaviour of pressing enter in multi-step forms was unintuitive in some places.
- :feature:`-` The submission list now includes a graph of submissions over time.
- :feature:`-` The sneak peek / is_featured flag is now shown in the submissions and talk API endpoints.
- :feature:`-` You can now use your authentication token to access all pages you have access to, not only the API. This makes integration of exports much easier.
- :support:`-` All manage commands available in pretalx are now included in the documentation.
- :feature:`240` When using paper cards to build a schedule, each card comes with a QR code link to a quick scheduling form for that submission.
- :feature:`-` Before releasing a new schedule, the user is now shown any warnings and what the public changelog will look like.
- :feature:`214` The schedule editor shows warnings on scheduling conflicts, including live feedback on where a talk can be placed.
- :feature:`474` The review dashboard now features the same search and filter options as the submission list.
- :bug:`473` Following the revamp of team permissions, override votes could no longer be configured. This has been corrected, and the general handling of override votes was improved.
- :support:`-` pretalx now doesn't support usernames any longer – as email addresses were already required for accounts, they are now the only means of logging in. This may confuse a few users – as an administrator, you can look up users' email addresses if they don't remember them, or change them, if necessary.
- :bug:`-` Questions couldn't be deleted, only made inactive.
- :feature:`408` You can now add minimum or maximum length restrictions to abstracts, descriptions, speaker biographies, and all text-based questions.
- :feature:`-` When linking to a talk on social media, the talk image is now shown.
- :feature:`-` French translation
- :feature:`-` The event logo is displayed larger and up to the full width of the document below. Please check that your event still looks as intended after upgrading.
- :feature:`149` Allow to order rooms manually.
- :feature:`149` Allow to order questions manually.
- :support:`-` We now have tests to make sure all config options and plugin hooks are documented.
- :feature:`-` Instead of setting a flag somewhere, pretalx now has an explicit "go live" button. There is also a corresponding signal plugins can listen to (please refer to the plugin documentation for further information).
- :bug:`463` Don't show a 404 error if a reviewer tries to review their own submission, but show an error message instead.
- :feature:`-` For organisers, the submission/talk API endpoints now contain the question answers given by the speakers.
- :feature:`-` Schedules now contain a search bar to filter talks by title or speaker.
- :feature:`-` Schedules now feature a sidebar navigation to jump directly to a selected day.
- :feature:`-` Allow organisers to configure which of the default CfP fields to request and require. Please check your settings after updating, as the migration is not guaranteed to work as expected.
- :feature:`-` Prevent organisers from adding a non-localhost mail server without transport level security to make sure our Privacy Policy holds true.
- :feature:`415` Allow organisers to trigger a password reset for team members.
- :bug:`451` Don't crash during ``pretalx init`` if no conference organiser slug is given.
- :release:`0.7.1 <2018-06-19>`
- :bug:`-` The new read-only links for submissions received the same secret token when migrating the database. No data was leaked as this made using the read-only links impossible. When upgrading to the next release, all read-only link addresses will be reset.
- :bug:`-` A one-character-oversight led to issues with the new navigation search with certain user permissions.
- :release:`0.7.0 <2018-06-19>`
- :feature:`430` To maintain compatability with frab xml exports, a ``<url>`` tag was added to the schedule xml export.
- :bug:`-` When trying to register a user with a nick that already existed in a different capitalization, pretalx failed to show a clear error message.
- :feature:`128` An event's schedule is now available even if the browser has no internet connection, provided it has opened the schedule previously.
- :support:`-` Provide better upgrade documentation for administrators.
- :support:`-` Add clever release notes.
- :bug:`443` (UI) The button colors when changing submission states were very unintuitive.
- :feature:`-` You can now configure the configuration file to be read with the ``PRETALX_CONFIG_FILE`` environment variable.
- :feature:`-` Some more context sensitive dashboard tiles were added, for example a countdown to the CfP end.
- :feature:`-` There is now a navigation search, allowing you to go directly to a range of useful pages.
- :bug:`444` If two organisers set a submission to 'accepted' at roughly the same time, two acceptance emails were put into the outbox.
- :bug:`-` Removing a speaker from a submission could be impossible if their nick contained special characters.
- :feature:`-` Submitters can share a submission via a read-only link.
- :feature:`-` Organisers can configure a list of talks to be shown as "sneak peek" before the first schedule is released.
- :bug:`446` If an event had a custom domain configured, absolute urls would still use the instance's default domain.
- :bug:`441` The "Mark speaker arrived" button is now only shown during and slightly before the event.
- :bug:`-` The API always showed the speaker biography as empty.
- :bug:`-` When accessing a confirmation link unauthenticated, a 404 page was shown instead of a login page.
- :feature:`-` The API now exports links to submission images and speaker avatars.
- :bug:`-` HTML exports failed if a talk was canceled.
- :bug:`-` An issue resulting in an empty HTML export was fixed.
- :release:`0.6.1 <2018-05-15>`
- :bug:`-` The "Copy to draft" button was missing when viewing a sent email.
- :bug:`431` Accepted, but unconfirmed talks were listed as "Other talks" publicly once the speaker had confirmed one talk and the first schedule was released.
- :release:`0.6.0 <2018-05-06>`
- :feature:`-` New plugin hook: ``pretalx.submission.signals.submission_state_change`` is triggered on any state change by a submission.
- :feature:`-` The frab compatible xml was improved by using correct UUIDs, and includes an XML comment with a pretalx version string.
- :feature:`-` The general look and feel and colorscheme has been improved.
- :feature:`-` Organisers can make more changes to speaker profiles and submissions to ease event administration.
- :feature:`-` pretalx now has a concept of organisers and teams.
- :feature:`-` To avoid running into issues when uploading custom CSS, and ensuring smooth operations, custom colors and CSS is not used in the organiser area anymore.
- :feature:`-` You can now send mails from templates and use shortcuts from submissions to send mails to specific speakers.
- :feature:`-` Since different events have different needs, organisers can now choose if submission abstracts, descriptions, and speaker biographies are required for their event.
- :bug:`375` Speakers could see their submission in the orga backend, but could access no information they did not put there themselves.
- :bug:`-` The API showed talks to organisers if no schedule had been released yet. It did not show the information to unauthorised users.
- :bug:`-` There was no possibility to reset a user's API token.
- :bug:`-` If an organiser changed a speaker's email address, they could assign an address already in use in the pretalx instance, resulting in buggy behaviour all around.
- :release:`0.5.0 <2018-03-07>`
- :feature:`-` pretalx now features a Plugin API, allowing to install custom plugins. Plugins can add their own exporters, and hook into various plugin hooks to be expanded over the course of this year. Plugins can be enabled or disabled per event. Documentation can be found here: https://docs.pretalx.org/en/latest/developer/plugins/index.html
- :feature:`340` Organisers can now decide if reviewers should be required to submit a score or a text with their review.
- :feature:`93` Organisers can provide room-based information for speakers, which will be provided in emails about talk scheduling.
- :feature:`318` The list of submissions is now better searchable.
- :feature:`294` Speakers can now upload an image that will be displayed next to their talk information.
- :feature:`-` Reviewers can now also be asked custom questions during their review, with all capabilities that speaker questions have.
- :feature:`352` There are now optional review deadlines, preventing reviews to be added, modified, or removed after a certain date.
- :feature:`-` Individual directories for logs, media, and static files can now be configured via environment variables.
- :feature:`348` Organisers can now show information snippets to submitters, or speakers.
- :feature:`-` Allow to filter question statistics by speaker status.
- :bug:`344` In the dashboard, an incorrect link was given to add new reviewers.
- :bug:`341` The "save" button was missing on the mail settings page.
- :bug:`333` Users could not see (instead not change) their submissions after CfP end, until they were either rejected or accepted.
- :bug:`-` In the <title> tag, the event was displayed twice, once properly and once in a technical representation.
- :bug:`-` Documentation fix: The environment variable for database passwords is ``PRETALX_DB_PASS``, not ``PRETALX_DB_PASSWORD``.
- :bug:`-` Unconfirmed talks showed up as empty boxes in the schedule editor.
- :bug:`-` Upgrading the privileges of an existing user did not result in an email, since no invitation was required.
- :bug:`300` The Docker setup was broken. It is fixed, and a notice of limited support was added to the documentation.
- :bug:`-` The orga view now always uses the event timezone.
- :release:`0.4.1 <2018-02-05>`
- :bug:`335` CfP was uneditable due to missing "Save" button.
- :bug:`336` No new questions could be added due to the wront template being loaded.
- :release:`0.4.0 <2018-02-04>`
- :feature:`-` There is now a page in the organiser area listing and linking all currently possible data exports in one export page.
- :feature:`322` You may now import XML files to release a new schedule.
- :feature:`292` We added a new team management interface to manage all team members and permissions in one place.
- :feature:`-` There is an `init` command for project setup. Currently it only adds the initial user, but in time it should ask for basic configuration, aswell.
- :feature:`-` The `rebuild` command now supports a `--clear` flag to remove all static assets prior to the rebuild.
- :feature:`-` You can choose a pattern for the header hero strip in your event color.
- :feature:`320` You can now choose different deadlines per submission type, overriding the default deadline.
- :feature:`325` All forms are instantly editable if you are allowed to edit them, and disabled otherwise. No more need to click "Edit"!
- :bug:`-` The schedule export could change project settings, requiring pretalx to be restarted to reset the settings. This could be avoided by unchecking "Generate HTML export on schedule release".
- :bug:`259` When running pretalx as (in-application) superuser, permission issues could arise. pretalx now warns and offers to migrate the account to an administrator account.
- :bug:`-` Frontend password validation was broken, and never displayed interactive password statistics. This was a display issue only.
- :bug:`327` We removed the unused `max_duration` property of submission types.
- :bug:`329` Users always saw the default submission type instead of their chosen one.
- :release:`0.3.1 <2018-01-18>`
- :bug:`-` Make various 404 errors more helpful.
- :bug:`-` Re-introduce support for the documented ``PRETALX_DATA_DIR`` environment variable.
- :bug:`-` Leaving an optional choice question empty resulted in a server error.
- :release:`0.3.0 <2018-01-17>`
- :feature:`243` Speakers can now be marked as "arrived".
- :feature:`67` Visitors can download an ical file containing all talks of a single speaker.
- :feature:`-` There is now an API for speakers.
- :feature:`-` The speaker biography is now shown in submissions in the API endpoint.
- :bug:`-` Non-superusers could not access the email sending form.
- :bug:`-` More than one event stage could be shown as active.
- :bug:`-` Trying to look at entered submissions without being logged in produced a server error instead of a 404.
- :bug:`-` If notifications about new submissions were turned on, they were sent to the submitter instead of the organizer.
- :release:`0.2.2 <2017-12-11>`
- :bug:`-` Reviewers could not view speaker pages.
- :bug:`-` Inviting somebody twice did not issue a second invitation object.
- :bug:`-` Somebody who was reviewer first could not be added to the organizer team.
- :release:`0.2.1 <2017-12-06>`
- :feature:`122` Added better meta tags, which leads to better display in social media.
- :bug:`289` Inactive questions could not be deleted (making them active first worked as a workaround).
- :bug:`288` Choice questions could not be deleted as long as they still had answer options.
- :bug:`-` Review team invitations sometimes failed, resulting in useless invitation objects.
- :bug:`-` When clicking the "Save & next" button when reviewing, an internal error was encountered after the review was saved.
- :bug:`-` Reviewers could not be removed from their team.
- :bug:`-` URLs were always generated with 'localhost' as their host.
- :bug:`-` When adding a submission in the orga backend with an orga user as speaker, the orga user did not receive a speaker profile.
- :release:`0.2.0 <2017-12-01>`
- :bug:`-` The default value for email SSL usage is now ``False``, permitting the default configuration of ``localhost:25`` to work on more machines out of the box.
- :feature:`159` E-mails are now sent with a multipart/HTML version, featuring the mail's text in a box, styled with the event's primary color.
- :feature:`126` You can now choose to hide the public schedule (including talk pages and speaker pages, but excluding feedback pages and the schedule.xml export)
- :feature:`215` Mail template placeholders are now validated so that templates including invalid placeholders cannot be saved at all.
- :feature:`208` You can now ask questions that take an uploaded file as an answer.
- :feature:`209` Speakers can now upload files which will be shown on their talk page.
- :feature:`210`, :feature:`195` The review interface has been rewritten to include fewer pages with more information relevant to the user, dependent on event stages and their role in the event.
- :feature:`38` pretalx can now be configured to run with celery (an asynchronous task scheduler) for long running tasks and tasks like email sending. A new config section was added, and usage has been documented.
- :feature:`-` A ``rebuild`` command was introduced that recompiles all static assets.
- :feature:`207` Question answers now receive a nice evaluation, aggregating all given answers.
- :feature:`233` Questions may now be marked as 'answers contain personal data'. Answers of these questions are deleted when users delete their accounts.
- :feature:`78` We moved to a new permission system that allows for more flexible roles. Please report any bugs that may relate to incorrect permissions.
- :feature:`171` You can now configure a custom domain to use with your event, in case you have an event specific domain for each of your events.
- :feature:`156` You can assign "override votes" to reviewers, which function like vetos (both positive and negative), on an individual basis.
- :feature:`-` A read only REST API was introduced. At the moment, it only supports resources for events and submissions.
- :bug:`304` pretalx crashed when an incorrect invite key was used, now it shows a 404 page.
- :bug:`-` When building absolute URLs for exports, emails, and RSS feeds, 'localhost' was used instead of the actual configured URL.
- :bug:`-` If an account was configured to be both an orga member and a reviewer, it encountered access rights issues.
- :bug:`-` When removing the custom event color, and then adding it again, caching issues could be encountered.
- :bug:`-` Inactive questions (questions not shown to speakers) could not be edited.
- :bug:`-` In some places, gravatar images of the visiting user were shown instead of the speaker.
- :bug:`-` The event stage display could show several conflicting phases as active.
- :bug:`287` The default submission type was not, in fact, suggested by default.
- :release:`0.1.0 <2017-11-01>`
