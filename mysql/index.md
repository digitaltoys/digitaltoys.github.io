# 위경도 거리로 쿼리

```sql
-- KM : 6371
-- MILES : 3959

SELECT
    id, (
      6371 * acos (
      cos ( radians(source_lat) )
      * cos( radians( lat ) )
      * cos( radians( lng ) - radians(source_lon) )
      + sin ( radians(source_lat) )
      * sin( radians( lat ) )
    )
) AS distance
FROM toilets
HAVING distance < 2
ORDER BY distance
LIMIT 0 , 20;
```
