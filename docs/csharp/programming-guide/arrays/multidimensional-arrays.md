---
title: Mehrdimensionale Arrays – C#-Programmierhandbuch
description: Arrays in C# können mehr als eine Dimension aufweisen. Bei dieser Beispieldeklaration wird ein zweidimensionales Array mit vier Zeilen und zwei Spalten erstellt.
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], multidimensional
- multidimensional arrays [C#]
ms.assetid: 020ce02e-7dff-4273-8e53-bf0b33747232
ms.openlocfilehash: a2f204c0866672b317569fbc620aa8af60829ffd
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475007"
---
# <a name="multidimensional-arrays-c-programming-guide"></a>Mehrdimensionale Arrays (C#-Programmierhandbuch)

Arrays können mehr als eine Dimension aufweisen. Die folgende Deklaration erstellt z.B. ein zweidimensionales Array mit vier Zeilen und zwei Spalten.  
  
 [!code-csharp[csProgGuideArrays#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#11)]  
  
 Die folgende Deklaration erstellt ein Array mit drei Dimensionen 4, 2 und 3.  
  
 [!code-csharp[csProgGuideArrays#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#12)]  
  
## <a name="array-initialization"></a>Arrayinitialisierung

 Sie können das Array wie im folgenden Beispiel gezeigt nach der Deklaration initialisieren.  
  
 [!code-csharp[csProgGuideArrays#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#13)]  
  
 Sie können das Array auch ohne Angabe des Rangs initialisieren.  
  
 [!code-csharp[csProgGuideArrays#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#14)]  
  
 Wenn Sie eine Arrayvariable ohne Initialisierung deklarieren möchten, müssen Sie der Variable mit dem Operator `new` ein Array zuweisen. Die Verwendung von `new` wird im folgenden Beispiel gezeigt.  
  
 [!code-csharp[csProgGuideArrays#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#15)]  
  
 Im folgende Beispiel wird einem bestimmten Arrayelement ein Wert zugewiesen.  
  
 [!code-csharp[csProgGuideArrays#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#16)]  
  
 Auf ähnliche Weise wird im folgenden Beispiel der Wert eines bestimmten Arrayelements abgerufen und der Variablen `elementValue` zugewiesen.  
  
 [!code-csharp[csProgGuideArrays#42](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#42)]  
  
 Im folgenden Codebeispiel werden die Arrayelemente auf Standardwerte initialisiert (mit Ausnahme von verzweigten Arrays).  
  
 [!code-csharp[csProgGuideArrays#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#17)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Arrays](./index.md)
- [Eindimensionale Arrays](./single-dimensional-arrays.md)
- [Verzweigte Arrays](./jagged-arrays.md)
