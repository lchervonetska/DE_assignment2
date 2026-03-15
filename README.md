# DE_assignment2

## Creating tables
```sql
CREATE DATABASE as2;
USE as2;

CREATE TABLE employees (
    employee_id INT AUTO_INCREMENT PRIMARY KEY,
    full_name VARCHAR(100),
    team VARCHAR(100),
    role VARCHAR(50),
    hire_date DATE
);


CREATE TABLE calls (
    call_id INT AUTO_INCREMENT PRIMARY KEY,
    employee_id INT,
    call_time DATETIME,
    phone VARCHAR(20),
    direction VARCHAR(10),
    status VARCHAR(50),

    FOREIGN KEY (employee_id) REFERENCES employees(employee_id)
);


INSERT INTO employees (full_name, team, role, hire_date) VALUES
('Olivia Johnson',     'Level 1 Support',  'Agent',         '2019-03-15'),
('Liam Smith',         'Level 1 Support',  'Agent',         '2020-06-01'),
('Emma Williams',      'Level 2 Support',  'Senior Agent',  '2018-11-20'),
('Noah Brown',         'Level 2 Support',  'Senior Agent',  '2021-01-10'),
('Ava Jones',          'Level 1 Support',  'Agent',         '2022-04-05'),
('William Garcia',     'Management',       'Team Lead',     '2017-08-12'),
('Sophia Martinez',    'Level 3 Support',  'Specialist',    '2019-07-30'),
('James Davis',        'Level 1 Support',  'Agent',         '2023-02-14'),
('Isabella Miller',    'Level 2 Support',  'Senior Agent',  '2020-09-22'),
('Oliver Wilson',      'Management',       'Manager',       '2016-05-18'),
('Mia Moore',          'Level 1 Support',  'Agent',         '2022-11-01'),
('Elijah Taylor',      'Level 3 Support',  'Specialist',    '2018-03-25'),
('Charlotte Anderson', 'Level 1 Support',  'Agent',         '2021-07-19'),
('Lucas Thomas',       'Level 2 Support',  'Senior Agent',  '2019-12-03'),
('Amelia Jackson',     'Level 1 Support',  'Agent',         '2023-05-08'),
('Mason White',        'Level 3 Support',  'Specialist',    '2017-10-15'),
('Harper Harris',      'Level 1 Support',  'Agent',         '2022-08-20'),
('Logan Martin',       'Level 2 Support',  'Senior Agent',  '2020-04-11'),
('Evelyn Thompson',    'Management',       'Team Lead',     '2018-06-27'),
('Aiden Garcia',       'Level 1 Support',  'Agent',         '2023-01-16'),
('Abigail Martinez',   'Level 1 Support',  'Agent',         '2021-10-04'),
('Carter Robinson',    'Level 2 Support',  'Senior Agent',  '2019-05-29'),
('Emily Clark',        'Level 3 Support',  'Specialist',    '2020-02-13'),
('Jackson Rodriguez',  'Level 1 Support',  'Agent',         '2022-06-30'),
('Scarlett Lewis',     'Level 1 Support',  'Agent',         '2023-03-22'),
('Sebastian Lee',      'Management',       'Manager',       '2015-11-09'),
('Grace Walker',       'Level 2 Support',  'Senior Agent',  '2021-04-17'),
('Henry Hall',         'Level 1 Support',  'Agent',         '2022-09-05'),
('Aria Allen',         'Level 3 Support',  'Specialist',    '2018-08-14'),
('Alexander Young',    'Level 1 Support',  'Agent',         '2020-12-01'),
('Chloe Hernandez',    'Level 2 Support',  'Senior Agent',  '2019-09-18'),
('Michael King',       'Level 1 Support',  'Agent',         '2023-06-10'),
('Penelope Wright',    'Level 1 Support',  'Agent',         '2022-01-25'),
('Daniel Lopez',       'Level 3 Support',  'Specialist',    '2017-04-03'),
('Layla Hill',         'Level 2 Support',  'Senior Agent',  '2021-08-12'),
('Matthew Scott',      'Level 1 Support',  'Agent',         '2023-04-29'),
('Riley Green',        'Management',       'Team Lead',     '2019-02-07'),
('Sebastian Adams',    'Level 1 Support',  'Agent',         '2022-07-18'),
('Zoey Baker',         'Level 2 Support',  'Senior Agent',  '2020-10-05'),
('Jack Gonzalez',      'Level 3 Support',  'Specialist',    '2018-01-22'),
('Victoria Nelson',    'Level 1 Support',  'Agent',         '2023-07-03'),
('Owen Carter',        'Level 1 Support',  'Agent',         '2021-11-14'),
('Nora Mitchell',      'Level 2 Support',  'Senior Agent',  '2020-07-08'),
('Wyatt Perez',        'Level 3 Support',  'Specialist',    '2017-12-19'),
('Hannah Roberts',     'Level 1 Support',  'Agent',         '2022-03-11'),
('Dylan Turner',       'Management',       'Manager',       '2016-09-28'),
('Lily Phillips',      'Level 1 Support',  'Agent',         '2023-08-15'),
('Nathan Campbell',    'Level 2 Support',  'Senior Agent',  '2019-11-06'),
('Eleanor Parker',     'Level 1 Support',  'Agent',         '2022-05-24'),
('Caleb Evans',        'Level 3 Support',  'Specialist',    '2018-07-31');


INSERT INTO calls (employee_id, call_time, phone, direction, status) VALUES
-- Older calls (> 3 days ago — already processed)
(1,  NOW() - INTERVAL 7 DAY + INTERVAL 1 HOUR,  '+380501234001', 'inbound',  'resolved'),
(2,  NOW() - INTERVAL 7 DAY + INTERVAL 2 HOUR,  '+380501234002', 'outbound', 'resolved'),
(3,  NOW() - INTERVAL 6 DAY + INTERVAL 1 HOUR,  '+380501234003', 'inbound',  'escalated'),
(4,  NOW() - INTERVAL 6 DAY + INTERVAL 3 HOUR,  '+380501234004', 'inbound',  'resolved'),
(5,  NOW() - INTERVAL 6 DAY + INTERVAL 5 HOUR,  '+380501234005', 'outbound', 'missed'),
(6,  NOW() - INTERVAL 5 DAY + INTERVAL 2 HOUR,  '+380501234006', 'inbound',  'resolved'),
(7,  NOW() - INTERVAL 5 DAY + INTERVAL 4 HOUR,  '+380501234007', 'outbound', 'resolved'),
(8,  NOW() - INTERVAL 5 DAY + INTERVAL 6 HOUR,  '+380501234008', 'inbound',  'escalated'),
(9,  NOW() - INTERVAL 4 DAY + INTERVAL 1 HOUR,  '+380501234009', 'inbound',  'resolved'),
(10, NOW() - INTERVAL 4 DAY + INTERVAL 3 HOUR,  '+380501234010', 'outbound', 'missed'),
(11, NOW() - INTERVAL 4 DAY + INTERVAL 5 HOUR,  '+380501234011', 'inbound',  'resolved'),
(12, NOW() - INTERVAL 3 DAY + INTERVAL 2 HOUR,  '+380501234012', 'outbound', 'resolved'),
(13, NOW() - INTERVAL 3 DAY + INTERVAL 4 HOUR,  '+380501234013', 'inbound',  'resolved'),
(14, NOW() - INTERVAL 3 DAY + INTERVAL 7 HOUR,  '+380501234014', 'inbound',  'escalated'),
(15, NOW() - INTERVAL 2 DAY + INTERVAL 1 HOUR,  '+380501234015', 'outbound', 'resolved'),
(16, NOW() - INTERVAL 2 DAY + INTERVAL 2 HOUR,  '+380501234016', 'inbound',  'resolved'),
(17, NOW() - INTERVAL 2 DAY + INTERVAL 4 HOUR,  '+380501234017', 'outbound', 'missed'),
(18, NOW() - INTERVAL 2 DAY + INTERVAL 6 HOUR,  '+380501234018', 'inbound',  'resolved'),
(19, NOW() - INTERVAL 1 DAY + INTERVAL 1 HOUR,  '+380501234019', 'inbound',  'resolved'),
(20, NOW() - INTERVAL 1 DAY + INTERVAL 2 HOUR,  '+380501234020', 'outbound', 'resolved'),
-- Recent calls (last 24 h — will be detected by first DAG run)
(21, NOW() - INTERVAL 23 HOUR, '+380501234021', 'inbound',  'resolved'),
(22, NOW() - INTERVAL 22 HOUR, '+380501234022', 'outbound', 'missed'),
(23, NOW() - INTERVAL 21 HOUR, '+380501234023', 'inbound',  'escalated'),
(24, NOW() - INTERVAL 20 HOUR, '+380501234024', 'inbound',  'resolved'),
(25, NOW() - INTERVAL 19 HOUR, '+380501234025', 'outbound', 'resolved'),
(26, NOW() - INTERVAL 18 HOUR, '+380501234026', 'inbound',  'resolved'),
(27, NOW() - INTERVAL 17 HOUR, '+380501234027', 'outbound', 'missed'),
(28, NOW() - INTERVAL 16 HOUR, '+380501234028', 'inbound',  'resolved'),
(29, NOW() - INTERVAL 15 HOUR, '+380501234029', 'inbound',  'escalated'),
(30, NOW() - INTERVAL 14 HOUR, '+380501234030', 'outbound', 'resolved'),
-- Very fresh calls (last 2 h — for subsequent DAG runs)
(31, NOW() - INTERVAL 110 MINUTE, '+380501234031', 'inbound',  'resolved'),
(32, NOW() - INTERVAL 100 MINUTE, '+380501234032', 'outbound', 'resolved'),
(33, NOW() - INTERVAL 90  MINUTE, '+380501234033', 'inbound',  'resolved'),
(34, NOW() - INTERVAL 80  MINUTE, '+380501234034', 'inbound',  'escalated'),
(35, NOW() - INTERVAL 70  MINUTE, '+380501234035', 'outbound', 'missed'),
(36, NOW() - INTERVAL 60  MINUTE, '+380501234036', 'inbound',  'resolved'),
(37, NOW() - INTERVAL 50  MINUTE, '+380501234037', 'outbound', 'resolved'),
(38, NOW() - INTERVAL 40  MINUTE, '+380501234038', 'inbound',  'resolved'),
(39, NOW() - INTERVAL 30  MINUTE, '+380501234039', 'inbound',  'resolved'),
(40, NOW() - INTERVAL 20  MINUTE, '+380501234040', 'outbound', 'resolved'),
(41, NOW() - INTERVAL 10  MINUTE, '+380501234041', 'inbound',  'missed'),
(42, NOW() - INTERVAL  5  MINUTE, '+380501234042', 'inbound',  'resolved'),
(43, NOW() - INTERVAL  4  MINUTE, '+380501234043', 'outbound', 'resolved'),
(44, NOW() - INTERVAL  3  MINUTE, '+380501234044', 'inbound',  'escalated'),
(45, NOW() - INTERVAL  2  MINUTE, '+380501234045', 'outbound', 'resolved'),
(46, NOW() - INTERVAL  1  MINUTE, '+380501234046', 'inbound',  'resolved'),
(1,  NOW(),                        '+380501234047', 'inbound',  'resolved'),
(5,  NOW(),                        '+380501234048', 'outbound', 'missed'),
(10, NOW(),                        '+380501234049', 'inbound',  'resolved'),
(15, NOW(),                        '+380501234050', 'outbound', 'resolved');

SELECT COUNT(*) FROM calls;
SELECT * FROM calls;
```

## Telephony data
<img width="1190" height="561" alt="Screenshot 2026-03-23 110804" src="https://github.com/user-attachments/assets/018a02a8-2dda-4d06-b32b-86183cedabfb" />

## Support calls dag

```python
from airflow import DAG
from airflow.operators.python import PythonOperator
from airflow.providers.mysql.hooks.mysql import MySqlHook
from airflow.models import Variable
from datetime import datetime, timedelta
import pandas as pd
import duckdb
import json
import os


TELEPHONY_DIR = "/usr/local/airflow/dags/telephony_data"
DUCKDB_PATH = "/tmp/support_calls.duckdb"


def _detect_new_calls(ti):
    hook = MySqlHook(mysql_conn_id='mysql_as2')
    last_time = Variable.get("last_loaded_call_time", default_var="2000-01-01 00:00:00")

    sql = f"SELECT call_id, employee_id, call_time, phone, direction, status FROM calls WHERE call_time > '{last_time}'"
    df = hook.get_pandas_df(sql)

    if df.empty:
        print("No new calls found.")
        return []

    print(f"New calls detected: {len(df)}")
    ti.xcom_push(key='new_calls_df', value=df.to_json())
    return df['call_id'].tolist()


def _load_telephony_details(ti):
    call_ids = ti.xcom_pull(task_ids='detect_new_calls')
    if not call_ids:
        return []

    telephony_data = []
    rejected_count = 0

    for cid in call_ids:
        file_path = os.path.join(TELEPHONY_DIR, f"call_{cid}.json")
        if os.path.exists(file_path):
            with open(file_path, 'r') as f:
                data = json.load(f)
                if all(k in data for k in ('duration_sec', 'short_description')) and data['duration_sec'] >= 0:
                    telephony_data.append(data)
                else:
                    rejected_count += 1
        else:
            print(f"File missing: {file_path}")
            rejected_count += 1

    print(f"Loaded {len(telephony_data)} JSONs. Rejected: {rejected_count}")
    return telephony_data


def _transform_and_load_duckdb(ti):
    calls_json = ti.xcom_pull(key='new_calls_df', task_ids='detect_new_calls')
    telephony_list = ti.xcom_pull(task_ids='load_telephony_details')

    if not calls_json or not telephony_list:
        print("Nothing to load into DuckDB.")
        return

    df_calls = pd.read_json(calls_json)
    df_telephony = pd.DataFrame(telephony_list)

    hook = MySqlHook(mysql_conn_id='mysql_as2')
    df_employees = hook.get_pandas_df("SELECT employee_id, full_name, team FROM employees")

    final_df = df_calls.merge(df_employees, on='employee_id').merge(df_telephony, on='call_id')

    if final_df.empty:
        print("No rows after join.")
        return

    print(f"Rows after join: {len(final_df)}")

    con = duckdb.connect(DUCKDB_PATH)
    con.execute("""
        CREATE TABLE IF NOT EXISTS support_call_enriched (
            call_id INTEGER PRIMARY KEY,
            employee_id INTEGER,
            call_time TIMESTAMP,
            phone VARCHAR,
            direction VARCHAR,
            status VARCHAR,
            full_name VARCHAR,
            team VARCHAR,
            duration_sec INTEGER,
            short_description TEXT
        )
    """)


    call_ids_str = ','.join(str(i) for i in final_df['call_id'].tolist())
    con.execute(f"DELETE FROM support_call_enriched WHERE call_id IN ({call_ids_str})")
    con.execute("INSERT INTO support_call_enriched SELECT * FROM final_df")

    total = con.execute("SELECT COUNT(*) FROM support_call_enriched").fetchone()[0]
    print(f"Inserted {len(final_df)} rows. Total in DuckDB: {total}")

    new_watermark = str(df_calls['call_time'].max())
    Variable.set("last_loaded_call_time", new_watermark)
    print(f"Watermark updated to: {new_watermark}")
    con.close()


default_args = {
    "owner": "airflow",
    "start_date": datetime(2026, 3, 1),
    "retries": 1,
    "retry_delay": timedelta(minutes=5),
}

with DAG(
        "hourly_support_pipeline",
        default_args=default_args,
        schedule="0 * * * *",
        catchup=False
) as dag:
    t1 = PythonOperator(task_id="detect_new_calls",          python_callable=_detect_new_calls)
    t2 = PythonOperator(task_id="load_telephony_details",    python_callable=_load_telephony_details)
    t3 = PythonOperator(task_id="transform_and_load_duckdb", python_callable=_transform_and_load_duckdb)

    t1 >> t2 >> t3
```

## Result

<img width="1237" height="350" alt="Screenshot 2026-03-23 100757" src="https://github.com/user-attachments/assets/0342ffb7-2ee1-4df9-88cc-85ca552559a2" />


