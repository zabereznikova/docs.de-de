---
title: "Übergeben von Arrays mithilfe von \"ref\" und \"out\" (C#-Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#], passing using ref and out
ms.assetid: 6a2b261e-a1cc-49a6-b4f0-6cacae385a1e
caps.latest.revision: 16
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
ms.openlocfilehash: 58fc359881295a9e6627ac1269ef17aa298009c7
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="passing-arrays-using-ref-and-out-c-programming-guide"></a>Übergeben von Arrays mithilfe von "ref" und "out" (C#-Programmierhandbuch)
Wie alle [out](../../../csharp/language-reference/keywords/out.md)-Parameter muss auch ein `out`-Parameter eines Arraytyps vor der Verwendung zugewiesen werden, d.h., er muss vom Aufgerufenen zugewiesen werden. Zum Beispiel:  
  
 [!code-cs[csProgGuideArrays#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_1.cs)]  
  
 Wie alle [ref](../../../csharp/language-reference/keywords/ref.md)-Parameter muss auch ein `ref`-Parameter eines Arraytyps vom Aufrufer definitiv zugewiesen werden. Daher besteht keine Notwendigkeit, dass die definitive Zuweisung vom Aufgerufenen vorgenommen wird. Ein `ref`-Parameter eines Arraytyps kann als Ergebnis des Aufrufs geändert werden. Beispielsweise kann dem Array der Wert [NULL](../../../csharp/language-reference/keywords/null.md) zugewiesen werden, oder es kann mit einem anderen Array initialisiert werden. Zum Beispiel:  
  
 [!code-cs[csProgGuideArrays#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_2.cs)]  
  
 In den beiden folgenden Beispielen wird der Unterschied zwischen `out` und `ref` bei der Übergabe von Arrays an Methoden veranschaulicht.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird das Array `theArray` im Aufrufer (der `Main`-Methode) deklariert und in der `FillArray`-Methode initialisiert. Anschließend werden die Elemente des Arrays an den Aufrufer zurückgegeben und angezeigt.  
  
 [!code-cs[csProgGuideArrays#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_3.cs)]  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird das Array `theArray` im Aufrufer (der `Main`-Methode) initialisiert und mithilfe des `FillArray`-Parameters an die `ref`-Methode übergeben. Einige Arrayelemente werden in der `FillArray`-Methode aktualisiert. Anschließend werden die Elemente des Arrays an den Aufrufer zurückgegeben und angezeigt.  
  
 [!code-cs[csProgGuideArrays#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_4.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [ref](../../../csharp/language-reference/keywords/ref.md)   
 [Modifizierer für out-Parameter](../../../csharp/language-reference/keywords/out-parameter-modifier.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Arrays](../../../csharp/programming-guide/arrays/index.md)   
 [Eindimensionale Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [Mehrdimensionale Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)   
 [Verzweigte Arrays](../../../csharp/programming-guide/arrays/jagged-arrays.md)

