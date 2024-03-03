---
{"dg-publish":true,"permalink":"/atlas/notes/ideas-notes/source-note-public/","tags":["class/admin","class/index"],"noteIcon":""}
---

2024-03-03T00:00:00.000+01:00

> [!info] Was ist eine Source-Note.
> - eine Source-Note ist **der Typ einer Notiz, der eine Quelle referenziert**
> - In Abgrenzung dazu gibt es weitere **[[Atlas/Notes/Ideas+Notes/Notiz-Typen\|Notiz-Typen]]**

> [!hint] Öffentliche Source Notes
> Nicht alle Source-Notes in meinem PKM-System sind öffentlich, aber die es sind. habe ich Euch hier mittels Data-View zusammengestellt:
>  
> ```dataview
Table without ID
  file.link as Notiz,
  file.folder as Ort,
  file.cday as Erstellt
FROM #class/sourceNote and !"Templates" and !"00_Admin"
WHERE dg-publish = true
SORT file.name, file.ctime ASC
