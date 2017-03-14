---
title: "How to: Sort An Array in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "Array.Sort"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "arrays [Visual Basic], sorting"
  - "examples [Visual Basic], arrays"
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# How to: Sort An Array in Visual Basic
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Dieses Beispiel deklariert ein Array von `String`\-Objekten mit der Bezeichnung `zooAnimals`, füllt es mit Daten und sortiert es anschließend alphabetisch.  
  
## Beispiel  
  
```  
Private Sub sortAnimals()  
    Dim zooAnimals(2) As String  
    zooAnimals(0) = "lion"  
    zooAnimals(1) = "turtle"  
    zooAnimals(2) = "ostrich"  
    Array.Sort(zooAnimals)  
End Sub  
```  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Zugriff auf Mscorlib.dll und den <xref:System>\-Namespace.  
  
## Robuste Programmierung  
 Unter den folgenden Bedingungen kann eine Ausnahme ausgelöst werden:  
  
-   Das Array ist leer \(<xref:System.ArgumentNullException>\-Klasse\).  
  
-   Das Array ist mehrdimensional \(<xref:System.RankException>\-Klasse\).  
  
-   Die <xref:System.IComparable>\-Schnittstelle wird von mindestens einem Element des Arrays nicht implementiert \(<xref:System.InvalidOperationException>\-Klasse\).  
  
## Siehe auch  
 <xref:System.Array.Sort%2A?displayProperty=fullName>   
 [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Troubleshooting Arrays](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)   
 [Auflistungen](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md)   
 [For Each...Next\-Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)