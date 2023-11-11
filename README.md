# ITD121_CanvasProject
This C# project is a structured drawing system which allows people to create, edit, and preview simple structured drawings. A canvas is rendered in the terminal console.

Task
This assignment aims to give you experience working on a simplified but realistic problem, of the kind you will encounter in the workplace.

In this assignment you develop a prototype of a structured drawing system which allows people to create, edit, and preview simple structured drawings. The system represents a minimum viable product which is not expected to include all aspects of the final working solution. Ultimately it is planned to incorporate the present system in a social media application which provides an image creation and sharing platform for creators, but the present version is limited to a single user scenario designed for personal use.

Your task is to apply object-oriented design and programming techniques to create a well-documented and easy to maintain software solution that achieves the user stories listed below, showcasing best-practice application of the software engineering principles and techniques covered in this unit.

Note: some stories are marked as “optional’. You are encouraged to try to implement them, however it is possible to obtain full marks without implementing optional stories. If the situation arises where your implementation of another feature is incomplete or defective, and you have implemented an optional feature, then the implementation of the optional feature will be taken into account.

User Stories
1.       Story: As the platform owner, I want to the system to provide a simple text-based user interface so it will be easy for me to test the system and easy to convert to a rich internet application in future versions.

Acceptance Criteria:

·         When the program starts, a Main Menu dialog is displayed, with the following options:

Command

Action

New

Create new drawing

Open

Open existing drawing (optional)

Edit

Edit drawing

Save

Save drawing (Optional)

Save as

Save drawing to new file (Optional)

Close

Exit from the system by returning from Main.

DO NOT USE Environment.Exit().

 

·         The user is required to supply a validated command, and the system takes subsequent action as appropriate.

·         All subsequent actions apart from Close will be mediated by similarly structured menus, or by “question/answer/validation” style dialogs.

·         When Close is selected, the program terminates gracefully.

·         Other selections are dealt with as indicated in the following stories.

2.      Story: As an image creator, I want to create a new drawing so I can expand my portfolio.

Acceptance Criteria:

·         A New Drawing dialog (available as an option on the Main Menu) allows the user to set the state of the current drawing to an “as new” state.

·         If the current drawing has changed since it was opened or saved:

o   The user is asked if they want to discard their changes.

o   If they do not want to lose their work, then the operation is cancelled.

·         If the operation is not cancelled, the current drawing is reset to an empty state, and the name is reset back to “UnnamedDrawing.txt”.

·         Control returns to the main menu.

3.      Story: As a user of the system, I want to open an existing drawing defined in a text file so that I can view and edit the drawing.

Acceptance criteria:

·         This operation is optional, however if correctly implemented it will compensate for errors which may exist elsewhere in the submission.

·         If the current drawing has changed since it was opened or saved:

a.      The user is asked if they want to discard their changes.

b.      If they do not want to lose their work, then the operation is cancelled.

·         If the operation is not cancelled:

a.      The current drawing is reset to an empty state.

b.      A File Open dialog (available as an option on the Main Menu) allows the user to enter the path to a file which contains a drawing definition.

c.      If the supplied path does not correspond to an existing file, then the message “File does not exist” is displayed.

d.     Otherwise, the program should attempt to parse a set of drawing instructions from the designated file. You are at liberty to take whatever action you wish in the event that an error occurs while parsing the file.

·         Control subsequently returns to the Main Menu.

4.      Story: As a user of the system, I want to edit the current drawing so I can express my design in a precise but creative way.

Acceptance criteria:

·         An Edit menu (available as an option on the Main Menu) allows the user to view and modify the current drawing, providing the following options:

Command

Action

Point

Add point to drawing

Line

Add line to the drawing

Text

Add text to drawing

Preview

Preview the drawing

List

List elements in the drawing

Delete

Delete element from drawing

Return

Return to previous menu

 

5.      Story: As a user of the system, I want to save the current drawing so I can view it later.

Acceptance Criteria:

·         A Save Dialog (available as an option on the Main Menu) allows the user to save the current drawing to the file specified by the current name

·         If the drawing is new – that is, the drawing name is “UnnamedDrawing.txt” – then control redirects to the next story (Save as) to obtain a new name.

·         Otherwise, the drawing is saved to the file specified by the current name.

·         The user is notified about the outcome of the attempted file save operation.

6.      Story: As a user of the system, I want to save the current drawing to a newly specified file so I can view it later.

Acceptance Criteria:

·         A Save As Dialog (available as an option on the Main Menu) allows the user to specify a new file name – something other than “UnnamedDrawing.txt” – and save the current drawing to that file.

o   Do not modify the supplied file name in any way, because doing so will almost certainly cause subsequent file system interactions to fail.

·         The user is notified about the outcome of the attempted file save operation.

7.      Story: As a client I want to be able to log out from the system so that the next person to use the system cannot access my private records or conduct transactions using my account.

Acceptance Criteria:

·         A Close option is available in the Main Menu.

·         When selected, the program exits gracefully.

8.     Story: As an artist, I want to add points to the current drawing so I can illustrate fine details.

Acceptance Criteria:

·         An Add Point Dialog (available as an option from the Edit Menu) allows the user to specify the location and symbol used to display a point, and if the drawing contains at least one drawing element, the position where the point is to be inserted in the list of drawing elements in the drawing.

·         The location is a pair of integers which specify the horizontal and vertical offset of the symbol, relative to the top-left corner of the display.

o   Integer values are read one at a time and validated via a retry loop.

·         The symbol is a single character obtained from the standard input stream.

o   Non-printable characters such as tab and backspace must be detected and rejected via a retry loop.

o   If the user enters multiple characters, then the first non-blank character in the input is selected. If the input contains no non-blank characters, then a space character – (char) 32 – is selected.

·         The position is an integer which must be greater than or equal to zero and must not be greater than the number of elements in the drawing plus one.

o   If the drawing contains no drawing elements, then the only valid insertion position is zero, so the program should not request the position from the user. The new element will be inserted into the drawing at position zero.

o   Integer values are validated and constrained to be within the legal range via a retry loop.

o   The user may enter a blank value to indicate that the new drawing element is to be appended to the drawing after all existing elements.

·         A drawing element representing the designated point is inserted into the list of drawing elements at the stipulated position.

9.      Story: As an artist, I want to add lines to the current drawing so I can illustrate large-scale shapes.

Acceptance Criteria:

·         An Add Line Dialog (available as an option from the Edit Menu) allows the user to specify the endpoints and symbol used to display a line, and if the drawing contains at least one drawing element, the position where the line is to be inserted in the list of drawing elements in the drawing.

·         The endpoints are pairs of integers which specify the extent of the line, relative to the top-left corner of the display.

o   Integer values are read one at a time and validated via a retry loop.

·         The symbol is a single character obtained from the standard input stream.

o   Non-printable characters such as tab and backspace must be detected and rejected via a retry loop.

o   If the user enters multiple characters, then the first non-blank character in the input is selected. If the input contains no non-blank characters, then a space character – (char) 32 – is selected.

·         The position is an integer which must be greater than or equal to zero and must not be greater than the number of elements in the drawing plus one.

o   If the drawing contains no drawing elements, then the only valid insertion position is zero, so the program should not request the position from the user. The new element will be inserted into the drawing at position zero.

o   Integer values are validated and constrained to be within the legal range via a retry loop.

o   The user may enter a blank value to indicate that the new drawing element is to be appended to the drawing after all existing elements.

·         A drawing element representing the designated line is inserted into the list of drawing elements at the stipulated position.

10.  Story: As an artist, I want to add text to the current drawing so I can use labels to add descriptive information to my diagrams.

Acceptance Criteria:

·         An Add Text dialog (available as an option from the Edit Menu) allows the user to specify the location and text used to display a label, and if the drawing contains at least one drawing element, the position where the label is to be inserted in the list of drawing elements in the drawing.

·         The location is a pair of integers which specified the start of the label, relative to the top-left corner of the display.

o   Integer values are read one at a time and validated via a retry loop.

·         The text is a sequence of characters entered as a single line obtained from the standard input stream.

o   Non-printable characters such as tab and backspace must be detected and replaced by space characters.

·         The position is an integer which must be greater than or equal to zero and must not be greater than the number of elements in the drawing plus one.

o   If the drawing contains no drawing elements, then the only valid insertion position is zero, so the program should not request the position from the user. The new element will be inserted into the drawing at position zero.

o   Integer values are validated and constrained to be within the legal range via a retry loop.

o   The user may enter a blank value to indicate that the new drawing element is to be appended to the drawing after all existing elements.

·         A drawing element representing the designated label is inserted into the list of drawing elements at the stipulated position.

11.   Story: As an artist working on a drawing, I want to preview the drawing so I can verify that it meets my expectations.

Acceptance Criteria:

·         A Preview dialog (available as an option from the Edit Menu) uses Graphics.cs to display the current drawing in the terminal window.

·         Drawing elements should be rendered according to their insertion position in the list. Elements with higher positions are rendered after those with lower positions, so if two elements overlap, the element with highest position is displayed over the top of the other.

·         The image is displayed until the user presses the Enter key. A prompt to this effect is added to the display in the lower left corner.

12.  Story: As an artist working on a drawing, I want to list the elements of the drawing in text format so I can see the detailed list of elements and find out the position of each element.

Acceptance Criteria:

·         A List dialog (available as an option from the Edit Menu) displays a numbered list including all drawing elements.

·         Element numbers start at 0.

13.  Story: As an artist working on a drawing, I want to be able to delete elements from the drawing so I can refine my ideas as I work.

Acceptance Criteria:

·         A Delete dialog (available as an option from the Edit Menu) interacts with the user to delete one of the existing elements from the drawing.

·         If the drawing contains no elements, then the user is notified accordingly, and control returns immediately to the Edit menu.

·         The position of the element which is to be removed is an integer which must be greater than or equal to zero and less than the number of elements in the drawing.

o   If the drawing contains exactly one element, then the only valid removal position is zero, so the program should not request the position from the user. The element at position zero will be removed from the drawing.

o   Integer values are validated and constrained to be within the legal range via a retry loop.

o   The user may enter a blank value to indicate that the last element in the drawing must be deleted.

·         The designated element is removed from the current drawing.

14.  Story: As a user of the system, I want to leave the Edit menu and return to the Main Menu.

Acceptance Criteria:

·         A Return option on the Edit menu takes the user back to the main menu.

User Interface
The company has plans to eventually develop a graphical user interface for this application, however, this prototype implementation will have a simple text-based interface.

Functionality will be assessed via a suite of MS-Test unit tests which will be provided at least 21 days prior to submission deadline.

The user interface of your solution must adhere strictly to the structure, format, and wording of all user interface elements as they appear in the unit tests.

Any divergence will adversely affect your score.

What to Submit
Submit a single ZIP archive containing all source files required to run your program via the supplied link in Canvas.

How to Submit
Submission will be carried out using the AMS system. Functionality of your program will be automatically assessed by AMS. Other aspects of the program will be assessed by teaching staff in the traditional manner.

Academic Integrity
Please read and follow the guidelines in QUT’s Academic Integrity Kit, which is available from the Blackboard site on the Assessment page. Programs submitted for this assignment will be analysed by the MoSS (Measure of Software Similarity) plagiarism detection system (http://theory.stanford.edu/~aiken/moss/).

Final Comment
All care has been taken in the production of this specification and related documentation, but as the assignment progresses the need for updates may arise. Updates will be publicised via Slack and email.

Appendix 1: Transcript
Lawrence@Lawrence-PC /w

$ dotnet run

Welcome to the Simple Drawing Editor!

 

Main menu - please select an option

 

New     -> Create new drawing

Open    -> Open existing drawing

Edit    -> Edit drawing

Save    -> Save drawing

Save as -> Save drawing as ...

Close   -> Exit from system

? edit

 

Editing drawing UnnamedDrawing.txt

 

Point   -> Add point to drawing

Line    -> Add line to drawing

Text    -> Add text to drawing

Preview -> Preview drawing

List    -> List elements in drawing

Delete  -> Delete element from drawing

Return  -> Return to previous menu

? point

 

Add point to drawing:

 

X: 1

Y: 2

Symbol: 3

 

Editing drawing UnnamedDrawing.txt

 

Point   -> Add point to drawing

Line    -> Add line to drawing

Text    -> Add text to drawing

Preview -> Preview drawing

List    -> List elements in drawing

Delete  -> Delete element from drawing

Return  -> Return to previous menu

? return

 

Main menu - please select an option

 

New     -> Create new drawing

Open    -> Open existing drawing

Edit    -> Edit drawing

Save    -> Save drawing

Save as -> Save drawing as ...

Close   -> Exit from system

? new

 

Edits have been made to the current drawing.

 

Do you want to discard them?

 

Yes -> Discard changes

No  -> Cancel

? yes

        Drawing successfully created!

 

Main menu - please select an option

 

New     -> Create new drawing

Open    -> Open existing drawing

Edit    -> Edit drawing

Save    -> Save drawing

Save as -> Save drawing as ...

Close   -> Exit from system

? edit

 

Editing drawing UnnamedDrawing.txt

 

Point   -> Add point to drawing

Line    -> Add line to drawing

Text    -> Add text to drawing

Preview -> Preview drawing

List    -> List elements in drawing

Delete  -> Delete element from drawing

Return  -> Return to previous menu

? list

 

Drawing contains the following elements:

 

Shape

End Shape

 

Editing drawing UnnamedDrawing.txt

 

Point   -> Add point to drawing

Line    -> Add line to drawing

Text    -> Add text to drawing

Preview -> Preview drawing

List    -> List elements in drawing

Delete  -> Delete element from drawing

Return  -> Return to previous menu

?

        Invalid option, please try again

 

Editing drawing UnnamedDrawing.txt

 

Point   -> Add point to drawing

Line    -> Add line to drawing

Text    -> Add text to drawing

Preview -> Preview drawing

List    -> List elements in drawing

Delete  -> Delete element from drawing

Return  -> Return to previous menu

? preview

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

Press enter to continue ...

 

 

Editing drawing UnnamedDrawing.txt

 

Point   -> Add point to drawing

Line    -> Add line to drawing

Text    -> Add text to drawing

Preview -> Preview drawing

List    -> List elements in drawing

Delete  -> Delete element from drawing

Return  -> Return to previous menu

? point

 

Add point to drawing:

 

X: 9

Y: 9

Symbol: W

 

Editing drawing UnnamedDrawing.txt

 

Point   -> Add point to drawing

Line    -> Add line to drawing

Text    -> Add text to drawing

Preview -> Preview drawing

List    -> List elements in drawing

Delete  -> Delete element from drawing

Return  -> Return to previous menu

? preview

 

 

 

 

 

 

 

 

 

         W

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

Press enter to continue ...

 

 

Editing drawing UnnamedDrawing.txt

 

Point   -> Add point to drawing

Line    -> Add line to drawing

Text    -> Add text to drawing

Preview -> Preview drawing

List    -> List elements in drawing

Delete  -> Delete element from drawing

Return  -> Return to previous menu

? line

 

Add line to drawing:

 

Start X: 1

Start Y: 1

End X: 19

End Y: 19

Symbol: O

Position (0 .. 1, blank == after last element): 0

 

Editing drawing UnnamedDrawing.txt

 

Point   -> Add point to drawing

Line    -> Add line to drawing

Text    -> Add text to drawing

Preview -> Preview drawing

List    -> List elements in drawing

Delete  -> Delete element from drawing

Return  -> Return to previous menu

? preview

 

 O

  O

   O

    O

     O

      O

       O

        O

         W

          O

           O

            O

             O

              O

               O

                O

                 O

                  O

                   O

 

 

 

 

 

 

 

 

Press enter to continue ...

 

 

Editing drawing UnnamedDrawing.txt

 

Point   -> Add point to drawing

Line    -> Add line to drawing

Text    -> Add text to drawing

Preview -> Preview drawing

List    -> List elements in drawing

Delete  -> Delete element from drawing

Return  -> Return to previous menu

? line

 

Add line to drawing:

 

Start X: 19

Start Y: 1

End X: 1

End Y: 19

Symbol: _

Position (0 .. 2, blank == after last element): 3

Please supply a whole number between 0 and 2

Position (0 .. 2, blank == after last element): -1

Please supply a whole number between 0 and 2

Position (0 .. 2, blank == after last element): 1

 

Editing drawing UnnamedDrawing.txt

 

Point   -> Add point to drawing

Line    -> Add line to drawing

Text    -> Add text to drawing

Preview -> Preview drawing

List    -> List elements in drawing

Delete  -> Delete element from drawing

Return  -> Return to previous menu

? list

 

Drawing contains the following elements:

 

Shape

Line    1       1       19      19      O

Line    19      1       1       19      _

Point   9       9       W

End Shape

 

Editing drawing UnnamedDrawing.txt

 

Point   -> Add point to drawing

Line    -> Add line to drawing

Text    -> Add text to drawing

Preview -> Preview drawing

List    -> List elements in drawing

Delete  -> Delete element from drawing

Return  -> Return to previous menu

? preview

 

 O                 _

  O               _

   O             _

    O           _

     O         _

      O       _

       O     _

        O   _

         W _

          _

         _ O

        _   O

       _     O

      _       O

     _         O

    _           O

   _             O

  _               O

 _                 O

 

 

 

 

 

 

 

 

Press enter to continue ...

 

 

Editing drawing UnnamedDrawing.txt

 

Point   -> Add point to drawing

Line    -> Add line to drawing

Text    -> Add text to drawing

Preview -> Preview drawing

List    -> List elements in drawing

Delete  -> Delete element from drawing

Return  -> Return to previous menu

? test

        Invalid option, please try again

 

Editing drawing UnnamedDrawing.txt

 

Point   -> Add point to drawing

Line    -> Add line to drawing

Text    -> Add text to drawing

Preview -> Preview drawing

List    -> List elements in drawing

Delete  -> Delete element from drawing

Return  -> Return to previous menu

? t

        Invalid option, please try again

 

Editing drawing UnnamedDrawing.txt

 

Point   -> Add point to drawing

Line    -> Add line to drawing

Text    -> Add text to drawing

Preview -> Preview drawing

List    -> List elements in drawing

Delete  -> Delete element from drawing

Return  -> Return to previous menu

? text

 

Add text to drawing:

 

X: 0

Y: 13

Text: Hello World!!! C# is a peculiar but fascinating language.

Position (0 .. 3, blank == after last element):

 

Editing drawing UnnamedDrawing.txt

 

Point   -> Add point to drawing

Line    -> Add line to drawing

Text    -> Add text to drawing

Preview -> Preview drawing

List    -> List elements in drawing

Delete  -> Delete element from drawing

Return  -> Return to previous menu

? lIst

 

Drawing contains the following elements:

 

Shape

Line    1       1       19      19      O

Line    19      1       1       19      _

Point   9       9       W

Text    0       13      Hello World!!! C# is a peculiar but fascinating language.

End Shape

 

Editing drawing UnnamedDrawing.txt

 

Point   -> Add point to drawing

Line    -> Add line to drawing

Text    -> Add text to drawing

Preview -> Preview drawing

List    -> List elements in drawing

Delete  -> Delete element from drawing

Return  -> Return to previous menu

? PrEvIeW

 

 O                 _

  O               _

   O             _

    O           _

     O         _

      O       _

       O     _

        O   _

         W _

          _

         _ O

        _   O

Hello World!!! C# is a peculiar but fascinating language.

      _       O

     _         O

    _           O

   _             O

  _               O

 _                 O

 

 

 

 

 

 

 

 

Press enter to continue ...

 

 

Editing drawing UnnamedDrawing.txt

 

Point   -> Add point to drawing

Line    -> Add line to drawing

Text    -> Add text to drawing

Preview -> Preview drawing

List    -> List elements in drawing

Delete  -> Delete element from drawing

Return  -> Return to previous menu

? return

 

Main menu - please select an option

 

New     -> Create new drawing

Open    -> Open existing drawing

Edit    -> Edit drawing

Save    -> Save drawing

Save as -> Save drawing as ...

Close   -> Exit from system

? close

 

Goodbye and thank you for using our service.

 

Lawrence@Lawrence-PC /w

$
