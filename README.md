# todo_list_rust

A tiny interactive todo CLI in Rust, with persistence to a plain text file. Zero dependencies — just `std`.

## What it does

Loops at a prompt that accepts:

| Command | Behavior |
| --- | --- |
| `create` | Asks for title, description, and priority (1–10). Validates input, appends to the list, persists to `db.txt`. |
| `delete` | Asks for a title, removes the matching item, persists. |
| `read` | Asks for a title, prints title / description / priority. |
| `read all` | Prints every item separated by a delimiter. |

State lives in `db.txt`, written line-by-line as `title\ndescription\npriority\n/////` records. The file is reloaded into memory on every startup.

## Run it

```sh
cargo run
```

```
What do you want to do? [create || update || delete || read || read all]
create
Enter the title of your todo item
Buy bread
Enter the description of your todo item
Sourdough
Enter the priority of your todo item
3
```

## Why

A small exercise in Rust ownership and borrowing: structs (`Item`, `TodoItems`), `&self` vs `&mut self` methods, owning vs borrowing strings, and rolling a simple line-oriented serializer + loader without `serde`.

## Stack

Rust 2021 · `std` only (no external deps)
