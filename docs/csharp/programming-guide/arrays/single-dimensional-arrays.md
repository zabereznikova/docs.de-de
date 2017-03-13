---
title: "Eindimensionale Arrays (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Arrays [C#], Eindimensional"
  - "Eindimensionale Arrays [C#]"
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# Eindimensionale Arrays (C#-Programmierhandbuch)
Sie können ein eindimensionales Array mit fünf ganzen Zahlen deklarieren, wie im folgenden Beispiel gezeigt:  
  
 [!code-cs[csProgGuideArrays#4](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_1.cs)]  
  
 Dieses Array umfasst Elemente von `array[0]` bis `array[4]`.  Der Operator [new](../../../csharp/language-reference/keywords/new.md) wird zum Erstellen des Arrays und zum Initialisieren der Arrayelemente mit ihren Standardwerten verwendet.  In diesem Beispiel werden alle Arrayelemente mit Null initialisiert.  
  
 Arrays, in denen Zeichenfolgenelemente gespeichert werden, können auf dieselbe Weise deklariert werden.  Beispiele:  
  
 [!code-cs[csProgGuideArrays#5](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_2.cs)]  
  
## Arrayinitialisierung  
 Ein Array kann bei der Deklaration initialisiert werden. In diesem Fall ist kein Rangspezifizierer erforderlich, da er bereits durch die Anzahl der Elemente in der Initialisierungsliste angegeben wird.  Beispiele:  
  
 [!code-cs[csProgGuideArrays#6](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_3.cs)]  
  
 Ein Zeichenfolgenarray kann auf dieselbe Weise initialisiert werden.  Im Folgenden sehen Sie die Deklaration eines Zeichenfolgenarrays, in dem jedes Arrayelement durch den Namen eines Wochentages initialisiert wird:  
  
 [!code-cs[csProgGuideArrays#7](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_4.cs)]  
  
 Bei der Initialisierung eines Arrays während der Deklaration können Sie die Eingabe folgendermaßen verkürzen:  
  
 [!code-cs[csProgGuideArrays#8](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_5.cs)]  
  
 Eine Arrayvariable kann auch ohne Initialisierung deklariert werden. Sie müssen jedoch den Operator `new` verwenden, wenn Sie dieser Variablen ein Array zuweisen.  Beispiele:  
  
 [!code-cs[csProgGuideArrays#9](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_6.cs)]  
  
 In C\# 3.0 werden implizit typisierte Arrays eingeführt.  Weitere Informationen finden Sie unter [Implizit typisierte Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).  
  
## Werttyp\- und Referenztyparrays  
 Betrachten Sie die folgende Arraydeklaration:  
  
 [!code-cs[csProgGuideArrays#10](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_7.cs)]  
  
 Das Ergebnis dieser Anweisung hängt davon ab, ob `SomeType` ein Werttyp oder ein Referenztyp ist.  Wenn dies ein Werttyp ist, wird durch die Anweisung ein Array mit 10 Elementen jeweils mit dem Typ `SomeType` erstellt.  Wenn `SomeType` ein Referenztyp ist, wird durch die Anweisung ein Array mit 10 Elementen erstellt, von denen jedes mit einem Nullverweis initialisiert wird.  
  
 Weitere Informationen zu Wert\- und Referenztypen finden Sie unter [Typen](../../../csharp/language-reference/keywords/types.md).  
  
## Siehe auch  
 <xref:System.Array>   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Arrays](../../../csharp/programming-guide/arrays/index.md)   
 [Mehrdimensionale Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)   
 [Verzweigte Arrays](../../../csharp/programming-guide/arrays/jagged-arrays.md)