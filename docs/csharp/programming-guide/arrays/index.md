---
title: Arrays – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: 24c6d54c3fe92ada661e732adec582e87ab62417
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69597531"
---
# <a name="arrays-c-programming-guide"></a>Arrays (C#-Programmierhandbuch)

Sie können mehrere Variablen des gleichen Typs in einer Arraydatenstruktur speichern. Ein Array wird deklariert, indem der Typ seiner Elemente angegeben wird.  
  
 `type[] arrayName;`  
  
 In den folgenden Beispiel wird ein eindimensionales, ein mehrdimensionales und ein verzweigtes Array erstellt:  
  
 [!code-csharp[csProgGuideArrays#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#1)]  
  
## <a name="array-overview"></a>Übersicht über Arrays

 Ein Array verfügt über die folgenden Eigenschaften:  
  
- Ein Array kann [eindimensional](./single-dimensional-arrays.md), [mehrdimensional](./multidimensional-arrays.md) oder [verzweigt](./jagged-arrays.md) sein.  
  
- Die Anzahl der Dimensionen und die Länge der einzelnen Dimensionen werden festgelegt, wenn die Arrayinstanz erstellt wird. Diese Werte können während der Lebensdauer der Instanz nicht geändert werden.  
  
- Numerische Arrayelemente sind standardmäßig auf 0 (null) festgelegt, Verweiselemente auf NULL.  
  
- Ein verzweigtes Array ist ein Array von Arrays, und deshalb sind seine Elemente Referenztypen und werden mit `null` initialisiert.  
  
- Arrays sind nullbasiert: Der Index eines Arrays mit `n` Elementen beginnt bei `0` und endet bei `n-1`.  
  
- Arrayelemente können einen beliebigen Typ aufweisen, z. B. auch einen Arraytyp.  
  
- Arraytypen sind [Referenztypen](../../language-reference/keywords/reference-types.md), die vom abstrakten Basistyp <xref:System.Array> abgeleitet werden. Da dieser Typ <xref:System.Collections.IEnumerable> und <xref:System.Collections.Generic.IEnumerable%601> implementiert, können Sie die [foreach](../../language-reference/keywords/foreach-in.md)-Iteration für alle Arrays in C# verwenden.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
  
- [Arrays als Objekte](./arrays-as-objects.md)  
  
- [Verwenden von foreach mit Arrays](./using-foreach-with-arrays.md)  
  
- [Übergeben von Arrays als Argumente](./passing-arrays-as-arguments.md)  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Sammlungen](../concepts/collections.md)
