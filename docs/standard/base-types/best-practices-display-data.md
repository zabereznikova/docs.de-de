---
title: Bewährte Methoden für das Anzeigen und Beibehalten formatierter Daten in .NET
description: Erfahren Sie, wie Sie numerische und Datumsdaten in .NET-Anwendungen effektiv anzeigen und beibehalten.
ms.date: 05/01/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.openlocfilehash: 83a491f6c843225c6242a343fe4132c2ce7caa74
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "93403471"
---
# <a name="best-practices-for-displaying-and-persisting-formatted-data"></a>Bewährte Methoden für das Anzeigen und Beibehalten formatierter Daten

In diesem Artikel wird außerdem untersucht, wie formatierte Daten, z. B. numerische Daten und Datums-/Uhrzeitdaten, für Anzeige und Speicherung behandelt werden.

Verwenden Sie beim Entwickeln mit .NET eine kulturabhängige Formatierung, um Daten, die keine Zeichenfolge sind, z. B. Zahlen und Datumsangaben, auf einer Benutzeroberfläche anzuzeigen. Verwenden Sie Formatierung mit der [invarianten Kultur](xref:System.Globalization.CultureInfo.InvariantCulture), um für Daten, die keine Zeichenfolge sind, das Zeichenfolgenformat beizubehalten. Wählen Sie nicht die kulturabhängige Formatierung, um numerische oder Datums-/Uhrzeitdaten im Zeichenfolgenformat beizubehalten.

## <a name="displaying-formatted-data"></a>Anzeigen formatierter Daten

Wenn Sie Benutzern Daten anzeigen, die keine Zeichenfolge sind, z. B. Zahlen sowie Datumsangaben und Zeitangaben, formatieren Sie diese den Kultureinstellungen des Benutzers entsprechend. In den folgenden Fällen wird bei Formatierungsvorgängen jeweils standardmäßig die aktuelle Threadkultur verwendet:

- Bei interpolierten Zeichenfolgen, die von den [C#](../../csharp/language-reference/tokens/interpolated.md)- und [Visual Basic](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md)-Compilern unterstützt werden.
- Bei Zeichenfolgenverkettungen, bei denen [C#](../../csharp/language-reference/operators/addition-operator.md#string-concatenation)- oder [Visual Basic](../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)-Verkettungsoperatoren verwendet werden oder die Methode <xref:System.String.Concat%2A?displayProperty=nameWithType> direkt aufgerufen wird.
- Die <xref:System.String.Format%2A?displayProperty=nameWithType> -Methode.
- Bei den `ToString`-Methoden der numerischen Typen sowie der Datums- und Uhrzeittypen.

Wenn Sie explizit angeben möchten, dass eine Zeichenfolge unter Verwendung der Konventionen einer bestimmten Kultur oder der [invarianten Kultur](xref:System.Globalization.CultureInfo.InvariantCulture) formatiert werden soll, haben Sie folgende Möglichkeiten:

- Rufen Sie bei Verwendung der Methoden <xref:System.String.Format%2A?displayProperty=nameWithType> und `ToString` eine Überladung mit einem Parameter vom Typ `provider` (beispielsweise <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> oder <xref:System.DateTime.ToString%28System.IFormatProvider%29?displayProperty=nameWithType>) auf, und übergeben Sie die Eigenschaft <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>, eine Instanz vom Typ <xref:System.Globalization.CultureInfo>, die die gewünschte Kultur darstellt, oder die Eigenschaft <xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType>.

- Lassen Sie bei der Verkettung von Zeichenfolgen keine impliziten Konvertierungen durch den Compiler zu. Rufen Sie stattdessen eine Überladung vom Typ `ToString` mit einem Parameter vom Typ `provider` auf, um eine explizite Konvertierung durchzuführen. Der Compiler verwendet beispielsweise implizit die aktuelle Kultur, wenn ein Wert vom Typ <xref:System.Double> in folgendem Code in eine Zeichenfolge konvertiert wird:

  [!code-csharp[Implicit String Conversion](./snippets/best-practices-strings/csharp/tostring/Program.cs#1)]
  [!code-vb[Implicit String Conversion](./snippets/best-practices-strings/vb/tostring/Program.vb#1)]

  Alternativ können Sie explizit die Kultur angeben, deren Formatierungskonventionen bei der Konvertierung verwendet werden sollen. Rufen Sie hierzu die Methode <xref:System.Double.ToString(System.IFormatProvider)?displayProperty=nameWithType> auf, wie im folgenden Code zu sehen:

  [!code-csharp[Explicit String Conversion](./snippets/best-practices-strings/csharp/tostring/Program.cs#2)]
  [!code-vb[Implicit String Conversion](./snippets/best-practices-strings/vb/tostring/Program.vb#2)]

- Weisen Sie für die Zeichenfolgeninterpolation eine interpolierte Zeichenfolge einer Instanz vom Typ <xref:System.FormattableString> (anstatt einer Instanz vom Typ <xref:System.String>) zu. Anschließend können Sie die Methode <xref:System.FormattableString.ToString?displayProperty=nameWithType> aufrufen, um eine Ergebniszeichenfolge zu erzeugen, die den Konventionen der aktuellen Kultur entspricht, oder die Methode <xref:System.FormattableString.ToString(System.IFormatProvider)?displayProperty=nameWithType>, um eine Ergebniszeichenfolge zu erzeugen, die den Konventionen einer angegebenen Kultur entspricht. Sie können auch die formatierbare Zeichenfolge an die statische Methode <xref:System.FormattableString.Invariant%2A?displayProperty=nameWithType> übergeben, um eine Ergebniszeichenfolge zu erzeugen, die den Konventionen der invarianten Kultur entspricht. Dieser Ansatz wird anhand des folgenden Beispiels veranschaulicht. (Bei der Ausgabe des Beispiels wird als aktuelle Kultur „en-US“ verwendet.)

  [!code-csharp[String interpolation](./snippets/best-practices-strings/csharp/formattable/Program.cs)]
  [!code-vb[String interpolation](./snippets/best-practices-strings/vb/formattable/Program.vb)]

## <a name="persisting-formatted-data"></a>Beibehalten formatierter Daten

Sie können Daten, die keine Zeichenfolge sind, entweder als Binärdaten oder als formatierte Daten beibehalten. Wenn Sie möchten, dass sie als formatierte Daten gespeichert werden, sollten Sie eine Überladung einer Formatierungsmethode aufrufen, die einen `provider` -Parameter einschließt, und dabei die <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> -Eigenschaft übergeben. Die invariante Kultur stellt ein konsistentes Format für formatierte Daten bereit, das unabhängig von der Kultur und dem Computers ist. Im Gegensatz dazu bringt das Beibehalten von Daten, die mit anderen Kulturen als der invarianten Kultur formatiert werden, einige Einschränkungen mit sich:

- Die Daten sind wahrscheinlich unbrauchbar, wenn sie auf einem System mit einer andere Kultur abgerufen werden oder wenn der Benutzer des aktuellen Systems die aktuelle Kultur ändert und versucht, die Daten abzurufen.
- Die Eigenschaften einer Kultur auf einem bestimmten Computer können von den Standardwerten abweichen. Ein Benutzer kann kulturabhängige Anzeigeeinstellungen jederzeit anpassen. Aufgrund dessen können formatierte Daten, die in einem System gespeichert sind, möglicherweise nicht mehr gelesen werden, wenn der Benutzer die Kultureinstellungen anpasst. Die computerübergreifende Portabilität von formatierten Daten wird wahrscheinlich sogar noch eingeschränkter.
- Internationale, regionale oder nationale Standards, die die Formatierung von Zahlen oder Datumsangaben und Uhrzeiten regeln, ändern sich mit der Zeit, und diese Änderungen werden in Windows-Betriebssystemupdates integriert. Wenn sich die Formatierungskonventionen ändern, können Daten, die anhand früherer Konventionen formatiert wurden, möglicherweise nicht mehr gelesen werden.

Das folgende Beispiel veranschaulicht die eingeschränkte Portabilität, die sich aus der Verwendung von kulturabhängiger Formatierung zum Beibehalten von Daten ergibt. In dem Beispiel wird ein Array von Daten- und Uhrzeitwerten in einer Datei gespeichert. Diese werden anhand der Konventionen der Kultur Englisch (USA) formatiert. Nachdem die aktuelle Threadkultur der Anwendung in Französisch (Schweiz) geändert wird, versucht die Anwendung, die gespeicherten Werte mithilfe der Formatierungskonventionen der aktuellen Kultur zu lesen. Der Versuch, zwei der Datenelemente zu lesen, löst eine <xref:System.FormatException> -Ausnahme aus, und das Array von Datumsangaben enthält nun zwei falsche Elemente, die <xref:System.DateTime.MinValue>entsprechen.

[!code-csharp[Conceptual.Strings.BestPractices#21](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/persistence.cs#21)]
[!code-vb[Conceptual.Strings.BestPractices#21](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/persistence.vb#21)]

Wenn Sie jedoch die <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>-Eigenschaft in den Aufrufen von <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> und <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> durch <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> ersetzen, werden wie in der folgenden Ausgabe gezeigt die beibehaltenen Datums- und Uhrzeitdaten erfolgreich wiederhergestellt:

```console
06.05.1758 21:26
05.05.1818 07:19
22.04.1870 23:54
08.09.1890 06:47
18.02.1905 15:12
```
