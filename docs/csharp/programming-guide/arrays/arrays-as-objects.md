---
title: Arrays als Objekte – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
ms.openlocfilehash: 0c4b5dcbd9e227e4edd5f549b687e3ded90ee9bc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54740488"
---
# <a name="arrays-as-objects-c-programming-guide"></a>Arrays als Objekte (C#-Programmierhandbuch)

In C# sind Arrays tatsächlich Objekte und nicht nur adressierbare Regionen zusammenhängender Speicher wie in C und C++. <xref:System.Array> ist der abstrakte Basistyp aller Typen von Arrays. Sie können die Eigenschaften und die anderen Klassenmember verwenden, über die <xref:System.Array> verfügt. Ein Beispiel dafür wäre die Verwendung der <xref:System.Array.Length%2A>-Eigenschaft, um die Länge eines Arrays zu erhalten. Der folgende Code weist die Länge des `numbers`-Arrays, die `5` beträgt, einer Variablen mit dem Namen `lengthOfNumbers` zu:  
  
 [!code-csharp[csProgGuideArrays#3](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_1.cs)]  
  
 Die <xref:System.Array>-Klasse bietet viele weitere nützliche Methoden und Eigenschaften zum Sortieren, Durchsuchen und Kopieren von Arrays.  
  
## <a name="example"></a>Beispiel

 In diesem Beispiel wird die <xref:System.Array.Rank%2A>-Eigenschaft verwendet, um die Anzahl der Dimensionen eines Arrays anzuzeigen.  
  
 [!code-csharp[csProgGuideArrays#2](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_2.cs)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [Arrays](../../../csharp/programming-guide/arrays/index.md)
- [Eindimensionale Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)
- [Mehrdimensionale Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)
- [Verzweigte Arrays](../../../csharp/programming-guide/arrays/jagged-arrays.md)
