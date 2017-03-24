---
title: "Too many files | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID67"
dev_langs: 
  - "VB"
ms.assetid: 2ff203e2-bba6-43ae-b72f-8e92a881c98f
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# Too many files
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Entweder wurden mehr Dateien im Stammverzeichnis erstellt als im Betriebssystem zulässig sind, oder es wurden mehr Dateien geöffnet als in der Einstellung **files\=** in der CONFIG.SYS\-Datei angegeben.  
  
### So beheben Sie diesen Fehler  
  
1.  Wenn das Programm Dateien im Stammverzeichnis öffnet, schließt oder speichert, ändern Sie das Programm, sodass es ein Unterverzeichnis verwendet.  
  
2.  Erhöhen Sie die Anzahl der angegebenen Dateien in der Einstellung **files\=** in der CONFIG.SYS\-Datei, und starten Sie den Computer neu.  
  
## Siehe auch  
 [Error Types](../../../visual-basic/programming-guide/language-features/error-types.md)