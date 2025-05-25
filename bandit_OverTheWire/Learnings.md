# 0.

Simple SSH login using the port and username. Nothing fancy here.

---

# 1.

Reading a file named `-` (a single dash).

* Use `./-` to explicitly point to the file in the current directory.
* Reminder: a lone `-` is often treated as STDIN/STDOUT (like `/dev/stdin` or `/dev/stdout`), so you need to avoid ambiguity.

---

# 2.

Reading a file with spaces in its name.

* Wrap the filename in quotes: `'filename with spaces'`
* Alternatively, escape the spaces using backslashes.

---

# 3.

The password is stored in a hidden file within a directory.

* Learn how to list hidden files using `ls -a`.
* Once you spot it, just `cat` the file like usual.

---

# 4.

You’re in a directory full of files—only one has the password, the rest are garbage.

* Most of the filenames start with `-f...`, so use `./filename` to avoid command confusion.
* Instead of `cat`ting everything, try using:

  ```bash
  file * | grep 'ASCII text'
  ```

  (This needs a small tweak, though—keep at it.)

---

# 5.

A bunch of file descriptions are given. Use them to identify the right file.

* The `file` command helps again here.
* You *can* solve it just using the file size, but don’t skip checking the `man` page—there’s a tiny but important detail.
* Quick tip:

  ```bash
  ! -executable
  ```

  filters out files with any execute bit set.

---

# 6.

Now you’re searching the **entire system**. Sounds wild, but it’s doable.

* Use `find` with flags like `-user`, `-group`, and maybe `-size`.
* Pipe errors to `/dev/null` to ignore permission issues:

  ```bash
  find / -user ... -group ... 2>/dev/null
  ```

---

# 7.

An easier one. Just combine `cat` and `grep`. You got this.

---

# 8.

This one's a bit of a thinker. You’ll need to chain commands properly.

* Read up on what each one does. Think: `cat`, `sort`, `uniq`, maybe more.
* The solution is in the piping.

---

# 9.

A fun one. You'll meet a new command: `strings`.

* Run it on the file and you’ll spot the password in no time.

---

# 10.

This one is self-explanatory. The answer is in the question—literally.

---

Let me know if you want this formatted for a specific platform (GitHub, PDF, terminal notes, etc.).
