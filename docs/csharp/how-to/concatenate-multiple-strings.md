---
title: 'Vorgehensweise: Verketten mehrerer Zeichenfolgen (C#-Handbuch)'
description: Es gibt mehrere Möglichkeiten zum Verketten von Zeichenfolgen in C#. Lernen Sie die Optionen und Gründe für verschiedene Auswahlmöglichkeiten kennen.
ms.date: 02/20/2018
helpviewer_keywords:
- joining strings [C#]
- concatenating strings [C#]
- strings [C#], concatenation
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
ms.openlocfilehash: 2e443030445d2817c8f53a044a261edd22eeb26e
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73973276"
---
# <a name="how-to-concatenate-multiple-strings-c-guide"></a>Vorgehensweise: Verketten mehrerer Zeichenfolgen (C#-Handbuch)

*Verkettung* ist der Prozess, eine Zeichenfolge ans Ende einer anderen Zeichenfolge anzufügen. Sie können Zeichenfolgen mithilfe des `+`-Operators verketten. Bei Zeichenfolgenliteralen und Zeichenfolgenkonstanten erfolgt die Verkettung beim Kompilieren. Es erfolgt keine Verkettung zur Laufzeit. Bei Zeichenfolgenvariablen erfolgt die Verkettung nur zur Laufzeit.

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

Im folgenden Beispiel wird die Verkettung genutzt, um ein langes Zeichenfolgenliteral in kleinere Zeichenfolgen aufzuteilen, wodurch die Lesbarkeit im Quellcode verbessert wird. Diese Teile werden zur Kompilierzeit in eine einzelne Zeichenfolge verkettet. Es entstehen unabhängig von der Anzahl an Zeichenfolgen keine Leistungseinbußen zur Laufzeit.  
  
 [!code-csharp-interactive[Combining strings at compile time](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#1)]  

Zum Verketten von Zeichenfolgenvariablen können Sie die Operatoren `+` und `+=`, die [Zeichenfolgeninterpolation](../language-reference/tokens/interpolated.md) oder die Methoden <xref:System.String.Format%2A?displayProperty=nameWithType>, <xref:System.String.Concat%2A?displayProperty=nameWithType>, <xref:System.String.Join%2A?displayProperty=nameWithType> oder <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType> verwenden. Der Operator `+` ist einfach zu verwenden und gut für intuitiv verständlichen Code geeignet. Auch wenn Sie mehrere `+`-Operatoren in einer Anweisung verwenden, wird der Inhalt der Zeichenfolge nur einmal kopiert. Der folgende Code zeigt Beispiele für die Verwendung der Operatoren `+` und `+=` zum Verketten von Zeichenfolgen:

[!code-csharp-interactive[combining strings using +](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#2)]  

In einigen Ausdrücken ist es einfacher, Zeichenfolgen mithilfe der Zeichenfolgeninterpolation zu verketten, wie in folgendem Beispiel gezeigt wird:
  
[!code-csharp-interactive[building strings using string interpolation](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#3)]  
  
> [!NOTE]
> Bei der Zeichenfolgenverkettung behandelt der C#-Compiler eine NULL-Zeichenfolge wie eine leere Zeichenfolge.

Eine andere Methoden zum Verketten von Zeichenfolgen ist <xref:System.String.Format%2A?displayProperty=nameWithType>. Diese Methode funktioniert gut, wenn Sie eine Zeichenfolge mit einer kleinen Anzahl von Zeichenfolgenkomponenten erstellen.

In anderen Fällen kann es passieren, dass Sie Zeichenfolgen in einer Schleife kombinieren, bei der Sie nicht wissen, wie viele Quellzeichenfolgen Sie kombinieren, und die tatsächliche Anzahl an Quellzeichenfolgen kann in solchen Fällen sehr groß sein. Für solche Szenarios wurde die Klasse <xref:System.Text.StringBuilder> entwickelt. Im folgenden Code werden Zeichenfolgen mit der Methode <xref:System.Text.StringBuilder.Append%2A> der Klasse <xref:System.Text.StringBuilder> verkettet.  
  
[!code-csharp-interactive[string concatenation using string builder](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#4)]  

Erfahren Sie mehr über die [Gründe für das Verketten von Zeichenfolgen oder die `StringBuilder`-Klasse](xref:System.Text.StringBuilder#StringAndSB)

Eine weitere Option zum Verketten von Zeichenfolgen aus einer Sammlung ist die Verwendung der Methode <xref:System.String.Concat%2A?displayProperty=nameWithType>. Verwenden Sie die <xref:System.String.Join%2A?displayProperty=nameWithType>-Methode, wenn Quellzeichenfolgen durch ein Trennzeichen getrennt werden sollen. Der folgenden Code kombiniert ein Array aus Wörtern mithilfe beider Methoden:

[!code-csharp-interactive[concatenation of string collection](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#5)]

Die letzte Option zum Verketten von Zeichenfolgen aus einer Sammlung ist die Verwendung von [LINQ](../programming-guide/concepts/linq/index.md) und der Methode <xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType>. Diese Methode kombiniert die Quellzeichenfolgen mithilfe eines Lambdaausdrucks. Der Lambdaausdruck fügt jede Zeichenfolge der vorhandenen Akkumulation zu. Im folgenden Beispiel wird ein Array von Worten kombiniert, indem zwischen jedem Wort im Array Leerzeichen hinzugefügt werden:

[!code-csharp-interactive[string concatenation using LINQ expressions](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#6)]  

Sie können diese Beispiele ausprobieren, indem Sie sich den Code in unserem [GitHub-Repository](https://github.com/dotnet/samples/tree/master/snippets/csharp/how-to/strings) ansehen. Alternativ dazu können Sie die Beispiele [als ZIP-Datei](https://github.com/dotnet/samples/raw/master/snippets/csharp/how-to/strings.zip) herunterladen.

## <a name="see-also"></a>Siehe auch

- <xref:System.String>
- <xref:System.Text.StringBuilder>
- [C#-Programmierhandbuch](../programming-guide/index.md)
- [Zeichenfolgen](../programming-guide/strings/index.md)
