---
title: "Bad file mode | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID54"
dev_langs: 
  - "VB"
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Bad file mode
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Zur Bearbeitung des Dateiinhalts verwendete Anweisungen müssen für den Modus, in dem die Datei geöffnet wurde, geeignet sein.  Mögliche Ursachen sind:  
  
-   Eine `FilePutObject`\- oder `FileGetObject`\-Anweisung gibt eine sequenzielle Datei an.  
  
-   Eine `Print`\-Anweisung gibt eine Datei an, die für einen anderen Zugriffsmodus als `Output` oder `Append` geöffnet wurde.  
  
-   Eine `Input`\-Anweisung gibt eine Datei an, die für einen anderen Zugriffsmodus als `Input` geöffnet wurde.  
  
-   Es wurde versucht, in eine schreibgeschützte Datei zu schreiben.  
  
### So beheben Sie diesen Fehler  
  
-   Stellen Sie sicher, dass `FilePutObject` und `FileGetObject` ausschließlich auf Dateien verweisen, die im Zugriffsmodus `Random` oder `Binary` geöffnet sind.  
  
-   Stellen Sie sicher, dass `Print` eine Datei angibt, die für den Zugriffsmodus `Output` oder `Append` geöffnet ist.  Andernfalls verwenden Sie eine andere Anweisung, um die Daten in die Datei einzufügen oder um die Datei im geeigneten Modus erneut zu öffnen.  
  
-   Stellen Sie sicher, dass `Input` eine für `Input` geöffnete Datei angibt.  Andernfalls verwenden Sie eine andere Anweisung, um die Daten in die Datei einzufügen oder um die Datei im geeigneten Modus erneut zu öffnen.  
  
-   Wenn Sie Daten in eine schreibgeschützte Datei schreiben, ändern Sie den Lese\-\/Schreibstatus der Datei, oder versuchen Sie, keine Daten in die Datei zu schreiben.  
  
-   Verwenden Sie die Funktionen, die im `My.Computer.FileSystem`\-Objekt verfügbar sind.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.FileSystem>   
 [Troubleshooting: Reading from and Writing to Text Files](../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)