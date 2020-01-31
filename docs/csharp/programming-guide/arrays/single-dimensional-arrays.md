---
title: Eindimensionale Arrays – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
ms.openlocfilehash: 8f093d22da789c6df750475e47a3b4e4685c5651
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744213"
---
# <a name="single-dimensional-arrays-c-programming-guide"></a>Eindimensionale Arrays (C#-Programmierhandbuch)

Sie können ein eindimensionales Array aus fünf ganzen Zahlen deklarieren, wie im folgenden Beispiel gezeigt:  
  
 [!code-csharp[csProgGuideArrays#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#4)]  
  
 Dieses Array enthält die Elemente `array[0]` bis `array[4]`. Der [neue](../../language-reference/operators/new-operator.md) Operator wird verwendet, um das Array zu erstellen und die Arrayelemente mit ihren Standardwerten zu initialisieren. In diesem Beispiel werden alle Arrayelemente mit null initialisiert.  
  
 Ein Array, das Zeichenfolgenelemente speichert, kann auf die gleiche Weise deklariert werden. Zum Beispiel:  
  
 [!code-csharp[csProgGuideArrays#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#5)]  
  
## <a name="array-initialization"></a>Arrayinitialisierung

 Arrays können nach der Deklaration initialisiert werden. In diesem Fall ist kein Längenspezifizierer erforderlich, da er bereits durch die Anzahl der Elemente in der Initialisierungsliste bereitgestellt wird. Zum Beispiel:  
  
 [!code-csharp[csProgGuideArrays#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#6)]  
  
 Ein Zeichenfolgenarray kann auf die gleiche Weise initialisiert werden. Die nachfolgende Deklaration zeigt ein Zeichenfolgenarray, in dem jedes Arrayelement durch den Namen eines Wochentags initialisiert wird:  
 
 ```csharp
 string[] weekDays = new string[] { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" };
 ```
  
 Beim Initialisieren eines Arrays nach der Deklaration können Sie die folgenden Kurzbefehle verwenden:  
  
 [!code-csharp[csProgGuideArrays#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#8)]  
  
 Eine Arrayvariable kann auch ohne Initialisierung deklariert werden. Verwenden Sie hierzu jedoch den Operator `new`, um dieser Variable ein Array zuzuweisen. Zum Beispiel:  
  
 [!code-csharp[csProgGuideArrays#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#9)]  
  
 In C# 3.0 werden implizit typisierte Arrays eingeführt. Weitere Informationen finden Sie unter [Implizit typisierte Arrays](./implicitly-typed-arrays.md).  
  
## <a name="value-type-and-reference-type-arrays"></a>Werttyp- und Verweistyparrays

 Betrachten Sie die folgende Arraydeklaration:  
  
 [!code-csharp[csProgGuideArrays#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#10)]  
  
 Das Ergebnis dieser Anweisung hängt davon ab, ob `SomeType` ein Werttyp oder ein Verweistyp ist. Bei einem Werttyp wird durch die Anweisung ein Array aus 10 Elementen erstellt, von denen jedes den Typ `SomeType` besitzt. Stellt `SomeType` einen Verweistyp dar, wird durch die Anweisung ein Array aus 10 Elementen erstellt, von denen jedes mit einem NULL-Verweis initialisiert wird.  
  
Weitere Informationen zu Werttypen und Verweistypen finden Sie unter [Werttypen](../../language-reference/builtin-types/value-types.md) und [Verweistypen](../../language-reference/keywords/reference-types.md).
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Array>
- [C#-Programmierhandbuch](../index.md)
- [Arrays](./index.md)
- [Mehrdimensionale Arrays](./multidimensional-arrays.md)
- [Verzweigte Arrays](./jagged-arrays.md)
