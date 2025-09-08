# C Programming Problem: Comprehensive Student Evaluation System

### Description
A university wants to implement a comprehensive final evaluation system for its students. This system must be able to calculate a final score based on several components, apply special conditions, and determine a letter grade and passing status. You are asked to create a C program that accepts a student's details, performs the calculations, and displays the results in a specified format.

---

### Input
Your program must accept five types of input from the keyboard:

1.  **Student Registration Number (NRP):** A very large integer for student identification. Use a suitable data type to store this large number (e.g., `long long int`).
2.  **Assignment Score:** A floating-point number.
3.  **Midterm Exam Score (UTS):** A floating-point number.
4.  **Final Exam Score (UAS):** A floating-point number.
5.  **Attendance Percentage:** A floating-point number indicating student attendance (between 0.0 and 100.0).

---

### Calculations and Special Conditions
The program must perform the following calculations:

* **Primary Average Score (`RataUtama`):** Calculated from `(Assignment Score + UTS Score + UAS Score) / 3`. Use arithmetic operators.

* **Attendance Penalty Points:**
    * If the **Attendance Percentage** is less than **75.0**, every 1% below 75.0 will reduce the `RataUtama` by **0.5** points. For example, an attendance of 70.0 (5% below 75.0) results in a penalty of `5 * 0.5 = 2.5` points.
    * If the **Attendance Percentage** is 75.0 or higher, there is no penalty.
    * Use relational and arithmetic operators for this condition.

* **Final Score (`NA`):**
    * `NA = RataUtama - Attendance Penalty Points`.
    * **Constraint:** The `NA` cannot be less than **0** or greater than **100**. If the calculation results in a value outside this range, it must be automatically adjusted to 0 or 100.
    * Use the **conditional operator `?:`** to apply this constraint.

* **Letter Grade:** Determined based on the `NA` using the following criteria:
    * `NA >= 90`: **'A'**
    * `NA >= 80`: **'B'**
    * `NA >= 70`: **'C'**
    * `NA >= 60`: **'D'**
    * `NA < 60`: **'E'**
    * Use the **nested conditional operator `?:`**.

* **Passing Status:**
    * **"Pass"** if the Letter Grade is 'A', 'B', or 'C' **AND** the Attendance Percentage is at least **65.0**.
    * **"Fail"** in all other cases.
    * **High Priority Exception:** If the `NA` is less than **50**, regardless of the Letter Grade and Attendance Percentage, the status is always **"Fail"**.
    * Use logical operators `&&` or `||` (implicitly via the conditional operator `?:`) and relational operators.

---

### Output
The program must display the following results to the screen using `printf()`, with the specified format and precision, and use appropriate escape sequences for layout:

1.  **NRP Mahasiswa:** Displayed as an integer.
2.  **Nilai Tugas:** Displayed with two decimal places.
3.  **Nilai UTS:** Displayed with two decimal places.
4.  **Nilai UAS:** Displayed with two decimal places.
5.  **Persentase Kehadiran:** Displayed with two decimal places, followed by a percent symbol (`%`).
6.  **Rata-rata Nilai Utama:** Displayed with two decimal places.
7.  **Nilai Akhir:** Displayed with two decimal places.
8.  **Grade Huruf:** Displayed as a character.
9.  **Status Kelulusan:** Displayed as text ("Pass" or "Fail").

---

### Example

#### Sample Input:
502499100123456
75.0
80.0
85.0
70.0


#### Sample Output:
=== Student Evaluation Report ===
NRP                  : 502499100123456
Assignment Score     : 75.00
Midterm Score        : 80.00
Final Exam Score     : 85.00
Attendance Percentage: 70.00%
Primary Average      : 80.00
Final Score          : 77.50
Grade                : C
Status               : Pass