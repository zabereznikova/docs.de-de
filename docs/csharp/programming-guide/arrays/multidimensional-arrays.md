---
title: "Mehrdimensionale Arrays (C#-Programmierhandbuch) | Microsoft Docs"
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
  - "Arrays [C#], Mehrdimensional"
  - "Mehrdimensionale Arrays [C#]"
ms.assetid: 020ce02e-7dff-4273-8e53-bf0b33747232
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Mehrdimensionale Arrays (C#-Programmierhandbuch)
Arrays können über mehr als eine Dimension verfügen.  Durch die folgende Deklaration wird z. B. ein zweidimensionales Array mit vier Zeilen und zwei Spalten erstellt.  
  
 [!code-cs[csProgGuideArrays#11](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_1.cs)]  
  
 Durch die nachstehende Deklaration wird ein Array mit den drei Dimensionen 4, 2 und 3 erstellt.  
  
 [!code-cs[csProgGuideArrays#12](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_2.cs)]  
  
## Arrayinitialisierung  
 Sie können das Array, wie im folgenden Beispiel dargestellt, während der Deklaration initialisieren.  
  
 [!code-cs[csProgGuideArrays#13](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_3.cs)]  
  
 Das Array kann auch ohne Angabe des Rangs initialisiert werden.  
  
 [!code-cs[csProgGuideArrays#14](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_4.cs)]  
  
 Falls Sie eine Arrayvariable ohne Initialisierung deklarieren möchten, müssen Sie der Variablen mit dem Operator `new` ein Array zuweisen.  Im folgenden Beispiel ist die Verwendung von `new` dargestellt:  
  
 [!code-cs[csProgGuideArrays#15](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_5.cs)]  
  
 Im folgenden Beispiel wird ein Wert einem bestimmten Arrayelement zugeordnet.  
  
 [!code-cs[csProgGuideArrays#16](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_6.cs)]  
  
 Entsprechend ruft das folgende Beispiel den Wert eines bestimmten Arrayelements ab und weist es variablem `elementValue` zu.  
  
 [!code-cs[csProgGuideArrays#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_7.cs)]  
  
 Das folgende Codebeispiel initialisiert die Arrayelemente auf die Standardwerte \(gilt nicht für verzweigte Arrays\).  
  
 [!code-cs[csProgGuideArrays#17](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_8.cs)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Arrays](../../../csharp/programming-guide/arrays/index.md)   
 [Eindimensionale Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [Verzweigte Arrays](../../../csharp/programming-guide/arrays/jagged-arrays.md)