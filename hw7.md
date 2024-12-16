```mermaid
erDiagram
    USER {
        int UserID PK
        string Name
        string Role
        string Email
    }
    QUESTION {
        int QuestionID PK
        string Text
        string Type
        int MaxScore
        string CorrectAnswer
    }
    ANSWER {
        int AnswerID PK
        int QuestionID FK
        int UserID FK
        string AnswerText
        datetime SubmissionTime
    }
    EVALUATION {
        int EvaluationID PK
        int AnswerID FK
        int Score
        string Feedback
        string Evaluator
    }
    EXAM {
        int ExamID PK
        string Title
        int CreatedBy FK
    }
    EXAM_QUESTION {
        int ExamID FK
        int QuestionID FK
    }
    EXAM_RESULT {
        int ResultID PK
        int ExamID FK
        int UserID FK
        int TotalScore
        datetime CompletionTime
    }

    USER --o{ ANSWER : submits
    QUESTION --o{ ANSWER : relates
    ANSWER -- EVALUATION : has
    USER --o{ EXAM : creates
    EXAM --o{ EXAM_QUESTION : includes
    EXAM_QUESTION }o-- QUESTION : contains
    EXAM --o{ EXAM_RESULT : records
    USER ||--o{ EXAM_RESULT : receives
