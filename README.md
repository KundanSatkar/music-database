# 🎵 Online Music Store — Database System

A fully normalized relational database system for an online music store,
built with PostgreSQL. Designed to handle 500K+ records with optimized 
query performance and BCNF normalization across 16 interconnected tables.

---

## 📊 Results
- ⚡ Reduced query execution time by **35%** through multi-column indexing
- 📈 Delivered insights **2x faster** to stakeholders
- 🔄 Improved query consistency by **40%** via normalization
- 🗄️ Handles **500K+ records** across 16 tables
- 📋 Developed **15+ complex SQL queries** for KPI reporting

---

## 🛠️ Tech Stack

| Layer | Tools |
|---|---|
| Database | PostgreSQL |
| Query Language | SQL |
| Analysis | Google BigQuery |
| Interface | Jupyter Notebook, Python |
| Normalization | BCNF (Boyce-Codd Normal Form) |

---

## 🏗️ Database Schema

16 interconnected tables covering:
- `customer` · `customer_location` · `customerbilling`
- `invoice` · `invoice_line`
- `track` · `track_price` · `album` · `artist`
- `genre` · `media_type` · `media_type_pricing`
- `playlist` · `playlist_track`
- `employee` · `location`

**E/R Diagram:**

![ER Diagram](E:R-Diagram.png)

---

## 🔬 Key Features

- Full normalization to **BCNF** with proper decomposition
- **Foreign keys, NOT NULLs, and enums** enforced throughout
- Query execution analysis using **EXPLAIN** before/after indexing
- Complex **JOIN, GROUP BY, Subquery** analytics
- Insights on top tracks, revenue by genre, and customer behavior

---

## 🚀 How to Run
```bash
# 1. Clone the repo
git clone https://github.com/KundanSatkar/music-database.git
cd music-database

# 2. Create the database
psql -d music -f create.sql

# 3. Load the data
psql -d music -f load.sql

# 4. Run queries interactively
jupyter notebook create_load.ipynb
```

> 💡 If create.sql or load.sql don't work, run the `create_load.ipynb` notebook directly.
> Database name: `music`

---

## 📁 Project Structure
```
music-database/
├── SQL/                  # SQL scripts
│   ├── create.sql        # Schema creation
│   └── load.sql          # Data loading
├── Data/                 # CSV files for all 16 tables
├── create_load.ipynb     # Interactive notebook
├── E:R-Diagram.png       # Entity-Relationship diagram
├── requirements.txt
└── README.md
```

---

## 💡 Sample Queries
```sql
-- Top 5 genres by total revenue
SELECT g.name, SUM(il.unit_price * il.quantity) AS revenue
FROM invoice_line il
JOIN track t ON il.track_id = t.track_id
JOIN genre g ON t.genre_id = g.genre_id
GROUP BY g.name
ORDER BY revenue DESC
LIMIT 5;
```


## 📬 Contact
**Kundan Satkar** — Database Design & SQL Analytics

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Kundan%20Satkar-blue?logo=linkedin)](https://www.linkedin.com/in/kundan-satkar)
[![GitHub](https://img.shields.io/badge/GitHub-KundanSatkar-black?logo=github)](https://github.com/KundanSatkar)
[![Email](https://img.shields.io/badge/Email-kundansatkar0%40gmail.com-red?logo=gmail)](mailto:kundansatkar0@gmail.com)
