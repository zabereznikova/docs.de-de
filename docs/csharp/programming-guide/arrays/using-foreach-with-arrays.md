---
title: Verwenden von foreach mit Arrays (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
ms.openlocfilehash: 8511d9dd3b7155d2f6bca229f264071b54ed173b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a>Verwenden von foreach mit Arrays (C#-Programmierhandbuch)
C# enthält außerdem die [foreach](../../../csharp/language-reference/keywords/foreach-in.md)-Anweisung. Diese Anweisung stellt eine einfache, klare Methode bereit, um die Elemente eines Arrays oder einer aufzählbaren Auflistung zu durchlaufen. Die `foreach`-Anweisung verarbeitet Elemente in der Reihenfolge, die vom Array oder Enumerator des Auflistungstyps zurückgegeben wird, also normalerweise vom nullten bis zum letzten Element. Durch folgenden Code wird beispielsweise ein Array mit dem Namen `numbers` erstellt, das mithilfe der `foreach`-Anweisung durchlaufen wird:  
  
 [!code-csharp[csProgGuideArrays#28](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_1.cs)]  
  
 Bei mehrdimensionalen Arrays können Sie dieselbe Methode zum Durchlaufen der Elemente verwenden. Beispiel:  
  
 [!code-csharp[csProgGuideArrays#29](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_2.cs)]  
  
 Bei mehrdimensionalen Arrays haben Sie jedoch eine größere Kontrolle über die Arrayelemente, indem Sie eine geschachtelte [for](../../../csharp/language-reference/keywords/for.md)-Schleife verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Array>  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Arrays](../../../csharp/programming-guide/arrays/index.md)  
 [Eindimensionale Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [Mehrdimensionale Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [Verzweigte Arrays](../../../csharp/programming-guide/arrays/jagged-arrays.md)
