sequenceDiagram
    participant User
    participant System

    User->>System: Log into the system   // Step I
    System-->>User: Present main dashboard  // Step II

    User->>System: Choose season   // Step III
    System-->>User: Display corresponding fields

    User->>System: Select field for job management   // Step IV
    System-->>User: Display existing jobs for the selected field  // Step V

    User->>System: Choose to add or modify a job   // Step VI

    alt Adding a New Job   // Step VII
        User->>System: Select job type
        User->>System: Specify start and finish times
        System->>System: Check entered information
        alt Information correct
            System->>System: Add job to field's job list
            System-->>User: Send notification about the new job
        else Information incorrect
            System-->>User: Display error message
        end
    else Marking a Job as Done   // Step VIII
        User->>System: Select job to mark as complete
        User->>System: Mark job as complete
        System->>System: Change job status to done/complete
        System-->>User: Send notification that the job is complete
    end

    User->>System: View list of jobs for the selected field   // Step IX
    User->>System: Log out   // Step X
