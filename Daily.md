# << [[<% moment(tp.file.title,'DD.MM.YY').add(-1,'days').format("DD.MM.YY") %>|⏪ Yesterday (<% moment(tp.file.title,'DD.MM.YY').add(-1,'days').format("DD.MM.YY") %>)]] | {{date:dddd}} | [[<% moment(tp.file.title,'DD.MM.YY').add(1,'days').format("DD.MM.YY") %>| Tomorrow (<% moment(tp.file.title,'DD.MM.YY').add(1,'days').format("DD.MM.YY") %>) ⏩]] >>


>[!example]- Links
>- [[KW<% tp.date.now("WW")%> <% tp.date.now("YYYY") %>]] | [[Next Actions]] | [[Waiting For]] | [[Someday Maybe]] | [[Mein Erreichtes]] | 

## Journal
<% tp.file.cursor(1) %>


>[!todo]- Aufgaben
>```tasks
>(due before <% tp.date.now("YYYY-MM-DD", 1, tp.file.title, "DD.MM.YYYY") %>) OR (description includes <% tp.date.now("DD.MM.YY", 0, tp.file.title, "DD.MM.YY") %>) OR (created on  <% tp.date.now("YYYY-MM-DD", 0, tp.file.title, "DD.MM.YYYY") %> )
>group by priority
>not done
>```
>![[New Tasks]]


>[!info]- Daily review
> - Empty inboxes
> - Review tomorrow's calendar
> - Write Hemingway Bridges

>[!check]- 
> ```tasks
>done <% tp.date.now("YYYY-MM-DD", 0, tp.file.title, "YYYY-MM-DD") %>
>hide due date
>hide recurrence rule
>hide done date
>heading does not include Daily Routine
>heading does not include Daily Review
>```

>[!done]- 📎 Changed files
>```dataview
>TABLE file.mtime AS "Last Modified"
>WHERE (file.mday = this.file.cday) and (file.name != this.file.name)
>SORT file.mtime DESC
>```