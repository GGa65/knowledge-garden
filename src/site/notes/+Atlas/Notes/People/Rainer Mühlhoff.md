```dataview
TABLE 
  file.link as Notiz
FROM "09_Sources"   
WHERE [file.frontmatter.autor:[[Rainer Mühlhoff]]]
GROUP BY file.link as SourceNote
SORT rows.file.day desc

```