
#### Data Management Guidelines

| Data Type       | Commitment   | Details                                                                                 |
|-----------------|--------------|-----------------------------------------------------------------------------------------|
| Raw Data        | Do not commit| Large files; Create subfolders for each manuscript version if there are different datasets generated.|
| Processed Data  | Do not commit| Large files; Create subfolders for each manuscript version if there are different datasets generated.|
| Published Data  | Always commit| Typically small files, such as supplementary tables in the manuscript.                    |

#### When to save processed data.
- If the data generation takes > 5 mins.
- Also include logs in this folder for better examination purpose.
- Create a new version for any kind of updates. Write description in the commit msg.


