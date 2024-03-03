---
{"dg-publish":true,"permalink":"/atlas/notes/ideas-notes/personen-notizen-public/","tags":["class/admin","class/index"],"noteIcon":""}
---

by GGa, 2024-03-03T00:00:00.000+01:00  

> [!Info] Was ist eine Personen-Notiz?
> eine **Personen-Notiz** ist eine Notiz-Typisierung innerhalb des Vaults, die Verwendung findet für Notizen über Menschen wie
> - Personen öffentlichen Interesses, denen ich innerhalb meines PKM-Systems in irgendeiner Art begegne
> - Arbeitskollegen & Branchen-Kollegen
> - Menschen, mit denen man vernetzt ist
> - Autoren, deren Bücher und Texte man liest

> [!sparkles] Purpose
> Man kann sich fragen, warum mache ich explizit Notizen über Menschen? 
> Gegenfrage: Warum notieren hunderte Freiwillige auf Wikipedia etwas über Wissenschaftler, Politiker, Künstler ...?
> 
> Ich möchte auch Begegnungen (aller Art) mit Menschen, die mich inspirieren, mir Feedback geben, mich herausfordern ... in meinem PKM-System festhalten.
> 

> [!hint] Öffentliche Personen Notizen
> Nicht alle Personen-Notizen in meinem PKM-System sind öffentlich, aber die es sind. habe ich Euch hier mittels Data-View zusammengestellt:
>  
> ```dataview
Table without ID
  file.link as Notiz,
  file.folder as Ort,
  file.cday as Erstellt
FROM #class/people  and !"Templates" and !"00_Admin"
WHERE dg-publish = true
SORT file.name, file.ctime ASC
