---
title: Arrays – C#-Programmierhandbuch
description: Speichern Sie mehrere Variablen des gleichen Typs in einer Arraydatenstruktur in C#. Deklarieren Sie ein Array, indem Sie einen Typ angeben, oder geben Sie ein Objekt an, um beliebige Typen zu speichern.
ms.date: 01/22/2021
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: 203d8b86da4e74d8c5397132a0ba68618eedf348
ms.sourcegitcommit: 4d5e25a46aa7cd0d29b4b9227b92987354d444c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98794769"
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

### <a name="arrays-as-objects"></a>Arrays als Objekte

In C# sind Arrays tatsächlich Objekte und nicht nur adressierbare Regionen zusammenhängender Speicher wie in C und C++. <xref:System.Array> ist der abstrakte Basistyp aller Typen von Arrays. Sie können die Eigenschaften und die anderen Klassenmember verwenden, über die <xref:System.Array> verfügt. Ein Beispiel dafür ist die Verwendung der <xref:System.Array.Length%2A>-Eigenschaft, um die Länge eines Arrays zu erhalten. Der folgende Code weist die Länge des `numbers`-Arrays, die `5` beträgt, einer Variablen mit dem Namen `lengthOfNumbers` zu:

[!code-csharp[csProgGuideArrays#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#3)]

Die <xref:System.Array>-Klasse bietet viele weitere nützliche Methoden und Eigenschaften zum Sortieren, Durchsuchen und Kopieren von Arrays. Im folgenden Beispiel wird die <xref:System.Array.Rank%2A>-Eigenschaft verwendet, um die Anzahl der Dimensionen eines Arrays anzuzeigen.

[!code-csharp[csProgGuideArrays#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#2)]

## <a name="see-also"></a>Weitere Informationen

- [Verwenden eindimensionaler Arrays](single-dimensional-arrays.md)
- [Verwenden mehrdimensionaler Arrays](multidimensional-arrays.md)
- [Verwenden verzweigter Arrays](jagged-arrays.md)
- [Verwenden von foreach mit Arrays](using-foreach-with-arrays.md)
- [Übergeben von Arrays als Argumente](passing-arrays-as-arguments.md)
- [Implizit typisierte Arrays](implicitly-typed-arrays.md)
- [C#-Programmierhandbuch](../index.md)
- [Sammlungen](../concepts/collections.md)

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]
