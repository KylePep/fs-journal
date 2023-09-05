# A bit more CSharp and SQL
1. What does ***inheritance*** accomplish for us in C#?

  > inheritance brings in properites from a parent class, Helps with standardizing data and preventing duplication or straying from the template

2. How does ***member inheritance*** work in C#? Does a `Class` inherit all members of the base `Class`?

  > Yes, you can mark them as virtual to make members overridable.

3. How does ***accessibility*** affect inheritance?

  > public, protected, internal, protected internal, private, private protected. It restircts what is allowed to inherit things from the parent, getting more restricted as it goes.

4. What is the difference between a `PRIMARY KEY` and a `FOREIGN KEY`

  > a Primary Key is the key a data table designates as its primary compartive column, what divides it among other tables.
  A foreign key is a key being referenced from one table to another. Used to establish a connection to then relate the two tables.

5. What is an ***alias***?

  > Alias point to an existing type or namespace.

6. Demonstrate how you would query a join statement that would get all of a doctors patients from the following collections:

  ```SQL
  CREATE TABLE doctors (
    id INT NOT NULL AUTO_INCREMENT,
    -- CODE OMITTED
    PRIMARY KEY (id)
  )

  CREATE TABLE patients (
    id INT NOT NULL AUTO_INCREMENT,
    -- CODE OMITTED
    PRIMARY KEY (id)
  )

  CREATE TABLE patient_doctors (
    id INT NOT NULL AUTO_INCREMENT,
    doctorId INT NOT NULL,
    patientId INT NOT NULL,

    FOREIGN KEY (doctorId)
      REFERENCES doctors(id),
    FOREIGN KEY (patientId)
      REFERENCES patients(id),
  )

  ```

  > string sql = @"
  SELECT
  pat_doc.*,
  pat.*,
  doc.*
  FROM patient_doctors pat_doc
  JOIN patients pat ON pat.id = pat_doc.patiendId
  JOIN doctors doc ON doc.id = pat_doc.doctorId
  WHERE pat_doc.doctorId = @doctorId
  ;";

  List<Patient_Doctors> patients = _db.Query<Patient_Doctors, Patient, Doctor, 
Patient_Doctors>(
  sql,
  (patientDoctor, patient, doctor) => 
  {
    doctor.patients = patient;
    return doctor
  },
  new {doctorId}).ToList();

  role="button" - to fix log in aria issue with lightHouse after type="button"