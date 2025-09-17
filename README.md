# Hotel Management System (Python + MySQL)

A simple **hotel management system** built with **Python** and **MySQL**.  
This project lets you manage **visitors, VIP visitors, room types, food menu, billing, and more** through a console-based menu-driven interface.

---

## Features

- Register visitor and VIP visitor details  
- View all visitors / VIP visitors  
- List all room types with pricing & amenities  
- Display hotel food menu and calculate bills  
- Delete visitor / VIP visitor records  
- Update phone numbers for visitors and VIPs  
- Manage billing (visitor & VIP bills)  
- View and sort visitors by check-in date  
- Calculate total bills for specific visitors
  
---

## Requirements

- **Python 3.x**
- **MySQL server** (with `world` database or custom one)
- Python libraries:
  - `mysql-connector-python`

Install the dependency with:

```bash
pip install mysql-connector-python
```

---

## Setup

1. Clone or download this repository.  
2. Create a MySQL database (default used here: `world`).  
3. Create the required tables:

```sql
CREATE TABLE Visitor (
    Aadhar VARCHAR(20) PRIMARY KEY,
    VName VARCHAR(50),
    VAge INT,
    VSex CHAR(1),
    CheckinDate DATE,
    VPhone VARCHAR(15),
    RoomType VARCHAR(30),
    RoomCharge DECIMAL(10,2),
    Total DECIMAL(10,2)
);

CREATE TABLE VIPVisitor (
    Aadhar1 VARCHAR(20) PRIMARY KEY,
    VName1 VARCHAR(50),
    VAge1 INT,
    VSex1 CHAR(1),
    CheckinDate1 DATE,
    VPhone1 VARCHAR(15),
    RoomType1 VARCHAR(30),
    RoomCharge1 DECIMAL(10,2),
    Total1 DECIMAL(10,2)
);

CREATE TABLE Bill (
    Aadhar VARCHAR(20),
    RoomNo INT,
    NoOfDays INT,
    Total DECIMAL(10,2)
);

CREATE TABLE VipBill (
    Aadhar1 VARCHAR(20),
    RoomNo1 INT,
    NoOfDays1 INT,
    Total DECIMAL(10,2)
);
```

4. Update the database connection in the script if needed:

```python
db1 = mysql.connector.connect(
    host="localhost",
    user="root",
    password="123456",
    database="world"
)
```

---

## Usage

Run the Python script:

```bash
python hotel.py
```

You'll see a **menu-driven interface**:

```
--------------------------------------------------
     CHOOSE AN OPERATION
--------------------------------------------------
1. Register Visitor Details
2. All Visitors Details
3. Register VIP Visitor Details
4. All VIP Visitor Details
...
19. Quit
```

Enter your choice and follow the prompts.

---

## Notes

- Ensure your MySQL server is running before launching the script.  
- Default database name is `world`. You can change it in the script if needed.  
- Phone numbers must be **10 digits**.  

---

## Future Enhancements

- Add a **GUI (Tkinter / PyQt / React frontend)**  
- Integrate **authentication system** (admin login)  
- Export bills to **PDF or Excel**  
- Cloud-based MySQL hosting for online hotel management  

---

## License

This project is open-source. Feel free to use and modify it for learning or personal use.
