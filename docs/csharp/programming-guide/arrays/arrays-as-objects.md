---
title: "Arrays als Objekte (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Arrays [C#], Als Objekte"
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# Arrays als Objekte (C#-Programmierhandbuch)
In C\# sind Arrays tatsächlich Objekte und nicht nur adressierbare, zusammenhängende Speicherbereiche wie in C und C\+\+.  <xref:System.Array> ist der abstrakte Basistyp aller Bereichstypen.  Sie können die Eigenschaften sowie andere Klassenmember von <xref:System.Array> verwenden.  Ein Beispiel dafür wäre die Verwendung der <xref:System.Array.Length%2A>\-Eigenschaft, um die Länge eines Arrays abzurufen.  Mit folgendem Code wird die Länge des `numbers`\-Arrays, die `5` beträgt, einer Variablen mit dem Namen `lengthOfNumbers` zugewiesen:  
  
 [!code-cs[csProgGuideArrays#3](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_1.cs)]  
  
 Die <xref:System.Array>\-Klasse stellt viele andere nützliche Methoden und Eigenschaften bereit, z. B. zum Sortieren, Suchen und Kopieren von Arrays.  
  
## Beispiel  
 In diesem Beispiel wird mithilfe der <xref:System.Array.Rank%2A>\-Eigenschaft die Anzahl von Dimensionen eines Arrays angezeigt.  
  
 [!code-cs[csProgGuideArrays#2](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_2.cs)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Arrays](../../../csharp/programming-guide/arrays/index.md)   
 [Eindimensionale Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [Mehrdimensionale Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)   
 [Verzweigte Arrays](../../../csharp/programming-guide/arrays/jagged-arrays.md)