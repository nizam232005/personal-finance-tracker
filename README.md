"# personal-finance-tracker" 
# 💰 Personal Finance Tracker

A command-line Python application to track personal income and expenses, stored persistently in a CSV file, with date-range filtering, financial summaries, and matplotlib visualizations.

-----

## 🚀 Features

- **Add Transactions** — Log income or expenses with date, amount, category, and description
- **View by Date Range** — Filter and display all transactions between two dates
- **Financial Summary** — Auto-calculates total income, total expenses, and net savings
- **Visual Plot** — Line chart showing income vs. expenses over time using matplotlib
- **Persistent Storage** — All data saved to `finance_data.csv` (survives restarts)
- **Smart Date Input** — Press Enter to default to today’s date

-----

## 🛠️ Tech Stack

|Component      |Technology                   |
|---------------|-----------------------------|
|Language       |Python 3                     |
|Data Storage   |CSV (via `csv` and `pandas`) |
|Data Processing|pandas                       |
|Visualization  |matplotlib                   |
|User Input     |Custom `data_entry.py` module|

-----

## 📁 Project Structure

```
finance-tracker/
│
├── main.py            # Core logic — CSV class, plotting, main menu loop
├── data_entry.py      # Input helper functions (date, amount, category, description)
└── finance_data.csv   # Auto-created on first run; stores all transactions
```

-----

## ⚙️ Installation & Setup

### Prerequisites

- Python 3.8+
- pip

### Steps

```bash
# 1. Clone the repository
git clone https://github.com/nizam232005/<repo-name>.git
cd <repo-name>

# 2. Install dependencies
pip install pandas matplotlib

# 3. Run the app
python main.py
```

-----

## 🗺️ How It Works

On launch, you get a simple menu:

```
1. Add a new transaction
2. View transactions and summary within a date range
3. Exit
```

### Option 1 — Add a Transaction

Prompts you for:

- **Date** — in `dd-mm-yyyy` format (or press Enter for today)
- **Amount** — must be a positive number
- **Category** — `Income` or `Expense`
- **Description** — brief note about the transaction

The entry is appended to `finance_data.csv`.

### Option 2 — View & Summarize

- Enter a start and end date
- Displays all matching transactions in a formatted table
- Shows **Total Income**, **Total Expense**, and **Net Savings**
- Optionally plots an Income vs. Expense line chart

### Option 3 — Exit

-----

## 📊 CSV Format (`finance_data.csv`)

```
date,amount,category,description
01-05-2025,5000,Income,Monthly salary
05-05-2025,1200,Expense,Rent payment
10-05-2025,300,Expense,Groceries
```

-----

## 🧩 Key Modules Explained

### `CSV` Class (`main.py`)

A utility class with three class methods:

|Method              |What it does                                               |
|--------------------|-----------------------------------------------------------|
|`initialize_csv()`  |Creates `finance_data.csv` with headers if it doesn’t exist|
|`add_entry()`       |Appends a new row to the CSV file                          |
|`get_transactions()`|Reads CSV, filters by date range, prints summary           |

### `plot_transactions(df)`

Takes the filtered DataFrame, resamples by day, and plots:

- 🟢 Green line → Daily Income
- 🔴 Red line → Daily Expenses

### `data_entry.py` (helper module)

Contains input validation functions:

- `get_date()` — validates `dd-mm-yyyy` format, supports default to today
- `get_amount()` — ensures positive numeric input
- `get_category()` — restricts to `Income` or `Expense`
- `get_descriptipn()` — free text description *(note: typo in original — `descriptipn`)*

-----

## 🔮 Future Improvements

- Add a GUI using Tkinter or a web interface with Flask
- Support multiple categories (Food, Rent, Salary, etc.)
- Monthly/weekly summary reports
- Export filtered data to PDF or Excel
- Budget limit alerts per category

-----

## 👤 Author

**Nizam** — B.Tech AI & Data Science, RCET Thrissur (KTU), Batch 2023–2027
