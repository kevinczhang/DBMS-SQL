# Trips and Users

```sql
WITH total_number_of_requests AS (
 
     SELECT request_at, COUNT(Id) AS 'Requests'
     FROM(
        SELECT DISTINCT Id,Request_at
        FROM        Trips  AS A
        INNER JOIN  Users  AS B ON A.Client_Id = B.Users_Id
        INNER JOIN  Users  AS C ON A.Driver_Id = C.Users_Id 
        WHERE B.Banned = 'No' AND C.Banned = 'No'
        AND   A.Request_at BETWEEN '2013-10-01' AND '2013-10-03'
    )Z
    GROUP BY Request_at


), total_number_of_cancels AS (

     SELECT  request_at, COUNT(Cancels) AS 'Cancels'
     FROM(
            SELECT  request_at,Id AS 'Cancels'
            FROM        Trips   AS A 
            INNER JOIN  Users   AS B ON A.Client_Id = B.Users_Id 
            INNER JOIN  Users   AS C ON A.Driver_Id = C.Users_Id
            WHERE B.Banned = 'No' AND C.Banned = 'No'
            AND   A.Request_at BETWEEN '2013-10-01' AND '2013-10-03'
            AND   A.Status IN ('cancelled_by_driver','cancelled_by_client')
    )Z
    GROUP BY request_at
)



SELECT  A.request_at AS Day, 
        ROUND(CAST(ISNULL(B.Cancels,0.0) AS FLOAT)/A.Requests,2) AS 'Cancellation Rate'
FROM      total_number_of_requests AS A 
LEFT JOIN total_number_of_cancels  AS B ON A.request_at=B.request_at
```
