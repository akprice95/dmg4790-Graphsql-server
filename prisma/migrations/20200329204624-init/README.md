# Migration `20200329204624-init`

This migration has been generated at 3/29/2020, 8:46:24 PM.
You can check out the [state of the schema](./schema.prisma) after the migration.

## Database Steps

```sql
CREATE TABLE "public"."Course" (
    "courseCode" text  NOT NULL DEFAULT '',
    "createdAt" timestamp(3)  NOT NULL DEFAULT '1970-01-01 00:00:00',
    "defaultCredits" text  NOT NULL DEFAULT '',
    "description" text  NOT NULL DEFAULT '',
    "id" text  NOT NULL ,
    "name" text  NOT NULL DEFAULT '',
    "termsOffered" text  NOT NULL DEFAULT '',
    "updatedAt" timestamp(3)  NOT NULL DEFAULT '1970-01-01 00:00:00',
    PRIMARY KEY ("id")
) 
```

## Changes

```diff
diff --git schema.prisma schema.prisma
migration ..20200329204624-init
--- datamodel.dml
+++ datamodel.dml
@@ -1,0 +1,19 @@
+datasource db {
+  provider = "postgresql"
+  url      = "postgresql://postgres:docker@localhost:5432/pg-docker?schema=public"
+}
+
+generator client {
+  provider = "prisma-client-js"
+}
+
+model Course {
+  id             String   @default(cuid()) @id
+  createdAt      DateTime @default(now())
+  updatedAt      DateTime @updatedAt
+  name           String
+  description    String
+  defaultCredits String
+  courseCode     String
+  termsOffered   String
+}
```


