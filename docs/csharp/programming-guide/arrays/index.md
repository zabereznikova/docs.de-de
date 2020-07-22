---
title: Arrays – C#-Programmierhandbuch
description: Speichern Sie mehrere Variablen des gleichen Typs in einer Arraydatenstruktur in C#. Deklarieren Sie ein Array, indem Sie einen Typ angeben, oder geben Sie ein Objekt an, um beliebige Typen zu speichern.
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: e302ff2e4c2488c4899c4eb99a666d2d322119ce
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474734"
---
# <a name="arrays-c-programming-guide"></a>Arrays (C#-Programmierhandbuch)

Sie können mehrere Variablen des gleichen Typs in einer Arraydatenstruktur speichern. Ein Array wird deklariert, indem der Typ seiner Elemente angegeben wird. Wenn Sie möchten, dass das Array Element jedes Typs speichert, können Sie `object` als dessen Typ angeben. Im vereinheitlichen Typsystem von C# erben alle Typen, vordefiniert und benutzerdefiniert sowie Verweis- und Werttypen, direkt oder indirekt von <xref:System.Object>.

```csharp
type[] arrayName;
```

## <a name="example"></a>Beispiel

In den folgenden Beispiel wird ein eindimensionales, ein mehrdimensionales und ein verzweigtes Array erstellt:

[!code-csharp[csProgGuideArrays#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#1)]

## <a name="array-overview"></a>Übersicht über Arrays

Ein Array verfügt über die folgenden Eigenschaften:

- Ein Array kann [eindimensional](single-dimensional-arrays.md), [mehrdimensional](multidimensional-arrays.md) oder [verzweigt](jagged-arrays.md) sein.
- Die Anzahl der Dimensionen und die Länge der einzelnen Dimensionen werden festgelegt, wenn die Arrayinstanz erstellt wird. Diese Werte können während der Lebensdauer der Instanz nicht geändert werden.
- Numerische Arrayelemente sind standardmäßig auf 0 (null) festgelegt, Verweiselemente auf NULL.
- Ein verzweigtes Array ist ein Array von Arrays, und deshalb sind seine Elemente Referenztypen und werden mit `null` initialisiert.
- Arrays sind nullbasiert: Der Index eines Arrays mit `n` Elementen beginnt bei `0` und endet bei `n-1`.
- Arrayelemente können einen beliebigen Typ aufweisen, z. B. auch einen Arraytyp.
- Arraytypen sind [Referenztypen](../../language-reference/keywords/reference-types.md), die vom abstrakten Basistyp <xref:System.Array> abgeleitet werden. Da dieser Typ <xref:System.Collections.IEnumerable> und <xref:System.Collections.Generic.IEnumerable%601> implementiert, können Sie die [foreach](../../language-reference/keywords/foreach-in.md)-Iteration für alle Arrays in C# verwenden.

## <a name="related-sections"></a>Verwandte Abschnitte

- [Arrays als Objekte](arrays-as-objects.md)
- [Verwenden von foreach mit Arrays](using-foreach-with-arrays.md)
- [Übergeben von Arrays als Argumente](passing-arrays-as-arguments.md)

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Sammlungen](../concepts/collections.md)
