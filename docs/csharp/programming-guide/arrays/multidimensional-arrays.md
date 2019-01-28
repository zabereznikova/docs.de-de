---
title: Mehrdimensionale Arrays – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], multidimensional
- multidimensional arrays [C#]
ms.assetid: 020ce02e-7dff-4273-8e53-bf0b33747232
ms.openlocfilehash: 4547bd94a0870dbb3955c4980361c8be0453616d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642411"
---
# <a name="multidimensional-arrays-c-programming-guide"></a>Mehrdimensionale Arrays (C#-Programmierhandbuch)

Arrays können mehr als eine Dimension aufweisen. Die folgende Deklaration erstellt z.B. ein zweidimensionales Array mit vier Zeilen und zwei Spalten.  
  
 [!code-csharp[csProgGuideArrays#11](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_1.cs)]  
  
 Die folgende Deklaration erstellt ein Array mit drei Dimensionen 4, 2 und 3.  
  
 [!code-csharp[csProgGuideArrays#12](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_2.cs)]  
  
## <a name="array-initialization"></a>Arrayinitialisierung

 Sie können das Array wie im folgenden Beispiel gezeigt nach der Deklaration initialisieren.  
  
 [!code-csharp[csProgGuideArrays#13](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_3.cs)]  
  
 Sie können das Array auch ohne Angabe des Rangs initialisieren.  
  
 [!code-csharp[csProgGuideArrays#14](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_4.cs)]  
  
 Wenn Sie eine Arrayvariable ohne Initialisierung deklarieren möchten, müssen Sie der Variable mit dem Operator `new` ein Array zuweisen. Die Verwendung von `new` wird im folgenden Beispiel gezeigt.  
  
 [!code-csharp[csProgGuideArrays#15](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_5.cs)]  
  
 Im folgende Beispiel wird einem bestimmten Arrayelement ein Wert zugewiesen.  
  
 [!code-csharp[csProgGuideArrays#16](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_6.cs)]  
  
 Auf ähnliche Weise wird im folgenden Beispiel der Wert eines bestimmten Arrayelements abgerufen und der Variablen `elementValue` zugewiesen.  
  
 [!code-csharp[csProgGuideArrays#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_7.cs)]  
  
 Im folgenden Codebeispiel werden die Arrayelemente auf Standardwerte initialisiert (mit Ausnahme von verzweigten Arrays).  
  
 [!code-csharp[csProgGuideArrays#17](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_8.cs)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [Arrays](../../../csharp/programming-guide/arrays/index.md)
- [Eindimensionale Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)
- [Verzweigte Arrays](../../../csharp/programming-guide/arrays/jagged-arrays.md)
