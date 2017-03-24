---
title: "Verzweigte Arrays (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Arrays [C#], Verzweigt"
  - "Verzweigte Arrays [C#]"
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# Verzweigte Arrays (C#-Programmierhandbuch)
Ein verzweigtes Array ist ein Array, dessen Elemente wiederum Arrays sind.  Die Elemente eines verzweigten Arrays können über unterschiedliche Dimensionen und Größen verfügen.  Ein verzweigtes Array wird manchmal auch als "Array von Arrays" bezeichnet. Die folgenden Beispiele zeigen, wie verzweigte Arrays deklariert und initialisiert werden und wie auf sie zugegriffen wird.  
  
 Im Folgenden sehen Sie die Deklaration eines eindimensionalen Arrays mit drei Elementen, von denen jedes ein eindimensionales Array von ganzen Zahlen darstellt:  
  
 [!code-cs[csProgGuideArrays#19](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_1.cs)]  
  
 Bevor Sie `jaggedArray` verwenden können, müssen die Elemente des Arrays initialisiert werden.  Sie können die Elemente wie folgt initialisieren:  
  
 [!code-cs[csProgGuideArrays#20](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_2.cs)]  
  
 Jedes Element ist ein eindimensionales Array von ganzen Zahlen.  Alle Elemente sind Arrays. Das erste verfügt über 5, das zweite über 4 und das dritte über 2 ganze Zahlen.  
  
 Es besteht auch die Möglichkeit, Initialisierungen zu verwenden, um die Arrayelemente mit Werten aufzufüllen. In diesem Fall ist die Arraygröße nicht erforderlich.  Beispiele:  
  
 [!code-cs[csProgGuideArrays#21](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_3.cs)]  
  
 Das Array kann auch, wie im Folgenden dargestellt, während der Deklaration initialisiert werden:  
  
 [!code-cs[csProgGuideArrays#22](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_4.cs)]  
  
 Sie können die folgende Kurzform verwenden.  Beachten Sie, dass Sie den Operator `new` bei der Initialisierung der Elemente nicht weglassen können, weil es für die Elemente keine Standardinitialisierung gibt:  
  
 [!code-cs[csProgGuideArrays#23](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_5.cs)]  
  
 Ein verzweigtes Array ist ein Array von Arrays, und deshalb sind seine Elemente Verweistypen und werden mit `null` initialisiert.  
  
 In den folgenden Beispielen wird veranschaulicht, wie der Zugriff auf einzelne Arrayelemente erfolgt:  
  
 [!code-cs[csProgGuideArrays#24](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_6.cs)]  
  
 Verzweigte und mehrdimensionale Arrays können auch kombiniert werden.  Im Folgenden sehen Sie die Beschreibung und Initialisierung eines eindimensionalen verzweigten Arrays, das drei zweidimensionale Arrayelemente unterschiedlicher Größe enthält.  Weitere Informationen zu zweidimensionalen Arrays finden Sie unter [Mehrdimensionale Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md).  
  
 [!code-cs[csProgGuideArrays#25](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_7.cs)]  
  
 Im folgenden Beispiel wird dargestellt, wie Sie auf einzelne Elemente zugreifen können. Der Wert von Element `[1,0]` des ersten Arrays wird angezeigt \(Wert `5`\):  
  
 [!code-cs[csProgGuideArrays#26](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_8.cs)]  
  
 Die Methode `Length` gibt die Anzahl der Arrays zurück, die im verzweigten Array enthalten sind.  Angenommen, Sie hätten das vorherige Array deklariert, dann gibt die Zeile:  
  
 [!code-cs[csProgGuideArrays#27](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_9.cs)]  
  
 Gibt einen Wert von 3 zurück.  
  
## Beispiel  
 In diesem Beispiel wird ein Array erstellt, dessen Elemente selbst Arrays sind.  Jedes Arrayelement hat eine andere Größe.  
  
 [!code-cs[csProgGuideArrays#18](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_10.cs)]  
  
## Siehe auch  
 <xref:System.Array>   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Arrays](../../../csharp/programming-guide/arrays/index.md)   
 [Eindimensionale Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [Mehrdimensionale Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)