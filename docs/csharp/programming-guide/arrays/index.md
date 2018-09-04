---
title: Arrays (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: 1469336bf034fd22c9d7355b2f8dd8be32721fdf
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43510637"
---
# <a name="arrays-c-programming-guide"></a>Arrays (C#-Programmierhandbuch)

Sie können mehrere Variablen des gleichen Typs in einer Arraydatenstruktur speichern. Ein Array wird deklariert, indem der Typ seiner Elemente angegeben wird.  
  
 `type[] arrayName;`  
  
 In den folgenden Beispielen werden ein eindimensionales, ein mehrdimensionales und ein verzweigtes Array erstellt:  
  
 [!code-csharp[csProgGuideArrays#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/index_1.cs)]  
  
## <a name="array-overview"></a>Übersicht über Arrays

 Ein Array verfügt über die folgenden Eigenschaften:  
  
-   Ein Array kann [eindimensional](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md), [mehrdimensional](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) oder [verzweigt](../../../csharp/programming-guide/arrays/jagged-arrays.md) sein.  
  
-   Die Anzahl der Dimensionen und die Länge der einzelnen Dimensionen werden festgelegt, wenn die Arrayinstanz erstellt wird. Diese Werte können während der Lebensdauer der Instanz nicht geändert werden.  
  
-   Numerische Arrayelemente sind standardmäßig auf 0 (null) festgelegt, Verweiselemente auf NULL.  
  
-   Ein verzweigtes Array ist ein Array von Arrays, und deshalb sind seine Elemente Referenztypen und werden mit `null` initialisiert.  
  
-   Arrays sind nullbasiert: Der Index eines Arrays mit `n` Elementen beginnt bei `0` und endet bei `n-1`.  
  
-   Arrayelemente können einen beliebigen Typ aufweisen, z. B. auch einen Arraytyp.  
  
-   Arraytypen sind [Referenztypen](../../../csharp/language-reference/keywords/reference-types.md), die vom abstrakten Basistyp <xref:System.Array> abgeleitet werden. Da dieser Typ <xref:System.Collections.IEnumerable> und <xref:System.Collections.Generic.IEnumerable%601> implementiert, können Sie die [foreach](../../../csharp/language-reference/keywords/foreach-in.md)-Iteration für alle Arrays in C# verwenden.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
  
-   [Arrays als Objekte](../../../csharp/programming-guide/arrays/arrays-as-objects.md)  
  
-   [Verwenden von foreach mit Arrays](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
-   [Übergeben von Arrays als Argumente](../../../csharp/programming-guide/arrays/passing-arrays-as-arguments.md)  
  
-   [Übergeben von Arrays mithilfe von "ref" und "out"](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)   
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [Sammlungen](https://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)  
- [Array-Auflistungstyp](https://msdn.microsoft.com/library/8a9964de-8941-47b1-a3cf-a01bc88db9e8)
