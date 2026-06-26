# Just Another Budget App - JABA

I decided that using a google form to record and store all my expenses was boring. So why not put my
computer science degree to good use??

This is just a fun little project I'm working on in my free time, if you somehow came across this
and want to use it go right ahead.

## So What Is This?

Not to be confused with any Huts, JABA is a simple webapp that allows you to record expenses (and
income!) quickly and intuitively. The current stored fields are:

- Amount: $ (cuz I'm American)
- Type: expense or income
- Category: A predefined category for the entry, with possibilities determined by the values in
  [src/lib/categories.ts](src/lib/categories.ts). A fuzzy search (thanks fuse!) helps you see what
  the possible categories are when you get to make an entry.
- Description: Something a bit more detailed than 'Category', but could still come up again. Like
  specifying which brand of gas station you went to. And there's a fuzzy search here too don't
  worry.
- Notes: Freeform for any extra information you want. Maybe you went to Kroger and bought $300 of
  cheese and want your tracker to be aware.
- Date: When the transaction occurs! And it defaults to the current date because clicking is
  something to be avoided.

## So How Do I Use It?

You actually want to? Awesome! I'm hoping to get some dockerfile setup later, but for now I'll just
throw a bunch of information at you and let you figure it out from there.

### Tech Stack

- [SvelteKit](https://kit.svelte.dev) - full-stack web framework
- [Drizzle ORM](https://orm.drizzle.team) - type-safe database queries
- [SQLite](https://sqlite.org) - local database via
  [better-sqlite3](https://github.com/WiseLibs/better-sqlite3)
- [Fuse.js](https://fusejs.io) - fuzzy search for autocomplete
- [Lucide Svelte](https://lucide.dev) - icons

### Project Structure

So you don't get lost finding the important stuff I hid around:

- [`src/routes/`](src/routes/) - page routes
- [`src/lib/server/db/`](src/lib/server/db/) - database schema, connection, and seed
- [`src/lib/categories.ts`](src/lib/categories.ts) - hardcoded category list
- [`drizzle/`](drizzle/) - generated migration files

### Getting Started

#### Prerequisites

- Node.js 20+

#### Installation

```bash
git clone https://github.com/rabbitrancher/JABA.git
cd JABA
npm install
```

#### Database Setup

```bash
npm run db:push
```

This generates migrations, applies them, and seeds the categories table.

#### Development

```bash
npm run dev
```

## License

MIT
