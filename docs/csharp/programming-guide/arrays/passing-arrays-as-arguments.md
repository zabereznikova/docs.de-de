---
title: "&#220;bergeben von Arrays als Argumente (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Arrays [C#], Übergeben als Argumente"
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# &#220;bergeben von Arrays als Argumente (C#-Programmierhandbuch)
Arrays können als Argumente an Methodenparameter übergeben werden.  Da Arrays Verweistypen sind, kann die Methode den Wert der Elemente ändern.  
  
## Übergeben von eindimensionalen Arrays als Argumente  
 Sie können ein initialisiertes eindimensionales Array an eine Methode übergeben.  Die folgende Anweisung sendet z. B. ein Array an eine print\-Methode.  
  
 [!code-cs[csProgGuideArrays#34](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_1.cs)]  
  
 Der folgende Code zeigt eine Teilimplementierung der print\-Methode.  
  
 [!code-cs[csProgGuideArrays#33](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_2.cs)]  
  
 Sie können ein neues Array in einem Schritt initialisieren und übergeben, wie im folgenden Beispiel gezeigt.  
  
 [!code-cs[CsProgGuideArrays#35](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_3.cs)]  
  
## Beispiel  
  
### Beschreibung  
 Im folgenden Beispiel wird ein Zeichenfolgenarray initialisiert und als Argument an eine `PrintArray`\-Methode für Zeichenfolgen übergeben.  Die Methode zeigt die Elemente des Arrays an.  Anschließend werden die Methoden `ChangeArray` und `ChangeArrayElement` aufgerufen, um zu veranschaulichen, dass das Senden eines Arrayarguments nach Wert Änderungen an den Arrayelementen nicht verhindert.  
  
### Code  
 [!code-cs[csProgGuideArrays#30](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_4.cs)]  
  
## Übergeben von mehrdimensionalen Arrays als Argumente  
 Die Übergabe eines initialisierten mehrdimensionalen Arrays an eine Methode erfolgt wie bei einem eindimensionalen Array.  
  
 [!code-cs[csProgGuideArrays#41](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_5.cs)]  
  
 Der folgende Code zeigt die Teildeklaration einer print\-Methode, die ein zweidimensionales Array als Argument erfordert.  
  
 [!code-cs[csProgGuideArrays#36](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_6.cs)]  
  
 Sie können ein neues Array in einem Schritt initialisieren und übergeben, wie im folgenden Beispiel gezeigt.  
  
 [!code-cs[csProgGuideArrays#32](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_7.cs)]  
  
## Beispiel  
  
### Beschreibung  
 Im folgenden Beispiel wird ein zweidimensionales Array mit ganzen Zahlen initialisiert und an die `Print2DArray`\-Methode übergeben.  Die Methode zeigt die Elemente des Arrays an.  
  
### Code  
 [!code-cs[csProgGuideArrays#31](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_8.cs)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Arrays](../../../csharp/programming-guide/arrays/index.md)   
 [Eindimensionale Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [Mehrdimensionale Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)   
 [Verzweigte Arrays](../../../csharp/programming-guide/arrays/jagged-arrays.md)