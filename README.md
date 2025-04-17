# CaseStatus

# `Application Center`
# Frontend
* The user enters the details in these fields.
![image](https://github.com/user-attachments/assets/230d6c4e-4d3a-46ca-8feb-516577b6ba8b)
* The api retrieves data and shows it to the user
![image](https://github.com/user-attachments/assets/e6a3db99-5679-4a1f-b40e-6b843c2322e0)

# Backend
* Once the user enters the fields and enter the button.
* An internal API call is being made to `/users/{userId}/applications/{applicationId}/case-status` (`CaseStatusRestController.kt`)
* If the `caseId == null`
    * Then makes this api call `/casestatus/api/v1/case/status/{applicationId}`
    * (From here on, Its been handled by `standalone-casestatus`.)
    * Then `checkStatus` (https://su2q4etor7.execute-api.us-west-2.amazonaws.com/prod/Case-Status-2024?receipt_number=%s)
* else
    * Then makes this api call `/casestatus/api/v1/case/update`
    * (From here on, Its been handled by `standalone-casestatus`.)
    * First, We call `getOrCreateCase()` this creates a new instances.
    * Then `checkStatus` (https://su2q4etor7.execute-api.us-west-2.amazonaws.com/prod/Case-Status-2024?receipt_number=%s)

# `Stand Alone` 
# Frontend
* The user enters the details in these fields
![image](https://github.com/user-attachments/assets/ab5ce2bb-e1e1-417c-8adf-b538f8021324)
* The api retrieves data and shows it to the user
![gf432csary423y23](https://github.com/user-attachments/assets/79d941a1-3b69-42f2-b163-9f159c88b280)

# Backend
* Once the user clicks on the button.
* (From here on, It's been handled by `common-static`.)
* Then it calls this api `https://su2q4etor7.execute-api.us-west-2.amazonaws.com/prod/Case-Status-2024?receipt_number=`

## How it is stored in the db?
* `case_t`
![image](https://github.com/user-attachments/assets/2ca6f8ba-bdfa-4b21-a37c-6b494fe62fe6)

* `case_status`
![image](https://github.com/user-attachments/assets/65d1cf29-ce11-4b0e-b900-3f3e03d3061a)

* `case_status_log_t`
![image](https://github.com/user-attachments/assets/3d6f999a-f33b-480c-87b9-1f3bfbce1337)
![image](https://github.com/user-attachments/assets/b59c9e37-8adb-4bbe-857a-482bcf66ab43)


word checker
more memory context
Refactor variable names
More models
Voice only mode
Return entire array if needed
Attach documents


Research

Finite State Machines (FSM): maintains context by moving through states.

Trie-based matching: for fast keyword lookup.

TF-IDF (classic vector-based search): find best-matching known inputs by scoring commonality.


