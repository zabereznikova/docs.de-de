---
title: "Array declared as for loop control variable cannot be declared with an initial size | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc32039"
  - "bc32039"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32039"
ms.assetid: 1d8b6560-c9eb-4b71-a038-24c6f5a5ce46
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Array declared as for loop control variable cannot be declared with an initial size
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Eine `For Each`\-Schleife verwendet ein Array als *Element*\-Iterationsvariable, initialisiert jedoch dieses Array.  
  
 Mit den folgenden Anweisungen wird veranschaulicht, wie dieser Fehler generiert werden kann.  
  
```  
Dim arrayList As New List(Of Integer())  
For Each listElement() As Integer In arrayList  
For Each listElement(1) As Integer In arrayList  
```  
  
 Die erste `For Each`\-Anweisung ist das ordnungsgemäße Verfahren für den Zugriff auf Elemente von `arrayList`.  Die zweite `For Each`\-Anweisung generiert diesen Fehler.  
  
 **Fehler\-ID:** BC32039  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie die Initialisierung aus der Deklaration der *Element*\-Iterationsvariablen.  
  
## Siehe auch  
 [For...Next\-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Auflistungen](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md)