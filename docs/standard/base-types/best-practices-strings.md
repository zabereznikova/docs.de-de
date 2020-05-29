---
title: Empfohlene Vorgehensweisen für die Verwendung von Zeichenfolgen in .NET
description: Erfahren Sie, wie Sie Zeichenfolgen effektiv in .NET-Anwendungen verwenden können.
ms.date: 05/01/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [.NET Framework],searching
- best practices,string comparison and sorting
- strings [.NET Framework],best practices
- strings [.NET Framework],basic string operations
- sorting strings
- strings [.NET Framework],sorting
- string comparison [.NET Framework],best practices
- string sorting
- comparing strings
- strings [.NET Framework],comparing
ms.assetid: b9f0bf53-e2de-4116-8ce9-d4f91a1df4f7
ms.openlocfilehash: 0fb7ec8d9de8fae7a0443984511e538d38d93c7a
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441005"
---
# <a name="best-practices-for-using-strings-in-net"></a>Empfohlene Vorgehensweisen für die Verwendung von Zeichenfolgen in .NET

.NET bietet umfangreiche Unterstützung für das Entwickeln von lokalisierten und globalisierten Anwendungen und erleichtert bei der Ausführung allgemeiner Operationen das Übernehmen von Konventionen der aktuellen oder einer anderen Kultur, beispielsweise bei der Sortierung und Anzeige von Zeichenfolgen. Das Sortieren oder Vergleichen von Zeichenfolgen stellt jedoch nicht immer eine kulturabhängige Operation dar. Beispielsweise sollten interne Zeichenfolgen von Anwendungen i. d. R. in allen Kulturen gleich behandelt werden. Wenn kulturabhängige Zeichenfolgendaten, z. B. XML-Tags, HTML-Tags, Benutzernamen, Dateipfade und Systemobjektnamen, kulturabhängig interpretiert werden, können Fehler im Anwendungscode auftreten, die Leistung kann sich verschlechtern, und in einigen Fällen kann es zu Sicherheitsproblemen kommen.

In diesem Thema werden die Methoden für die Sortierung, den Vergleich und die Schreibweise von Zeichenfolgen in .NET untersucht. Darüber hinaus werden Empfehlungen zum Auswählen einer entsprechenden Zeichenfolgen-Verarbeitungsmethode gegeben und weitere Informationen dazu bereitgestellt. Er wird außerdem untersucht, wie formatierte Daten, z. B. numerische Daten und Datums-/Uhrzeitdaten, für die Anzeige und Speicherung behandelt werden.

## <a name="recommendations-for-string-usage"></a>Empfehlungen zur Zeichenfolgenverwendung

Beachten Sie folgende grundlegende Empfehlungen zur Verwendung von Zeichenfolgen bei der Entwicklung mit .NET:

- Verwenden Sie Überladungen, die die Regeln für Zeichenfolgenvergleiche in Zeichenfolgenoperationen explizit angeben. Normalerweise müssen Sie dazu eine Methodenüberladung mit einem Parameter vom Typ <xref:System.StringComparison>aufrufen.
- Verwenden Sie <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> oder <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType> als sichere Standardeinstellung für kulturunabhängige Zeichenfolgenvergleiche.
- Verwenden Sie Vergleiche mit <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> oder <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType> für eine bessere Leistung.
- Verwenden Sie Zeichenfolgenoperationen, die auf <xref:System.StringComparison.CurrentCulture?displayProperty=nameWithType> basieren, um die Ausgabe für Benutzer anzuzeigen.
- Verwenden Sie den nicht linguistischen <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> -Wert oder den nicht linguistischen <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType> -Wert anstelle von Zeichenfolgenoperationen, die auf <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> basieren, wenn der Vergleich linguistisch nicht relevant (z. B. symbolisch) ist.
- Verwenden Sie die <xref:System.String.ToUpperInvariant%2A?displayProperty=nameWithType> -Methode anstelle der <xref:System.String.ToLowerInvariant%2A?displayProperty=nameWithType> -Methode, wenn Sie Zeichenfolgen für einen Vergleich normalisieren.
- Verwenden Sie eine Überladung der <xref:System.String.Equals%2A?displayProperty=nameWithType> -Methode, um zu überprüfen, ob zwei Zeichenfolgen übereinstimmen.
- Verwenden Sie die <xref:System.String.Compare%2A?displayProperty=nameWithType> - und <xref:System.String.CompareTo%2A?displayProperty=nameWithType> -Methoden zum Sortieren von Zeichenfolgen, und nicht, um eine Überprüfung auf Gleichheit durchzuführen.
- Verwenden Sie kulturabhängige Formatierung, um Daten, die keine Zeichenfolge sind, z. B. Zahlen und Datumsangaben, auf einer Benutzeroberfläche anzuzeigen. Verwenden Sie Formatierung mit der [invarianten Kultur](xref:System.Globalization.CultureInfo.InvariantCulture), um für Daten, die keine Zeichenfolge sind, das Zeichenfolgenformat beizubehalten.

Vermeiden Sie folgende Vorgehensweisen bei der Verwendung von Zeichenfolgen:

- Verwenden Sie keine Überladungen, die die Regeln für Zeichenfolgenvergleiche in Zeichenfolgenoperationen nicht explizit oder implizit angeben.
- Verwenden Sie keine Zeichenfolgenoperationen, die auf <xref:System.StringComparison.InvariantCulture?displayProperty=nameWithType> basieren. Eine der wenigen Ausnahmen stellt dabei die Beibehaltung von Zeichenfolgen dar, die zwar linguistisch relevant, jedoch kulturunabhängig sind.
- Verwenden Sie keine Überladung der <xref:System.String.Compare%2A?displayProperty=nameWithType> -Methode oder der <xref:System.String.CompareTo%2A> -Methode, und führen Sie eine Überprüfung mit einem Rückgabewert von 0 (null) durch, um zu bestimmten, ob zwei Zeichenfolgen übereinstimmen.
- Verwenden Sie nicht kulturabhängige Formatierung, um numerische Daten oder Datums-/Uhrzeitdaten im Zeichenfolgenformat beizubehalten.

## <a name="specifying-string-comparisons-explicitly"></a>Explizites Angeben von Zeichenfolgenvergleichen

Die Methoden zum Bearbeiten von Zeichenfolgen in .NET werden i.d.R. überladen. Während einige Überladungen normalerweise Standardwerte akzeptieren, geben andere Überladungen exakt an, wie Zeichenfolgen verglichen oder bearbeitet werden sollen. Methoden, die keine Standardwerte verwenden, enthalten i. d. R einen Parameter vom Typ <xref:System.StringComparison>. Dabei handelt es sich um eine Enumeration, die explizit Regeln für Zeichenfolgenvergleiche anhand von Kultur und Schreibweise angibt. In der folgenden Tabelle werden die Member der <xref:System.StringComparison> -Enumeration beschrieben.

|StringComparison-Member|Beschreibung|
|-----------------------------|-----------------|
|<xref:System.StringComparison.CurrentCulture>|Führt einen Vergleich mit der aktuellen Kultur unter Beachtung der Groß- und Kleinschreibung durch.|
|<xref:System.StringComparison.CurrentCultureIgnoreCase>|Führt einen Vergleich mit der aktuellen Kultur ohne Beachtung der Groß- und Kleinschreibung durch.|
|<xref:System.StringComparison.InvariantCulture>|Führt einen Vergleich mit der invarianten Kultur unter Beachtung der Groß- und Kleinschreibung durch.|
|<xref:System.StringComparison.InvariantCultureIgnoreCase>|Führt einen Vergleich mit der invarianten Kultur ohne Beachtung der Groß- und Kleinschreibung durch.|
|<xref:System.StringComparison.Ordinal>|Führt einen Ordinalvergleich durch.|
|<xref:System.StringComparison.OrdinalIgnoreCase>|Führt einen Ordinalvergleich ohne Beachtung der Groß- und Kleinschreibung durch.|

Die <xref:System.String.IndexOf%2A> -Methode, die den Index einer Teilzeichenfolge in einem <xref:System.String> -Objekt zurückgibt, das einem Zeichen oder einer Zeichenfolge entspricht, weist beispielsweise neun Überladungen auf:

- <xref:System.String.IndexOf%28System.Char%29>, <xref:System.String.IndexOf%28System.Char%2CSystem.Int32%29>und <xref:System.String.IndexOf%28System.Char%2CSystem.Int32%2CSystem.Int32%29>führen standardmäßig eine kulturunabhängige Ordinalsuche nach einem Zeichen in der Zeichenfolge unter Beachtung der Groß- und Kleinschreibung durch.
- <xref:System.String.IndexOf%28System.String%29>, <xref:System.String.IndexOf%28System.String%2CSystem.Int32%29>und <xref:System.String.IndexOf%28System.String%2CSystem.Int32%2CSystem.Int32%29>führen standardmäßig eine kulturabhängige Suche nach einer Teilzeichenfolge in der Zeichenfolge unter Beachtung der Groß- und Kleinschreibung durch.
- <xref:System.String.IndexOf%28System.String%2CSystem.StringComparison%29>, <xref:System.String.IndexOf%28System.String%2CSystem.Int32%2CSystem.StringComparison%29>und <xref:System.String.IndexOf%28System.String%2CSystem.Int32%2CSystem.Int32%2CSystem.StringComparison%29>enthalten einen Parameter vom Typ <xref:System.StringComparison> , mit dem das Format des Vergleichs angegeben werden kann.

Aus den folgenden Gründen wird empfohlen, eine Überladung ohne Standardwerte auszuwählen:

- Einige Überladungen mit Standardparametern (die in der Zeichenfolgeninstanz nach einem <xref:System.Char> suchen) führen einen Ordinalvergleich durch, während andere Überladungen (die in der Zeichenfolgeninstanz nach einer Zeichenfolge suchen) kulturabhängig sind. Es ist nicht leicht, sich zu merken, welche Methode welchen Standardwert verwendet, und Überladungen können schnell verwechselt werden.
- Der Zweck des Codes, der Standardwerte für Methodenaufrufe verwendet, ist nicht klar. Im folgenden Beispiel, das auf Standardwerten beruht, ist nur schwer erkennbar, ob der Entwickler tatsächlich einen Ordinalvergleich oder einen linguistischen Vergleich von zwei Zeichenfolgen durchführen wollte oder ob ein Unterschied in der Groß-/Kleinschreibung zwischen `protocol` und „HTTP“ möglicherweise dazu führt, dass bei einer Prüfung auf Gleichheit `false`aufrufen.

     [!code-csharp[Conceptual.Strings.BestPractices#1](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/explicitargs1.cs#1)]
     [!code-vb[Conceptual.Strings.BestPractices#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/explicitargs1.vb#1)]

Im Allgemeinen empfiehlt es sich, eine Methode aufzurufen, die keine Standardwerte verwendet, da der Zweck des Codes andernfalls möglicherweise nicht eindeutig ist. Dies erleichtert wiederum das Lesen, Verwalten und Debuggen des Codes. Im folgenden Beispiel wird auf die Fragen eingegangen, die sich zum vorherigen Beispiel stellen. Es wird deutlich gemacht, dass der Ordinalvergleich verwendet wird und dass Unterschiede in der Groß- und Kleinschreibung ignoriert werden.

[!code-csharp[Conceptual.Strings.BestPractices#2](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/explicitargs1.cs#2)]
[!code-vb[Conceptual.Strings.BestPractices#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/explicitargs1.vb#2)]

## <a name="the-details-of-string-comparison"></a>Details zum Zeichenfolgenvergleich

Zeichenfolgenvergleiche bilden den Kern zahlreicher Operationen, die sich auf Zeichenfolgen beziehen; dies gilt insbesondere für Sortierungen und Überprüfungen auf Gleichheit. Zeichenfolgen werden in einer bestimmten Reihenfolge sortiert: Wenn „my“ in einer sortierten Zeichenfolgenliste vor „string“ angezeigt wird, muss „my“ bei einem Vergleich einen kleineren oder gleichen Wert wie „string“ haben. Darüber hinaus wird beim Vergleich implizit Gleichheit definiert. Die Vergleichsoperation gibt 0 (null) für Zeichenfolgen zurück, die als gleich betrachtet werden. Dies kann so interpretiert werden, dass keine Zeichenfolge kleiner ist als die andere. Sinnvolle Operationen mit Zeichenfolgen schließen i. d. R. mindestens eines der folgenden Verfahren ein: Vergleich mit einer anderen Zeichenfolge und Ausführen eines genau definierten Sortiervorgangs.

> [!NOTE]
> Sie können die aus mehreren Textdateien bestehenden [Sorting Weight Tables](https://www.microsoft.com/download/details.aspx?id=10921) herunterladen. Diese Textdateien enthalten Informationen zur Gewichtung der Zeichen, die bei Sortier- und Vergleichsvorgängen unter Windows-Betriebssystemen verwendet werden, sowie die [Default Unicode Collation Element Table](https://www.unicode.org/Public/UCA/latest/allkeys.txt), die neueste Version der Sortiergewichtungstabelle für Linux und macOS. Die spezifische Version der Sortiergewichtungstabelle unter Linux und macOS hängt von der auf dem System installierten Version der [International Components for Unicode](http://site.icu-project.org/) ab. Informationen zu ICU-Versionen und den Unicode-Versionen, die durch sie implementiert werden, finden Sie unter [Downloading ICU](http://site.icu-project.org/download).

Die Überprüfung der Sortierreihenfolge zweier Zeichenfolgen oder ihre Überprüfung auf Gleichheit ergibt jedoch nicht ein einzelnes richtiges Ergebnis. Das Ergebnis ist vielmehr abhängig von den Kriterien, die dem Zeichenfolgenvergleich zugrunde liegen. Insbesondere können Zeichenfolgenvergleiche, die Ordinalvergleiche darstellen oder auf der Schreibweise und den Sortierungskonventionen der aktuellen oder der [invarianten Kultur](xref:System.Globalization.CultureInfo.InvariantCulture) (eine auf der englischen Sprache basierende Kultur, die nicht von einem Gebietsschema abhängig ist) basieren, zu unterschiedlichen Ergebnissen führen.

Ferner können Zeichenfolgenvergleiche, die verschiedene .NET-Versionen nutzen oder .NET unter verschiedenen Betriebssystemen oder Betriebssystemversionen verwenden, unterschiedliche Ergebnisse zurückgeben. Weitere Informationen finden Sie unter [Zeichenfolgen und der Unicode-Standard](xref:System.String#Unicode).

### <a name="string-comparisons-that-use-the-current-culture"></a>Zeichenfolgenvergleiche mit der aktuellen Kultur

Ein Kriterium für Zeichenfolgenvergleiche stellt die Verwendung der Konventionen der aktuellen Kultur dar. Vergleiche, die auf der aktuellen Kultur basieren, verwenden die aktuelle Kultur oder das aktuelle Gebietsschema des Threads. Wenn die Kultur nicht vom Benutzer festgelegt wird, wird standardmäßig die Einstellung im Fenster **Ländereinstellungen** in der Systemsteuerung verwendet. Vergleiche, die auf der aktuellen Kultur basieren, sollten immer dann verwendet werden, wenn Daten linguistisch relevant sind und kulturabhängige Interaktionen von Benutzern widerspiegeln.

Das Verhalten im Hinblick auf Vergleiche und die Groß- und Kleinschreibung in .NET ändert sich jedoch, wenn sich die Kultur ändert. Dies ist der Fall, wenn eine Anwendung auf einem Computer mit einer anderen Kultur ausgeführt wird, als der Computer, auf dem die Anwendung entwickelt wurde, oder wenn der ausführende Thread seine Kultur ändert. Dieses Verhalten ist beabsichtigt, für viele Entwickler jedoch nicht offensichtlich. Im folgenden Beispiel werden die Unterschiede zwischen den Sortierreihenfolgen in der englischen (amerikanisch, "en-US") und schwedischen ("sv-SE") Kultur herausgestellt. Beachten Sie, dass die Wörter „ångström“, „Windows“ und „Visual Studio“ in den sortierten Zeichenfolgenarrays an unterschiedlichen Positionen angezeigt werden.

[!code-csharp[Conceptual.Strings.BestPractices#3](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/comparison1.cs#3)]
[!code-vb[Conceptual.Strings.BestPractices#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/comparison1.vb#3)]

Vergleiche mit der aktuellen Kultur, bei denen nicht zwischen Groß- und Kleinschreibung unterschieden wird, entsprechen kulturabhängigen Vergleichen, ignorieren jedoch die Schreibweise, die von der aktuellen Kultur des Threads vorgegeben wird. Dieses Verhalten zeigt sich möglicherweise auch bei Sortierreihenfolgen.

Vergleiche mit der Semantik der aktuellen Kultur werden standardmäßig für folgende Methoden verwendet:

- <xref:System.String.Compare%2A?displayProperty=nameWithType> -Überladungen, die keinen <xref:System.StringComparison> -Parameter enthalten.
- <xref:System.String.CompareTo%2A?displayProperty=nameWithType> -Überladungen.
- Die <xref:System.String.StartsWith%28System.String%29?displayProperty=nameWithType> -Standardmethode und die <xref:System.String.StartsWith%28System.String%2CSystem.Boolean%2CSystem.Globalization.CultureInfo%29?displayProperty=nameWithType> -Methode mit einem `null`<xref:System.Globalization.CultureInfo> -Parameter enthalten.
- Die <xref:System.String.EndsWith%28System.String%29?displayProperty=nameWithType>-Standardmethode und die <xref:System.String.EndsWith%28System.String%2CSystem.Boolean%2CSystem.Globalization.CultureInfo%29?displayProperty=nameWithType>-Methode mit einem `null`<xref:System.Globalization.CultureInfo>-Parameter
- <xref:System.String.IndexOf%2A?displayProperty=nameWithType> -Überladungen, die eine <xref:System.String> als Suchparameter akzeptieren und keinen <xref:System.StringComparison> -Parameter aufweisen.
- <xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> -Überladungen, die eine <xref:System.String> als Suchparameter akzeptieren und keinen <xref:System.StringComparison> -Parameter aufweisen.

In jedem Fall wird empfohlen, eine Überladung mit einem <xref:System.StringComparison> -Parameter aufzurufen, um den Zweck des Methodenaufrufs eindeutig anzugeben.

Wenn nicht linguistische Zeichenfolgendaten linguistisch interpretiert werden, oder wenn Zeichenfolgendaten in einer bestimmten Kultur mit den Konventionen einer anderen Kultur interpretiert werden, können offensichtliche und nur schwer erkennbare Fehler auftreten. Kanonisches Beispiel ist das Problem mit dem Zeichen "I" im Türkischen.

In beinahe allen lateinischen Alphabetarten,  einschließlich des englischen (USA) Alphabets, ist das Zeichen "i" (\u0069) die Kleinschreibungsvariante des Zeichens "I" (\u0049). Diese Regel zur Groß- und Kleinschreibung wird von Entwicklern, die in den entsprechenden Kulturen programmieren, leicht als Standard zugrunde gelegt. Das türkische Alphabet ("tr-TR") enthält jedoch ein "I" mit einem Punkt ("İ" bzw. \u0130), welches den Großbuchstaben des Zeichens "i" darstellt. Ferner verfügt Türkisch auch über ein kleines „i ohne Punkt“ („ı“ bzw. \u0131), dessen Entsprechung als Großbuchstabe das Zeichen „I“ ist. Die Kultur Aserbaidschanisch (az-AZ) weist ein analoges Verhalten auf.

Annahmen über die Großschreibung von "i" oder die Kleinschreibung von "I" sind daher nicht für alle Kulturen gleichermaßen gültig. Wenn Sie die Standardüberladungen für Zeichenfolgenvergleichsroutinen verwenden, weisen diese je nach der zugrunde liegenden Kultur Unterschiede auf. Bei einem Vergleich nicht linguistischer Daten kann die Verwendung der Standardüberladungen zu unerwünschten Ergebnissen führen. Dies wird durch den folgenden Versuch veranschaulicht, einen Vergleich der Zeichenfolgen "file" und "FILE" ohne Beachtung der Groß- und Kleinschreibung durchzuführen.

[!code-csharp[Conceptual.Strings.BestPractices#11](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/turkish1.cs#11)]
[!code-vb[Conceptual.Strings.BestPractices#11](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/turkish1.vb#11)]

Dieser Vergleich kann signifikante Probleme verursachen, wenn die Kultur versehentlich in sicherheitsrelevanten Einstellungen verwendet wird, wie im folgenden Beispiel veranschaulicht. Ein Methodenaufruf wie `IsFileURI("file:")` gibt `true` zurück, wenn die aktuelle Kultur "Englisch (USA)" ist und `false`, wenn die aktuelle Kultur "Türkisch" ist. In einem System mit der Kultur "Türkisch" wäre es daher vorstellbar, dass Sicherheitsvorkehrungen umgangen werden, die den Zugriff auf URIs blockieren, die mit "FILE:" beginnen und nicht zwischen Groß- und Kleinschreibung unterscheiden.

[!code-csharp[Conceptual.Strings.BestPractices#12](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/turkish1.cs#12)]
[!code-vb[Conceptual.Strings.BestPractices#12](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/turkish1.vb#12)]

Stattdessen sollte der Code daher in diesem Fall wie im folgenden Beispiel geschrieben werden, da „file:“ als nicht linguistischer und kulturunabhängiger Bezeichner interpretiert werden soll:

[!code-csharp[Conceptual.Strings.BestPractices#13](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/turkish1.cs#13)]
[!code-vb[Conceptual.Strings.BestPractices#13](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/turkish1.vb#13)]

### <a name="ordinal-string-operations"></a>Ordinalzeichenfolgenvorgänge

Der <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> -Wert oder der <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType> -Wert in einem Methodenaufruf kennzeichnen einen nicht linguistischen Vergleich, in dem die Funktionen von natürlichen Sprachen ignoriert werden. Bei Methoden, die mit diesen <xref:System.StringComparison> -Werten aufgerufen werden, werden für Entscheidungen bezüglich Zeichenfolgenoperation einfache Bytevergleiche anstelle von Groß- und Kleinschreibung oder nach Kultur parametrisierten Entsprechungstabellen zugrunde gelegt. In aller Regel ist diese Vorgehensweise am besten für die beabsichtigte Interpretation von Zeichenfolgen geeignet und macht den Code sicherer und zuverlässiger.

Ordinalvergleiche sind Zeichenfolgenvergleiche, in denen die einzelnen Bytes einer Zeichenfolge ohne linguistische Interpretation verglichen werden, z. B. entspricht "windows" nicht "Windows". Dies stellt im Grunde einen Aufruf der `strcmp` -Funktion dar. Verwenden Sie diesen Vergleich, wenn der Kontext eine exakte Entsprechung von Zeichenfolgen oder eine konservative Entsprechungsrichtlinie verlangt. Darüber hinaus werden Ordinalvergleiche am schnellsten durchgeführt, da beim Bestimmen eines Ergebnisses keine linguistischen Regeln verwendet werden.

Zeichenfolgen in .NET können eingebettete NULL-Zeichen aufweisen. Einer der auffälligsten Unterschiede zwischen einem ordinalen und einem kulturabhängigen Vergleich (einschließlich Vergleichen, die die invariante Kultur verwenden) betrifft die Behandlung von eingebetteten NULL-Zeichen in einer Zeichenfolge. Wenn Sie die <xref:System.String.Compare%2A?displayProperty=nameWithType> -Methode und die <xref:System.String.Equals%2A?displayProperty=nameWithType> -Methode verwenden, um kulturabhängige Vergleiche (einschließlich Vergleichen, die die invariante Kultur verwenden) durchzuführen, werden diese Zeichen ignoriert. Bei kulturabhängigen Vergleichen können Zeichenfolgen mit eingebetteten NULL-Zeichen daher als gleichwertig mit Zeichenfolgen ohne diese Zeichen angesehen werden.

> [!IMPORTANT]
> Auch wenn eingebettete NULL-Zeichen von Zeichenfolgenvergleichsmethoden ignoriert werden, ist dies bei Zeichenfolgensuchmethoden wie <xref:System.String.Contains%2A?displayProperty=nameWithType>, <xref:System.String.EndsWith%2A?displayProperty=nameWithType>, <xref:System.String.IndexOf%2A?displayProperty=nameWithType>, <xref:System.String.LastIndexOf%2A?displayProperty=nameWithType>und <xref:System.String.StartsWith%2A?displayProperty=nameWithType> nicht der Fall.

Im folgenden Beispiel wird ein kulturabhängiger Vergleich der Zeichenfolge „Aa“ mit einer ähnlichen Zeichenfolge durchgeführt, die mehrere eingebettete NULL-Zeichen zwischen „A“ und „a“ enthält, und es wird angezeigt, inwieweit die beiden Zeichenfolgen als gleich betrachtet werden:

[!code-csharp[Conceptual.Strings.BestPractices#19](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/embeddednulls1.cs#19)]
 [!code-vb[Conceptual.Strings.BestPractices#19](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/embeddednulls1.vb#19)]

Wie das folgende Beispiel zeigt, werden die Zeichenfolgen bei einem Ordinalvergleich jedoch nicht als gleich betrachtet:
  
[!code-csharp[Conceptual.Strings.BestPractices#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/embeddednulls2.cs#20)]
[!code-vb[Conceptual.Strings.BestPractices#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/embeddednulls2.vb#20)]

Ordinalvergleiche, bei denen die Groß- und Kleinschreibung nicht beachtet wird, folgen als nächster konservativer Ansatz. Diese Vergleichen ignorieren die Groß- und Kleinschreibung i. d. R.; "windows" entspricht dann beispielsweise "Windows". Im Hinblick auf ASCII-Zeichen entspricht diese Richtlinie <xref:System.StringComparison.Ordinal?displayProperty=nameWithType>, mit der Ausnahme, dass die üblichen ASCII-Schreibungsregeln nicht beachtet wird. Ein beliebiges Zeichen in [A, Z] (\u0041-\u005A) entspricht daher dem zugehörigen Zeichen in [a,z] (\u0061-\007A). Die Groß- und Kleinschreibung außerhalb des ASCII-Bereichs verwendet die Tabellen der invarianten Kultur. Daher entspricht der folgende Vergleich

[!code-csharp[Conceptual.Strings.BestPractices#4](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/comparison2.cs#4)]
[!code-vb[Conceptual.Strings.BestPractices#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/comparison2.vb#4)]

dem nachstehenden Vergleich (ist jedoch schneller):

[!code-csharp[Conceptual.Strings.BestPractices#5](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/comparison2.cs#5)]
[!code-vb[Conceptual.Strings.BestPractices#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/comparison2.vb#5)]

Diese Vergleiche werden immer noch sehr schnell durchgeführt.

> [!NOTE]
> Das Zeichenfolgenverhalten von Dateisystem, Registrierungsschlüsseln und -werten sowie Umgebungsvariablen wird am besten von <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType>dargestellt.

<xref:System.StringComparison.Ordinal?displayProperty=nameWithType> und <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType> verwenden die Binärwerte direkt und eignen sich am besten für Vergleiche. Wenn Sie nicht sicher über die Vergleichseinstellungen sind, verwenden Sie einen dieser beiden Werte. Da hier jedoch ein Vergleich auf Byteebene durchgeführt wird, erfolgt die Sortierung nicht anhand einer linguistischen Sortierreihenfolge (analog zu einem englischen Wörterbuch), sondern anhand einer binären Rangfolge. Die Ergebnisse erscheinen Benutzern möglicherweise in den meisten Kontexten seltsam.

Ordinalemantik ist die Standardeinstellung für <xref:System.String.Equals%2A?displayProperty=nameWithType> -Überladungen, die kein <xref:System.StringComparison> -Argument (einschließlich des Gleichheitsoperators) enthalten. In jedem Fall wird empfohlen, eine Überladung mit einem <xref:System.StringComparison> -Parameter aufzurufen.

### <a name="string-operations-that-use-the-invariant-culture"></a>Zeichenfolgenvorgänge mit der invarianten Kultur

Vergleiche mit der invarianten Kultur verwenden die <xref:System.Globalization.CultureInfo.CompareInfo%2A> -Eigenschaft, die von der statischen <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> -Eigenschaft zurückgegeben wird. Dieses Verhalten ist in allen Systemen gleich: Zeichen außerhalb des Bereichs werden in Zeichen übersetzt, von denen angenommen wird, dass es sich um die invarianten Entsprechungen handelt. Diese Richtlinie kann für das kulturübergreifende Beibehalten eines Satzes von Zeichenfolgenverhalten hilfreich sein, führt jedoch oftmals zu unerwarteten Ergebnissen.

Vergleiche mit der invarianten Kultur, bei denen nicht zwischen Groß- und Kleinschreibung unterschieden wird, verwenden für Vergleichsinformationen ebenfalls die statische <xref:System.Globalization.CultureInfo.CompareInfo%2A> -Eigenschaft, die von der statischen <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> -Eigenschaft zurückgegeben wird. Alle Unterschiede bezüglich der Groß- und Kleinschreibung in den übersetzten Zeichen werden ignoriert.

Vergleiche, die <xref:System.StringComparison.InvariantCulture?displayProperty=nameWithType> verwenden, und <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> , werden analog für ASCII-Zeichenfolgen ausgeführt. <xref:System.StringComparison.InvariantCulture?displayProperty=nameWithType> trifft jedoch linguistische Entscheidungen, die sich möglicherweise nicht für Zeichenfolgen eignen, die als Bytesatz interpretiert werden müssen. Das `CultureInfo.InvariantCulture.CompareInfo` -Objekt führt dazu, dass die <xref:System.String.Compare%2A> -Methode bestimmte Zeichensätze als äquivalent interpretiert. Die folgende Äquivalenz ist beispielsweise in der invarianten Kultur gültig:

InvariantCulture: a + ̊ = å

Der LATEINISCHE KLEINBUCHSTABE "a" (\u0061) wird, wenn er sich neben dem KOMBINIERENDEN ÜBERGESETZTEN RING "+ " ̊" (\u030a) befindet, als LATEINISCHER KLEINBUCHSTABE MIT ÜBERGESETZTEM RING interpretiert "å" (\u00e5). Wie das folgende Beispiel zeigt, unterscheidet sich dieses Verhalten vom Ordinalvergleich.

[!code-csharp[Conceptual.Strings.BestPractices#15](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/comparison3.cs#15)]
[!code-vb[Conceptual.Strings.BestPractices#15](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/comparison3.vb#15)]

Wenn sie Dateinamen, Cookies oder andere Elemente interpretieren, die eine Kombination wie „å“ enthalten können, bieten Ordinalvergleiche immer noch das transparenteste und am besten geeignete Verhalten an.

Insgesamt verfügt die invariante Kultur nur über sehr wenige Eigenschaften, die für einen Vergleich hilfreich sind. Sie führt Vergleiche mit linguistischer Relevanz durch und kann daher keine vollständige symbolische Äquivalenz garantieren, eignet sich jedoch nicht unbedingt für die Anzeige in einer beliebigen Kultur. Einer der wenigen Gründe, <xref:System.StringComparison.InvariantCulture?displayProperty=nameWithType> für Vergleiche zu verwenden, besteht darin, sortierte Daten für die kulturübergreifend einheitliche Anzeige beizubehalten. Wenn beispielsweise eine große Datendatei mit einer Liste sortierter Anzeigebezeichner einer Anwendung angehört, würde das Hinzufügen von Elementen zu dieser Liste einen Einfügevorgang mit invarianter Sortierung erfordern.

## <a name="choosing-a-stringcomparison-member-for-your-method-call"></a>Auswählen eines StringComparison-Members für den Methodenaufruf

In der folgenden Tabelle wird die Zuordnung von semantischem Zeichenfolgenkontext zu einem <xref:System.StringComparison>-Enumerationsmember beschrieben:

|Daten|Verhalten|System.StringComparison-Entsprechung<br /><br /> value|
|----------|--------------|-----------------------------------------------------|
|Interne Bezeichner, die die Groß- und Kleinschreibung beachten.<br /><br /> Bezeichner in Standards wie XML und HTTP, die die Groß- und Kleinschreibung beachten.<br /><br /> Sicherheitsbezogene Einstellungen, die die Groß- und Kleinschreibung beachten.|Ein nicht linguistischer Bezeichner mit exakt übereinstimmenden Bytes.|<xref:System.StringComparison.Ordinal>|
|Interne Bezeichner, die die Groß- und Kleinschreibung nicht beachten.<br /><br /> Bezeichner in Standards wie XML und HTTP, die die Groß- und Kleinschreibung nicht beachten.<br /><br /> Dateipfade.<br /><br /> Registrierungsschlüssel und -werte.<br /><br /> Umgebungsvariablen.<br /><br /> Ressourcenbezeichner (z. B. Handlenamen).<br /><br /> Sicherheitsbezogene Einstellungen, die die Groß- und Kleinschreibung nicht beachten.|Ein nicht linguistischer Bezeichner, bei dem die Groß- und Kleinschreibung keine Rolle spielt; insbesondere für Daten, die in den meisten Systemdiensten von Windows gespeichert werden.|<xref:System.StringComparison.OrdinalIgnoreCase>|
|Einige beibehaltene, linguistisch relevante Daten.<br /><br /> Anzeige von linguistischen Daten, die eine feste Sortierreihenfolge erfordern.|Kulturunabhängige Daten, die dennoch linguistisch relevant sind.|<xref:System.StringComparison.InvariantCulture><br /><br /> - oder -<br /><br /> <xref:System.StringComparison.InvariantCultureIgnoreCase>|
|Daten, die dem Benutzer angezeigt werden.<br /><br /> Die meisten Benutzereingaben.|Daten, die lokale linguistische Regeln erfordern.|<xref:System.StringComparison.CurrentCulture><br /><br /> - oder -<br /><br /> <xref:System.StringComparison.CurrentCultureIgnoreCase>|

## <a name="common-string-comparison-methods-in-net"></a>Allgemeine Methoden zum Zeichenfolgenvergleich in .NET

In den folgenden Abschnitten werden die Methoden beschrieben, die am häufigsten für Zeichenfolgenvergleiche verwendet werden.

### <a name="stringcompare"></a>String.Compare

Standardinterpretation: <xref:System.StringComparison.CurrentCulture?displayProperty=nameWithType>.

Der Aufruf dieser Methode stellt die zentrale Operation für Zeichenfolgeninterpretation dar. Aus diesem Grund sollten alle Instanzen von Methodenaufrufen untersucht werden, um zu bestimmen, ob Zeichenfolgen anhand der aktuellen Kultur oder unabhängig von der Kultur (symbolisch) interpretiert werden sollen. Üblicherweise handelt es sich um eine symbolische Interpretation, und stattdessen sollte ein <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> -Vergleich verwendet werden.

Die <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> -Klasse, die von der <xref:System.Globalization.CultureInfo.CompareInfo%2A?displayProperty=nameWithType> -Eigenschaft zurückgegeben wird, enthält auch eine <xref:System.Globalization.CompareInfo.Compare%2A> -Methode, die zahlreiche Vergleichsoptionen (ordinal, ohne Leerraumzeichen, ohne Zeichen vom Typ Kana usw.) über die <xref:System.Globalization.CompareOptions> -Flagenumeration zur Verfügung stellt.

### <a name="stringcompareto"></a>String.CompareTo

Standardinterpretation: <xref:System.StringComparison.CurrentCulture?displayProperty=nameWithType>.

Diese Methode bietet derzeit keine Überladung an, die einen <xref:System.StringComparison> -Typ angibt. Diese Methode kann normalerweise in das empfohlene <xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> -Format konvertiert werden.

Diese Methode wird von Typen implementiert, die die <xref:System.IComparable> - und die <xref:System.IComparable%601> -Schnittstelle implementieren. Da der <xref:System.StringComparison> -Parameter hier nicht verfügbar ist, ermöglichen implementierende Typen oftmals das Angeben eines <xref:System.StringComparer> im entsprechenden Konstruktor. Im folgenden Beispiel wird eine `FileName` -Klasse definiert, deren Klassenkonstruktor einen <xref:System.StringComparer> -Parameter enthält. Dieses <xref:System.StringComparer> -Objekt wird dann in der `FileName.CompareTo` -Methode verwendet.

[!code-csharp[Conceptual.Strings.BestPractices#6](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/api1.cs#6)]
[!code-vb[Conceptual.Strings.BestPractices#6](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/api1.vb#6)]

### <a name="stringequals"></a>String.Equals

Standardinterpretation: <xref:System.StringComparison.Ordinal?displayProperty=nameWithType>.

Mit der <xref:System.String> -Klasse können Sie eine Überprüfung auf Gleichheit durchführen, indem Sie die Überladungen der statischen <xref:System.String.Equals%2A> -Methode oder der entsprechenden Instanzenmethode aufrufen, oder indem Sie den statischen Gleichheitsoperator verwenden. Die Überladungen und der Operator verwenden standardmäßig einen Ordinalvergleich . Unabhängig davon wird jedoch empfohlen, eine Überladung aufrufen, die den <xref:System.StringComparison> -Typ explizit angibt; dies gilt auch, wenn Sie einen Ordinalvergleich ausführen möchten. Auf diese Weise können bestimmte Zeichenfolgeninterpretationen leichter in Code gefunden werden.

### <a name="stringtoupper-and-stringtolower"></a>String.ToUpper und String.ToLower

Standardinterpretation: <xref:System.StringComparison.CurrentCulture?displayProperty=nameWithType>.

Diese Methoden sollten mit besonderer Sorgfalt verwendet werden, da das Erzwingen der Groß- oder Kleinschreibung einer Zeichenfolge oftmals unabhängig von der Schreibweise als kleine Normalisierung für Zeichenfolgenvergleiche verwendet wird. Wenn dies der Fall ist, sollten Sie einen Vergleich ohne Beachtung der Groß- und Kleinschreibung in Erwägung ziehen.

Die <xref:System.String.ToUpperInvariant%2A?displayProperty=nameWithType> -Methode und die <xref:System.String.ToLowerInvariant%2A?displayProperty=nameWithType> -Methode sind ebenfalls verfügbar. <xref:System.String.ToUpperInvariant%2A> wird standardmäßig zur Normalisierung der Schreibweise verwendet. Das Verhalten von Vergleichen mit <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType> setzt sich aus zwei Aufrufen zusammen: einem Aufruf von <xref:System.String.ToUpperInvariant%2A> für beide Zeichenfolgenargumente und einem Vergleich mithilfe von <xref:System.StringComparison.Ordinal?displayProperty=nameWithType>.

Überladungen sind auch für die Konvertierung in Groß- und Kleinschreibung in einer bestimmten Kultur verfügbar. Dazu wird ein <xref:System.Globalization.CultureInfo> -Objekt übergeben, das die Kultur für die Methode darstellt.

### <a name="chartoupper-and-chartolower"></a>Char.ToUpper und Char.ToLower

Standardinterpretation: <xref:System.StringComparison.CurrentCulture?displayProperty=nameWithType>.

Diese Methoden funktionieren ähnliche wie die <xref:System.String.ToUpper%2A?displayProperty=nameWithType> -Methode und die <xref:System.String.ToLower%2A?displayProperty=nameWithType> -Methode, die im vorherigen Abschnitt beschrieben werden.

### <a name="stringstartswith-and-stringendswith"></a>String.StartsWith und String.EndsWith

Standardinterpretation: <xref:System.StringComparison.CurrentCulture?displayProperty=nameWithType>.

Standardmäßig führen beide Methoden einen kulturabhängigen Vergleich durch.

### <a name="stringindexof-and-stringlastindexof"></a>String.IndexOf und String.LastIndexOf

Standardinterpretation: <xref:System.StringComparison.CurrentCulture?displayProperty=nameWithType>.

Die Durchführung von Vergleichen durch die Standardüberladungen dieser Methoden ist nicht konsistent. Alle <xref:System.String.IndexOf%2A?displayProperty=nameWithType> - und <xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> -Methoden mit einem <xref:System.Char> -Parameter führen einen Ordinalvergleich durch. Die <xref:System.String.IndexOf%2A?displayProperty=nameWithType> - und die <xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> -Standardmethode mit einem <xref:System.String> -Parameter führen dagegen einen kulturabhängigen Vergleich durch.

Wenn Sie die <xref:System.String.IndexOf%28System.String%29?displayProperty=nameWithType> -Methode oder die <xref:System.String.LastIndexOf%28System.String%29?displayProperty=nameWithType> -Methode aufrufen und eine Zeichenfolge übergeben, die in der aktuellen Instanz gesucht werden soll, empfiehlt es sich, eine Überladung aufrufen, die den <xref:System.StringComparison> -Typ explizit angibt. Mit den Überladungen, die ein <xref:System.Char> -Argument enthalten, können Sie keinen <xref:System.StringComparison> -Typ angeben.

## <a name="methods-that-perform-string-comparison-indirectly"></a>Methoden für den indirekten Zeichenfolgenvergleich

Einige Methoden, die keine Zeichenfolgenmethoden darstellen und deren zentrale Operation ein Zeichenfolgenvergleich ist, verwenden den <xref:System.StringComparer> -Typ. Die <xref:System.StringComparer> -Klasse enthält sechs statische Eigenschaften, die <xref:System.StringComparer> -Instanzen zurückgeben, deren <xref:System.StringComparer.Compare%2A?displayProperty=nameWithType> -Methoden folgende Arten von Zeichenfolgenvergleichen durchführen:

- Kulturabhängige Zeichenfolgenvergleiche mit der aktuellen Kultur. Dieses <xref:System.StringComparer> -Objekt wird von der <xref:System.StringComparer.CurrentCulture%2A?displayProperty=nameWithType> -Eigenschaft zurückgegeben.
- Vergleiche mit der aktuellen Kultur ohne Beachtung der Groß- und Kleinschreibung. Dieses <xref:System.StringComparer> -Objekt wird von der <xref:System.StringComparer.CurrentCultureIgnoreCase%2A?displayProperty=nameWithType> -Eigenschaft zurückgegeben.
- Kulturunabhängige Vergleiche mit den Wortvergleichsregeln der invarianten Kultur. Dieses <xref:System.StringComparer> -Objekt wird von der <xref:System.StringComparer.InvariantCulture%2A?displayProperty=nameWithType> -Eigenschaft zurückgegeben.
- Kulturunabhängige Vergleiche mit den Wortvergleichsregeln der invarianten Kultur ohne Beachtung der Groß- und Kleinschreibung. Dieses <xref:System.StringComparer> -Objekt wird von der <xref:System.StringComparer.InvariantCultureIgnoreCase%2A?displayProperty=nameWithType> -Eigenschaft zurückgegeben.
- Ordinalvergleich. Dieses <xref:System.StringComparer> -Objekt wird von der <xref:System.StringComparer.Ordinal%2A?displayProperty=nameWithType> -Eigenschaft zurückgegeben.
- Ordinalvergleich ohne Beachtung der Groß- und Kleinschreibung. Dieses <xref:System.StringComparer> -Objekt wird von der <xref:System.StringComparer.OrdinalIgnoreCase%2A?displayProperty=nameWithType> -Eigenschaft zurückgegeben.

### <a name="arraysort-and-arraybinarysearch"></a>Array.Sort und Array.BinarySearch

Standardinterpretation: <xref:System.StringComparison.CurrentCulture?displayProperty=nameWithType>.

Wenn Sie Daten in einer Auflistung speichern oder beibehaltene Daten aus einer Datei oder einer Datenbank in eine Auflistung lesen, können die Invarianten in der Auflistung durch einen Wechsel der aktuellen Kultur ungültig werden. Die <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> -Methode geht davon aus, dass die Elemente im zu durchsuchenden Array bereits sortiert wurden. Um die einzelnen Zeichenfolgenelemente im Array zu sortieren, ruft die <xref:System.Array.Sort%2A?displayProperty=nameWithType> -Methode die <xref:System.String.Compare%2A?displayProperty=nameWithType> -Methode auf. Kulturabhängige Vergleich bergen ein gewisses Risiko, falls sich die Kultur zwischen dem Zeitpunkt der Sortierung des Arrays und dem Durchsuchen des Inhalts ändert. Im folgenden Code beispielsweise wird das Speichern und Abrufen für den Comparer ausgeführt, der implizit von der `Thread.CurrentThread.CurrentCulture` -Eigenschaft zurückgegeben wird. Wenn sich die Kultur zwischen dem Aufruf von `StoreNames` und dem Aufruf von `DoesNameExist`möglicherweise ändert, kann bei der binären Suche ein Fehler auftreten; dies gilt insbesondere, wenn der Arrayinhalt zwischen den beiden Methodenaufrufen beibehalten wird.

[!code-csharp[Conceptual.Strings.BestPractices#7](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/indirect1.cs#7)]
 [!code-vb[Conceptual.Strings.BestPractices#7](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/indirect1.vb#7)]

Eine empfohlene Variante wird im folgenden Beispiel angezeigt, in dem die gleiche (kulturunabhängige) Ordinalvergleichsmethode verwendet wird, um das Array zu sortieren und zu durchsuchen. Der Änderungscode wird in den zwei Beispielen in den Zeilen mit der Bezeichnung `Line A` und `Line B` angezeigt.

[!code-csharp[Conceptual.Strings.BestPractices#8](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/indirect1.cs#8)]
[!code-vb[Conceptual.Strings.BestPractices#8](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/indirect1.vb#8)]

Wenn diese Daten beibehalten und zwischen Kulturen verschoben werden, und wenn eine Sortierung verwendet wird, um die Daten für den Benutzer anzuzeigen, können Sie <xref:System.StringComparison.InvariantCulture?displayProperty=nameWithType>verwenden, da durch die linguistische Verarbeitung eine bessere Benutzerausgabe erzielt wird und Änderungen der Kultur keine Auswirkungen haben. Im folgenden Beispiel werden die zwei vorherigen Beispiele geändert, um die invariante Kultur zum Sortieren und Durchsuchen des Arrays zu verwenden.

[!code-csharp[Conceptual.Strings.BestPractices#9](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/indirect1.cs#9)]
[!code-vb[Conceptual.Strings.BestPractices#9](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/indirect1.vb#9)]

### <a name="collections-example-hashtable-constructor"></a>Beispiel einer Sammlung: Hashtable-Konstruktor

Auch beim Hashen von Zeichenfolgen können sich, je nachdem, wie die Zeichenfolgen verglichen werden, Auswirkungen auf die Operation ergeben.

Im folgenden Beispiel wird ein <xref:System.Collections.Hashtable> -Objekt instanziiert, indem das <xref:System.StringComparer> -Objekt übergeben wird, das von der <xref:System.StringComparer.OrdinalIgnoreCase%2A?displayProperty=nameWithType> -Eigenschaft zurückgegeben wird. Da eine Klasse <xref:System.StringComparer> , die von <xref:System.StringComparer> abgeleitet wird, die <xref:System.Collections.IEqualityComparer> -Schnittstelle implementiert, wird die <xref:System.Collections.IEqualityComparer.GetHashCode%2A> -Methode verwendet, um den Hashcode von Zeichenfolgen in der Hashtabelle zu berechnen.

[!code-csharp[Conceptual.Strings.BestPractices#10](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/indirect2.cs#10)]
[!code-vb[Conceptual.Strings.BestPractices#10](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/indirect2.vb#10)]

## <a name="displaying-and-persisting-formatted-data"></a>Anzeigen und Beibehalten von formatierten Daten

Wenn Sie Benutzern Daten anzeigen, die keine Zeichenfolge sind, z. B. Zahlen sowie Datumsangaben und Zeitangaben, formatieren Sie diese den Kultureinstellungen des Benutzers entsprechend. In den folgenden Fällen wird bei Formatierungsvorgängen jeweils standardmäßig die aktuelle Threadkultur verwendet:

- Bei interpolierten Zeichenfolgen, die von den [C#](../../csharp/language-reference/tokens/interpolated.md)- und [Visual Basic](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md)-Compilern unterstützt werden.
- Bei Zeichenfolgenverkettungen, bei denen [C#](../../csharp/language-reference/operators/addition-operator.md#string-concatenation)- oder [Visual Basic](../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md )-Verkettungsoperatoren verwendet werden oder die Methode <xref:System.String.Concat%2A?displayProperty=nameWithType> direkt aufgerufen wird.
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
