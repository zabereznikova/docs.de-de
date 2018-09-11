---
title: 'Vorgehensweise: Vergleichen von Zeichenfolgen – C#-Leitfaden'
description: Lernen Sie, Zeichenfolgenwerte unter oder ohne Berücksichtigung der Groß-/Kleinschreibung und der Kultur zu vergleichen und zu sortieren.
ms.date: 03/20/2018
helpviewer_keywords:
- strings [C#], comparison
- comparing strings [C#]
ms.openlocfilehash: 3c841a1152613ec877bb6172dc8d053bf060b33b
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43484101"
---
# <a name="how-to-compare-strings-in-c"></a>Vergleichen von Zeichenfolgen in C\#

Durch den Vergleich zweier Zeichenfolgen können Sie entweder feststellen, ob diese gleich sind oder in welche Reihenfolge sie beim Sortieren gebracht werden sollen.

Beide Vorgänge werden durch folgende Faktoren erschwert:

- Sie können einen Ordinalvergleich oder einen linguistischen Vergleich durchführen.
- Sie können festlegen, ob die Groß/-Kleinschreibung berücksichtigt werden soll.
- Sie können kulturspezifische Vergleiche durchführen.
- Linguistische Vergleiche sind kultur- und plattformabhängig.

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

Wenn Sie Zeichenfolgen vergleichen, definieren Sie für diese eine Reihenfolge. Bei einigen Vergleichen wird eine Zeichenfolgensequenz sortiert. Sobald sich die Sequenz in einer bestimmten Reihenfolge befindet, können Menschen und Softwareanwendungen leichter darin suchen. Bei anderen Vergleichen kann überprüft werden, ob Zeichenfolgen identisch sind. Identitätsprüfungen sind mit Gleichheitsprüfungen zu vergleichen, doch einige Unterschiede wie die Groß-/Kleinschreibung werden möglicherweise ignoriert.

## <a name="default-ordinal-comparisons"></a>Standardordinalvergleich

Für die am häufigsten verwendeten Methoden <xref:System.String.CompareTo%2A?displayProperty=nameWithType>, <xref:System.String.Equals%2A?displayProperty=nameWithType> und <xref:System.String.op_Equality%2A?displayProperty=nameWithType> wird ein Ordinalvergleich, ein Vergleich unter Berücksichtigung der Groß/-Kleinschreibung und die aktuelle Kultur verwendet. Die Ergebnisse der jeweiligen Methoden sind im folgenden Beispiel dargestellt:

[!code-csharp-interactive[Comparing strings using an ordinal comparison](../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs#1)]

Bei Ordinalvergleichen werden linguistische Regeln nicht berücksichtigt. Stattdessen wird jedes Zeichen der Zeichenfolge verglichen. Bei anderen Vergleichen wird zwischen der Groß/-Kleinschreibung unterschieden. Da diese Standardmethoden die aktuelle Kultur verwenden, sind die Ergebnisse vom Gebietsschema und den Spracheinstellungen des Computers abhängig, auf dem die Methoden ausgeführt werden. Wenn die Reihenfolge von Zeichenfolgen auf unterschiedlichen Computern oder an unterschiedlichen Orten gleich sein soll, sind diese Vergleiche ungeeignet.

## <a name="case-insensitive-ordinal-comparisons"></a>Ordinalvergleich ohne Beachtung der Groß- und Kleinschreibung

Mit der <xref:System.String.Equals%2A?displayProperty=nameWithType>-Methode können Sie einen <xref:System.StringComparison>-Wert von <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType> angeben,
um einen Vergleich ohne Beachtung der Groß-/Kleinschreibung durchzuführen. Alternativ können Sie die statische Methode <xref:System.String.Compare%2A> verwenden, die denselben Zweck erfüllt und ein boolesches Argument erfordert. Diese Methoden werden im folgenden Codebeispiel verwendet:

[!code-csharp-interactive[Comparing strings ignoring case](../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs#2)]

## <a name="linguistic-comparisons"></a>Linguistische Vergleiche

Zeichenfolgen können auch mit linguistischen Regeln für die aktuelle Kultur sortiert werden.
Dies wird manchmal als „Wortsortierreihenfolge“ bezeichnet. Beim Ausführen eines linguistischen Vergleichs werden möglicherweise einigen nicht alphanumerischen Unicode-Zeichen eine bestimmte Gewichtung zugeordnet. Beispielsweise wird dem Bindestrich („-“) ggf. eine sehr geringe Gewichtung zugeordnet, sodass „coop“ und „co-op“ in einer Sortierreihenfolge nebeneinander angezeigt werden. Darüber hinaus können einige Unicode-Zeichen einer Sequenz alphanumerischer Zeichen entsprechen. Im folgenden Beispiel werden die Sätze „Sie tanzen auf der Straße.“ und „Sie tanzen auf der Strasse.“ verwendet, wobei „Straße“ einmal mit „ss“ und einmal mit „ß“ geschrieben wird. Unter Windows entspricht in den Kulturen „en-US“ und „de-DE“ die Zeichenfolge „ss“ dem scharfen S („ß“).

[!code-csharp-interactive[Comparing strings using linguistic rules](../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs#3)]

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

Im folgenden Beispiel wird <xref:System.Globalization.CultureInfo> für die aktuelle Kultur gespeichert.
Die ursprüngliche Kultur kann für das Objekt des aktuellen Threads festgelegt und abgerufen werden. Damit tatsächlich ein kulturabhängiger Vergleich verwendet wird, werden die Vergleiche mit dem <xref:System.StringComparison.CurrentCulture>-Wert ausgeführt.

Die verwendete Kultur wirkt sich auf linguistische Vergleiche aus. Im folgenden Beispiel werden die beiden deutsche Sätze unter Berücksichtigung der Kulturen „en-US“ und „de-DE“ verglichen und die Ergebnisse angezeigt:

[!code-csharp-interactive[Comparing strings across cultures](../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs#4)]

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

[!code-csharp-interactive[Sorting an array of strings](../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs#5)]

Nach der Sortierung des Arrays können Sie mit einer Binärsuche nach Einträgen suchen. Bei einer Binärsuche wird als Startposition die Mitte der Collection gewählt, um zu bestimmen, welche Hälfte der Collection die gesuchte Zeichenfolge enthält. Jeder nachfolgende Vergleich unterteilt den verbleibenden Teil der Collection in zwei weitere Teile.  Das Array wird mithilfe von <xref:System.StringComparer.CurrentCulture?displayProperty=nameWithType> sortiert. Die lokale Funktion `ShowWhere` gibt Informationen zur Position aus, an der die Zeichenfolge gefunden wurde. Wenn die Zeichenfolge nicht gefunden wurde, gibt der Rückgabewert an, an welcher Stelle sich die Zeichenfolge befände, wenn diese vorhanden wäre.

[!code-csharp-interactive[Searching in a sorted array](../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs#6)]

## <a name="ordinal-sorting-and-searching-in-collections"></a>Ordinales Sortieren und Suchen in Collections

Im folgenden Codebeispiel wird die <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>-Collectionklasse zum Speichern von Zeichenfolgen verwendet. Die Zeichenfolgen werden mit der <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType>-Methode sortiert. Diese Methode benötigt einen Delegaten, der zwei Zeichenfolgen vergleicht und sortiert. Die <xref:System.String.CompareTo%2A?displayProperty=nameWithType>-Methode stellt diese Vergleichsfunktion bereit. Führen Sie das Beispiel aus, und beachten Sie die Reihenfolge. Bei diesem Sortiervorgang werden Zeichenfolgen ordinal unter Berücksichtigung der Groß-/Kleinschreibung sortiert. Mit den statischen <xref:System.String.Compare%2A?displayProperty=nameWithType>-Methoden können Sie unterschiedliche Vergleichsregeln angeben.

[!code-csharp-interactive[Sorting a list of strings](../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs#7)]

Nach der Sortierung kann die Liste der Zeichenfolgen mit einer Binärsuche durchsucht werden. Im folgenden Beispiel wird gezeigt, wie Sie die sortierte Liste mit derselben Vergleichsfunktion durchsuchen. Die lokale Funktion `ShowWhere` zeigt an, wo sich der gesuchte Text befindet oder befände, wenn er vorhanden wäre:

[!code-csharp-interactive[csProgGuideStrings#11](../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs#8)]

Achten Sie darauf, zum Sortieren und Suchen von Zeichenfolgen immer dieselbe Vergleichsart zu verwenden. Andernfalls werden unerwartete Ergebnisse angezeigt.

Auflistungsklassen wie <xref:System.Collections.Hashtable?displayProperty=nameWithType>, <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> und <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> verfügen über Konstruktoren, die einen <xref:System.StringComparer?displayProperty=nameWithType>-Parameter übernehmen, wenn der Typ des Elements oder der Schlüssel `string` ist. Im Allgemeinen sollten Sie nach Möglichkeit diese Konstruktoren verwenden und entweder <xref:System.StringComparer.Ordinal?displayProperty=nameWithType> oder <xref:System.StringComparer.OrdinalIgnoreCase?displayProperty=nameWithType> angeben.

## <a name="reference-equality-and-string-interning"></a>Verweisgleichheit und Internalisieren von Zeichenfolgen

Bisher wurde für kein Beispiel <xref:System.Object.ReferenceEquals%2A> verwendet. Diese Methode erkennt, ob zwei Zeichenfolgen demselben Objekt entsprechen. Dies kann zu inkonsistenten Ergebnissen in Zeichenfolgenvergleichen führen. Im folgenden Beispiel wird das C#-Feature *Zeichenfolgeninternalisierung* demonstriert. Wenn ein Programm zwei oder mehr identische Zeichenfolgenvariablen deklariert, speichert der Compiler alle am selben Speicherort. Durch Aufrufen der <xref:System.Object.ReferenceEquals%2A>-Methode können Sie sehen, dass die beiden Zeichenfolgen tatsächlich auf das gleiche Objekt im Arbeitsspeicher verweisen. Mit der <xref:System.String.Copy%2A?displayProperty=nameWithType>-Methode können Sie eine Internalisierung verhindern. Nach der Erstellung der Kopie verfügen beide Zeichenfolgen über unterschiedliche Speicherorte, obwohl sie denselben Wert besitzen. Wenn Sie das folgende Beispiel ausführen, werden die Zeichenfolgen `a` und `b` *internalisiert* – für beide wird also derselbe Speicherort verwendet. Für die Zeichenfolgen `a` und `c` ist dies hingegen nicht der Fall.

[!code-csharp-interactive[Demonstrating string interning](../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs#9)]

> [!NOTE]
> Wenn Sie Zeichenfolgen auf Gleichheit überprüfen, sollten Sie Methoden verwenden, die explizit angeben, welche Art von Vergleich Sie durchführen möchten. Dadurch kann Ihr Code viel besser verwaltet und gelesen werden. Verwenden Sie dabei die überladenen Methoden der Klassen <xref:System.String?displayProperty=nameWithType> und <xref:System.Array?displayProperty=nameWithType>, die einen <xref:System.StringComparison>-Enumerationsparameter akzeptieren. Dadurch geben Sie die Art des Vergleichs an, der ausgeführt werden soll. Vermeiden Sie die Verwendung der Operatoren `==` und `!=`, wenn Sie Zeichenfolgen auf Gleichheit überprüfen. Die <xref:System.String.CompareTo%2A?displayProperty=nameWithType>-Instanzmethoden führen immer einen Ordinalvergleich unter Berücksichtigung der Groß-/Kleinschreibung durch. Sie eignen sich in erster Linie für die Sortierung von Zeichenfolgen in alphabetischer Reihenfolge.

## <a name="see-also"></a>Siehe auch

- <xref:System.Globalization.CultureInfo?displayProperty=nameWithType>  
- <xref:System.StringComparer?displayProperty=nameWithType>  
- [Zeichenfolgen](../programming-guide/strings/index.md)  
- [Vergleichen von Zeichenfolgen](../../standard/base-types/comparing.md)  
- [Globalisieren und Lokalisieren von Anwendungen](/visualstudio/ide/globalizing-and-localizing-applications)
