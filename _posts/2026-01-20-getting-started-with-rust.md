---
title: "Getting Started with Rust: A Beginner's Journey"
description: "My first steps into the world of Rust programming and why I think it's worth learning in 2026."
date: 2026-01-20
categories: [tech]
tags: [rust, programming, learning]
---

After years of writing JavaScript and Python, I decided to venture into systems programming with Rust. Here's what I've learned so far.

## Why Rust?

The promise of memory safety without garbage collection always intrigued me. In a world where security vulnerabilities from memory issues still plague major software, Rust's approach feels refreshingly modern.

## First Impressions

The borrow checker was humbling. Coming from languages where you don't think twice about references, Rust forces you to be explicit about ownership. At first, it felt like fighting the compiler. Now, it feels like having a patient teacher.

```rust
fn main() {
    let s1 = String::from("hello");
    let s2 = &s1; // Borrowing, not moving
    println!("{} {}", s1, s2);
}
```

## Resources That Helped

- The official Rust Book (it's genuinely excellent)
- Rustlings for hands-on exercises
- The Rust community on Discord

## What's Next

I'm planning to build a small CLI tool to solidify my understanding. Stay tuned for updates on that project.

The learning curve is steep, but the view from here is already looking promising.
