--add data entry to the webapi.source table

--add in the table using the + button, editing the name source_id

WEBAPI SCRIPT 
````R
BEGIN;
INSERT INTO webapi.source_daimon (
	source_daimon_id, 
	source_id, 
	daimon_type, 
	table_qualifier, 
	priority) 
SELECT 
4, 
source_id, 0, 'Magu_CDM_Schema', 0
FROM webapi.source
WHERE source_key = 'ALPHA MAGU HIV';
END;
````
COMMIT;

RESULTS
````R
BEGIN;
INSERT INTO webapi.source_daimon (
	source_daimon_id, 
	source_id, 
	daimon_type, 
	table_qualifier, 
	priority) 
SELECT 
5, 
source_id, 2, 'magu_results', 0
FROM webapi.source
WHERE source_key = 'ALPHA MAGU HIV';
END;
````
VOCAB
````R
BEGIN;
INSERT INTO webapi.source_daimon (
	source_daimon_id, 
	source_id, 
	daimon_type, 
	table_qualifier, 
	priority) 
SELECT 
6, 
source_id, 1, 'vocab', 10
FROM webapi.source
WHERE source_key = 'ALPHA MAGU HIV';
END;
````
CLICK TO REFRESH ATLAS
# http://127.0.0.1/WebAPI/source/refresh
