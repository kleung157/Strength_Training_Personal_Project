## Workouts 2023 - Data Analysis

/* Current Objectives */
/* Time */
How many minutes -> hours per week?
SELECT SUM(Workouts.Time_Spent_mins) / 52 AS Minutes_Per_Week
FROM Workouts
;
SELECT SUM(Workouts.Time_Spent_mins) / 60 / 52 AS Hours_Per_Week
FROM Workouts
;

How many sessions were completed and skipped?
SELECT COUNT(Workouts.Workout_ID) AS Sessions_Completed
FROM Workouts
WHERE Workouts.Time_Spent_Mins > 1
;
SELECT COUNT(Workouts.Workout_ID) / 11 AS Days_Completed
FROM Workouts
WHERE Workouts.Time_Spent_Mins > 1
;
SELECT COUNT(Workouts.Comments) AS Sessions_Skipped
FROM Workouts
WHERE Comments LIKE '%skip%'
;
SELECT COUNT(Workouts.Comments) / 11 AS Days_Skipped
FROM Workouts
WHERE Comments LIKE '%skip%'
;

Which was the most and least consistent month?
SELECT COUNT(Workouts.Date) AS Total_Sessions, SUM(Workouts.Time_Spent_mins) AS Total_Time
FROM Workouts
WHERE (Workouts.Date BETWEEN '2023-01-01' AND '2023-01-31')
    AND Workouts.Time_Spent_mins > 0
;
SELECT COUNT(Workouts.Date) AS Total_Sessions, SUM(Workouts.Time_Spent_mins) AS Total_Time
FROM Workouts
WHERE (Workouts.Date BETWEEN '2023-02-01' AND '2023-02-28')
    AND Workouts.Time_Spent_mins > 0
;
SELECT COUNT(Workouts.Date) AS Total_Sessions, SUM(Workouts.Time_Spent_mins) AS Total_Time
FROM Workouts
WHERE (Workouts.Date BETWEEN '2023-03-01' AND '2023-03-31')
    AND Workouts.Time_Spent_mins > 0
;
SELECT COUNT(Workouts.Date) AS Total_Sessions, SUM(Workouts.Time_Spent_mins) AS Total_Time
FROM Workouts
WHERE (Workouts.Date BETWEEN '2023-04-01' AND '2023-04-30')
    AND Workouts.Time_Spent_mins > 0
;
SELECT COUNT(Workouts.Date) AS Total_Sessions, SUM(Workouts.Time_Spent_mins) AS Total_Time
FROM Workouts
WHERE (Workouts.Date BETWEEN '2023-05-01' AND '2023-05-31')
    AND Workouts.Time_Spent_mins > 0
;
SELECT COUNT(Workouts.Date) AS Total_Sessions, SUM(Workouts.Time_Spent_mins) AS Total_Time
FROM Workouts
WHERE (Workouts.Date BETWEEN '2023-06-01' AND '2023-06-30')
    AND Workouts.Time_Spent_mins > 0
;
SELECT COUNT(Workouts.Date) AS Total_Sessions, SUM(Workouts.Time_Spent_mins) AS Total_Time
FROM Workouts
WHERE (Workouts.Date BETWEEN '2023-07-01' AND '2023-07-31')
    AND Workouts.Time_Spent_mins > 0
;
SELECT COUNT(Workouts.Date) AS Total_Sessions, SUM(Workouts.Time_Spent_mins) AS Total_Time
FROM Workouts
WHERE (Workouts.Date BETWEEN '2023-08-01' AND '2023-08-30')
    AND Workouts.Time_Spent_mins > 0
;
SELECT COUNT(Workouts.Date) AS Total_Sessions, SUM(Workouts.Time_Spent_mins) AS Total_Time
FROM Workouts
WHERE (Workouts.Date BETWEEN '2023-09-01' AND '2023-09-30')
    AND Workouts.Time_Spent_mins > 0
;
SELECT COUNT(Workouts.Date) AS Total_Sessions, SUM(Workouts.Time_Spent_mins) AS Total_Time
FROM Workouts
WHERE (Workouts.Date BETWEEN '2023-10-01' AND '2023-10-31')
    AND Workouts.Time_Spent_mins > 0
;
SELECT COUNT(Workouts.Date) AS Total_Sessions, SUM(Workouts.Time_Spent_mins) AS Total_Time
FROM Workouts
WHERE (Workouts.Date BETWEEN '2023-11-01' AND '2023-11-30')
    AND Workouts.Time_Spent_mins > 0
;
SELECT COUNT(Workouts.Date) AS Total_Sessions, SUM(Workouts.Time_Spent_mins) AS Total_Time
FROM Workouts
WHERE (Workouts.Date BETWEEN '2023-12-01' AND '2023-12-31')
    AND Workouts.Time_Spent_mins > 0
;

Total time spent for the year?
SELECT SUM(Workouts.Time_Spent_Mins) AS Minutes
FROM Workouts
;
SELECT SUM(Workouts.Time_Spent_Mins) / 60 AS Hours
FROM Workouts
;

Total time missed for the year?
SELECT COUNT(Workouts.Time_Spent_Mins) / 12 * 3 * 60 AS Time_Missed
FROM Workouts
WHERE Comments LIKE '%skip%'
;

/* Weight */
Heaviest rep weight for each compound lift?
SELECT MAX(Workouts.Highest_Weight) AS Overhead_Press
FROM Workouts
WHERE Workouts.Exercise_ID = 10000
;
SELECT MAX(Workouts.Highest_Weight) AS Sumo_Deadlift
FROM Workouts
WHERE Workouts.Exercise_ID = 10001
;
SELECT MAX(Workouts.Highest_Weight) AS Conventional_Deadlift
FROM Workouts
WHERE Workouts.Exercise_ID = 10002
;
SELECT MAX(Workouts.Highest_Weight) AS Squat
FROM Workouts
WHERE Workouts.Exercise_ID = 10003
;
SELECT MAX(Workouts.Highest_Weight) AS Bench_Press
FROM Workouts
WHERE Workouts.Exercise_ID = 10004
;

Lowest rep weight for each compound lift?
SELECT MIN(Workouts.Lowest_Weight) AS Overhead_Press
FROM Workouts
WHERE Workouts.Exercise_ID = 10000
;
SELECT MIN(Workouts.Lowest_Weight) AS Sumo_Deadlift
FROM Workouts
WHERE Workouts.Exercise_ID = 10001
;
SELECT MIN(Workouts.Lowest_Weight) AS Conventional_Deadlift
FROM Workouts
WHERE Workouts.Exercise_ID = 10002
;
SELECT MIN(Workouts.Lowest_Weight) AS Squat
FROM Workouts
WHERE Workouts.Exercise_ID = 10003
;
SELECT MIN(Workouts.Lowest_Weight) AS Bench_Press
FROM Workouts
WHERE Workouts.Exercise_ID = 10004
;

Most and least improved workouts
SELECT Workouts.Workout_ID, Workouts.Date, Exercise.Name, Exercise.Type, Exercise.Category, Workouts.Sets, Workouts.Repetitions, Workouts.Lowest_Weight, Workouts.Highest_Weight, Workouts.Time_Spent_mins, Week.Start_Date, Week.End_Date, Workouts.Comments 
FROM Workouts
FULL JOIN Exercise ON Workouts.Exercise_ID = Exercise.Exercise_ID
FULL JOIN Week ON Workouts.Week_ID = Week.Week_ID
;

What are the total repetitions for each barbell exercise?
SELECT SUM(Workouts.Sets * Workouts.Repetitions) AS Total_Repetitions
FROM Workouts
FULL JOIN Exercise ON Workouts.Exercise_ID = Exercise.Exercise_ID
WHERE Exercise.Name = 'Overhead_Press'
;
SELECT SUM(Workouts.Sets * Workouts.Repetitions) AS Total_Repetitions
FROM Workouts
FULL JOIN Exercise ON Workouts.Exercise_ID = Exercise.Exercise_ID
WHERE Exercise.Name = 'Sumo Deadlift'
;
SELECT SUM(Workouts.Sets * Workouts.Repetitions) AS Total_Repetitions
FROM Workouts
FULL JOIN Exercise ON Workouts.Exercise_ID = Exercise.Exercise_ID
WHERE Exercise.Name = 'Conventional Deadlift'
;
SELECT SUM(Workouts.Sets * Workouts.Repetitions) AS Total_Repetitions
FROM Workouts
FULL JOIN Exercise ON Workouts.Exercise_ID = Exercise.Exercise_ID
WHERE Exercise.Name = 'Squat'
;
SELECT SUM(Workouts.Sets * Workouts.Repetitions) AS Total_Repetitions
FROM Workouts
FULL JOIN Exercise ON Workouts.Exercise_ID = Exercise.Exercise_ID
WHERE Exercise.Name = 'Bench Press'
;

What are the total repetitions for each accessory exercise?
SELECT SUM(Workouts.Sets * Workouts.Repetitions) AS Total_Repetitions
FROM Workouts
FULL JOIN Exercise ON Workouts.Exercise_ID = Exercise.Exercise_ID
WHERE Exercise.Name = 'Dumbbell Row'
;
SELECT SUM(Workouts.Sets * Workouts.Repetitions) AS Total_Repetitions
FROM Workouts
FULL JOIN Exercise ON Workouts.Exercise_ID = Exercise.Exercise_ID
WHERE Exercise.Name = 'Lateral Pull Down'
;
SELECT SUM(Workouts.Sets * Workouts.Repetitions) AS Total_Repetitions
FROM Workouts
FULL JOIN Exercise ON Workouts.Exercise_ID = Exercise.Exercise_ID
WHERE Exercise.Name = 'Shoulder Shrug'
;
SELECT SUM(Workouts.Sets * Workouts.Repetitions) AS Total_Repetitions
FROM Workouts
FULL JOIN Exercise ON Workouts.Exercise_ID = Exercise.Exercise_ID
WHERE Exercise.Name = 'Flat Dumbbell'
;
SELECT SUM(Workouts.Sets * Workouts.Repetitions) AS Total_Repetitions
FROM Workouts
FULL JOIN Exercise ON Workouts.Exercise_ID = Exercise.Exercise_ID
WHERE Exercise.Name = 'Incline Dumbbell'
;
SELECT SUM(Workouts.Sets * Workouts.Repetitions) AS Total_Repetitions
FROM Workouts
FULL JOIN Exercise ON Workouts.Exercise_ID = Exercise.Exercise_ID
WHERE Exercise.Name = 'Leg Curl'
;
SELECT SUM(Workouts.Sets * Workouts.Repetitions) AS Total_Repetitions
FROM Workouts
FULL JOIN Exercise ON Workouts.Exercise_ID = Exercise.Exercise_ID
WHERE Exercise.Name = 'Dumbbell Shoulder'
;
SELECT SUM(Workouts.Sets * Workouts.Repetitions) AS Total_Repetitions
FROM Workouts
FULL JOIN Exercise ON Workouts.Exercise_ID = Exercise.Exercise_ID
WHERE Exercise.Name = 'Dumbbell Curl'
;
SELECT SUM(Workouts.Sets * Workouts.Repetitions) AS Total_Repetitions
FROM Workouts
FULL JOIN Exercise ON Workouts.Exercise_ID = Exercise.Exercise_ID
WHERE Exercise.Name = 'Tricep Pull Down'
;
SELECT SUM(Workouts.Sets * Workouts.Repetitions) AS Total_Repetitions
FROM Workouts
FULL JOIN Exercise ON Workouts.Exercise_ID = Exercise.Exercise_ID
WHERE Exercise.Name = 'Pull Back Machine'
;

What are the total repetitions for each month and the total average per session?
SELECT COUNT(Workouts.Date) AS Total_Sessions, SUM(Workouts.Sets * Workouts.Repetitions) AS Total_Repetitions
FROM Workouts
WHERE (Workouts.Date BETWEEN '2023-01-01' AND '2023-01-31')
    AND Workouts.Time_Spent_mins > 0
;
SELECT COUNT(Workouts.Date) AS Total_Sessions, SUM(Workouts.Sets * Workouts.Repetitions) AS Total_Repetitions
FROM Workouts
WHERE (Workouts.Date BETWEEN '2023-02-01' AND '2023-02-28')
    AND Workouts.Time_Spent_mins > 0
;
SELECT COUNT(Workouts.Date) AS Total_Sessions, SUM(Workouts.Sets * Workouts.Repetitions) AS Total_Repetitions
FROM Workouts
WHERE (Workouts.Date BETWEEN '2023-03-01' AND '2023-03-31')
    AND Workouts.Time_Spent_mins > 0
;
SELECT COUNT(Workouts.Date) AS Total_Sessions, SUM(Workouts.Sets * Workouts.Repetitions) AS Total_Repetitions
FROM Workouts
WHERE (Workouts.Date BETWEEN '2023-04-01' AND '2023-04-30')
    AND Workouts.Time_Spent_mins > 0
;
SELECT COUNT(Workouts.Date) AS Total_Sessions, SUM(Workouts.Sets * Workouts.Repetitions) AS Total_Repetitions
FROM Workouts
WHERE (Workouts.Date BETWEEN '2023-05-01' AND '2023-05-31')
    AND Workouts.Time_Spent_mins > 0
;
SELECT COUNT(Workouts.Date) AS Total_Sessions, SUM(Workouts.Sets * Workouts.Repetitions) AS Total_Repetitions
FROM Workouts
WHERE (Workouts.Date BETWEEN '2023-06-01' AND '2023-06-30')
    AND Workouts.Time_Spent_mins > 0
;
SELECT COUNT(Workouts.Date) AS Total_Sessions, SUM(Workouts.Sets * Workouts.Repetitions) AS Total_Repetitions
FROM Workouts
WHERE (Workouts.Date BETWEEN '2023-07-01' AND '2023-07-31')
    AND Workouts.Time_Spent_mins > 0
;
SELECT COUNT(Workouts.Date) AS Total_Sessions, SUM(Workouts.Sets * Workouts.Repetitions) AS Total_Repetitions
FROM Workouts
WHERE (Workouts.Date BETWEEN '2023-08-01' AND '2023-08-31')
    AND Workouts.Time_Spent_mins > 0
;
SELECT COUNT(Workouts.Date) AS Total_Sessions, SUM(Workouts.Sets * Workouts.Repetitions) AS Total_Repetitions
FROM Workouts
WHERE (Workouts.Date BETWEEN '2023-09-01' AND '2023-09-30')
    AND Workouts.Time_Spent_mins > 0
;
SELECT COUNT(Workouts.Date) AS Total_Sessions, SUM(Workouts.Sets * Workouts.Repetitions) AS Total_Repetitions
FROM Workouts
WHERE (Workouts.Date BETWEEN '2023-10-01' AND '2023-10-31')
    AND Workouts.Time_Spent_mins > 0
;
SELECT COUNT(Workouts.Date) AS Total_Sessions, SUM(Workouts.Sets * Workouts.Repetitions) AS Total_Repetitions
FROM Workouts
WHERE (Workouts.Date BETWEEN '2023-11-01' AND '2023-11-30')
    AND Workouts.Time_Spent_mins > 0
;
SELECT COUNT(Workouts.Date) AS Total_Sessions, SUM(Workouts.Sets * Workouts.Repetitions) AS Total_Repetitions
FROM Workouts
WHERE (Workouts.Date BETWEEN '2023-12-01' AND '2023-12-31')
    AND Workouts.Time_Spent_mins > 0
;

What is the volume vs. intensity of the workouts in terms of reps/weight?

/* Variables */
What variables affected workouts?
SELECT Exercise.Name, Exercise.Type, Exercise.Category, Workouts.Sets, Workouts.Repetitions, Workouts.Lowest_Weight, Workouts.Highest_Weight, Workouts.Time_Spent_mins, Workouts.Comments 
FROM Workouts
FULL JOIN Exercise ON Workouts.Exercise_ID = Exercise.Exercise_ID
FULL JOIN Week ON Workouts.Week_ID = Week.Week_ID
WHERE NOT Comments = ''

Which body category was the most and least targeted?
SELECT COUNT(Exercise.Category) AS Leg_Sessions
FROM Workouts
JOIN Exercise ON Workouts.Exercise_ID = Exercise.Exercise_ID
WHERE Exercise.Category = 'Legs'
;
SELECT COUNT(Exercise.Category) AS Arm_Sessions
FROM Workouts
JOIN Exercise ON Workouts.Exercise_ID = Exercise.Exercise_ID
WHERE Exercise.Category = 'Arms'
;
SELECT COUNT(Exercise.Category) AS Chest_Sessions
FROM Workouts
JOIN Exercise ON Workouts.Exercise_ID = Exercise.Exercise_ID
WHERE Exercise.Category = 'Chest'
;
SELECT COUNT(Exercise.Category) AS Back_Sessions
FROM Workouts
JOIN Exercise ON Workouts.Exercise_ID = Exercise.Exercise_ID
WHERE Exercise.Category = 'Back'
;
