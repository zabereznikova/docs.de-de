---
title: 'Vorgehensweise: Ändern von Zeichenfolgeninhalten – C#-Leitfaden'
description: Hier finden Sie Beispiele für verschiedene Techniken zum Ändern vorhandener Zeichenfolgeninhalte in C#, die ein neues Zeichenfolgenobjekt zurückgeben.
ms.date: 02/26/2018
helpviewer_keywords:
- strings [C#], modifying
ms.openlocfilehash: ecce8857befc66353deea341d81f8c6e4313b951
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86473967"
---
# <a name="how-to-modify-string-contents-in-c"></a>Vorgehensweise: Ändern von Zeichenfolgeninhalten in C\#

In diesem Artikel werden verschiedene Methoden zum Erzeugen einer `string` durch Modifizieren einer vorhandenen `string` erläutert. Alle diese gezeigten Methoden geben das Ergebnis der Modifizierung als neues `string`-Objekt zurück. Die Beispiele speichern das Ergebnis in einer neuen Variable, um zu zeigen, dass es sich bei den ursprünglichen und den bearbeiteten Zeichenfolgen um unterschiedliche Instanzen handelt. Sie können die ursprüngliche `string` und die neue, bearbeitete `string` untersuchen, wenn Sie die einzelnen Beispiele ausführen.

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

In diesem Artikel werden mehrere Methoden aufgezeigt. Sie können vorhandenen Text ersetzen. Sie können nach Mustern suchen und übereinstimmenden Text durch anderen Text ersetzen. Sie können Zeichenfolgen als Zeichensequenzen behandeln. Sie können zudem Hilfsmethoden verwenden, die Leerräume entfernen. Verwenden Sie diejenigen Methoden, die am besten zu Ihrem Szenario passen.

## <a name="replace-text"></a>Ersetzen von Text

Der folgende Code erstellt eine neue Zeichenfolge, indem er vorhandenen Text ersetzt.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet1":::

Der vorherige Code veranschaulicht diese *unveränderliche* Eigenschaft von Zeichenfolgen. Im vorherigen Beispiel können Sie sehen, dass die ursprüngliche Zeichenfolge `source` nicht modifiziert wird. Die Methode <xref:System.String.Replace%2A?displayProperty=nameWithType> erstellt eine neue `string`, die die Modifizierungen enthält.

Die Methode <xref:System.String.Replace%2A> kann entweder Zeichenfolgen oder einzelne Zeichen ersetzen. In beiden Fällen wird jedes Vorkommen des gesuchten Texts ersetzt.  In folgendem Beispiel werden alle „ “-Zeichen durch \_ ersetzt:

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet2":::

Die Quellzeichenfolge bleibt unverändert, und es wird eine neue Zeichenfolge mit der Ersetzung zurückgegeben.

## <a name="trim-white-space"></a>Entfernen von Leerräumen

Sie können die Methoden <xref:System.String.Trim%2A?displayProperty=nameWithType>, <xref:System.String.TrimStart%2A?displayProperty=nameWithType> und <xref:System.String.TrimEnd%2A?displayProperty=nameWithType> verwenden, um führende oder nachfolgende Leerräume zu entfernen.  Im folgenden Code ist ein Beispiel für jede Methode dargestellt. Die Quellzeichenfolge bleibt unverändert. Diese Methoden geben eine neue Zeichenfolge mit modifiziertem Inhalt zurück.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet3":::

## <a name="remove-text"></a>Entfernen von Text

Mit der Methode <xref:System.String.Remove%2A?displayProperty=nameWithType> können Sie Text aus einer Zeichenfolge entfernen. Diese Methode entfernt mehrere Zeichen ab einem spezifischen Index. In folgendem Beispiel wird gezeigt, wie Sie <xref:System.String.IndexOf%2A?displayProperty=nameWithType> gefolgt von <xref:System.String.Remove%2A> verwenden können, um Text aus einer Zeichenfolge zu entfernen:

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet4":::

## <a name="replace-matching-patterns"></a>Ersetzen von übereinstimmenden Mustern

Sie können [reguläre Ausdrücke](../../standard/base-types/regular-expressions.md) verwenden, um Text, der mit Mustern übereinstimmt, durch neuen Text zu ersetzen, der auch durch ein Muster definiert werden kann. In folgendem Beispiel wird die Klasse <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> verwendet, um ein Muster in einer Quellzeichenfolge zu finden und dieses durch Text mit korrekter Großschreibung zu ersetzen. Die Methode <xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.Text.RegularExpressions.MatchEvaluator,System.Text.RegularExpressions.RegexOptions)?displayProperty=nameWithType> akzeptiert eine Funktion, die die Logik der Ersetzung als eines ihrer Argumente bereitstellt. In diesem Beispiel ist diese Funktion `LocalReplaceMatchCase` eine **lokale Funktion**, die in der Beispielmethode deklariert wird. `LocalReplaceMatchCase` verwendet die <xref:System.Text.StringBuilder?displayProperty=nameWithType>-Klasse zum Erstellen der Ersatzzeichenfolge mit korrekter Großschreibung.

Reguläre Ausdrücke sind besonders beim Suchen und Ersetzen von Text nützlich, der einem bestimmten Muster folgt, und nicht so sehr bei bekanntem Text. Weitere Informationen finden Sie unter [Vorgehensweise: Durchsuchen von Zeichenfolgen](search-strings.md). Das Suchmuster „the\s“ sucht nach dem Wort „the“ gefolgt von einem Leerzeichen. Der Teil des Musters stellt sicher, das es nicht „there“ als Übereinstimmung in der Quellzeichenfolge ansieht. Weitere Informationen zur Sprache für reguläre Ausdrücke finden Sie unter [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](../../standard/base-types/regular-expression-language-quick-reference.md).

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet5":::

Die Methode <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> gibt eine unveränderliche Zeichenfolge zurück, die den Inhalt im <xref:System.Text.StringBuilder>-Objekt enthält.

## <a name="modifying-individual-characters"></a>Modifizieren einzelner Zeichen

Sie können ein Zeichenarray aus einer Zeichenfolge erzeugen, den Inhalt des Arrays modifizieren und dann eine neue Zeichenfolge aus dem modifizierten Inhalt des Arrays erstellen.

In folgendem Beispiel wird gezeigt, wie Sie mehrere Zeichen in einer Zeichenfolge ersetzen. Zunächst wird die Methode <xref:System.String.ToCharArray?displayProperty=nameWithType> verwendet, um ein Zeichenarray zu erstellen. Die Methode <xref:System.String.IndexOf%2A> wird verwendet, um den Startindex des Worts „fox“ zu finden. Die folgenden drei Zeichen werden durch ein anderes Wort ersetzt. Zum Schluss wird eine neue Zeichenfolge aus dem aktualisierten Zeichenarray erstellt.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet6":::

## <a name="programmatically-build-up-string-content"></a>Programmgesteuertes Erstellen von Zeichenfolgeninhalten

Da Zeichenfolgen unveränderlich sind, erzeugen die vorherigen Beispiele alle temporäre Zeichenfolgen oder -arrays. In Hochleistungsszenarien ist es möglicherweise wünschenswert, diese Heapzuordnungen zu vermeiden. .NET Core bietet die Methode <xref:System.String.Create%2A?displayProperty=nameWithType>, mit der Sie den Zeicheninhalt einer Zeichenfolge über einen Rückruf programmgesteuert füllen können, wobei die zwischengeschalteten temporären Zeichenfolgenzuordnungen vermieden werden.

:::code language="csharp" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet7":::

Sie können eine Zeichenfolge in einem festen Block mit unsicherem Code ändern. Es wird jedoch **stark** davon abgeraten, den Inhalt der Zeichenfolge nach deren Erstellung zu ändern. Dadurch können Abläufe auf unvorhersehbare Weise beeinträchtigt werden. Wenn jemand beispielsweise eine Zeichenfolge internalisiert, die den gleichen Inhalt wie Ihre hat, erhält er Ihre Kopie und erwartet nicht, dass Sie seine Zeichenfolge ändern.

## <a name="see-also"></a>Siehe auch

- [Reguläre Ausdrücke von .NET Framework](../../standard/base-types/regular-expressions.md)
- [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](../../standard/base-types/regular-expression-language-quick-reference.md)
