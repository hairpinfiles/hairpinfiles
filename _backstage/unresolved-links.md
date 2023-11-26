---
title: Unresolved Links
description: a list of links which are "unresolved", aka the page they are trying to link to doesn't exist.
---
```dataview
TABLE WITHOUT ID key AS "unresolved link", rows.file.link AS "referencing file"
FROM !"_backstage"
FLATTEN file.outlinks as outlinks
WHERE !(outlinks.file)
GROUP BY outlinks
```