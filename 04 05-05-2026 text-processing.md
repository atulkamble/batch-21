# 📘 Linux Text Handling & File Operations – Hands-on Lab

---

## 📌 1️⃣ Basic System Commands

```bash
clear
sudo yum update -y
history
ls
ls -la
```

### 🔹 Points to Remember

* `history` → shows previously executed commands
* `ls -la` → shows hidden files + permissions

---

## 📌 2️⃣ File Creation & Editing

```bash
touch file1.txt
touch file2.txt
nano file1.txt
nano file2.txt
```

### 🔹 View Files

```bash
cat file1.txt
cat file2.txt
```

---

## 📌 3️⃣ Combine & Display Files

```bash
cat file1.txt file2.txt > combine.txt
cat combine.txt
tac combine.txt
nl combine.txt
```

### 🔹 Explanation

* `>` → overwrite output
* `tac` → reverse content
* `nl` → line numbers

---

## 📌 4️⃣ File Viewing Commands

```bash
head combine.txt
tail combine.txt
more combine.txt
less aws.txt
```

### 🔹 Difference

* `head` → first lines
* `tail` → last lines
* `more` → basic scroll
* `less` → advanced navigation

---

## 📌 5️⃣ Echo & Redirection

```bash
echo "hello world"
echo "hello world" > helloworld.txt
echo "World" >> helloworld.txt
```

### 🔹 Important

* `>` → overwrite
* `>>` → append

---

## 📌 6️⃣ File Copy, Move & Delete

```bash
cp a.txt b.txt
mv combine.txt newfile.txt
mv a.txt b.txt
rm aws.txt
rm file1.txt file2.txt helloworld.txt newfile.txt
rm -rf new/
```

### 🔹 Key Concepts

* `cp` → copy
* `mv` → rename/move
* `rm -rf` → force delete (⚠️ dangerous)

---

## 📌 7️⃣ Directory Management

```bash
mkdir new
mv b.txt new
tree
```

### 🔹 Install Tree

```bash
sudo yum install tree -y
tree --version
```

---

## 📌 8️⃣ Word Count (wc Command)

```bash
wc helloworld.txt
wc -l helloworld.txt
wc -w helloworld.txt
wc -c helloworld.txt
```

### 🔹 Output Meaning

```
lines  words  bytes
```

### ⚡ Example

```
2  2  12 helloworld.txt
```

👉 Extra bytes due to:

* newline characters (`\n`)
* spaces

---

## 📌 9️⃣ Pattern Searching (grep)

```bash
grep "el" helloworld.txt
grep -i "el" helloworld.txt
grep -c "el" helloworld.txt
grep "Hello" helloworld.txt
grep -c "Hello" helloworld.txt
```

### 🔹 Options

* `-i` → ignore case
* `-c` → count matches

---

## 📌 🔟 File Content Example

```bash
Hello
World
```

---

## 📌 1️⃣1️⃣ Important Learning Summary

### 🔥 Must Know Commands

* File ops → `touch`, `cp`, `mv`, `rm`
* Viewing → `cat`, `head`, `tail`, `less`
* Processing → `wc`, `grep`
* Editing → `nano`

---

## ⚡ DevOps / Interview Tips

* Always remember:

  * `>` overwrite vs `>>` append
  * `grep -i` for case-insensitive search
  * `wc -c` counts bytes (includes newline)
* `rm -rf` should be used carefully (production risk ⚠️)
* Combine commands using pipes later (`|`)

---

## 📦 Suggested GitHub Repo Name

```
linux-text-processing-lab
```

OR

```
linux-file-handling-practice
```

OR (best for your profile 👇)

```
linux-cli-devops-labs
```

---
