---
title: Eindimensionale Arrays (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: cc42640715274b89c4c4a12ced8c0ae6af603318
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="single-dimensional-arrays-c-programming-guide"></a>Eindimensionale Arrays (C#-Programmierhandbuch)
Sie können ein eindimensionales Array aus fünf ganzen Zahlen deklarieren, wie im folgenden Beispiel gezeigt:  
  
 [!code-cs[csProgGuideArrays#4](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_1.cs)]  
  
 Dieses Array enthält die Elemente `array[0]` bis `array[4]`. Der [neue](../../../csharp/language-reference/keywords/new.md) Operator wird verwendet, um das Array zu erstellen und die Arrayelemente mit ihren Standardwerten zu initialisieren. In diesem Beispiel werden alle Arrayelemente mit null initialisiert.  
  
 Ein Array, das Zeichenfolgenelemente speichert, kann auf die gleiche Weise deklariert werden. Zum Beispiel:  
  
 [!code-cs[csProgGuideArrays#5](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_2.cs)]  
  
## <a name="array-initialization"></a>Arrayinitialisierung  
 Arrays können nach der Deklaration initialisiert werden. In diesem Fall ist kein Rangbezeichner erforderlich, da er bereits durch die Anzahl der Elemente in der Initialisierungsliste bereitgestellt wird. Zum Beispiel:  
  
 [!code-cs[csProgGuideArrays#6](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_3.cs)]  
  
 Ein Zeichenfolgenarray kann auf die gleiche Weise initialisiert werden. Die nachfolgende Deklaration zeigt ein Zeichenfolgenarray, in dem jedes Arrayelement durch den Namen eines Wochentags initialisiert wird:  
  
 [!code-cs[csProgGuideArrays#7](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_4.cs)]  
  
 Beim Initialisieren eines Arrays nach der Deklaration können Sie die folgenden Kurzbefehle verwenden:  
  
 [!code-cs[csProgGuideArrays#8](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_5.cs)]  
  
 Eine Arrayvariable kann auch ohne Initialisierung deklariert werden. Verwenden Sie hierzu jedoch den Operator `new`, um dieser Variable ein Array zuzuweisen. Zum Beispiel:  
  
 [!code-cs[csProgGuideArrays#9](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_6.cs)]  
  
 In C# 3.0 werden implizit typisierte Arrays eingeführt. Weitere Informationen finden Sie unter [Implizit typisierte Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).  
  
## <a name="value-type-and-reference-type-arrays"></a>Werttyp- und Verweistyparrays  
 Betrachten Sie die folgende Arraydeklaration:  
  
 [!code-cs[csProgGuideArrays#10](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_7.cs)]  
  
 Das Ergebnis dieser Anweisung hängt davon ab, ob `SomeType` ein Werttyp oder ein Verweistyp ist. Bei einem Werttyp wird durch die Anweisung ein Array aus 10 Elementen erstellt, von denen jedes den Typ `SomeType` besitzt. Stellt `SomeType` einen Verweistyp dar, wird durch die Anweisung ein Array aus 10 Elementen erstellt, von denen jedes mit einem NULL-Verweis initialisiert wird.  
  
 Weitere Informationen zu Werttypen und Verweistypen finden Sie unter [Typen](../../../csharp/language-reference/keywords/types.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Array>   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Arrays](../../../csharp/programming-guide/arrays/index.md)   
 [Mehrdimensionale Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)   
 [Verzweigte Arrays](../../../csharp/programming-guide/arrays/jagged-arrays.md)

