---
title: 'Vorgehensweise: Verketten mehrerer Zeichenfolgen (C#-Handbuch)'
description: Es gibt mehrere Möglichkeiten zum Verketten von Zeichenfolgen in C#. Lernen Sie die Optionen und Gründe für verschiedene Auswahlmöglichkeiten kennen.
ms.date: 02/20/2018
helpviewer_keywords:
- joining strings [C#]
- concatenating strings [C#]
- strings [C#], concatenation
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
ms.openlocfilehash: f2aae14deac967a833fb3510acdb32e0971485b5
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537482"
---
# <a name="how-to-concatenate-multiple-strings-c-guide"></a>Vorgehensweise: Verketten mehrerer Zeichenfolgen (C#-Handbuch)

*Verkettung* ist der Prozess, eine Zeichenfolge ans Ende einer anderen Zeichenfolge anzufügen. Sie können Zeichenfolgen mithilfe des `+`-Operators verketten. Bei Zeichenfolgenliteralen und Zeichenfolgenkonstanten erfolgt die Verkettung beim Kompilieren. Es erfolgt keine Verkettung zur Laufzeit. Bei Zeichenfolgenvariablen erfolgt die Verkettung nur zur Laufzeit.

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

Im folgenden Beispiel wird die Verkettung genutzt, um ein langes Zeichenfolgenliteral in kleinere Zeichenfolgen aufzuteilen, wodurch die Lesbarkeit im Quellcode verbessert wird. Diese Teile werden zur Kompilierzeit in eine einzelne Zeichenfolge verkettet. Es entstehen unabhängig von der Anzahl an Zeichenfolgen keine Leistungseinbußen zur Laufzeit.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/Concatenate.cs" id="Snippet1":::

Zum Verketten von Zeichenfolgenvariablen können Sie die Operatoren `+` und `+=`, die [Zeichenfolgeninterpolation](../language-reference/tokens/interpolated.md) oder die Methoden <xref:System.String.Format%2A?displayProperty=nameWithType>, <xref:System.String.Concat%2A?displayProperty=nameWithType>, <xref:System.String.Join%2A?displayProperty=nameWithType> oder <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType> verwenden. Der Operator `+` ist einfach zu verwenden und gut für intuitiv verständlichen Code geeignet. Auch wenn Sie mehrere `+`-Operatoren in einer Anweisung verwenden, wird der Inhalt der Zeichenfolge nur einmal kopiert. Der folgende Code zeigt Beispiele für die Verwendung der Operatoren `+` und `+=` zum Verketten von Zeichenfolgen:

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/Concatenate.cs" id="Snippet2":::

In einigen Ausdrücken ist es einfacher, Zeichenfolgen mithilfe der Zeichenfolgeninterpolation zu verketten, wie in folgendem Beispiel gezeigt wird:

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/Concatenate.cs" id="Snippet3":::

> [!NOTE]
> Bei der Zeichenfolgenverkettung behandelt der C#-Compiler eine NULL-Zeichenfolge wie eine leere Zeichenfolge.

Eine andere Methoden zum Verketten von Zeichenfolgen ist <xref:System.String.Format%2A?displayProperty=nameWithType>. Diese Methode funktioniert gut, wenn Sie eine Zeichenfolge mit einer kleinen Anzahl von Zeichenfolgenkomponenten erstellen.

In anderen Fällen kann es passieren, dass Sie Zeichenfolgen in einer Schleife kombinieren, bei der Sie nicht wissen, wie viele Quellzeichenfolgen kombiniert werden, und die tatsächliche Anzahl an Quellzeichenfolgen kann in solchen Fällen sehr groß sein. Für solche Szenarios wurde die Klasse <xref:System.Text.StringBuilder> entwickelt. Im folgenden Code werden Zeichenfolgen mit der Methode <xref:System.Text.StringBuilder.Append%2A> der Klasse <xref:System.Text.StringBuilder> verkettet.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/Concatenate.cs" id="Snippet4":::

Erfahren Sie mehr über die [Gründe für das Verketten von Zeichenfolgen oder die `StringBuilder`-Klasse](/dotnet/api/system.text.stringbuilder#the-string-and-stringbuilder-types).

Eine weitere Option zum Verketten von Zeichenfolgen aus einer Sammlung ist die Verwendung der Methode <xref:System.String.Concat%2A?displayProperty=nameWithType>. Verwenden Sie die <xref:System.String.Join%2A?displayProperty=nameWithType>-Methode, wenn Quellzeichenfolgen durch ein Trennzeichen getrennt werden sollen. Der folgenden Code kombiniert ein Array aus Wörtern mithilfe beider Methoden:

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/Concatenate.cs" id="Snippet5":::

Die letzte Option zum Verketten von Zeichenfolgen aus einer Sammlung ist die Verwendung von [LINQ](../programming-guide/concepts/linq/index.md) und der Methode <xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType>. Diese Methode kombiniert die Quellzeichenfolgen mithilfe eines Lambdaausdrucks. Der Lambdaausdruck fügt jede Zeichenfolge der vorhandenen Akkumulation zu. Im folgenden Beispiel wird ein Array von Worten kombiniert, indem zwischen jedem Wort im Array Leerzeichen hinzugefügt werden:

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/Concatenate.cs" id="Snippet6":::

## <a name="see-also"></a>Siehe auch

- <xref:System.String>
- <xref:System.Text.StringBuilder>
- [C#-Programmierhandbuch](../programming-guide/index.md)
- [Zeichenfolgen](../programming-guide/strings/index.md)
