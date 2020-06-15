---
title: 'Vorgehensweise: Vergleichen von Zeichenfolgen – C#-Leitfaden'
description: Lernen Sie, Zeichenfolgenwerte unter oder ohne Berücksichtigung der Groß-/Kleinschreibung und der Kultur zu vergleichen und zu sortieren.
ms.date: 10/03/2018
helpviewer_keywords:
- strings [C#], comparison
- comparing strings [C#]
ms.openlocfilehash: 725441f5399f72b6457af461d51419c35077f4c2
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662913"
---
# <a name="how-to-compare-strings-in-c"></a>Vergleichen von Zeichenfolgen in C\#

Durch den Vergleich zweier Zeichenfolgen können Sie entweder feststellen, ob diese gleich sind, oder in welche Reihenfolge sie beim Sortieren gebracht werden sollen.

Beide Vorgänge werden durch folgende Faktoren erschwert:

- Sie können einen Ordinalvergleich oder einen linguistischen Vergleich durchführen.
- Sie können festlegen, ob die Groß/-Kleinschreibung berücksichtigt werden soll.
- Sie können kulturspezifische Vergleiche durchführen.
- Linguistische Vergleiche sind kultur- und plattformabhängig.

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

Wenn Sie Zeichenfolgen vergleichen, definieren Sie für diese eine Reihenfolge. Bei einigen Vergleichen wird eine Zeichenfolgensequenz sortiert. Sobald sich die Sequenz in einer bestimmten Reihenfolge befindet, können Menschen und Softwareanwendungen leichter darin suchen. Bei anderen Vergleichen kann überprüft werden, ob Zeichenfolgen identisch sind. Identitätsprüfungen sind mit Gleichheitsprüfungen zu vergleichen, doch einige Unterschiede wie die Groß-/Kleinschreibung werden möglicherweise ignoriert.

## <a name="default-ordinal-comparisons"></a>Standardordinalvergleich

Standardmäßig gilt für die gängigsten Vorgänge Folgendes:

- <xref:System.String.CompareTo%2A?displayProperty=nameWithType>
- <xref:System.String.Equals%2A?displayProperty=nameWithType>
- <xref:System.String.op_Equality%2A?displayProperty=nameWithType> und <xref:System.String.op_Inequality%2A?displayProperty=nameWithType> (d.h. [equality-Operatoren `==` bzw. `!=`](../language-reference/operators/equality-operators.md#string-equality))

führen einen Ordinalvergleich unter Berücksichtigung der Groß/-Kleinschreibung aus und verwenden die aktuelle Kultur, wenn erforderlich. Dies wird im folgenden Beispiel veranschaulicht:

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs" id="Snippet1":::

Bei dem Standardordinalvergleich werden keine linguistischen Regeln berücksichtigt, wenn Zeichenfolgen verglichen werden. In ihm wird der binäre Wert jedes <xref:System.Char>-Objekts in zwei Zeichenfolgen verglichen. Dies bedingt, dass im Standardordinalvergleich ebenfalls die Groß-/Kleinschreibung beachtet wird.

Beachten Sie, dass sich der Test auf Gleichheit mit <xref:System.String.Equals%2A?displayProperty=nameWithType> und den Operatoren `==` und `!=` von einem Zeichenfolgenvergleich mit den Methoden <xref:System.String.CompareTo%2A?displayProperty=nameWithType> und <xref:System.String.Compare(System.String,System.String)?displayProperty=nameWithType)> unterscheidet. Während in den Tests auf Gleichheit ein Ordinalvergleich mit Beachtung der Groß-/Kleinschreibung ausgeführt wird, wird in den Vergleichsmethoden ein Vergleich unter Beachtung der Groß-/Kleinschreibung und der aktuellen Kultur ausgeführt. Weil die Standardvergleichsmethoden häufig unterschiedliche Arten von Vergleichen ausführen, sollten Sie die Absicht Ihres Codes immer verdeutlichen, indem Sie eine Überladung aufrufen, in der die Art des auszuführenden Vergleichs explizit angegeben ist.

## <a name="case-insensitive-ordinal-comparisons"></a>Ordinalvergleich ohne Beachtung der Groß- und Kleinschreibung

Mit der <xref:System.String.Equals(System.String,System.StringComparison)?displayProperty=nameWithType>-Methode können Sie einen <xref:System.StringComparison>-Wert von <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType> angeben,
um einen Ordinalvergleich ohne Beachtung der Groß-/Kleinschreibung auszuführen. Es gibt auch eine statische <xref:System.String.Compare(System.String,System.String,System.StringComparison)?displayProperty=nameWithType>-Methode, in der ein Ordinalvergleich ohne Beachtung der Groß-/Kleinschreibung ausgeführt wird, wenn Sie den Wert <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType> für das <xref:System.StringComparison>-Argument angeben. Diese Methoden werden im folgenden Codebeispiel verwendet:

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs" id="Snippet2":::

Wenn Sie einen Ordinalvergleich ohne Beachtung der Groß-/Kleinschreibung ausführen, verwenden Sie die Schreibungskonventionen der [invarianten Kultur](xref:System.Globalization.CultureInfo.InvariantCulture).

## <a name="linguistic-comparisons"></a>Linguistische Vergleiche

Zeichenfolgen können auch mit linguistischen Regeln für die aktuelle Kultur sortiert werden.
Dies wird manchmal als „Wortsortierreihenfolge“ bezeichnet. Beim Ausführen eines linguistischen Vergleichs werden möglicherweise einigen nicht alphanumerischen Unicode-Zeichen bestimmte Gewichtungen zugewiesen. Beispielsweise wird dem Bindestrich („-“) ggf. eine sehr geringe Gewichtung zugeordnet, sodass „coop“ und „co-op“ in einer Sortierreihenfolge nebeneinander angezeigt werden. Darüber hinaus können einige Unicode-Zeichen einer Sequenz von <xref:System.Char>-Instanzen entsprechen. Im folgenden Beispiel werden die Sätze „Sie tanzen auf der Straße.“ und „Sie tanzen auf der Strasse.“ verwendet, in Deutsch mit „ss“ (U+0073 U+0073) in einer Zeichenfolge und „ß“ (U+00DF) in einer anderen. Unter Windows entspricht in den Kulturen „en-US“ und „de-DE“ die Zeichenfolge „ss“ linguistisch dem scharfen S/Eszett („ß“).

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs" id="Snippet3":::

Im folgenden Beispiel wird veranschaulicht, dass linguistische Vergleiche betriebssystemabhängig sind. Der Host für das interaktive Fenster wird unter Linux ausgeführt. Der linguistische Vergleich und der Ordinalvergleich führen zu identischen Ergebnissen. Wenn Sie dasselbe Beispiel auf einem Windows-Host ausführen, wird Folgendes ausgegeben:

```console
<coop> is less than <co-op> using invariant culture
<coop> is greater than <co-op> using ordinal comparison
<coop> is less than <cop> using invariant culture
<coop> is less than <cop> using ordinal comparison
<co-op> is less than <cop> using invariant culture
<co-op> is less than <cop> using ordinal comparison
```

Unter Windows ändert sich die Sortierreihenfolge von „cop“, „coop“ und „co-op“, wenn Sie anstelle eines Ordinalvergleichs einen linguistischen Vergleich verwenden. Die unterschiedlichen Vergleichsarten führen auch bei den beiden deutschen Beispielsätzen zu unterschiedlichen Ergebnissen.

## <a name="comparisons-using-specific-cultures"></a>Vergleiche unter Berücksichtigung bestimmter Kulturen

In diesem Beispiel werden <xref:System.Globalization.CultureInfo>-Objekte für die Kulturen „en-US“ und „de-DE“ gespeichert.
Damit tatsächlich ein kulturabhängiger Vergleich verwendet wird, werden die Vergleiche mit einem <xref:System.Globalization.CultureInfo>-Objekt ausgeführt.

Die verwendete Kultur wirkt sich auf linguistische Vergleiche aus. Im folgenden Beispiel werden die beiden deutsche Sätze unter Berücksichtigung der Kulturen „en-US“ und „de-DE“ verglichen und die Ergebnisse angezeigt:

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs" id="Snippet4":::

Mit kulturabhängigen Vergleichen werden üblicherweise Zeichenfolgeneingaben unterschiedlicher Benutzer verglichen und sortiert. Die Zeichen und Sortierungskonventionen dieser Zeichenfolgen können allerdings je nach Gebietsschema des Benutzercomputers variieren. Sogar Zeichenfolgen, die identische Zeichen enthalten, sortieren je nach Kultur des aktuellen Threads möglicherweise unterschiedlich. Wenn der folgende Beispielcode lokal auf einem Windows-Computer ausgeführt wird, werden die folgenden Ergebnisse angezeigt:

```console
<coop> is less than <co-op> using en-US culture
<coop> is greater than <co-op> using ordinal comparison
<coop> is less than <cop> using en-US culture
<coop> is less than <cop> using ordinal comparison
<co-op> is less than <cop> using en-US culture
<co-op> is less than <cop> using ordinal comparison
```

Linguistische Vergleiche sind sowohl von der aktuellen Kultur als auch vom Betriebssystem abhängig. Dies muss bei Zeichenfolgenvergleichen berücksichtigt werden.

## <a name="linguistic-sorting-and-searching-strings-in-arrays"></a>Linguistisches Sortieren und Suchen nach Zeichenfolgen in Arrays

In den folgenden Beispielen wird gezeigt, wie Sie mit einem linguistischen Vergleich, der abhängig von der aktuellen Kultur ist, Zeichenfolgen in einem Array sortieren und nach diesen suchen. Dabei werden die statischen <xref:System.Array>-Methoden verwendet, die einen <xref:System.StringComparer?displayProperty=nameWithType>-Parameter akzeptieren.

Im nächsten Beispiel wird demonstriert, wie Sie Zeichenfolgen in einem Array unter Berücksichtigung der aktuellen Kultur sortieren können:

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs" id="Snippet5":::

Nach der Sortierung des Arrays können Sie mit einer Binärsuche nach Einträgen suchen. Bei einer Binärsuche wird als Startposition die Mitte der Collection gewählt, um zu bestimmen, welche Hälfte der Collection die gesuchte Zeichenfolge enthält. Jeder nachfolgende Vergleich unterteilt den verbleibenden Teil der Collection in zwei weitere Teile.  Das Array wird mit der <xref:System.StringComparer.CurrentCulture?displayProperty=nameWithType>-Eigenschaft sortiert. Die lokale Funktion `ShowWhere` gibt Informationen zur Position aus, an der die Zeichenfolge gefunden wurde. Wenn die Zeichenfolge nicht gefunden wurde, gibt der Rückgabewert an, an welcher Stelle sich die Zeichenfolge befände, wenn diese vorhanden wäre.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs" id="Snippet6":::

## <a name="ordinal-sorting-and-searching-in-collections"></a>Ordinales Sortieren und Suchen in Collections

Im folgenden Codebeispiel wird die <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>-Collectionklasse zum Speichern von Zeichenfolgen verwendet. Die Zeichenfolgen werden mit der <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType>-Methode sortiert. Diese Methode benötigt einen Delegaten, der zwei Zeichenfolgen vergleicht und sortiert. Die <xref:System.String.CompareTo%2A?displayProperty=nameWithType>-Methode stellt diese Vergleichsfunktion bereit. Führen Sie das Beispiel aus, und beachten Sie die Reihenfolge. Bei diesem Sortiervorgang werden Zeichenfolgen ordinal unter Berücksichtigung der Groß-/Kleinschreibung sortiert. Mit den statischen <xref:System.String.Compare%2A?displayProperty=nameWithType>-Methoden können Sie unterschiedliche Vergleichsregeln angeben.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs" id="Snippet7":::

Nach der Sortierung kann die Liste der Zeichenfolgen mit einer Binärsuche durchsucht werden. Im folgenden Beispiel wird gezeigt, wie Sie die sortierte Liste mit derselben Vergleichsfunktion durchsuchen. Die lokale Funktion `ShowWhere` zeigt an, wo sich der gesuchte Text befindet oder befände, wenn er vorhanden wäre:

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs" id="Snippet8":::

Achten Sie darauf, zum Sortieren und Suchen von Zeichenfolgen immer dieselbe Vergleichsart zu verwenden. Andernfalls werden unerwartete Ergebnisse angezeigt.

Auflistungsklassen wie <xref:System.Collections.Hashtable?displayProperty=nameWithType>, <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> und <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> verfügen über Konstruktoren, die einen <xref:System.StringComparer?displayProperty=nameWithType>-Parameter übernehmen, wenn der Typ des Elements oder der Schlüssel `string` ist. Im Allgemeinen sollten Sie nach Möglichkeit diese Konstruktoren verwenden und entweder <xref:System.StringComparer.Ordinal?displayProperty=nameWithType> oder <xref:System.StringComparer.OrdinalIgnoreCase?displayProperty=nameWithType> angeben.

## <a name="reference-equality-and-string-interning"></a>Verweisgleichheit und Internalisieren von Zeichenfolgen

Bisher wurde für kein Beispiel <xref:System.Object.ReferenceEquals%2A> verwendet. Diese Methode erkennt, ob zwei Zeichenfolgen demselben Objekt entsprechen. Dies kann zu inkonsistenten Ergebnissen in Zeichenfolgenvergleichen führen. Im folgenden Beispiel wird das C#-Feature *Zeichenfolgeninternalisierung* demonstriert. Wenn ein Programm zwei oder mehr identische Zeichenfolgenvariablen deklariert, speichert der Compiler alle am selben Speicherort. Durch Aufrufen der <xref:System.Object.ReferenceEquals%2A>-Methode können Sie sehen, dass die beiden Zeichenfolgen tatsächlich auf das gleiche Objekt im Arbeitsspeicher verweisen. Mit der <xref:System.String.Copy%2A?displayProperty=nameWithType>-Methode können Sie eine Internalisierung verhindern. Nach der Erstellung der Kopie verfügen beide Zeichenfolgen über unterschiedliche Speicherorte, obwohl sie denselben Wert besitzen. Wenn Sie das folgende Beispiel ausführen, werden die Zeichenfolgen `a` und `b`*internalisiert* – für beide wird also derselbe Speicherort verwendet. Für die Zeichenfolgen `a` und `c` ist dies hingegen nicht der Fall.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs" id="Snippet9":::

> [!NOTE]
> Wenn Sie Zeichenfolgen auf Gleichheit überprüfen, sollten Sie Methoden verwenden, die explizit angeben, welche Art von Vergleich Sie durchführen möchten. Dadurch kann Ihr Code viel besser verwaltet und gelesen werden. Verwenden Sie dabei die überladenen Methoden der Klassen <xref:System.String?displayProperty=nameWithType> und <xref:System.Array?displayProperty=nameWithType>, die einen <xref:System.StringComparison>-Enumerationsparameter akzeptieren. Dadurch geben Sie die Art des Vergleichs an, der ausgeführt werden soll. Vermeiden Sie die Verwendung der Operatoren `==` und `!=`, wenn Sie Zeichenfolgen auf Gleichheit überprüfen. Die <xref:System.String.CompareTo%2A?displayProperty=nameWithType>-Instanzmethoden führen immer einen Ordinalvergleich unter Berücksichtigung der Groß-/Kleinschreibung durch. Sie eignen sich in erster Linie für die Sortierung von Zeichenfolgen in alphabetischer Reihenfolge.

Sie können eine Zeichenfolge in den Internpool schreiben oder auf eine im Internpool vorhandene Zeichenfolge verweisen, indem Sie die <xref:System.String.Intern%2A?displayProperty=nameWithType>-Methode aufrufen. Um zu bestimmen, ob eine Zeichenfolge im Internpool vorhanden ist, rufen Sie die <xref:System.String.IsInterned%2A?displayProperty=nameWithType>-Methode auf.

## <a name="see-also"></a>Siehe auch

- <xref:System.Globalization.CultureInfo?displayProperty=nameWithType>
- <xref:System.StringComparer?displayProperty=nameWithType>
- [Zeichenfolgen](../programming-guide/strings/index.md)
- [Vergleichen von Zeichenfolgen](../../standard/base-types/comparing.md)
- [Globalisieren und Lokalisieren von Anwendungen](/visualstudio/ide/globalizing-and-localizing-applications)
