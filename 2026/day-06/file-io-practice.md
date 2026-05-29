# File I/O Practice

Objective

Practice basic file creation, writing, appending, and reading using Linux command-line tools.

⸻

## File Creation

touch notes.txt

Creates an empty file.

⸻

## Writing and Appending

echo "Linux file practice" > notes.txt
echo "Learning redirection" >> notes.txt
echo "Learning DevOps" >> notes.txt

* ">" overwrites file contents.
* ">>" appends new content.

⸻

## Reading Files

cat notes.txt
head -n 2 notes.txt
tail -n 2 notes.txt

* cat displays the full file.
* head displays the beginning.
* tail displays the end.

⸻

## Using tee

echo "Using tee command" | tee -a notes.txt

Displays output and writes to a file simultaneously.

⸻

# Additional Practice

## Search Text

grep "ERROR" app.log
grep -v "ERROR" app.log

* Search matching lines.
* Display non-matching lines.

## Count Entries

grep "ERROR" app.log | wc -l

Count matching log entries.

## Show Line Numbers

cat -n app.log
nl app.log

Display file contents with line numbers.

## Extract Fields

cut -d ":" -f1 users.txt
cut -d ":" -f2 users.txt
cut -d ":" -f3 users.txt

Extract fields using a delimiter.

## Find Files

find . -name "*.log"

Locate log files.

## Sort and Count Unique Values

grep "ERROR" app.log | sort | uniq
grep "ERROR" app.log | sort | uniq -c
grep "ERROR" app.log | sort | uniq -c | sort -nr

Used to identify the most common log errors.

⸻

## Key Takeaways

* ">" overwrites files.
* ">>" appends to files.
* tee writes to a file and displays output.
* grep is the primary tool for searching logs.
* wc -l counts entries.
* sort and uniq help summarize log data.
* Linux commands become more powerful when combined with pipes (|).
