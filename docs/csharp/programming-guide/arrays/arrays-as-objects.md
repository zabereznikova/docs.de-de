---
title: Arrays als Objekte (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
ms.openlocfilehash: f1abe10839c30d48f56ac6044d75d290a59b4cce
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43505558"
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
