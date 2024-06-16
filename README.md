# SoupDB: A Lightweight HTML-based Database Management Framework

SoupDB is a lightweight and flexible HTML-based database management framework built with Python and BeautifulSoup. It allows you to create, manage, and query HTML-based databases using familiar database operations and CSS selectors. Whether you need to handle small datasets or manage data in a web-friendly format, SoupDB provides an intuitive and powerful solution.

## Features
- **Dynamic Column Management**: Add, delete, and rename columns dynamically.
- **Row Operations**: Add, update, delete, and query rows with ease.
- **Sorting and Filtering**: Sort and filter rows based on column values.
- **Aggregation Functions**: Perform sum, average, min, and max operations on numeric columns.
- **Search and Pagination**: Search for specific values and paginate results for large datasets.
- **CSV Import/Export**: Seamlessly import from and export to CSV files.
- **Conditional Updates**: Update rows based on specified conditions.
- **Duplicate Detection and Removal**: Detect and remove duplicate rows.
- **CSS Selector Querying**: Utilize the power of CSS selectors for querying data.

## Installation

```bash
pip install beautifulsoup4
```

## Usage

### Initialize SoupDB
```python
from soupdb import HTMLDatabase

# Create an HTML database instance with dynamic columns
db = HTMLDatabase("Employee Database", ["ID", "Name", "Age", "Occupation"])

# Add columns dynamically
db.add_column("Department")
```

### Add Rows
```python
# Add rows to the database
db.add_row([1, "John Doe", 30, "Engineer", "R&D"])
db.add_row([2, "Jane Smith", 25, "Designer", "UI/UX"])
db.add_row([3, "Sam Brown", 40, "Manager", "HR"])
```

### Query and Sort Data
```python
# Sort by Age
db.sort_by_column("Age")
sorted_by_age = db.get_all_rows()

# Filter rows by Occupation
filtered_by_occupation = db.filter_rows("Occupation", "Designer")
```

### Export to and Import from CSV
```python
# Export to CSV
db.export_to_csv("database.csv")

# Create a new database instance and import from CSV
new_db = HTMLDatabase()
new_db.import_from_csv("database.csv")
imported_data = new_db.get_all_rows()
```

### Aggregate Functions
```python
# Aggregate functions
sum_of_ages = db.aggregate("Age", "sum")
average_age = db.aggregate("Age", "average")
min_age = db.aggregate("Age", "min")
max_age = db.aggregate("Age", "max")
```

### Search and Pagination
```python
# Search
search_results = db.search("John Doe")

# Pagination
paginated_results = db.paginate(1, 2)
```

### Conditional Update and Remove Duplicates
```python
# Conditional update
db.conditional_update("Name", "Jane Smith", [2, "Jane Doe", 26, "Lead Designer", "UI/UX"])

# Remove duplicates
db.remove_duplicates()
```

### Save to and Load from HTML
```python
# Save the database to an HTML file
db.save_to_file("database.html")

# Load the HTML content back for querying
db.load_from_file("database.html")
```

## Contributing
Contributions are welcome! Please feel free to submit a Pull Request or open an issue to help improve SoupDB.

## License
This project is licensed under the MIT License.
