# **huppup**

## Setup

### Node stuff

First thing is there's some error with the webpack build that's solved with: `export NODE_OPTIONS=--openssl-legacy-provider`

Except VS Code doesn't start when that's set, so ... okay, I don't know about build/serve/etc, for the moment it's in the npm script, start the project with `yarn dev`

### Postgres

Then we've run `sudo -u postgres createuser --superuser gareth` and `sudo -u postgres createdb --owner=gareth huppup`

Thanks! [https://www3.ntu.edu.sg/home/ehchua/programming/sql/PostgreSQL_GetStarted.html](https://www3.ntu.edu.sg/home/ehchua/programming/sql/PostgreSQL_GetStarted.html)

Then we've updated schema.prisma and .env.local, deleted the migrations folder, and ran `blitz prisma migrate dev`

Note, we have not set up a test db, nor edited .env.test.local

Whoop, okay, need a password if connecting over TCP, so `psql huppup` and then `\password gareth` and then add that to the connection string in .env.local, _then_ it will work.
