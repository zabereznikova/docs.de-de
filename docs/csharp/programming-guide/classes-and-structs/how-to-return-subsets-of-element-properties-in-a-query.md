---
title: "Gewusst wie: Zur&#252;ckgeben von Teilmengen von Elementeigenschaften in einer Abfrage (C#-Programmierhandbuch) | Microsoft Docs"
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
  - "Anonyme Typen [C#], Für Teilmengen von Elementeigenschaften"
ms.assetid: fabdf349-f443-4e3f-8368-6c471be1dd7b
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Zur&#252;ckgeben von Teilmengen von Elementeigenschaften in einer Abfrage (C#-Programmierhandbuch)
Verwenden Sie in einem Abfrageausdruck einen anonymen Typ, wenn die beiden folgenden Bedingungen gelten:  
  
-   Sie möchten nur einige der Eigenschaften jedes Quellelements zurückgeben.  
  
-   Sie müssen die Abfrageergebnisse nicht außerhalb des Methodengültigkeitsbereichs speichern, in dem die Abfrage ausgeführt wurde.  
  
 Wenn Sie von jedem Quellelement nur eine Eigenschaft oder ein Feld zurückgeben möchten, können Sie dazu den Punktoperator in der `select`\-Klausel verwenden.  Um beispielsweise nur die `ID` von jedem `student` zurückzugeben, schreiben Sie die `select`\-Klausel wie folgt:  
  
```  
select student.ID;  
```  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie Sie einen anonymen Typ verwenden können, um nur eine Teilmenge der Eigenschaften jedes Quellelements zurückzugeben, das der angegebenen Bedingung entspricht.  
  
 [!code-cs[csProgGuideLINQ#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/csLINQProgRef/csRef30LangFeatures_2.cs#31)]  
  
 Beachten Sie, dass der anonyme Typ den Namen des Quellelements für seine Eigenschaften verwendet, wenn keine Namen angegeben werden.  Um den Eigenschaften im anonymen Typ neue Namen zu geben, schreiben Sie die `select`\-Anweisung wie folgt:  
  
```  
select new { First = student.FirstName, Last = student.LastName };  
```  
  
 Wenn Sie dies im vorherigen Beispiel versuchen, dann muss auch die `Console.WriteLine`\-Anweisung geändert werden:  
  
```  
Console.WriteLine(student.First + " " + student.Last);  
```  
  
## Kompilieren des Codes  
  
-   Um diesen Code auszuführen, kopieren Sie die Klasse, und fügen Sie sie in ein Visual C\#\-Konsolenanwendungsprojekt ein, das in [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)] erstellt wurde.  Dieses Projekt gilt standardmäßig für Version 3.5 von [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] und hat einen Verweis auf System.Core.dll sowie eine `using`\-Direktive für System.Linq.  Wenn eine oder mehrere dieser Anforderungen im Projekt fehlen, können Sie sie manuell hinzufügen.  Weitere Informationen hierzu finden Sie unter [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Anonyme Typen](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)