
A user opens the app and confirms the age + privacy consent check.


The current question for the active 15-minute slot is loaded.


The user votes Yes or No.


The backend validates that no vote has already been cast for this question by this device fingerprint.


Only an anonymous counter (yes_count or no_count) on the Topic is atomically incremented.


The individual vote choice is never stored as a record.


The user is shown the closing screen and can view aggregated results.
