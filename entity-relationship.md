erDiagram
  // Entities
  entity "Student" {
    + StudentID
    Name
    DoB
  }
  entity "Teacher" {
    + TeacherID
    Name
    Speciality
    Department
  }
  entity "Course" {
    + CourseCode
    Title
    Description
  }
  entity "Room" {
    + RoomNo
    Capacity
    Availability
  }
  entity "Invigilator" {
    + InvigilatorID
    Name
    Speciality
    Department
  }
  entity "Exam" {
    + ExamNo
    Date
    StartTime
    Duration
  }

  // Relationships
  "Student" --|{ "takes" |{ "Course"
  "Course" --|{ "is hosted in" |{ "Room"
  "Invigilator" --|{ "invigilates" |{ "Exam"
  "Exam" --|{ "is taken in" |{ "Room"

  // Constraints
  constraint "Each student must take at least one course." for "Student"
  constraint "Each course can only be taken by one student." for "Course"
  constraint "Each exam must be invigilated by at least one invigilator." for "Exam"
  constraint "Each exam must be taken in one room." for "Exam"
