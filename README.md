Download Link: https://assignmentchef.com/product/solved-csci3180-assignment-1-ta-ranking-system-in-cobol-and-c
<br>
Teachers always want to find the best and dedicated TAs for their courses. Different courses require different skills sets. Different TAs have different skills and also preferences for the courses that they are interested in. In this assignment, you have to implement part of a TA matching system. Your program should help each course to rank the top 3 TAs. You are required to implement it once using COBOL and once using C.

2           Assignment Details

Jimmy is designing a simple TA Matching System (the “System” hereafter) to find the most suitable TAs for each course. He is asking you to implement the TA ranking module of this system. The system reads 1) the courses’ requirements as well as 2) the candidate TAs’ skills and preferences as input, and reports the top 3 TAs for each course, where TAs are ranked by <em>matching scores </em>(to be explained later).

<h2>2.1         TA ranking system</h2>

In this System, course instructors will enter their requirements for TAs: 3 required skills, and 5 optional skills. Candidate TAs will enter their profiles: 8 skills, and their 1st, 2nd and 3rd preferred courses.

The System keeps the course instructors’ requirements in a file: <strong>instructors.txt</strong>. Each line of the file represents the requirements of a course, containing the course ID, required skills, and optional skills. Also, the System keeps another file containing all the candidate TAs’ information: <strong>candidates.txt</strong>. Each line of the file records a candidate TA’s information, including the TA ID, skills, and preferred courses. Figures 1 and 2 give an example of the <strong>instructors.txt </strong>and <strong>candidates.txt </strong>files (spaces are explicitly displayed as) respectively. Notice that skill names are padded by spaces so that each skill name takes exactly 15 characters. Some skill names may contain multiple words and have spaces between words, e.g. Shellscript .

Jimmy has designed the following policy regarding the matching score that measures how suitable a candidate is to be the TA of a course. The matching score of each pair of (<em>course, TA</em>) is computed as:

(

1 + <em>skill </em><em>score </em>+ <em>preference score          </em>if all the required skills are satisfied

<em>score</em>(<em>course,TA</em>) =

0                                                                      otherwise

where

<ul>

 <li><em>skill </em><em>score</em>: number of optional skills satisfied by the TA</li>

 <li><em>preference score</em>: TA’s preference to the course, according to the following table</li>

</ul>

<table width="404">

 <tbody>

  <tr>

   <td width="109"> </td>

   <td width="96">1st preference</td>

   <td width="101">2nd preference</td>

   <td width="98">3rd preference</td>

  </tr>

  <tr>

   <td width="109"><em>preference score</em></td>

   <td width="96">1.5</td>

   <td width="101">1</td>

   <td width="98">0.5</td>

  </tr>

 </tbody>

</table>

Taking the <strong>instructors.txt </strong>and <strong>candidates.txt </strong>in Figures 1 and 2 respectively as an example:

<em>score</em>(3180<em>,</em>1155136773) = 1 + 5 + 1<em>.</em>5 = 7<em>.</em>5

<em>score</em>(3180<em>,</em>1152147332) = 0

The <strong>output.txt </strong>file should not output the matching scores of every TA for each course directly, but reports only the top 3 TAs for each course. Figure 3 is an example of the <strong>output.txt </strong>file. Note that, if less than <em>k </em>candidates satisfy the required skills specified by the course, the Rank-<em>k </em>TA for that course is filled with 0000000000:

Besides, pay attention to the cases that the <strong>instructors.txt </strong>file or the <strong>candidates.txt </strong>file is empty. If the <strong>instructors.txt </strong>file is empty, the <strong>output.txt </strong>file should be empty too; if the <strong>candidates.txt </strong>file is empty, the Rank-<em>k </em>TA for all the courses should be filled with 0000000000.

Figure 3: Sample of output.txt

Jimmy needs your help. You are required to implement a program to generate the ranking report of each course.

<h2>2.2         General Specification</h2>

You are required to write two programs, one in COBOL and the other one in C, for the student ranking module of the System. You should name your COBOL source as “ta ranking.cob” and your C source as “ta ranking.c”.

<h3>1.    Input and Output Specification</h3>

Your programs should read two input files: <strong>instructors.txt </strong>and <strong>candidates.txt</strong>, which contain instructors’ requirements and candidates’ skills and preferences. The detailed specification of input format is given in Section 2.3. For each course, your program needs to calculate the matching score for each candidate. These calculations should be strictly based on the policy described above. Afterwards, TAs are ranked by their matching scores with each course. In case of a tie (two TAs having the same matching score), the TA with <strong>lower </strong>TA ID will have a better rank than the other. Your program should output one file to report the top 3 TAs for each course and display them in ranking order (i.e. the first one is the best TA, the second one is the second best and so on). The output file format should follow the description in Section 2.4. You can “hardcode” the input file names in your program. And the naming of the output file should be: <strong>output.txt</strong>.

<h3>2.    Restrictions on using COBOL and C</h3>

For COBOL, in order to force you to program as in the old days, ONLY 2 keywords are allowed in selection and loop statements: “IF” and “GOTO”. You are not allowed to use modern control constructs, such as if-then-else or while loop. Using any other keywords will receive marks deduction. But for C, you can use whatever you want.

<h3>3.    Error Handling</h3>

The programs should also handle possible errors gracefully by printing meaningful error messages to the standard output. For example, your program should be able to check whether the input file exists or not. If not, display a warning message ”non-existing file!”. However, you <strong>CAN </strong>assume that the input files are free of format on content errors.

<h3>4.    Good Programming Style</h3>

A good programming style not only improves your grade but also helps you a lot in debugging. Poor programming style will receive marks deduction. Construct your program with good readability and modularity. Provide sufficient documentation by commenting your codes properly but never redundantly. Divide up your programs into subroutines instead of clogging the main program. The main section of your program should only handle the basic file manipulation such as file opening and closing, and subprogram calling. The main purpose of programming is not just to make the program right but also make it good.

<h3>5.    Other Notes</h3>

You are <strong>NOT </strong>allowed to implement your program in another language (e.g. Java/Python) and then initiate system calls or external library calls in COBOL and C. Your source codes will be compiled and PERUSED, and the object code tested!

Do not implement your programs in multiple source files. Although COBOL and C do allow you to build a project with subroutines scattered among multiple source files, you should only submit one source file for each language.

<strong>NO PLAGIARISM!!!! </strong>You are free to design your own algorithm and code your own implementation, but you should not “borrow” codes from your classmates. If you use an algorithm or code snippet that is publicly available or use codes from your classmates or friends, be sure to DECLARE it in the comments of your program. Failure to comply will be considered as plagiarism.

A crash introduction to COBOL will be given in the upcoming tutorials. Please DO attend the tutorials to get a brief idea on COBOL, and then learn the language by yourselves. We assume that you are proficient in C. For a more in-depth study, we encourage students to search relevant resources on the Internet (just Google it!).

<h2>2.3         Input File Format Specification</h2>

There are two input files: <strong>instructors.txt</strong>, and <strong>candidates.txt</strong>. All input files are in plain ASCII text. Each line is ended with the characters “r
” on windows machine, including the last line. You can write your programs on whatever OS you like, but please verify that they can be compiled and run correctly on Windows machines in SHB924/909 because we will grade your assignment there. You should strictly follow the format as stated in the following.

<ul>

 <li>Each line of <strong>txt </strong>contains nine fields of fixed length for a course. The lines are sorted by course IDs in <strong>ascending order</strong>.

  <ol>

   <li><em>Course ID</em>: a 4-digit number followed by a space.</li>

   <li><em>Required skills</em>: 3 required skills, each of which is a string of 15 characters (spaces are padded at the end in case the skill name is less than 15 characters).</li>

   <li><em>Optional skills</em>: 5 optional skills, each of which is a string of 15 characters (spaces are padded at the end in case the skill name is less than 15 characters).</li>

  </ol></li>

 <li>Each line of <strong>txt </strong>contains twelve fields of fixed lengths of a candidate’s skills and preferences. The lines are sorted by TA IDs in <strong>ascending order</strong>.

  <ol>

   <li><em>TA ID</em>: a 10-digit number followed by a space.</li>

   <li><em>Skills</em>: 8 skills, each of which is a string of 15 characters (spaces are padded in case the skill name is less than 15 characters).</li>

   <li><em>Preference</em>: 3 preferences, each of which is a 4-digit number followed by a space.</li>

  </ol></li>

</ul>

You may make the following assumptions on the files:

<ul>

 <li>All input files strictly follow the format specified in Section 2.3.</li>

 <li>File <strong>txt </strong>is sorted by course ID in ascending order.</li>

 <li>File <strong>txt </strong>is sorted by TA ID in ascending order.</li>

 <li>The number of skills in file <strong>txt </strong>is fixed to 8, and there are no duplicate skills.</li>

</ul>

<h2>2.4         Output File Format Specification</h2>

There is only one output file: <strong>output.txt</strong>. You should strictly follow the format as stated in the following.

<ul>

 <li>Each line of <strong>output.txt </strong>contains 4 fields of fixed lengths of the top 3 TAs for each course. The lines should be sorted by course IDs in ascending order (the same order as in “<strong>instructors.txt</strong>“).</li>

</ul>

<ol>

 <li><em>Course ID</em>: a 4-digit number followed by a space.</li>

 <li><em>Rank-1 TA</em>: The best TA, which is a 10-digit number followed by a space. If no candidates satisfy the required skills specified by the course, this field is filled by 0000000000.</li>

 <li><em>Rank-2 TA</em>: The 2nd best TA, which is a 10-digit number followed by a space. If less than 2 candidates satisfy the required skills specified by the course, this field is filled by 000000000.</li>

 <li><em>Rank-3 TA</em>: The 3rd best TA, which is a 10-digit number followed by a space. If less than 3 candidates satisfy the required skills specified by the course, this field is filled by 0000000000.</li>

</ol>

Pay attention to the special cases, as we have mentioned in the previous sections:

<ul>

 <li>For Rank-<em>k </em>TA of a course, if less than <em>k </em>candidates satisfy the required skills specified by the course, the Rank-<em>k </em>TA for that course is filled with 0000000000.</li>

 <li>If the <strong>txt </strong>file is empty, the <strong>output.txt </strong>file should be empty too.</li>

 <li>If the <strong>txt </strong>file is empty, the Rank-<em>k </em>TA for all the courses should be filled with 0000000000.</li>

 <li>If the input file is non-existent, display a warning message ”non-existing file!”.</li>

</ul>

<h2>2.5         Report</h2>

You should give a simple report to answer the following questions within one A4 page:

<ol>

 <li>Compare the conveniences and difficulties in implementing the TA Ranking System in COBOL and C. You can divide the implementation into specific tasks such as “reading file in certain format”, “simulating loops”, “procedure/function call” and so on. Give code segments in your programs to support your explanation.</li>

 <li>Compare COBOL with modern programming languages (e.g. Java/Python/…) from different aspects (e.g. variable declarations, paradigm, data type, parameter parsing, …). You are free to pick your favorite modern programming language.</li>

 <li>Do you think COBOL is suitable for writing applications like in this assignment, especially when some of the input needs to be passed several times? Explain in terms of, say, the aspect like programming difficulty, efficiency of you program, etc.</li>

 <li>In your program design, how do you separate the tasks into submodules? Tell us briefly the functionality of each submodule and the main flow of your program in terms of these submodules.</li>

</ol>

<h1></h1>