---
title: Eindimensionale Arrays – C#-Programmierhandbuch
ms.date: 06/03/2020
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
ms.openlocfilehash: e189253eedc21fa2d51e16407f04b034610bb57b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410243"
---
# <a name="single-dimensional-arrays-c-programming-guide"></a>Eindimensionale Arrays (C#-Programmierhandbuch)

Sie erstellen ein eindimensionales Array mit dem Operator [new](../../language-reference/operators/new-operator.md), indem Sie den Arrayelementtyp und die Anzahl der Elemente angeben. Im folgenden Beispiel wird ein Array aus fünf Integern deklariert:

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="IntDeclaration":::

Dieses Array enthält die Elemente `array[0]` bis `array[4]`. Die Elemente des Arrays werden mit dem Standardwert des Elementtyps initialisiert (`0` für Integer).

Arrays können jeden beliebigen Elementtyp speichern, den Sie angeben. Dies wird im folgenden Beispiel veranschaulicht, in dem ein Array aus Zeichenfolgen deklariert wird:

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="StringDeclaration":::

## <a name="array-initialization"></a>Arrayinitialisierung

Sie können die Elemente eines Arrays initialisieren, wenn Sie das Array deklarieren. Der Spezifizierer für die Länge ist nicht erforderlich, weil dieser von der Anzahl der Elemente in der Initialisierungsliste abgeleitet wird. Zum Beispiel:

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="IntInitialization":::

Im folgenden Code wird eine Deklaration eines Zeichenfolgenarrays veranschaulicht, in dem jedes Arrayelement durch den Namen eines Wochentags initialisiert wird:

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="StringInitialization":::
  
Wie im folgenden Code gezeigt, können Sie den `new`-Ausdruck und den Arraytyp bei der Deklaration vermeiden, wenn Sie ein Array initialisieren. Diese Art von Array wird als [implizit typisiertes Array](implicitly-typed-arrays.md) bezeichnet:

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="ShorthandInitialization":::

Sie können eine Arrayvariable deklarieren, ohne sie zu erstellen. Sie müssen jedoch den Operator `new` verwenden, wenn Sie dieser Variable ein neues Array zuweisen. Zum Beispiel:

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="DeclareAllocate":::

## <a name="value-type-and-reference-type-arrays"></a>Werttyp- und Verweistyparrays

Betrachten Sie die folgende Arraydeklaration:  

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="FinalInstantiation":::

Das Ergebnis dieser Anweisung hängt davon ab, ob `SomeType` ein Werttyp oder ein Verweistyp ist. Wenn es sich um einen Werttyp handelt, erstellt die Anweisung ein Array aus 10 Elementen, die alle den Typ `SomeType` aufweisen. Stellt `SomeType` einen Verweistyp dar, wird durch die Anweisung ein Array aus 10 Elementen erstellt, von denen jedes mit einem NULL-Verweis initialisiert wird. In beiden Instanzen werden die Elemente mit dem Standardwert für den Elementtyp initialisiert. Weitere Informationen zu Werttypen und Verweistypen finden Sie unter [Werttypen](../../language-reference/builtin-types/value-types.md) und [Verweistypen](../../language-reference/keywords/reference-types.md).
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Array>
- [Arrays](./index.md)
- [Mehrdimensionale Arrays](./multidimensional-arrays.md)
- [Verzweigte Arrays](./jagged-arrays.md)
