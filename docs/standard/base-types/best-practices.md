---
title: Empfohlene Vorgehensweisen für die Verwendung von regulären Ausdrücken in .NET
description: Erfahren Sie, wie Sie effiziente, effektive reguläre Ausdrücke in .NET erstellen.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- .NET Framework regular expressions, best practices
- regular expressions, best practices
ms.assetid: 618e5afb-3a97-440d-831a-70e4c526a51c
author: rpetrusha
ms.author: ronpet
ms.custom: seodec18
ms.openlocfilehash: 89585ff97183912feb9b9af0bd326041b7381bfb
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774305"
---
# <a name="best-practices-for-regular-expressions-in-net"></a>Empfohlene Vorgehensweisen für die Verwendung von regulären Ausdrücken in .NET

Die Engine für reguläre Ausdrücke in .NET ist ein leistungsstarkes Tool mit vollem Funktionsumfang, das Texte auf Grundlage von Musterübereinstimmungen verarbeitet, anstatt Literaltext zu vergleichen und nach Übereinstimmungen mit diesem zu suchen. In den meisten Fällen wird die Suche nach Musterabgleichen schnell und effizient ausgeführt. Gelegentlich kann die Engine für reguläre Ausdrücke jedoch sehr langsam wirken. In Extremfällen kann auch der Eindruck entstehen, dass das Modul nicht mehr reagiert, wenn für die Verarbeitung relativ kleiner Eingaben mehrere Stunden oder sogar Tage benötigt werden.

In diesem Thema werden einige Best Practices erläutert, mit denen Entwickler sicherstellen können, dass ihre regulären Ausdrücke optimale Leistung erzielen.

## <a name="consider-the-input-source"></a>Bedenken der Eingabequelle

Im Allgemeinen können reguläre Ausdrücke zwei Arten von Eingaben annehmen: eingeschränkte und nicht eingeschränkte. Bei eingeschränkten Eingaben handelt es sich um Text, der aus einer bekannten oder verlässlichen Quelle stammt und einem vordefinierten Format folgt. Eine nicht eingeschränkte Eingabe ist Text, der aus einer unzuverlässigen Quelle stammt, z. B. von einem Webbenutzer, und keinem vordefinierten oder erwarteten Format folgt.

Muster regulärer Ausdrücke werden in der Regel für die Übereinstimmung mit gültigen Eingaben konzipiert. Das bedeutet, dass ein Entwickler den Text überprüft, mit dem eine Übereinstimmung erzielt werden soll, und anschließend ein entsprechendes Muster für reguläre Ausdrücke erstellt. Dann ermittelt der Entwickler, ob dieses Muster Korrekturen oder Ausarbeitungen erfordert, indem er es mit mehreren gültigen Eingabeelementen testet. Wenn das Muster mit allen als gültig geltenden Eingaben übereinstimmt, gilt es als einsatzbereit und kann in eine veröffentlichte Anwendung eingeschlossen werden. Somit ist das Muster für reguläre Ausdrücke geeignet für Übereinstimmungen mit eingeschränkten Eingaben. Allerdings ist es nicht geeignet für die Übereinstimmung mit nicht eingeschränkten Eingaben.

Für Übereinstimmungen mit nicht eingeschränkten Eingaben muss ein regulärer Ausdruck drei Arten von Text effizient verarbeiten können:

- Text, der mit dem Muster eines regulären Ausdrucks übereinstimmt.

- Text, der nicht mit dem Muster eines regulären Ausdrucks übereinstimmt.

- Text, der fast mit dem Muster eines regulären Ausdrucks übereinstimmt.

Der letzte Texttyp ist besonders problematisch für reguläre Ausdrücke, die für die Behandlung eingeschränkter Eingaben vorgesehen sind. Wenn ein solcher regulärer Ausdruck zudem auf umfangreicher [Rückverfolgung](../../../docs/standard/base-types/backtracking-in-regular-expressions.md) beruht, kann die Engine für reguläre Ausdrücke für die Verarbeitung von scheinbar harmlosem Text übermäßig lange Zeit brauchen (in manchen Fällen mehrere Stunden oder Tage).

> [!WARNING]
> Im folgenden Beispiel wird ein regulärer Ausdruck verwendet, der für übermäßige Rückverfolgung anfällig ist und wahrscheinlich gültige E-Mail-Adressen zurückweisen wird. Er sollte nicht in einer E-Mail-Validierungsroutine nicht verwendet werden. Einen regulären Ausdruck, der E-Mail-Adressen überprüft, finden Sie unter [Vorgehensweise: Überprüfen, ob Zeichenfolgen ein gültiges E-Mail-Format aufweisen](../../../docs/standard/base-types/how-to-verify-that-strings-are-in-valid-email-format.md).

Als Beispiel dient hier ein sehr häufig verwendeter, jedoch äußerst problematischer regulärer Ausdruck zum Überprüfen des Alias einer E-Mail-Adresse. Der reguläre Ausdruck `^[0-9A-Z]([-.\w]*[0-9A-Z])*$` wird konzipiert, um eine als gültig angenommene E-Mail-Adresse zu verarbeiten, die aus einem alphanumerischen Zeichen gefolgt von keinem oder weiteren Zeichen besteht, bei denen es sich um alphanumerische Zeichen, Punkte oder Bindestriche handeln kann. Der reguläre Ausdruck muss mit einem alphanumerischen Zeichen enden. Die Verarbeitung von gültigen Eingaben durch diesen regulären Ausdruck erfolgt zwar reibungslos, aber das folgende Beispiel zeigt, dass die Leistung bei der Verarbeitung von fast gültigen Eingaben sehr schlecht ist.

[!code-csharp[Conceptual.RegularExpressions.BestPractices#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/cs/design2.cs#1)]
[!code-vb[Conceptual.RegularExpressions.BestPractices#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/vb/design2.vb#1)]

Die Ausgabe im Beispiel zeigt, dass die Engine für reguläre Ausdrücke den gültigen E-Mail-Alias in etwa demselben Zeitintervall verarbeitet, unabhängig von dessen Länge. Wenn die fast gültige E-Mail-Adresse andererseits mehr als fünf Zeichen aufweist, wird die Verarbeitungszeit für jedes weitere Zeichen in der Zeichenfolge nahezu verdoppelt. Dies bedeutet, dass die Verarbeitung einer fast gültigen Zeichenfolge mit 28 Zeichen mehr als eine Stunde und die einer fast gültigen Zeichenfolge mit 33 Zeichen ungefähr einen Tag dauern würde.

Da dieser reguläre Ausdruck ausschließlich im Hinblick auf das Format der Eingaben entwickelt wurde, für die eine Übereinstimmung gefunden werden sollte, werden Eingaben, die nicht mit dem Muster übereinstimmen, nicht berücksichtigt. Dies kann wiederum dazu führen, dass nicht eingeschränkte Eingaben, die fast mit dem Muster für reguläre Ausdrücke übereinstimmen, die Leistung erheblich beeinträchtigen.

Um dieses Problem zu beheben, können Sie wie folgt vorgehen:

- Beim Erstellen eines Musters sollten Sie berücksichtigen, wie sich das Zurückverfolgen auf die Leistung der Engine für reguläre Ausdrücke auswirken könnte. Dies gilt insbesondere, wenn ein regulärer Ausdruck für die Verarbeitung nicht eingeschränkter Eingaben vorgesehen ist. Weitere Informationen finden Sie im Abschnitt [Steuern der Rückverfolgung](#take-charge-of-backtracking).

- Testen Sie den regulären Ausdruck sowohl mit ungültigen und fast gültigen Eingaben als auch mit gültigen Eingaben gründlich. Um Eingaben für einen bestimmten regulären Ausdruck zufällig zu generieren, können Sie [Rex](https://www.microsoft.com/research/project/rex-regular-expression-exploration/) verwenden, ein Tool für das Untersuchen von regulären Ausdrücken von Microsoft Research.

## <a name="handle-object-instantiation-appropriately"></a>Angemessene Behandlung der Objektinstanziierung

Den Kern des .NET-Objektmodells für reguläre Ausdrücke bildet die <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType>-Klasse, die die Engine für reguläre Ausdrücke darstellt. Häufig ist die einzige Hauptursache für Leistungsbeeinträchtigungen bei regulären Ausdrücken die Art, wie die <xref:System.Text.RegularExpressions.Regex>-Engine verwendet wird. Das Definieren eines regulären Ausdrucks beinhaltet das enge Verbinden der Engine für reguläre Ausdrücke mit einem Muster für reguläre Ausdrücke. Hierzu wird ein <xref:System.Text.RegularExpressions.Regex>-Objekt durch Übergeben des Konstruktors an ein reguläres Ausdrucksmuster instanziiert, oder eine statische Methode wird aufgerufen, indem das reguläre Ausdrucksmuster zusammen mit der zu analysierenden Zeichenfolge an sie übergeben wird. Somit ist dieser Verbindungsprozess zwangsläufig aufwendig.

> [!NOTE]
> Eine ausführlichere Erläuterung der Leistungseinbußen bei der Verwendung interpretierter und kompilierter regulärer Ausdrücke finden Sie unter [Optimieren der Leistung regulärer Ausdrücke, Teil II: Steuern der Rückverfolgung](https://blogs.msdn.microsoft.com/bclteam/2010/08/03/optimizing-regular-expression-performance-part-ii-taking-charge-of-backtracking-ron-petrusha/) im BCL-Teamblog.

Sie können die Engine für reguläre Ausdrücke mit einem bestimmten Muster für reguläre Ausdrücke verknüpfen und die Engine dann verwenden, um Textübereinstimmungen auf verschiedene Weise zu suchen:

- Sie können eine statische Methode für Musterübereinstimmungen aufrufen, z. B. <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%29?displayProperty=nameWithType>. Hierfür ist keine Instanziierung des Objekts eines regulären Ausdrucks erforderlich.

- Sie können ein <xref:System.Text.RegularExpressions.Regex>-Objekt instanziieren und eine Instanzmethode für Musterübereinstimmungen eines interpretierten regulären Ausdrucks aufrufen. Dies ist die Standardmethode zum Binden der Engine für reguläre Ausdrücke an ein Muster für reguläre Ausdrücke. Das Ergebnis tritt ein, wenn ein <xref:System.Text.RegularExpressions.Regex>-Objekt ohne ein `options`-Argument instanziiert wird, das das <xref:System.Text.RegularExpressions.RegexOptions.Compiled>-Flag beinhaltet.

- Sie können ein <xref:System.Text.RegularExpressions.Regex>-Objekt instanziieren und eine Instanzmethode für Musterübereinstimmungen eines kompilierten regulären Ausdrucks aufrufen. Objekte regulärer Ausdrücke stellen kompilierte Muster dar, wenn ein <xref:System.Text.RegularExpressions.Regex>-Objekt mit einem `options`-Argument instanziiert wird, das das <xref:System.Text.RegularExpressions.RegexOptions.Compiled>-Flag beinhaltet.

- Sie können ein <xref:System.Text.RegularExpressions.Regex>-Objekt für besondere Zwecke erstellen, das eng mit einem bestimmten Muster für reguläre Ausdrücke verknüpft ist, dieses Objekt kompilieren und in einer eigenständigen Assembly speichern. Hierfür rufen Sie die <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType>-Methode auf.

Die Art und Weise, wie Sie Methoden für Übereinstimmungen mit regulären Ausdrucken aufrufen, kann erhebliche Auswirkungen auf die Anwendung haben. In den folgenden Abschnitten wird erläutert, wann statische Methodenaufrufe, interpretierte reguläre Ausdrücke und kompilierte reguläre Ausdrücke verwendet werden, um die Leistung Ihrer Anwendung zu verbessern.

> [!IMPORTANT]
> Die Art des Methodenaufrufs (statisch, interpretiert, kompiliert) wirkt sich auf die Leistung aus, wenn ein regulärer Ausdruck wiederholt in Methodenaufrufen verwendet wird oder wenn eine Anwendung umfassenden Gebrauch von Objekten regulärer Ausdrücke macht.

### <a name="static-regular-expressions"></a>Statische reguläre Ausdrücke

Statische Methoden für reguläre Ausdrücke werden als Alternative zum wiederholten Instanziieren eines Objekts für reguläre Ausdrücke mit demselben regulären Ausdruck empfohlen. Im Gegensatz zu Mustern regulärer Ausdrücke, die von Objekten regulärer Ausdrücke verwendet werden, speichert die Engine für reguläre Ausdrücke entweder die Vorgangscodes oder die kompilierte Microsoft Intermediate Language (MSIL) aus Mustern intern zwischen, die in statischen Methodenaufrufen verwendet werden.

Beispielsweise ruft ein Ereignishandler häufig eine andere Methode auf, um Benutzereingaben zu überprüfen. Dies wird im folgenden Code widergespiegelt, in dem das <xref:System.Windows.Forms.Button>-Ereignis eines <xref:System.Windows.Forms.Control.Click>-Steuerelements verwendet wird, um eine Methode namens `IsValidCurrency` aufzurufen, die überprüft, ob der Benutzer ein Währungssymbol gefolgt von mindestens einer Dezimalziffer eingegeben hat.

[!code-csharp[Conceptual.RegularExpressions.BestPractices#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/cs/static1.cs#2)]
[!code-vb[Conceptual.RegularExpressions.BestPractices#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/vb/static1.vb#2)]

Eine sehr ineffiziente Implementierung der `IsValidCurrency`-Methode wird im folgenden Beispiel gezeigt. Beachten Sie, dass jeder Methodenaufruf ein <xref:System.Text.RegularExpressions.Regex>-Objekt mit demselben Muster erneut instanziiert. Dies bedeutet wiederum, dass das Muster für reguläre Ausdrücke bei jedem Aufruf der Methode erneut kompiliert werden muss.

[!code-csharp[Conceptual.RegularExpressions.BestPractices#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/cs/static1.cs#3)]
[!code-vb[Conceptual.RegularExpressions.BestPractices#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/vb/static1.vb#3)]

Sie sollten diesen ineffizienten Code durch einen Aufruf der statischen <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%29?displayProperty=nameWithType>-Methode ersetzen. Dadurch entfällt die Notwendigkeit, jedes Mal ein <xref:System.Text.RegularExpressions.Regex>-Objekt zu instanziieren, wenn Sie eine Methode für Musterübereinstimmungen aufrufen möchten. Außerdem kann die Engine für reguläre Ausdrücke eine kompilierte Version des regulären Ausdrucks aus dem Cache abrufen.

[!code-csharp[Conceptual.RegularExpressions.BestPractices#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/cs/static2.cs#4)]
[!code-vb[Conceptual.RegularExpressions.BestPractices#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/vb/static2.vb#4)]

Standardmäßig werden die letzten 15 zuletzt verwendeten statischen Muster für reguläre Ausdrücke zwischengespeichert. Für Anwendungen, die eine größere Anzahl von zwischengespeicherten statischen regulären Ausdrücken benötigen, kann die Größe des Caches durch Festlegen der <xref:System.Text.RegularExpressions.Regex.CacheSize%2A?displayProperty=nameWithType>-Eigenschaft angepasst werden.

Der in diesem Beispiel verwendete reguläre Ausdruck `\p{Sc}+\s*\d+` überprüft, ob die Eingabezeichenfolge ein Währungssymbol und mindestens eine Dezimalziffer enthält. Das Muster wird entsprechend der folgenden Tabelle definiert.

|Muster|BESCHREIBUNG|
|-------------|-----------------|
|`\p{Sc}+`|Übereinstimmung mit mindestens einem Zeichen aus der Unicode-Kategorie Symbol, Währung.|
|`\s*`|Sucht nach 0 (null) oder mehr Leerzeichen.|
|`\d+`|Entsprechung für mindestens eine Dezimalstelle finden.|

### <a name="interpreted-vs-compiled-regular-expressions"></a>Interpretierte im Vergleich zu kompilierten regulären Ausdrücken

Muster für reguläre Ausdrücke, die nicht durch Angabe der <xref:System.Text.RegularExpressions.RegexOptions.Compiled>-Option an die Engine für reguläre Ausdrücke gebunden sind, werden interpretiert. Wenn ein Objekt für reguläre Ausdrücke instanziiert wird, konvertiert die Engine für reguläre Ausdrücke den regulären Ausdruck in einen Satz von Operationscodes. Beim Aufrufen einer Instanzmethode werden die Operationscodes in MSIL konvertiert und vom JIT-Compiler ausgeführt. Wenn eine statische Methode für reguläre Ausdrücke aufgerufen und der reguläre Ausdruck nicht im Cache gefunden wird, konvertiert die Engine für reguläre Ausdrücke den regulären Ausdruck ebenfalls in einen Satz von Operationscodes und speichert diese im Cache. Dann werden diese Operationscodes in MSIL konvertiert, damit der JIT-Compiler sie ausführen kann. Interpretierte reguläre Ausdrücke reduzieren die Ladezeit, führen aber zu einer langsameren Ausführungszeit. Ihre Verwendung empfiehlt sich daher vor allem dann, wenn der reguläre Ausdruck in einer kleinen Anzahl von Methodenaufrufen verwendet wird oder wenn die genaue Anzahl von Aufrufen der Methoden mit regulären Ausdrücken zwar unbekannt, jedoch erwartungsgemäß niedrig ist. Wenn die Anzahl der Methodenaufrufe zunimmt, wird die durch die kürzere Startzeit erzielte Leistungssteigerung durch die langsamere Ausführungsgeschwindigkeit wieder ausgeglichen.

Muster für reguläre Ausdrücke, die durch Angabe der <xref:System.Text.RegularExpressions.RegexOptions.Compiled>-Option an die Engine für reguläre Ausdrücke gebunden sind, werden kompiliert. Wenn also ein Objekt für reguläre Ausdrücke instanziiert oder eine statische Methode mit regulären Ausdrücken aufgerufen wird und der reguläre Ausdruck nicht im Cache gefunden wird, konvertiert die Engine für reguläre Ausdrücke den regulären Ausdruck in einen vorläufigen Satz von Operationscodes, der wiederum in MSIL konvertiert wird. Wenn eine Methode aufgerufen wird, führt der JIT-Compiler die MSIL aus. Im Gegensatz zu interpretierten regulären Ausdrücken erhöhen kompilierte reguläre Ausdrücke die Startzeit. Einzelne Methoden für Musterübereinstimmungen werden aber schneller ausgeführt. Dadurch vergrößert sich der Leistungsvorteil, der sich aus dem Kompilieren eines regulären Ausdrucks ergibt, relativ zur Anzahl der aufgerufenen Methoden für reguläre Ausdrücke.

Zusammenfassend wird empfohlen, interpretierte reguläre Ausdrücke dann zu verwenden, wenn Sie relativ selten Methoden für reguläre Ausdrücke mit einem bestimmten regulären Ausdruck aufrufen. Kompilierte reguläre Ausdrücke sollten Sie verwenden, wenn Sie relativ häufig Methoden für reguläre Ausdrücke mit einem bestimmten regulären Ausdruck aufrufen. Der genaue Schwellenwert, an dem die langsamere Ausführungsgeschwindigkeit interpretierter regulärer Ausdrücke die Vorteile der kürzen Startzeit aufhebt bzw. an dem die langsamere Startzeit kompilierter regulärer Ausdrücke die Vorteile der schnelleren Ausführungszeit aufhebt, ist schwer festzulegen. Diese Schwellenwerte hängen von verschiedenen Faktoren ab, z. B. der Komplexität des regulären Ausdrucks und den spezifischen verarbeiteten Daten. Um zu bestimmen, ob interpretierte oder kompilierte reguläre Ausdrücke die optimale Leistung für Ihr spezifisches Anwendungsszenario bieten, können Sie die <xref:System.Diagnostics.Stopwatch>-Klasse verwenden, um die jeweiligen Ausführungszeiten zu vergleichen.

Im folgenden Beispiel wird die Leistung von kompilierten und interpretierten regulären Ausdrücken beim Lesen der ersten zehn Sätze und beim Lesen aller Sätze im Text *The Financier* von Theodore Dreiser verglichen. Die Ausgabe im Beispiel zeigt: Wenn nur zehn Aufrufe von Methoden für Übereinstimmungen mit regulären Ausdrücken erfolgen, bietet ein interpretierter regulärer Ausdruck eine bessere Leistung als ein kompilierter regulärer Ausdruck. Ein kompilierter regulärer Ausdruck bietet jedoch die bessere Leistung bei vielen Aufrufen (in diesem Fall über 13.000).

[!code-csharp[Conceptual.RegularExpressions.BestPractices#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/cs/compare1.cs#5)]
[!code-vb[Conceptual.RegularExpressions.BestPractices#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/vb/compare1.vb#5)]

Das im Beispiel verwendete Muster für reguläre Ausdrücke, `\b(\w+((\r?\n)|,?\s))*\w+[.?:;!]`, wird entsprechend der folgenden Tabelle definiert.

|Muster|BESCHREIBUNG|
|-------------|-----------------|
|`\b`|Der Vergleich beginnt an einer Wortgrenze.|
|`\w+`|Übereinstimmung mit mindestens einem Wortzeichen.|
|<code>(\r?\n)&#124;,?\s)</code>|Übereinstimmung mit entweder keinem oder einem Wagenrücklaufzeichen gefolgt von einem Zeilenumbruchzeichen oder mit keinem oder einem Komma gefolgt von einem Leerzeichen.|
|<code>(\w+((\r?\n)&#124;,?\s))*</code>|Übereinstimmung mit keinem oder mehreren Vorkommen eines oder mehrerer Wortzeichen gefolgt von entweder keinem oder einem Wagenrücklaufzeichen und einem Zeilenumbruchzeichen oder von keinem oder einem Komma gefolgt von einem Leerzeichen.|
|`\w+`|Übereinstimmung mit mindestens einem Wortzeichen.|
|`[.?:;!]`|Übereinstimmung mit einem Punkt, Fragezeichen, Doppelpunkt, Semikolon oder Ausrufezeichen.|

### <a name="regular-expressions-compiled-to-an-assembly"></a>Reguläre Ausdrücke: In einer Assembly kompiliert

Mit .NET können Sie auch eine Assembly erstellen, die kompilierte reguläre Ausdrücke enthält. Hierdurch werden die Leistungseinbußen bei der Kompilierung regulärer Ausdrücke von der Laufzeit zur Entwurfszeit verschoben. Es sind jedoch einige zusätzliche Schritte erforderlich: Sie müssen die regulären Ausdrücke im Voraus definieren und in eine Assembly kompilieren. Der Compiler kann dann beim Kompilieren von Quellcode, in dem die regulären Ausdrücke der Assembly verwendet werden, auf diese Assembly verweisen. Jeder kompilierte reguläre Ausdruck in der Assembly wird durch eine Klasse dargestellt, die von <xref:System.Text.RegularExpressions.Regex> abgeleitet wird.

Um reguläre Ausdrücke in einer Assembly zu kompilieren, rufen Sie die <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%28System.Text.RegularExpressions.RegexCompilationInfo%5B%5D%2CSystem.Reflection.AssemblyName%29?displayProperty=nameWithType>-Methode auf und übergeben an diese Methode ein Array von <xref:System.Text.RegularExpressions.RegexCompilationInfo>-Objekten, die die zu kompilierenden regulären Ausdrücke darstellen, und ein <xref:System.Reflection.AssemblyName>-Objekt, das Informationen über die zu erstellende Assembly enthält.

Das Kompilieren regulärer Ausdrücke in einer Assembly wird in den folgenden Situationen empfohlen:

- Wenn Sie als Komponentenentwickler eine Bibliothek mit wiederverwendbaren regulären Ausdrücken erstellen möchten.

- Wenn die Anzahl der Aufrufe der Methoden für Musterübereinstimmungen mit regulären Ausdrücken erwartungsgemäß unbestimmt ist (von ein bis zwei bis zu mehreren Tausend oder zehntausend Aufrufen). Im Gegensatz zu kompilierten oder interpretierten regulären Ausdrücken bieten reguläre Ausdrücke, die in separaten Assemblys kompiliert werden, eine konsistente Leistung, die nicht von der Anzahl der Methodenaufrufe abhängt.

Wenn Sie kompilierte reguläre Ausdrücke verwenden, um die Leistung zu optimieren, sollten Sie nicht mithilfe der Reflektion die Assembly erstellen, die Engine für reguläre Ausdrücke laden und die Methoden für Musterübereinstimmungen ausführen. Hierbei sollten Sie es vermeiden, Muster für reguläre Ausdrücke dynamisch zu erstellen und zum Zeitpunkt der Assemblyerstellung Optionen für Musterabgleiche anzugeben (z. B. Musterabgleiche ohne Berücksichtigung der Groß-/Kleinschreibung). Außerdem müssen Sie den Code, mit dem die Assembly erstellt wird, von dem Code trennen, der den regulären Ausdruck verwendet.

Im folgenden Beispiel wird gezeigt, wie eine Assembly erstellt wird, die einen kompilierten regulären Ausdruck enthält. Die Assembly `RegexLib.dll` wird mit einer einzelnen Klasse regulärer Ausdrücke erstellt, `SentencePattern`, die das reguläre Ausdrucksmuster für Satzübereinstimmungen enthält, das im Abschnitt [Interpretierte und kompilierte reguläre Ausdrücke](#interpreted-vs-compiled-regular-expressions) verwendet wird.

[!code-csharp[Conceptual.RegularExpressions.BestPractices#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/cs/compile1.cs#6)]
[!code-vb[Conceptual.RegularExpressions.BestPractices#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/vb/compile1.vb#6)]

Wenn das Beispiel in eine ausführbare Datei kompiliert und ausgeführt wird, wird eine Assembly mit dem Namen `RegexLib.dll` erstellt. Der reguläre Ausdruck wird von einer Klasse mit dem Namen `Utilities.RegularExpressions.SentencePattern` dargestellt, die von <xref:System.Text.RegularExpressions.Regex> abgeleitet ist. Im folgenden Beispiel wird dann der kompilierte reguläre Ausdruck verwendet, um die Sätze aus dem Text *The Financier* von Theodore Dreiser zu extrahieren.

[!code-csharp[Conceptual.RegularExpressions.BestPractices#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/cs/compile2.cs#7)]
[!code-vb[Conceptual.RegularExpressions.BestPractices#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/vb/compile2.vb#7)]

## <a name="take-charge-of-backtracking"></a>Steuern der Rückverfolgung

Normalerweise bewegt sich die Engine für reguläre Ausdrücke für den Vergleich mit einem regulären Ausdrucksmuster linear durch eine Eingabezeichenfolge. Wenn jedoch unbestimmte Quantifizierer, z. B. `*`, `+` oder `?` in einem Muster für reguläre Ausdrücke verwendet werden, gibt die Engine für reguläre Ausdrücke möglicherweise einen Teil der erfolgreichen Teilübereinstimmungen auf und kehrt zu einem zuvor gespeicherten Zustand zurück, um nach einer erfolgreichen Übereinstimmung mit dem gesamten Muster zu suchen. Dieser Prozess wird als Rückverfolgung bezeichnet.

> [!NOTE]
> Weitere Informationen zur Rückverfolgung finden Sie unter [Einzelheiten zum Verhalten regulärer Ausdrücke](../../../docs/standard/base-types/details-of-regular-expression-behavior.md) und [Backtracking](../../../docs/standard/base-types/backtracking-in-regular-expressions.md). Eine ausführliche Erörterung der Rückverfolgung finden Sie in [Optimieren der Leistung regulärer Ausdrücke, Teil II: Steuern der Rückverfolgung](https://blogs.msdn.microsoft.com/bclteam/2010/08/03/optimizing-regular-expression-performance-part-ii-taking-charge-of-backtracking-ron-petrusha/) im BCL-Teamblog.

Durch die Unterstützung des Zurückverfolgens werden reguläre Ausdrücke leistungsstark und flexibel. Außerdem wird die Steuerung der Ausführung der Engine für reguläre Ausdrücke in die Hände der Entwickler von regulären Ausdrücken gelegt. Entwickler sind sich dieser Verantwortung oft nicht bewusst und verwenden die Rückverfolgung falsch oder übermäßig. Dies ist einer der Hauptfaktoren für die Beeinträchtigung der Leistung von regulären Ausdrücken. Im ungünstigsten Fall kann sich die Ausführungszeit für jedes zusätzliche Zeichen in der Eingabezeichenfolge verdoppeln. Durch Verwendung der Rückverfolgung ist es tatsächlich leicht, eine programmatische Entsprechung einer Endlosschleife zu erstellen, wenn die Eingabe fast mit dem Muster für reguläre Ausdrücke übereinstimmt. Für die Verarbeitung einer relativ kurzen Eingabezeichenfolge kann die Engine mehrere Stunden oder sogar Tage brauchen.

Leistungseinbußen bei Anwendungen kommen häufig vor, wenn die Rückverfolgung verwendet wird, obwohl diese für eine Übereinstimmung nicht erforderlich ist. Beispielsweise stimmt der reguläre Ausdruck `\b\p{Lu}\w*\b` mit allen Wörtern überein, die mit einem Großbuchstaben beginnen, wie in der folgenden Tabelle dargestellt.

|Muster|BESCHREIBUNG|
|-|-|
|`\b`|Der Vergleich beginnt an einer Wortgrenze.|
|`\p{Lu}`|Übereinstimmung mit einem Großbuchstaben.|
|`\w*`|Übereinstimmung mit keinem oder mehreren Wortzeichen.|
|`\b`|Der Vergleich endet an einer Wortgrenze.|

Da eine Wortgrenze weder mit einem Wortzeichen identisch noch eine Teilmenge eines Wortzeichens ist, ist es nicht möglich, dass die Engine für reguläre Ausdrücke beim Abgleichen von Wortzeichen eine Wortgrenze überschreitet. Das bedeutet, dass das Zurückverfolgen für diesen regulären Ausdruck nie zum Gesamterfolg von Übereinstimmungen beitragen kann – lediglich die Leistung kann beeinträchtigt werden, da die Engine für reguläre Ausdrücke gezwungen wird, den Zustand für jede erfolgreiche vorläufige Übereinstimmung eines Wortzeichens zu speichern.

Wenn Sie feststellen, dass eine Rückverfolgung nicht notwendig ist, können Sie sie mithilfe des Sprachelements `(?>subexpression)` deaktivieren. Im folgenden Beispiel wird eine Eingabezeichenfolge unter Verwendung von zwei regulären Ausdrücken analysiert. Der erste, `\b\p{Lu}\w*\b`, beruht auf Rückverfolgung. Der zweite, `\b\p{Lu}(?>\w*)\b`, deaktiviert die Rückverfolgung. Wie die Ausgabe im Beispiel zeigt, liefern beide dasselbe Ergebnis.

[!code-csharp[Conceptual.RegularExpressions.BestPractices#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/cs/backtrack2.cs#10)]
[!code-vb[Conceptual.RegularExpressions.BestPractices#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/vb/backtrack2.vb#10)]

In vielen Fällen ist das Zurückverfolgen wichtig, um ein Muster für reguläre Ausdrücke mit dem Eingabetext abzugleichen. Eine übermäßige Rückverfolgung kann jedoch die Leistung erheblich beeinträchtigen und den Eindruck erwecken, dass eine Anwendung nicht mehr reagiert. Dies geschieht insbesondere dann, wenn Quantifizierer geschachtelt sind und der Text, der dem äußeren Teilausdruck entspricht, eine Teilmenge des Texts ist, der dem inneren Teilausdruck entspricht.

> [!WARNING]
> Vermeiden Sie übermäßige Rückverfolgung, und verwenden Sie außerdem die Timeoutfunktion, um sicherzustellen, dass eine übermäßige Rückverfolgung die Leistung von regulären Ausdrücken nicht zu sehr beeinträchtigt. Weitere Informationen finden Sie im Abschnitt [Verwenden von Timeoutwerten](#use-time-out-values).

Beispielsweise soll das Muster für reguläre Ausdrücke `^[0-9A-Z]([-.\w]*[0-9A-Z])*\$$` einer Teilenummer entsprechen, die aus mindestens einem alphanumerischen Zeichen besteht. Alle zusätzlichen Zeichen können aus einem alphanumerischen Zeichen, einem Bindestrich, einem Unterstrich oder einem Punkt bestehen. Das letzte Zeichen muss jedoch alphanumerisch sein. Ein Dollarzeichen beendet die Teilenummer. In einigen Fällen kann dieses Muster für reguläre Ausdrücke eine sehr schlechte Leistung aufweisen, da die Quantifizierer geschachtelt sind und der Teilausdruck `[0-9A-Z]` eine Teilmenge des Teilausdrucks `[-.\w]*` ist.

In diesen Fällen können Sie die Leistung regulärer Ausdrücke optimieren, indem Sie die geschachtelten Quantifizierer entfernen und den äußeren Teilausdruck durch eine Lookahead- oder Lookbehindassertion mit einer Breite von 0 ersetzen. Lookahead- und Lookbehindassertionen sind Anker, d. h., sie bewegen nicht den Mauszeiger in der Eingabezeichenfolge, sondern überprüfen in Vorwärts- bzw. Rückwärtsrichtung, ob eine bestimmte Bedingung erfüllt ist. Beispielsweise kann der reguläre Ausdruck für die Teilenummer wie folgt umgeschrieben werden: `^[0-9A-Z][-.\w]*(?<=[0-9A-Z])\$$`. Dieses Muster für den regulären Ausdruck wird entsprechend der folgenden Tabelle definiert.

|Muster|BESCHREIBUNG|
|-------------|-----------------|
|`^`|Beginnt den Vergleich am Anfang der Eingabezeichenfolge.|
|`[0-9A-Z]`|Übereinstimmung mit einem alphanumerischen Zeichen. Die Teilenummer muss aus mindestens diesem Zeichen bestehen.|
|`[-.\w]*`|Übereinstimmung mit keinem oder mehreren Vorkommen eines beliebigen Wortzeichens, eines Bindestrichs oder eines Punkts.|
|`\$`|Übereinstimmung mit einem Dollarzeichen.|
|`(?<=[0-9A-Z])`|Lookahead-Überprüfung am beendenden Dollarzeichen, um sicherzustellen, dass das vorherige Zeichen alphanumerisch ist.|
|`$`|Ende des Abgleichs am Ende der Eingabezeichenfolge.|

Im folgenden Beispiel wird die Verwendung dieses regulären Ausdrucks veranschaulicht, um ein Array abzugleichen, das mögliche Teilenummern enthält.

[!code-csharp[Conceptual.RegularExpressions.BestPractices#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/cs/backtrack4.cs#11)]
[!code-vb[Conceptual.RegularExpressions.BestPractices#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/vb/backtrack4.vb#11)]

Die Sprache für reguläre Ausdrücke in .NET beinhaltet die folgenden Sprachelemente, die Sie verwenden können, um geschachtelte Quantifizierer zu vermeiden. Weitere Informationen finden Sie unter [Gruppierungskonstrukte](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).

|Sprachelement|BESCHREIBUNG|
|----------------------|-----------------|
|`(?=` `subexpression` `)`|Positives Lookahead mit einer Breite von 0. Lookahead-Überprüfung für die aktuelle Position, um zu ermitteln, ob `subexpression` mit der Eingabezeichenfolge übereinstimmt.|
|`(?!` `subexpression` `)`|Negatives Lookahead mit einer Breite von 0. Lookahead-Überprüfung für die aktuelle Position, um zu ermitteln, ob `subexpression` nicht mit der Eingabezeichenfolge übereinstimmt.|
|`(?<=` `subexpression` `)`|Positives Lookbehind mit einer Breite von 0. Lookbehind-Überprüfung für die aktuelle Position, um zu ermitteln, ob `subexpression` mit der Eingabezeichenfolge übereinstimmt.|
|`(?<!` `subexpression` `)`|Negatives Lookbehind mit einer Breite von 0. Lookbehind-Überprüfung für die aktuelle Position, um zu ermitteln, ob `subexpression` nicht mit der Eingabezeichenfolge übereinstimmt.|

## <a name="use-time-out-values"></a>Verwenden von Timeoutwerten

Wenn Ihre regulären Ausdrücke Eingaben verarbeiten, die annähernd mit dem Muster des regulären Ausdrucks übereinstimmen, wird häufig übermäßige Rückverfolgung verwendet. Dies beeinträchtigt die Leistung signifikant. Sie sollten die Verwendung der Rückverfolgung sorgfältig abwägen und den regulären Ausdruck mit annähernd übereinstimmenden Eingaben testen. Legen Sie darüber hinaus einen Timeoutwert fest, um ggf. die Beeinträchtigung durch übermäßige Rückverfolgung zu minimieren.

Das Timeoutintervall des regulären Ausdrucks definiert den Zeitraum bis zum Timeout, für den die Engine für reguläre Ausdrücke nach einer einzelnen Übereinstimmung sucht. Das standardmäßige Timeoutintervall ist <xref:System.Text.RegularExpressions.Regex.InfiniteMatchTimeout?displayProperty=nameWithType>. Dies bedeutet, dass für den reguläre Ausdruck kein Timeout erfolgt. Sie können diesen Wert folgendermaßen überschreiben und ein Timeoutintervall definieren:

- Stellen Sie beim Instanziieren eines <xref:System.Text.RegularExpressions.Regex>-Objekts einen Timeoutwert bereit, indem Sie den <xref:System.Text.RegularExpressions.Regex.%23ctor%28System.String%2CSystem.Text.RegularExpressions.RegexOptions%2CSystem.TimeSpan%29?displayProperty=nameWithType>-Konstruktor aufrufen.

- Rufen Sie eine statische Methode für einen Musterabgleich auf, wie z. B. <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%2CSystem.TimeSpan%29?displayProperty=nameWithType> oder <xref:System.Text.RegularExpressions.Regex.Replace%28System.String%2CSystem.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%2CSystem.TimeSpan%29?displayProperty=nameWithType>, die einen `matchTimeout`-Parameter einschließt.

- Für kompilierte reguläre Ausdrücke, die durch Aufrufen der <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType>-Methode erstellt werden, indem der Konstruktor mit dem Parametertyp <xref:System.TimeSpan> aufgerufen wird.

Wenn Sie ein Timeoutintervall definiert haben und am Ende dieses Intervalls keine Übereinstimmung gefunden wird, löst die Methode des regulären Ausdrucks eine <xref:System.Text.RegularExpressions.RegexMatchTimeoutException>-Ausnahme aus. In Ihrem Ausnahmehandler können Sie auswählen, dass erneut ein Abgleich mit einem längeren Timeoutintervall versucht wird, dass der Versuch abgebrochen und davon ausgegangen wird, dass keine Übereinstimmung vorhanden ist, oder dass der Versuch abgebrochen und die Ausnahmeinformationen für eine zukünftige Analyse protokolliert werden.

Im folgenden Beispiel wird eine `GetWordData`-Methode definiert, die einen regulären Ausdruck mit einem Timeoutintervall von 350 Millisekunden instanziiert, um für ein Textdokument die Anzahl der Wörter und die durchschnittliche Anzahl der Zeichen pro Wort zu berechnen. Wenn ein Timout für den entsprechenden Vorgang erfolgt, wird das Timeoutintervall um 350 Millisekunden erhöht und das <xref:System.Text.RegularExpressions.Regex>-Objekt erneut instanziiert. Wenn das neue Timeoutintervall 1 Sekunde übersteigt, löst die Methode für den Aufrufer erneut eine Ausnahme aus.

[!code-csharp[Conceptual.RegularExpressions.BestPractices#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/cs/timeout1.cs#12)]
[!code-vb[Conceptual.RegularExpressions.BestPractices#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/vb/timeout1.vb#12)]

## <a name="capture-only-when-necessary"></a>Erfassungen nur bei Bedarf

Reguläre Ausdrücke in .NET unterstützen eine Reihe von Gruppierungskonstrukten, mit denen Sie ein Muster für reguläre Ausdrücke in einen Teilausdruck oder in mehrere Teilausdrücke gruppieren können. Die am häufigsten verwendeten Gruppierungskonstrukte in der .NET-Sprache für reguläre Ausdrücke sind `(`*Teilausdruck*`)` zum Definieren einer nummerierten Erfassungsgruppe und `(?<`*Name*`>`*Teilausdruck*`)` zum Definieren einer benannten Erfassungsgruppe. Gruppierungskonstrukte sind wichtig für das Erstellen von Rückverweisen und für das Definieren eines Teilausdrucks, auf den ein Quantifizierer angewendet wird.

Die Verwendung dieser Sprachelemente hat jedoch auch Nachteile. Sie führen dazu, dass das von der <xref:System.Text.RegularExpressions.GroupCollection>-Eigenschaft zurückgegebene <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType>-Objekt mit den neuesten unbenannten oder benannten Erfassungen aufgefüllt wird. Wenn ein einzelnes Gruppierungskonstrukt mehrere Teilzeichenfolgen in der Eingabezeichenfolge erfasst hat, wird auch das von der <xref:System.Text.RegularExpressions.CaptureCollection>-Eigenschaft einer bestimmten Erfassungsgruppe zurückgegebene <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType>-Objekt mit mehreren <xref:System.Text.RegularExpressions.Capture>-Objekten aufgefüllt.

Gruppierungskonstrukte werden häufig nur in einem regulären Ausdruck verwendet, damit Quantifizierer auf sie angewendet werden können. Die von diesen Teilausdrücken erfassten Gruppen werden später nicht verwendet. Beispielsweise soll der reguläre Ausdruck `\b(\w+[;,]?\s?)+[.?!]` einen vollständigen Satz erfassen. In der folgenden Tabelle werden die Sprachelemente in diesem regulären Ausdrucksmuster und ihre Auswirkungen auf die <xref:System.Text.RegularExpressions.Match>-Auflistung und die <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType>-Auflistung des <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType>-Objekts beschrieben.

|Muster|BESCHREIBUNG|
|-------------|-----------------|
|`\b`|Der Vergleich beginnt an einer Wortgrenze.|
|`\w+`|Übereinstimmung mit mindestens einem Wortzeichen.|
|`[;,]?`|Übereinstimmung mit keinem oder einem Komma oder Semikolon.|
|`\s?`|Übereinstimmung mit keinem oder einem Leerzeichen.|
|`(\w+[;,]?\s?)+`|Übereinstimmung mit einem oder mehreren Vorkommen eines oder mehrerer Wortzeichen, gefolgt von einem optionalen Komma oder Semikolon, gefolgt von einem optionalen Leerzeichen. Hiermit wird die erste Erfassungsgruppe definiert. Dies ist erforderlich, damit die Kombination mehrerer Wortzeichen (d. h. ein Wort) gefolgt von einem optionalen Interpunktionssymbol wiederholt wird, bis die Engine für reguläre Ausdrücke das Ende eines Satzes erreicht.|
|`[.?!]`|Übereinstimmung mit einem Punkt, Fragezeichen oder Ausrufezeichen.|

Wie im folgenden Beispiel gezeigt, werden das <xref:System.Text.RegularExpressions.GroupCollection>-Objekt und das <xref:System.Text.RegularExpressions.CaptureCollection>-Objekt mit Erfassungen aus der Übereinstimmungssuche aufgefüllt, wenn eine Übereinstimmung gefunden wird. In diesem Fall wird die Erfassungsgruppe `(\w+[;,]?\s?)` angegeben, damit der `+`-Quantifizierer darauf angewendet werden kann, wodurch das Muster für reguläre Ausdrücke Übereinstimmungen für jedes Wort in einem Satz erfassen kann. Andernfalls würde es mit dem letzten Wort in einem Satz abgeglichen werden.

[!code-csharp[Conceptual.RegularExpressions.BestPractices#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/cs/group1.cs#8)]
[!code-vb[Conceptual.RegularExpressions.BestPractices#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/vb/group1.vb#8)]

Wenn Sie Teilausdrücke nur verwenden, um Quantifizierer darauf anzuwenden, und den erfassten Text nicht benötigen, sollten Sie Gruppenerfassungen deaktivieren. Zum Beispiel verhindert das Sprachelement `(?:subexpression)`, dass die Gruppe, auf die es angewendet wird, übereinstimmende Teilzeichenfolgen erfasst. Im folgenden Beispiel wird das Muster eines regulären Ausdrucks aus dem vorherigen Beispiel in `\b(?:\w+[;,]?\s?)+[.?!]` geändert. Hiermit wird verhindert, dass die Engine für reguläre Ausdrücke die <xref:System.Text.RegularExpressions.GroupCollection>-Auflistung und die <xref:System.Text.RegularExpressions.CaptureCollection>-Auflistung auffüllt, wie die Ausgabe im Beispiel zeigt.

[!code-csharp[Conceptual.RegularExpressions.BestPractices#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/cs/group2.cs#9)]
[!code-vb[Conceptual.RegularExpressions.BestPractices#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/vb/group2.vb#9)]

Erfassungen können Sie auf eine der folgenden Arten deaktivieren:

- Verwenden Sie das Sprachelement `(?:subexpression)`. Dieses Element verhindert die Erfassung übereinstimmender Teilzeichenfolge in der Gruppe, auf die es angewendet wird. Die Erfassung von Teilzeichenfolgen in geschachtelten Gruppen wird nicht deaktiviert.

- Verwenden Sie die <xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture>-Option. Diese Option deaktiviert alle unbenannten oder impliziten Erfassungen im Muster für reguläre Ausdrücke. Wenn Sie diese Option verwenden, können nur Teilzeichenfolgen erfasst werden, die mit benannten Gruppen übereinstimmen, die mit dem Sprachelement `(?<name>subexpression)` definiert wurden. Das <xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture>-Flag kann an den `options`-Parameter eines <xref:System.Text.RegularExpressions.Regex>-Klassenkonstruktors oder an den `options`-Parameter einer statischen <xref:System.Text.RegularExpressions.Regex> Übereinstimmungsmethode übergeben werden.

- Verwenden Sie die `n`-Option im Sprachelement `(?imnsx)`. Diese Option deaktiviert alle unbenannten oder impliziten Erfassungen ab dem Punkt im Muster für reguläre Ausdrücke, an dem das Element erscheint. Erfassungen werden entweder bis zum Ende des Musters oder so lange deaktiviert, bis die `(-n)`-Option unbenannte oder implizite Erfassungen aktiviert. Weitere Informationen finden Sie unter [Verschiedene Konstrukte](../../../docs/standard/base-types/miscellaneous-constructs-in-regular-expressions.md).

- Verwenden Sie die `n`-Option im Sprachelement `(?imnsx:subexpression)`. Diese Option deaktiviert alle unbenannten oder impliziten Erfassungen in `subexpression`. Erfassungen von allen unbenannten oder impliziten geschachtelten Erfassungsgruppen werden ebenfalls deaktiviert.

## <a name="related-topics"></a>Verwandte Themen

|Titel|BESCHREIBUNG|
|-----------|-----------------|
|[Einzelheiten zum Verhalten regulärer Ausdrücke](../../../docs/standard/base-types/details-of-regular-expression-behavior.md)|Überprüft die Implementierung der Engine für reguläre Ausdrücke in .NET. Schwerpunkt dieses Themas ist die Flexibilität regulärer Ausdrücke. Außerdem wird die Verantwortung des Entwicklers erläutert, das effiziente und stabile Ausführen der Engine für reguläre Ausdrücke sicherzustellen.|
|[Backtracking](../../../docs/standard/base-types/backtracking-in-regular-expressions.md)|Erläutert die Rückverfolgung und deren Auswirkungen auf die Leistung von regulären Ausdrücken. Zudem werden Sprachelemente beschrieben, die Alternativen zum Zurückverfolgen bieten.|
|[Sprachelemente für reguläre Ausdrücke – Kurzübersicht](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)|Beschreibt die Elemente der Sprache für reguläre Ausdrücke in .NET und enthält Links zu ausführlichen Dokumentationen für jedes Sprachelement.|
