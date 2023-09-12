
SELECT _column1, column2, ..._  FROM _table_name_  WHERE _columnN_ LIKE _pattern_;
startswith

|   |   |
|---|---|
|WHERE CustomerName LIKE 'a%'|Finds any values that start with "a"|
|WHERE CustomerName LIKE '%a'|Finds any values that end with "a"|
|WHERE CustomerName LIKE '%or%'|Finds any values that have "or" in any position|
|WHERE CustomerName LIKE '_r%'|Finds any values that have "r" in the second position|
|WHERE CustomerName LIKE 'a_%'|Finds any values that start with "a" and are at least 2 characters in length|
|WHERE CustomerName LIKE 'a__%'|Finds any values that start with "a" and are at least 3 characters in length|
|WHERE ContactName LIKE 'a%o'|Finds any values that start with "a" and ends with "o"|


SELECT _column_name(s)_  
FROM _table_name_  
WHERE _column_name_ BETWEEN _value1_ AND _value2;_


UPDATE patients SET allergies = 'NKA' where allergies is NULL;

SELECT CONCAT(first_name, ' ', last_name) AS full_name FROM patients;

select first_name, last_name, province_name from patients JOIN province_names ON province_names.province_id = patients.province_id;

SELECT COUNT(*) AS patient_count
FROM patients
WHERE YEAR(birth_date) = 2010;


SELECT first_name, last_name, height FROM patients where height = (SELECT MAX(height) FROM patients);

select * FROM patients where patient_id in (1,45,534,879,1000);

SELECT COUNT(*) FROM admissions;


SELECT * FROM admissions where DATE(admission_date) = DATE(discharge_date);


SELECT patient_id, COUNT(*) AS total_admissions FROM admissions WHERE patient_id = 579 GROUP BY patient_id;

SELECT DISTINCT city FROM patients WHERE province_id = 'NS';

SELECT DISTINCT city FROM patients WHERE city LIKE 'A%' OR city LIKE 'E%' OR city LIKE 'I%' OR city LIKE 'O%' OR city LIKE 'U%' ORDER BY city ASC;

SELECT first_name FROM patients GROUP BY first_name HAVING COUNT(*) = 1;

SELECT first_name FROM patients ORDER BY LENGTH(first_name), first_name;

SELECT province_names.province_name, COUNT(patients.patient_id) AS total_patients FROM patients JOIN province_names ON province_names.province_id = patients.province_id GROUP BY province_names.province_name ORDER BY total_patients DESC;

SELECT doctors.doctor_id, CONCAT(doctors.first_name, ' ', doctors.last_name) AS doctor_name,
    (SELECT MIN(admission_date) FROM admissions WHERE admissions.attending_doctor_id = doctors.doctor_id) AS first_admission_date,
    (SELECT MAX(admission_date) FROM admissions WHERE admissions.attending_doctor_id = doctors.doctor_id) AS last_admission_date
FROM doctors;

SELECT doctors.first_name, doctors.last_name, COUNT(*) AS total_admissions FROM doctors JOIN admissions ON doctors.doctor_id = admissions.attending_doctor_id GROUP BY doctors.first_name, doctors.last_name;

SELEcT patient_id, concat(patient_id, len(last_name), year(birth_date)) as temp_password from patients  WHERE patient_id IN ( SELECT patient_id FROM admissions );

SELECT first_name, last_name, 'Patient' AS role
FROM patients UNION ALL SELECT first_name, last_name, 'Doctor' AS role
FROM doctors;

SELECT first_name, last_name, count(*) as d FROM patients GROUP BY first_name, last_name HAVING COUNT(*) > 1;

SELECT patient_id, diagnosis FROM admissions GROUP BY patient_id, diagnosis HAVING COUNT(*) > 1;


python3 manage.py shell < shell/test_script.py