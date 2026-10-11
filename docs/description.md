# Appointment Book – Programme Description

Last updated: 11 October 2026

## Overview

The appointment book (Ordinations-Terminbuch) replaces the paper calendar at reception with a single HTML file that runs in a web browser. It manages appointments of any duration, displays free and booked times at a glance, and requires neither installation nor an internet connection.

The programme is tailored to a practice with few opening days and a long lead time; the default settings are Wednesday and Friday from 08:00 to 13:00. Opening days, times and appointment durations can be freely adjusted, making it suitable for other businesses that operate on an appointment basis.

Key features:

- Month overview for 1 to 12 months, either as occupancy in colour steps or as a timeline per day
- Day sheet showing all appointments and free times for the selected day
- Book, edit, move, insert and remove appointments, including by dragging with the mouse
- Search for the next free appointment and for a patient’s appointments
- Undo function for up to 30 changes
- Name list with suggestions for name, telephone number and notes
- Save day sheets as PDF, Word, Excel, OpenDocument, text or Markdown
- Data file to which every change is automatically saved, with one-click backup
- Interface in German or English, switchable in the settings

## Getting started and requirements

The entire programme consists of the file `Terminbuch.html`. Double-clicking opens it in the browser; there is no installation and no additional files.

- **Browser:** The latest versions of Chrome or Edge are recommended. In Firefox, everything works except the data file and the name file.
- **Internet:** Not required. The file does not download anything from the internet.
- **Device:** Designed for a PC with a mouse at reception. On tablets and mobile phones, the page is displayed in a single column; dragging with the mouse is not possible on these devices.
- **Light and dark modes:** The display follows the operating system’s settings.

In the browser tab, the page displays its own icon: a calendar page with fields in the booking colours; the orange field represents today. The icon is embedded in the HTML file. The same graphic is included as `Terminbuch.ico` for a desktop shortcut.

When first launched, the programme displays fictitious sample data so that a filled-in book can be seen. The ‘Delete sample data’ button in the top bar removes the sample data along with the associated names; the book is then empty and ready for use.

Before the first real appointment, you should set the opening days, times and usual appointment duration under ‘Opening hours, appointment duration and backup’, and select the storage folder. This also creates the data file.

## Interface layout

The page features the overview and tools on the left, and the day sheet for the selected day on the right. The day sheet remains stationary whilst scrolling and has its own scroll bar.

| Section | Where | Content |
| --- | --- | --- |
| Header | top | Name of the practice, opening hours, usual appointment duration, status of the data file and three key figures |
| Month overview | left | Calendar showing the occupancy per day, navigation, number of months, undo |
| Day sheet | right | Appointments and free times for the selected day |
| Find a free appointment | bottom left | The next free appointments from a specified date |
| Find a patient’s appointment | bottom left | Search by name, telephone number or note |
| Save day sheets | bottom left | Saves a period in seven file formats |
| Opening hours, appointment duration and backup | at the very bottom, expandable | Settings, data file, backup, name list |

The three key figures at the top are:

- **Next free appointment:** One click takes you to that day and opens the booking form.
- **Free within 4 weeks:** Number of free appointments of the usual duration in the next 28 days.
- **Appointments from today:** Number of all appointments entered from today onwards.

## Month overview

The month overview shows how full each opening day is and also allows you to select a day. Clicking on a day opens its day sheet.

### How to use

- **Arrows and ‘Today’:** The arrows scroll through the months; ‘Today’ jumps to the current month and the next opening day.
- **Months:** The selection shows 1 to 12 months side by side. Your choice is saved.
- **Occupancy or Timeline:** The toggle switches between the two views.
- **Tooltip on hover:** Hovering the mouse over a day shows the date, opening hours, number of appointments and free appointments.

### ‘Occupancy’ view

Each opening day is colour-coded according to the proportion of opening hours that are booked and displays the number of free appointments.

| Level | Meaning |
| --- | --- |
| empty (white with border) | no appointments booked |
| up to ⅓ | no more than one-third of opening hours booked |
| up to ⅔ | no more than two-thirds booked |
| over ⅔ | more than two-thirds booked, but at least one appointment still free |
| full (darkest level) | no appointment of the usual duration left |

The field displays ‘3 free’ or ‘full’. The programme counts how many times the usual appointment duration still fits into the gaps. In the dark display, the levels are reversed; there, the fullest day is the lightest.

### ‘Timeline’ view

Each day shows its opening hours as a timeline in one to four rows, from early to late. Booked sections are blue, free ones are grey, and the length corresponds to the duration. This shows at what time of day there is still space available.

### Further indicators

- **Calendar week:** Small and grey in the narrow column to the left of each week.
- **Opening days:** Their weekdays are shown in bold in the header row.
- **Closed days:** Hatched with the word ‘closed’, such as public holidays or leave.
- **Today:** An orange dot in the corner of the field.
- **Past days:** Faded.
- **Free in the month:** To the right of the month’s name is the total number of free appointments from today onwards.

### Zooming in on a month

When the selection is set to one month, you can drag the grid at its bottom-right corner with the mouse to enlarge it. Numbers and timelines expand accordingly; the size is saved.

## Day sheet

The day sheet lists all appointments and free times for the selected day in chronological order. Above this are the date, the number of appointments, the number of free appointments and a timeline covering the entire opening hours.

### Free times

Free times are the gaps between appointments. Each gap is divided, starting from its beginning, into pieces of the usual appointment duration.

- If an appointment ends at 15:15, 15:15 is offered as the next free time.
- A remainder shorter than the usual duration appears in the list as ‘free · only 10 min’. It does not count as a free appointment.
- Free times that have already passed are no longer displayed.

### Book an appointment

1. Click ‘Book’ at the desired free time.
2. Enter the name. Known names are suggested, and the telephone number is then filled in automatically.
3. Adjust the start time and duration if necessary. The start time is set in 5-minute increments, and the duration ranges from 5 to 600 minutes. Below this, ‘from 15:00 to 15:15’ is displayed for verification.
4. The telephone number and note are optional. Previously used terms are suggested for the note.
5. Save by clicking ‘Book’ or pressing the Enter key. ‘Cancel’ or Esc discards the entry.

### Checks when saving

- **Overlap:** If the new appointment overlaps with subsequent appointments, it is inserted and the others are pushed back. The programme lists them beforehand; a second click confirms. A start time in the middle of an ongoing appointment is rejected.
- **Outside opening hours, a closed day or in the past:** A warning appears. Clicking the save button a second time books the appointment anyway. If the date, start time and duration remain the same when editing, there is no warning.
- **Past midnight:** This is rejected.

### Changing an appointment or moving it to another day

‘Edit’ opens the appointment showing the name, date, start time, duration, telephone number and note.

- You can type in the new date or select it by clicking on a day in the month overview. The target day is outlined in orange with a dotted line.
- The free times of the target day are listed below the form. Clicking on one takes over that time.
- After saving, the day sheet shows the target day.
- Whilst the form is open, clicking in the month overview selects the target date and does not change the day.

### Removing an appointment

‘Remove’ requires confirmation with ‘Really remove’. The appointment is then deleted and its time reappears as free in the list and in the overview.

### Closing days and extra days

The button at the bottom of the day sheet changes the status of the day.

| Initial status | Button | Effect |
| --- | --- | --- |
| Opening day | Close day | No more free times, e.g. for leave or training |
| Manually closed day | Reopen day | The day counts as an opening day again |
| Public holiday or other weekday | Open as extra day | The day gets opening hours on a one-off basis |
| Extra day | Close extra day again | The day is closed again |

An extra day takes the opening hours of the first opening day in the settings. If appointments are still booked on a closed day, they are kept and the day sheet points this out.

## Moving appointments with the mouse

Any appointment in the day sheet can be grabbed with the mouse and dragged onto a free time, another appointment or a different day. All other appointments retain their entries, provided there is sufficient space.

### Onto a free time on the same day

- **The appointment fits into the gap:** It is moved there immediately.
- **The gap is too short:** A warning appears listing the affected appointments and their new times. ‘Continue’ carries out the move, whilst ‘Cancel’ leaves everything as it was.

If you continue, the following appointments are only moved back as far as necessary. Example: A 15-minute appointment is dragged onto a free time of 10 minutes; the following appointments are pushed back by 5 minutes. If there is a gap afterwards, it absorbs the difference and later appointments remain in their original positions.

Two special cases:

- If the last moved appointment would end after closing time, this is also stated in the warning.
- If appointments would be pushed past midnight, the move is rejected.

### Inserting between two appointments

If an appointment is dragged onto another appointment, it is inserted before it. A blue line above the target appointment indicates the insertion point.

The target appointment and the appointments immediately following it are moved back by the duration of the inserted appointment until a gap accommodates the difference. Before the change is applied, a prompt lists all the new times and asks you to ‘Continue’.

Example: A 15-minute appointment is dragged onto the 08:30 appointment. It is set to 08:30, the previous appointment moves to 08:45 and the next one moves from 09:00 to 09:15.

A new appointment can be inserted in exactly the same way. The ‘+ before’ button in an appointment’s row opens the form with its start time. When saving, the programme lists the appointments that will be pushed back, and a second click confirms the change.

### To another day

If an appointment is dragged to a specific day in the month overview, the edit form opens with that date and the free times of the target day. The change is only saved by clicking ‘Save’.

Appointments on past dates cannot be dragged. On devices without a mouse, use the ‘Edit’ option.

## Finding a free appointment and patient search

### Finding a free appointment

This tool lists the next eight free appointments of the usual duration from a given date. It is intended for follow-up appointments with a long lead time.

- The buttons ‘from today’, ‘in 1 month’, ‘in 2 months’, ‘in 3 months’, ‘in 4 months’ and ‘in 6 months’ set the start date.
- Any other date can be selected in the ‘Not before’ field.
- Clicking on a result takes you to that day and opens the booking form.
- The search looks up to 18 months in advance.

### Finding a patient’s appointment

The search finds appointments by name, telephone number or note and starts with as few as two letters. It is helpful when someone calls and cannot remember their appointment.

- Up to twelve results are displayed, showing the date, time and name.
- Upcoming appointments appear at the top; past appointments appear at the bottom marked ‘past’.
- Clicking on a result opens the day sheet for that day.

## Undo

The ‘↶ Undo’ button reverses up to 30 changes one step at a time. The number in brackets shows how many steps are possible; Ctrl+Z works in the same way.

The following actions can be undone:

- Booking, editing, moving, inserting and removing appointments
- Closing and opening days
- Changes to opening hours, appointment duration, public holiday rules and name
- Changes to the name list
- Restoring a backup, loading the version from the data file and deleting the sample data

The view itself is not included – i.e. language, display, number of months and zoom level. The list of steps only applies whilst the page is open. Ctrl+Z does not work whilst the cursor is in an input field.

## Name list and name file

The programme remembers the name, telephone number and note for each saved appointment and suggests them the next time you enter an appointment. The list can be found in the settings under ‘Name list’.

### Suggestions when entering data

- Matching names appear in the ‘Name’ field as soon as you start typing.
- If a recognised name is selected, the programme inserts the saved telephone number.
- A newly entered telephone number replaces the saved one.
- Previously used terms appear in the ‘Note’ field.

### Managing the list

| Button | Effect |
| --- | --- |
| Delete single entries | Opens the list with a search field. For each row, you can delete the name or just its telephone number; below that, each note term. |
| Save name list | Saves the list to the file `terminbuch-namen.json`. |
| Import name list | Imports such a file and adds it to the existing list. |
| Clear list | Removes all names and note terms. |

Any deletion can be undone using ‘Undo’. Booked appointments remain unaffected by the deletion of a name.

### Name file: automatic saving and importing

Select a JSON file once using ‘Connect name file’. The programme will then automatically save every change to the list to this file and import it on start-up.

- **Permission:** The browser will request permission to access the file the next time it is launched. A bar will then appear at the top with an ‘Allow access’ button. From Chrome 122 onwards, the prompt also offers the option to allow access on every visit.
- **Merging:** When the file is imported, it is merged with the list; no names are lost.
- **Protection of other files:** A file with different content is rejected and not overwritten.
- **Disconnect:** ‘Disconnect’ stops automatic saving. The file is retained.

This feature is only available in Chrome and Edge with the local file. In other browsers, a message appears instead; manual saving and importing remain possible. The name list is also contained within the data file. A separate name file is only necessary if the list is needed on its own.

## Saving day sheets

This tool writes the day sheets for a selected period to a file, for printing, filing or sharing. It includes all opening days within the period and closed days on which appointments are scheduled.

1. Select the period under ‘From’ and ‘To’ (maximum 400 days). The default setting is today and the following 14 days.
2. Select the format.
3. If required, tick ‘Include free times’. Consecutive free times then appear as a single row.
4. Click ‘Save’. The file is saved to the storage folder. If none is selected, it will be saved to the browser’s downloads folder.

‘Selected day only’ sets both date fields to the day currently open in the day sheet.

| Format | File extension | Structure |
| --- | --- | --- |
| PDF | .pdf | A4, one heading per day with a table, page numbers. Very long names and notes are truncated. |
| Word | .docx | One heading per day with a table |
| OpenDocument Text | .odt | One heading per day with a table |
| Excel | .xlsx | One sheet ‘Appointments’, one row per appointment, with date and time as real date and time values |
| OpenDocument Spreadsheet | .ods | One sheet ‘Appointments’, one row per appointment |
| Text | .txt | Fixed-width columns |
| Markdown | .md | Headings and tables in Markdown |

PDF, Word, OpenDocument Text, Text and Markdown include the columns Start, End, Duration, Name, Phone and Note. The spreadsheet formats also include Date and Weekday, so that the list can be sorted and filtered.

With the English interface the file name is `daysheets_FROM_to_TO` with the relevant file extension, for example `daysheets_2026-10-19_to_2026-10-30.pdf`. With the German interface it is `tagesblaetter_VON_bis_BIS`.

## Settings

All settings are located in the drop-down section ‘Opening hours, appointment duration and backup’ at the end of the left-hand column. Any changes take effect immediately and can be undone.

| Setting | Values | Effect |
| --- | --- | --- |
| Sprache / Language | Deutsch or English | Language of the entire interface and the saved day sheets |
| Name in header | Free text, up to 60 characters | Page header and title of the saved day sheets |
| Usual appointment duration | 5, 10, 15, 20, 30, 45 or 60 minutes | Duration in which free times are offered and counted. Default setting for new appointments. |
| Opening days | Monday to Sunday, start and end times for each day | Specifies on which days of the week and at what times appointments are offered |
| Close Austrian public holidays automatically | on or off | Closes the 13 statutory public holidays |

Notes:

- **Changed opening hours:** Appointments already entered will remain, even if they subsequently fall outside the opening hours. The timelines will then show the extended range.
- **Changed appointment duration:** This only affects how free times are offered. Appointments already entered retain their duration.
- **Public holidays:** The following are included: New Year’s Day, Epiphany, Easter Monday, Labour Day, Ascension Day, Whit Monday, Corpus Christi, Assumption Day, National Day, All Saints’ Day, Immaculate Conception, Christmas Day and St. Stephen’s Day. An individual public holiday can be opened as an extra day in the day sheet.
- **Validation:** If the end of a day does not come after its start, the entry will be rejected with a message.

### Language

The interface is available in German and English. On first launch, the browser’s language is used: German for a German browser, otherwise English. You can switch the language in the settings under ‘Sprache / Language’; the change takes effect immediately and is saved.

| Area | What changes with the language |
| --- | --- |
| Interface | all labels, notes and messages |
| Date | Days of the week and months, including the notation: ‘Mi 21.10.2026’ becomes ‘Wed 21 Oct 2026’ |
| Public holidays | the names of the 13 Austrian public holidays, such as ‘Christtag’ and ‘Christmas Day’ |
| Day sheets | Headings and columns in all seven formats. The file name in English is `daysheets_FROM_to_TO` |
| Sample data | Notes and the default name in the header, provided the sample data has not been deleted |

The following remain the same in both languages:

- names, telephone numbers and notes you have entered, and a name in the header you have chosen yourself
- the file names `terminbuch-daten.json`, `terminbuch-namen.json` and those of the backups
- times in 24-hour format and the week from Monday to Sunday
- the public holiday rule, which always refers to Austria

If two PCs are using the same data file, each browser retains its own language. A language change cannot be undone using ‘Undo’; simply selecting the language is sufficient.

The most important terms in both languages:

| German | English |
| --- | --- |
| Ordinationstage | Opening days |
| Tagesblatt | Day sheet |
| Auslastung, Zeitfenster | Occupancy, Timeline |
| Eintragen, Ändern, Absagen | Book, Edit, Remove |
| + davor | + before |
| Tag sperren, Zusatztag | Close day, Extra day |
| Übliche Termindauer | Usual appointment duration |
| Speicherordner, Datendatei | Storage folder, Data file |
| Sicherung, Namensliste | Backup, Name list |
| Rückgängig | Undo |

## Data storage and backup

The programme saves automatically after every change; there is no save button. Data is always saved to the browser’s internal memory and additionally to the data file, provided one is connected.

The following are saved: appointments, closed days and extra days, settings, the name list, as well as language, display, number of months and zoom level.

### Storage folder

The storage folder determines where the programme saves its files. We recommend the folder containing the `Terminbuch.html` file, for example `D:\Terminbuch`.

1. Click on ‘Set up storage’ in the header. The settings will expand to show the folder containing the HTML file.
2. Click on ‘Choose storage folder’ and choose this folder.
3. If no data file is linked yet, the programme will create `terminbuch-daten.json` there or open the existing one.

| File | Created by | File name |
| --- | --- | --- |
| Data file | every change, automatically | `terminbuch-daten.json` |
| Backup | ‘Create backup’ | `terminbuch-YYYY-MM-DD_HHMM.json` |
| Name list | ‘Save name list’ | `terminbuch-namen.json` |
| Day sheets | ‘Save’ under ‘Save day sheets’ | `daysheets_FROM_to_TO` with extension |

Notes:

- If no storage folder is specified, the backup, name list and day sheets will be saved in the browser’s downloads folder.
- A browser does not automatically recognise the folder for an HTML file, so it must be selected once.
- The first time you save after launching the application, the browser will ask for permission to access the folder.
- A file with the same name will be overwritten. Backups therefore include the date and time in their filenames.
- The browser does not allow certain folders. A dedicated subfolder will work.
- The storage folder is only available in Chrome and Edge with the local file.

### Data file

The data file is a standard JSON file containing the entire appointment book, for example `terminbuch-daten.json`, stored in a folder on your PC or on a network share. This is the recommended place to keep the data when used in a practice.

- Any standard data backup will include this file.
- The appointments will survive the deletion of browser data and a change of browser.
- To move to another PC, simply open the file there.

Set-up:

1. The simplest method is to select the storage folder. The data file will then be created automatically in this folder.
2. If you want it to be located elsewhere, such as on a network share, select ‘Create new data file’ in the settings and specify the folder and name. The current data will be saved there immediately.
3. On another PC or following a fresh installation, select ‘Open existing data file’ instead.

The current status will then be displayed in the line below the opening hours, for example ‘Data file terminbuch-daten.json · last saved at 09:58:12’. Selecting ‘Disconnect’ in the settings stops automatic saving, but the file is retained.

### Synchronisation between file and browser

On start-up and before every save, the programme checks whether the file has been modified elsewhere in the meantime.

| Situation | What the programme does |
| --- | --- |
| File and browser are the same | Nothing; the header displays ‘up to date’ |
| The file has been changed elsewhere, but not here | The version from the file is applied |
| Changes made only here | The version here is written to the file |
| Both have been changed | Auto-save pauses. A red bar displays the number of appointments on both sides and asks which version should be used. |
| The browser is empty or displays sample data; the file contains an appointment book | The file is applied without prompting |
| The file contains something other than an appointment book | It is rejected and not overwritten |
| The file is inaccessible | A message appears. The changes remain in the browser and will be applied the next time you save. |

The bar offers ‘Load the version from the file’ and ‘Overwrite the file with the version here’. It remains visible whilst scrolling. Loading from the file can be undone using ‘Undo’.

### Browser permission

The next time the browser is launched, it will request permission to access the file. A bar will then appear at the top with the option ‘Allow access’; until then, data is only saved within the browser. From Chrome 122 onwards, the prompt also offers the option to allow access on every visit.

The data file is only available in Chrome and Edge with the local file `Terminbuch.html`.

### Without a data file

- The data is tied to this specific browser. In another browser or on another computer, the book will be empty.
- Deleting the website data in the browser will also delete the appointment book.
- Regular backups are therefore essential, ideally at the end of each day’s practice.

### Creating and restoring a backup

| Button | Effect |
| --- | --- |
| Create backup | Writes all data to the file `terminbuch-YYYY-MM-DD_HHMM.json` in the storage folder; if no storage folder exists, it is saved in the downloads folder |
| Restore backup | Replaces the entire current state with the contents of the selected backup file |

Restoring can be undone using ‘Undo’ as long as the page remains open. A file that is not an appointment book backup will be rejected.

If using a data file, it is sufficient to include this file in your usual data backup. The one-click backup is intended for creating a dated copy, for example before making major changes.

## Limits

In testing, the programme handles around 60,000 appointments; there is no built-in upper limit. The limit is set by the browser’s internal memory, which can hold around 5 million characters.

| Item | Value |
| --- | --- |
| Total appointments | around 60,000 in testing, for entries with name, telephone number and note |
| Appointments per day | up to 288, comprising 5-minute appointments spread over 24 hours. Up to 60 during a 5-hour opening period. |
| Duration of an appointment | 5 to 600 minutes in 5-minute increments |
| Start time of an appointment | 5-minute intervals |
| Usual appointment duration | 5, 10, 15, 20, 30, 45 or 60 minutes |
| Opening hours | one continuous time window per weekday, on up to 7 weekdays |
| Name, telephone number, note | 80, 40 and 120 characters |
| Name in header | 60 characters |
| List of names | No fixed limit. The maintenance list displays 300 entries per search. |
| Undo | 30 steps |
| Months in the overview | 1 to 12 |
| Find a free appointment | 8 results, up to 18 months in advance |
| Patient search | 12 results displayed |
| Save day sheets | Period up to 400 days |

For context:

- **Storage requirements:** 1,000 appointments take up around 82,000 characters. With two opening days per week and ten appointments each, that amounts to approximately 1,000 appointments per year.
- **Speed:** With 50,000 appointments, saving took 38 milliseconds and displaying took 21 milliseconds.
- **Old appointments:** These are retained and are never automatically deleted.
- **Full storage:** A red bar appears to indicate when the browser can no longer save data. Data continues to be written to a linked data file.

Measurements were taken in a Chromium-based test browser. Similar values can be expected in Chrome and Edge, though they may vary depending on the version.

## Limitations and notes on use

The appointment book is a single-user programme designed solely for booking appointments. The following points should be noted before using it in a practice.

### What the programme cannot do

- **No multi-user operation:** Two PCs cannot work on the same appointment book simultaneously. If the data file is stored on a shared drive, they can do so one after the other. Simultaneous changes are detected and reported, but are not merged.
- **No password, no encryption:** Anyone with access to the PC and the browser can view the appointments. The backup file is also unencrypted.
- **No online booking and no reminders:** Patients cannot book appointments themselves; the programme sends neither text messages nor emails.
- **No recurring appointments:** Recurring appointments must be entered individually.
- **No patient records and no billing:** Only the name, telephone number and a brief note are stored.

### Data protection

Patients’ names, telephone numbers and appointments constitute personal data. The computer should have a dedicated user account with a password, and backups as well as saved day sheets should be kept in a secure location. The legal assessment is the responsibility of the practice.

### Test status

- All functions were tested in a Chromium-based test browser.
- The seven file formats were opened and checked using LibreOffice and other tools. Testing with Microsoft Word and Excel was not carried out.
- The storage folder, data file and name file were tested using dummy files. The actual file dialogue in Chrome and Edge has not yet been tested.
- The English interface was tested through all workflows on 11 October 2026, including the seven file formats. No German text remained. The German interface subsequently delivered the same results as before.
- A trial run over a few days at the practice, alongside the paper calendar, is recommended before the paper calendar is phased out.

A review of the entire programme code on 9 October 2026 revealed six weaknesses, which have been fixed:

- A full or blocked browser storage was not reported. A red bar now appears.
- Two open windows of the same appointment book could overwrite each other. Each window now adopts the changes made in the other.
- If the browser revoked permission for the data file or name file, the button to re-grant permission was missing.
- Changing the view was treated as a data change and could trigger an unnecessary prompt when synchronising with the data file.
- In the PDF, letters such as Š, č or ő were replaced by question marks. Now Š is retained, whilst č and ő appear as c and o.
- Changing the telephone number or note for a past appointment required an unnecessary confirmation.

### Keyboard

| Key | Effect |
| --- | --- |
| Enter key | Saves the open appointment form |
| Esc | Closes the form, the removal prompt or the move warning |
| Ctrl+Z | Undoes the last change |