---
title: "Arrays (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Arrays [C#]"
  - "C#-Sprache, Arrays"
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
caps.latest.revision: 33
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 33
---
# Arrays (C#-Programmierhandbuch)
Sie können mehrere Variablen des gleichen Typs in einer Arraydatenstruktur speichern.  Ein Array wird deklariert, indem der Typ seiner Elemente angegeben wird.  
  
 `type[] arrayName;`  
  
 In den folgenden Beispielen werden ein eindimensionales, ein mehrdimensionales und ein verzweigtes Array erstellt:  
  
 [!code-cs[csProgGuideArrays#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/index_1.cs)]  
  
## Übersicht über Arrays  
 Ein Array verfügt über die folgenden Eigenschaften:  
  
-   Ein Array kann [eindimensional](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md), [mehrdimensional](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) oder [verzweigt](../../../csharp/programming-guide/arrays/jagged-arrays.md) sein.  
  
-   Die Anzahl der Dimensionen und die Länge der einzelnen Dimensionen werden festgelegt, wenn die Arrayinstanz erstellt wird.  Diese Werte können während der Lebensdauer der Instanz nicht geändert werden.  
  
-   Numerische Arrayelemente sind standardmäßig auf 0 \(null\) festgelegt, Verweiselemente auf NULL.  
  
-   Ein verzweigtes Array ist ein Array von Arrays, und deshalb sind seine Elemente Referenztypen und werden mit `null` initialisiert.  
  
-   Arrays sind nullbasiert: Der Index eines Arrays mit `n` Elementen beginnt bei `0` und endet bei `n-1`.  
  
-   Arrayelemente können einen beliebigen Typ aufweisen, z. B. auch einen Arraytyp.  
  
-   Arraytypen sind [Referenztypen](../../../csharp/language-reference/keywords/reference-types.md), die vom abstrakten Basistyp <xref:System.Array> abgeleitet werden.  Da dieser Typ <xref:System.Collections.IEnumerable> und <xref:System.Collections.Generic.IEnumerable%601> implementiert, können Sie die [foreach](../../../csharp/language-reference/keywords/foreach-in.md)\-Iteration für alle Arrays in C\# verwenden.  
  
## Verwandte Abschnitte  
  
-   [Arrays als Objekte](../../../csharp/programming-guide/arrays/arrays-as-objects.md)  
  
-   [Verwenden von foreach mit Arrays](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
-   [Übergeben von Arrays als Argumente](../../../csharp/programming-guide/arrays/passing-arrays-as-arguments.md)  
  
-   [Übergeben von Arrays mithilfe von "ref" und "out"](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)  
  
-   [Weitere Informationen zu Variablen](http://go.microsoft.com/fwlink/?LinkId=221230) im Buch zum [Einstieg in Visual C\# 2010](http://go.microsoft.com/fwlink/?LinkId=221214)  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Auflistungen](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md)   
 [Array Collection Type](http://msdn.microsoft.com/de-de/8a9964de-8941-47b1-a3cf-a01bc88db9e8)