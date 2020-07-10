# Migration `20200709200359-created-contact`

This migration has been generated at 7/9/2020, 8:03:59 PM.
You can check out the [state of the schema](./schema.prisma) after the migration.

## Database Steps

```sql
PRAGMA foreign_keys=OFF;

CREATE TABLE "quaint"."Contact" (
"createdAt" DATE NOT NULL DEFAULT CURRENT_TIMESTAMP ,"email" TEXT NOT NULL  ,"id" INTEGER NOT NULL  PRIMARY KEY AUTOINCREMENT,"message" TEXT NOT NULL  ,"name" TEXT NOT NULL  )

PRAGMA "quaint".foreign_key_check;

PRAGMA foreign_keys=ON;
```

## Changes

```diff
diff --git schema.prisma schema.prisma
migration 20200709182912-created-post..20200709200359-created-contact
--- datamodel.dml
+++ datamodel.dml
@@ -1,7 +1,7 @@
 datasource DS {
   provider = "sqlite"
-  url = "***"
+  url = "***"
 }
 generator client {
   provider      = "prisma-client-js"
@@ -9,11 +9,18 @@
 }
 // Define your own datamodels here and run `yarn redwood db save` to create
 // migrations for them.
-// TODO: Please remove the following example:
 model Post {
   id        Int      @id @default(autoincrement())
   title     String
   body      String
   createdAt DateTime @default(now())
 }
+
+model Contact {
+  id        Int      @id @default(autoincrement())
+  name      String
+  email     String
+  message   String
+  createdAt DateTime @default(now())
+}
```


