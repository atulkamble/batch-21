# 📘 Introduction to Text Processing in Linux

Text processing is one of the most powerful features of Linux.
Linux treats **everything as a file**, and most operations are performed using text-based commands.

### 🔹 Why Text Processing?

* Automate tasks
* Analyze logs
* Filter data
* Transform output
* Build pipelines (DevOps, SRE, Cloud)

---

# 📄 File Viewing Commands

## 1. `cat` (Concatenate)

```bash
cat file.txt
```

* Displays full content
* Used to combine files

✅ Points:

* Not suitable for large files

---

## 2. `less`

```bash
less file.txt
```

* Scroll up/down
* Better for large files

✅ Shortcuts:

* `q` → quit
* `/word` → search

---

## 3. `more`

```bash
more file.txt
```

* Page-by-page viewing

✅ Limitation:

* No backward scrolling

---

## 4. `head`

```bash
head file.txt
head -n 5 file.txt
```

* Shows first lines (default: 10)

---

## 5. `tail`

```bash
tail file.txt
tail -n 5 file.txt
tail -f file.txt
```

* Shows last lines
* `-f` → live log monitoring (VERY IMPORTANT)

---

# 📝 File Creation & Basic Handling

```bash
touch file.txt        # create empty file
echo "Hello" > file.txt
nano file.txt
vi file.txt
```

✅ Points:

* `touch` → create/update timestamp
* `echo` → quick content writing

---

# 🔁 Output Redirection

## Types:

### 1. Overwrite (`>`)

```bash
echo "Hello" > file.txt
```

### 2. Append (`>>`)

```bash
echo "World" >> file.txt
```

### 3. Error Redirection

```bash
command 2> error.log
```

### 4. All Output

```bash
command > output.log 2>&1
```

✅ Points:

* `>` replaces content
* `>>` adds content

---

# 🔗 Pipes and Command Chaining

## Pipe (`|`)

```bash
cat file.txt | grep "error"
```

👉 Output of one command → input of another

---

## Command Chaining

```bash
cmd1 && cmd2   # run cmd2 if cmd1 succeeds
cmd1 || cmd2   # run cmd2 if cmd1 fails
cmd1 ; cmd2    # run both always
```

✅ Points:

* `|` → data flow
* `&&` → success-based execution

---

# 📊 Word Count & Statistics (`wc`)

```bash
wc file.txt
wc -l file.txt   # lines
wc -w file.txt   # words
wc -c file.txt   # characters
```

✅ Output format:

```
lines words characters filename
```

---

# 🔍 Pattern Searching with grep

```bash
grep "error" file.txt
```

## Useful Options:

```bash
grep -i "error" file.txt   # ignore case
grep -n "error" file.txt   # line numbers
grep -r "error" /dir       # recursive
grep -v "error" file.txt   # NOT match
```

✅ Points:

* Very important for logs
* Used in DevOps monitoring

---

# 🔢 Text Processing with sort and uniq

## sort

```bash
sort file.txt
sort -r file.txt   # reverse
sort -n file.txt   # numeric
```

## uniq

```bash
uniq file.txt
uniq -c file.txt   # count duplicates
```

👉 Best Practice:

```bash
sort file.txt | uniq
```

✅ Points:

* `uniq` works only on **sorted data**

---

# ✂️ Text Extraction using cut

```bash
cut -d ":" -f1 /etc/passwd
```

## Options:

* `-d` → delimiter
* `-f` → field number

Example:

```bash
echo "name:age:city" | cut -d ":" -f2
```

Output:

```
age
```

---

# ⚡ Important Points to Remember (Exam + Interview)

### 🔥 Must-Know Commands

* `cat`, `less`, `head`, `tail`
* `grep`, `wc`, `cut`
* `sort`, `uniq`

---

### 🔥 High-Value Concepts

* `tail -f` → log monitoring
* `| (pipe)` → command chaining
* `>` vs `>>` → overwrite vs append
* `grep -i`, `-r`, `-v` → common flags

---

### 🔥 Real-Time Use Cases

* Log analysis:

```bash
tail -f app.log | grep "ERROR"
```

* Count errors:

```bash
grep "ERROR" app.log | wc -l
```

* Unique IPs:

```bash
cut -d " " -f1 access.log | sort | uniq -c
```

---

### 🔥 Interview Tip

👉 Combine commands (very important):

```bash
cat file.txt | grep "data" | sort | uniq -c
```

---
