---
title: Arrays – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: 258ade63ab7c9008f6c892ed109bf5ea5ab974f3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64584606"
---
# <a name="arrays-c-programming-guide"></a>Arrays (C#-Programmierhandbuch)

Sie können mehrere Variablen des gleichen Typs in einer Arraydatenstruktur speichern. Ein Array wird deklariert, indem der Typ seiner Elemente angegeben wird.  
  
 `type[] arrayName;`  
  
 In den folgenden Beispiel wird ein eindimensionales, ein mehrdimensionales und ein verzweigtes Array erstellt:  
  
 [!code-csharp[csProgGuideArrays#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#1)]  
  
## <a name="array-overview"></a>Übersicht über Arrays

 Ein Array verfügt über die folgenden Eigenschaften:  
  
- Ein Array kann [eindimensional](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md), [mehrdimensional](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) oder [verzweigt](../../../csharp/programming-guide/arrays/jagged-arrays.md) sein.  
  
- Die Anzahl der Dimensionen und die Länge der einzelnen Dimensionen werden festgelegt, wenn die Arrayinstanz erstellt wird. Diese Werte können während der Lebensdauer der Instanz nicht geändert werden.  
  
- Numerische Arrayelemente sind standardmäßig auf 0 (null) festgelegt, Verweiselemente auf NULL.  
  
- Ein verzweigtes Array ist ein Array von Arrays, und deshalb sind seine Elemente Referenztypen und werden mit `null` initialisiert.  
  
- Arrays sind nullbasiert: Der Index eines Arrays mit `n` Elementen beginnt bei `0` und endet bei `n-1`.  
  
- Arrayelemente können einen beliebigen Typ aufweisen, z. B. auch einen Arraytyp.  
  
- Arraytypen sind [Referenztypen](../../../csharp/language-reference/keywords/reference-types.md), die vom abstrakten Basistyp <xref:System.Array> abgeleitet werden. Da dieser Typ <xref:System.Collections.IEnumerable> und <xref:System.Collections.Generic.IEnumerable%601> implementiert, können Sie die [foreach](../../../csharp/language-reference/keywords/foreach-in.md)-Iteration für alle Arrays in C# verwenden.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
  
- [Arrays als Objekte](../../../csharp/programming-guide/arrays/arrays-as-objects.md)  
  
- [Verwenden von foreach mit Arrays](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
- [Übergeben von Arrays als Argumente](../../../csharp/programming-guide/arrays/passing-arrays-as-arguments.md)  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [Sammlungen](../../../csharp/programming-guide/concepts/collections.md)
