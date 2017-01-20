---
title: "Gewusst wie: Erstellen einer geschachtelten Gruppe (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Gruppieren von Gruppen in LINQ-Abfragen"
  - "Gruppieren von LINQ-Abfragen"
  - "Gruppen [LINQ in C#], Geschachtelt"
  - "Geschachtelte Abfragen [C#]"
  - "Abfragen [LINQ in C#], Geschachtelte Gruppen"
  - "Abfrageausdrücke [LINQ in C#], Geschachtelte Gruppen"
ms.assetid: f48c64af-6d4e-473c-ab27-02f78b5ec2b9
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Erstellen einer geschachtelten Gruppe (C#-Programmierhandbuch)
Im folgenden Beispiel wird gezeigt, wie geschachtelte Gruppen in einem [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)]\-Abfrageausdruck erstellt werden.  Jede Gruppe, die in Abhängigkeit vom Studienjahr oder Notenniveau erstellt wird, wird anschließend anhand der Namen der einzelnen Personen weiter in Gruppen unterteilt.  
  
## Beispiel  
 [!code-cs[csProgGuideLINQ#24](../../../csharp/programming-guide/arrays/codesnippet/CSharp/csLINQProgRef/csrefLINQHowTos.cs#24)]  
  
 Beachten Sie, dass zum Durchlaufen der inneren Elemente einer geschachtelten Gruppe drei geschachtelte `foreach`\-Schleifen erforderlich sind.  
  
## Kompilieren des Codes  
 Dieses Beispiel enthält Verweise auf Objekte, die in der Beispielanwendung in [Gewusst wie: Abfragen einer Auflistung von Objekten](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md) definiert werden.  Um diese Methode zu kompilieren und auszuführen, fügen Sie sie in die `StudentClass`\-Klasse dieser Anwendung ein, und fügen Sie ihr von der `Main`\-Methode einen Aufruf hinzu.  
  
 Wenn Sie diese Methode an Ihre eigene Anwendung anpassen, beachten Sie, dass LINQ [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] Version 3.5 benötigt und dass das Projekt einen Verweis auf System.Core.dll enthalten und eine Direktive für System.Linq verwenden muss.  LINQ\-to\-SQL\-, LINQ\-to\-XML\- und LINQ\-to\-DataSet\-Typen erfordern zusätzliche Usings und Verweise.  Weitere Informationen hierzu finden Sie unter [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  
  
## Siehe auch  
 [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)