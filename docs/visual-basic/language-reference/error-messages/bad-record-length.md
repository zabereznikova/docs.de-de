---
title: "Bad record length | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID59"
dev_langs: 
  - "VB"
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Bad record length
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Dieser Fehler kann folgende Ursachen haben:  
  
-   Die Länge einer Datensatzvariable, die in einer der Anweisungen `FileGet`, `FileGetObject`, `FilePut` oder `FilePutObject` angegeben ist, unterscheidet sich von der Länge, die in der entsprechenden `FileOpen`\-Anweisung angegeben ist.  
  
-   Die Variable in einer `FilePut`\- oder `FilePutObject`\-Anweisung ist oder enthält eine Zeichenfolge variabler Länge.  
  
-   Die Variable in einer `FilePut`\-Anweisung oder `FilePutObject`\-Anweisung gehört zum `Variant`\-Typ oder enthält einen solchen.  
  
### So beheben Sie diesen Fehler  
  
1.  Vergewissern Sie sich, dass die Summe der Größen von Variablen fester Länge im benutzerdefinierten Typ, der den Variablentyp des Datensatzes angibt, den gleichen Wert wie in der `Len`\-Klausel der `FileOpen`\-Anweisung aufweist.  
  
2.  Wenn die Variable in einer `FilePut`\-Anweisung oder `FilePutObject`\-Anweisung eine Zeichenfolge variabler Länge ist oder enthält, vergewissern Sie sich, dass die Zeichenfolge variabler Länge mindestens zwei Zeichen kürzer ist als die Datensatzlänge, die in der `Len`\-Klausel der `FileOpen`\-Anweisung angegeben ist.  
  
3.  Wenn die Variable in einer `FilePut`\-Anweisung oder `FilePutObject`\-Anweisung zum `Variant`\-Typ gehört oder einen solchen enthält, vergewissern Sie sich, dass die Zeichenfolge variabler Länge mindestens 4 Bytes kürzer ist als die Datensatzlänge, die in der `Len`\-Klausel der `FileOpen`\-Anweisung angegeben ist.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>   
 <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>   
 <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>   
 <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>