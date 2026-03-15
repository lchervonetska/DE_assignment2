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
