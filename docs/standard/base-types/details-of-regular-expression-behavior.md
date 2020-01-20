---
title: Verhalten regulärer Ausdrücke
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regular expressions, behavior
- .NET Framework regular expressions, behavior
ms.assetid: 0ee1a6b8-caac-41d2-917f-d35570021b10
ms.openlocfilehash: af812e1e42d57c349e94b5992b768636857d2a0c
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348284"
---
# <a name="details-of-regular-expression-behavior"></a>Einzelheiten zum Verhalten regulärer Ausdrücke

Die .NET Framework-Engine für reguläre Ausdrücke ist eine zurückverfolgende Engine zum Abgleich regulärer Ausdrücke, die eine herkömmliche NFA-Engine (Nondeterministic Finite Automaton) beinhaltet, wie sie beispielsweise auch von Perl, Python, Emacs und Tcl verwendet wird. Dadurch unterscheidet es sich von schnelleren, aber vom Umfang her beschränkten DFA-Engines (Deterministic Finite Automaton), die reine reguläre Ausdrücke verwenden. Diese werden z.B. in awk, egrep oder lex verwendet. Außerdem unterscheidet es sich dadurch von standardisierten, aber langsameren POSIX-NFAs. Im folgenden Abschnitt werden die drei Typen von Engines für reguläre Ausdrücke beschrieben, und es wird erklärt, warum reguläre Ausdrücke in .NET Framework mit einer herkömmlichen NFA-Engine implementiert werden.

## <a name="benefits-of-the-nfa-engine"></a>Vorteile der NFA-Engine

 Wenn DFA-Engines Mustervergleiche durchführen, wird die Verarbeitungsreihenfolge durch die Eingabezeichenfolge gesteuert. Die Engine beginnt am Anfang der Eingabezeichenfolge und geht sequenziell vor, um zu bestimmen, ob das nächste Zeichen mit dem Muster für reguläre Ausdrücke übereinstimmt. So wird garantiert die längstmögliche Zeichenfolge abgeglichen. Da dasselbe Zeichen niemals zweimal getestet wird, unterstützen DFA-Engines keine Rückverfolgung. Da eine DFA-Engine nur einen endlichen Zustand enthält, kann damit kein Muster mit Rückverweisen abgeglichen werden, und weil es keine explizite Erweiterung erstellt, kann es keine Teilausdrücke erfassen.

 Im Gegensatz zu DFA-Engines wird beim Musterabgleich durch herkömmliche NFA-Engines die Verarbeitungsreihenfolge durch das Muster für reguläre Ausdrücke gesteuert. Während der Verarbeitung eines bestimmten Sprachelements verwendet die Engine den gierigen Abgleich, das heißt, sie gleicht so viel wie irgend möglich von der Eingabezeichenfolge ab. Es speichert jedoch auch seinen Zustand, nachdem ein Teilausdruck erfolgreich abgeglichen wurde. Wenn keine Übereinstimmung gefunden wurde, kann die Engine in einen gespeicherten Zustand zurückkehren, um weitere Abgleiche auszuführen. Dieser Prozess, bei dem ein erfolgreicher Teilausdrucksabgleich verlassen wird, um spätere Sprachelemente im regulären Ausdruck ebenfalls finden zu können, wird als „Backtracking“ oder *Rückverfolgung* bezeichnet. NFA-Engines verwenden die Rückverfolgung, um alle möglichen Erweiterungen eines regulären Ausdrucks in einer bestimmten Reihenfolge zu testen und die erste Übereinstimmung zu akzeptieren. Da eine herkömmliche NFA-Engine für einen erfolgreichen Abgleich eine spezielle Erweiterung des regulären Ausdrucks erstellt, können Übereinstimmungen mit Teilausdrücken erfasst und Übereinstimmungen mit Rückverweisen gefunden werden. Allerdings kann ein herkömmliches NFA aufgrund der Rückverfolgung den gleichen Zustand über unterschiedliche Pfade mehrmals erreichen. Das Resultat ist im ungünstigsten Fall ein exponentiell verlangsamtes Laufzeitverhalten. Da von einer herkömmlichen NFA-Engine die erste Übereinstimmung akzeptiert wird, bleiben weitere (möglicherweise längere) Übereinstimmungen unentdeckt.

 POSIX-NFA-Engines arbeiten wie herkömmliche NFA-Engines, jedoch mit einem Unterschied: Die Rückverfolgung wird so lange fortgesetzt, bis gewährleistet ist, dass die längstmögliche Übereinstimmung gefunden wurde. Aus diesem Grund ist eine POSIX-NFA-Engine langsamer als eine herkömmliche NFA-Engine. Außerdem ist es bei Verwendung einer POSIX-NFA-Engine nicht möglich, durch eine Änderung der Reihenfolge bei der Rückverfolgungssuche einer kürzeren Übereinstimmung Vorrang vor einer längeren zu geben.

 Programmierer bevorzugen meist herkömmliche NFA-Engines, da sie eine umfassendere Kontrolle des Zeichenfolgenabgleichs bieten als DFA- oder POSIX-NFA-Engines. Obwohl sie im ungünstigsten Fall langsam sind, kann durch die Verwendung von Suchmustern, die Mehrdeutigkeiten vermeiden und die Rückverfolgung einschränken, ein lineares oder polynomisches Laufzeitverhalten erreicht werden. Anders ausgedrückt werden bei NFA-Engines zwar Kompromisse bei der Leistung zugunsten von Funktionalität und Flexibilität eingegangen, doch bieten sie meist eine gute bis akzeptable Leistung, wenn ein regulärer Ausdruck gut geschrieben wurde und Fälle vermieden werden, in denen die Rückverfolgung die Leistung exponentiell beeinträchtigt.

> [!NOTE]
> Weitere Informationen über die durch eine übermäßige Rückverfolgung verursachten Leistungseinbußen sowie über Methoden, einen regulären Ausdruck zur Umgehung dieses Problems zu erstellen, finden Sie unter [Rückverfolgung](../../../docs/standard/base-types/backtracking-in-regular-expressions.md).

## <a name="net-framework-engine-capabilities"></a>Funktionen der .NET Framework-Engine

 Um die Vorteile eines herkömmlichen NFA-Engine voll ausschöpfen zu können, enthält die .NET Framework-Engine für reguläre Ausdrücke einen vollständigen Satz von Konstrukten, mit deren Hilfe Programmierer die Rückverfolgungs-Engine steuern können. Diese Konstrukte können dazu verwendet werden, Übereinstimmungen schneller zu finden oder spezielle Erweiterungen eines regulären Ausdrucks anderen vorzuziehen.

 Weitere Funktionen der .NET Framework-Engine für reguläre Ausdrücke:

- Verzögerte Quantifizierer: `??`, `*?`, `+?`, `{`*n*`,`*m*`}?`. Diese Konstrukte veranlassen die Rückverfolgungs-Engine, zuerst die kleinste Anzahl von Wiederholungen zu durchsuchen. Im Gegensatz dazu wird bei „gierigen“ Quantifizierern die maximale Anzahl an Wiederholungen zuerst berücksichtigt. Das folgende Beispiel veranschaulicht die Unterschiede zwischen beiden. Mit einem regulären Ausdruck wird nach einem Satz gesucht, der auf eine Zahl endet, und zum Erfassen dieser Zahl ist eine Erfassungsgruppe vorgesehen. Der reguläre Ausdruck `.+(\d+)\.` schließt den gierigen Quantifizierer `.+` ein, der bewirkt, dass die Engine für reguläre Ausdrücke nur die letzte Ziffer der Zahl erfasst. Im Gegensatz dazu schließt der reguläre Ausdruck `.+?(\d+)\.` den trägen Quantifizierer `.+?` ein, der bewirkt, dass die Engine für reguläre Ausdrücke die gesamte Zahl erfasst.

     [!code-csharp[Conceptual.RegularExpressions.Design#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/lazy1.cs#1)]
     [!code-vb[Conceptual.RegularExpressions.Design#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/lazy1.vb#1)]

     Die gierigen und trägen Versionen dieses regulären Ausdrucks werden der folgenden Tabelle entsprechend definiert:

    |Muster|Beschreibung|
    |-------------|-----------------|
    |`.+` (gieriger Quantifizierer)|Sucht nach mindestens einem Vorkommen eines beliebigen Zeichens. Dadurch sucht die Engine für reguläre Ausdrücke nach einer Übereinstimmung mit der gesamten Zeichenfolge und führt dann bei Bedarf die Rückverfolgung aus, um im Rest des Musters eine Übereinstimmung zu finden.|
    |`.+?` (träger Quantifizierer)|Sucht nach mindestens einem Vorkommen eines beliebigen Zeichens, jedoch so wenigen wie möglich.|
    |`(\d+)`|Sucht nach mindestens einem numerischen Zeichen und weist dieses der ersten Erfassungsgruppe zu.|
    |`\.`|Entsprechung für einen Punkt finden.|

     Weitere Informationen zu verzögerten Quantifizierern finden Sie unter [Quantifizierer](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md).

- Positives Lookahead: `(?=`*Teilausdruck*`)`. Diese Funktion ermöglicht es der Rückverfolgungs-Engine, nach dem Finden eines Teilausdrucks zu derselben Textstelle zurückzukehren. Um einen Text vollständig zu durchsuchen, empfiehlt es sich, unterschiedliche Muster von derselben Startposition aus anzuwenden. Zudem kann die Engine überprüfen, ob eine Teilzeichenfolge am Ende der Übereinstimmung vorhanden ist, ohne dass die Teilzeichenfolge im übereinstimmenden Text enthalten ist. Im folgenden Beispiel werden die Wörter in einem Satz, denen keine Interpunktionszeichen folgen, mithilfe eines positiven Lookaheads extrahiert.

     [!code-csharp[Conceptual.RegularExpressions.Design#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/lookahead1.cs#2)]
     [!code-vb[Conceptual.RegularExpressions.Design#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/lookahead1.vb#2)]

     Der reguläre Ausdruck `\b[A-Z]+\b(?=\P{P})` wird entsprechend der Darstellung in der folgenden Tabelle definiert:

    |Muster|Beschreibung|
    |-------------|-----------------|
    |`\b`|Der Vergleich beginnt an einer Wortgrenze.|
    |`[A-Z]+`|Sucht ein- oder mehrmals nach einer Übereinstimmung mit einem beliebigen Buchstabenzeichen. Bei diesem Vergleich wird die Groß-/Kleinschreibung nicht beachtet, da die <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType>-Methode mit der <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType>-Option aufgerufen wird.|
    |`\b`|Der Vergleich endet an einer Wortgrenze.|
    |`(?=\P{P})`|Lookahead, um zu bestimmen, ob es sich beim nächsten Zeichen um ein Interpunktionszeichen handelt. Wenn dies nicht der Fall ist, ist der Abgleich erfolgreich.|

     Weitere Informationen zu positiven Lookaheadassertionen finden Sie unter [Gruppierungskonstrukte](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).

- Negatives Lookahead: `(?!`*Teilausdruck*`)`. Diese Funktion ermöglicht es, nur dann eine Übereinstimmung mit einem Ausdruck zu erhalten, wenn ein Teilausdruck kein Ergebnis liefert. Dies ist beim Bereinigen einer Suche besonders effektiv, da es oftmals einfacher ist, einen Ausdruck für einen auszuschließenden Fall anzugeben als einen Ausdruck für Fälle, die eingeschlossen werden sollen. Beispielsweise ist es schwierig, einen Ausdruck für Wörter zu schreiben, die nicht mit „un“ beginnen. Im folgenden Beispiel erfolgt der Ausschluss mithilfe eines negativen Lookaheads.

     [!code-csharp[Conceptual.RegularExpressions.Design#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/lookahead2.cs#3)]
     [!code-vb[Conceptual.RegularExpressions.Design#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/lookahead2.vb#3)]

     Das Muster für reguläre Ausdrücke `\b(?!non)\w+\b` wird entsprechend der folgenden Tabelle definiert:

    |Muster|Beschreibung|
    |-------------|-----------------|
    |`\b`|Der Vergleich beginnt an einer Wortgrenze.|
    |`(?!non)`|Lookahead, um sicherzustellen, dass die aktuelle Zeichenfolge nicht mit „non“ beginnt. Andernfalls wird keine Übereinstimmung gefunden.|
    |`(\w+)`|Übereinstimmung mit mindestens einem Wortzeichen.|
    |`\b`|Der Vergleich endet an einer Wortgrenze.|

     Weitere Informationen zu negativen Lookaheadassertionen finden Sie unter [Gruppierungskonstrukte](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).

- Bedingte Auswertung: `(?(`*Ausdruck*`)`*ja*`|`*nein*`)` und `(?(`*Name*`)`*ja*`|`*nein*`)`, wobei *Ausdruck* ein zu suchender Teilausdruck ist, *Name* der Name einer Erfassungsgruppe, *ja* die zu suchende Zeichenfolge, wenn *Ausdruck* gefunden wurde oder *Name* eine gültige, nicht leere Erfassungsgruppe ist, und *nein* der zu suchende Teilausdruck ist, wenn *Ausdruck* nicht gefunden wurde oder *Name* keine gültige, nicht leere Erfassungsgruppe ist. Mit dieser Funktion kann die Engine je nach Ergebnis eines vorherigen Teilausdrucksabgleichs oder je nach Ergebnis einer Assertion mit einer Breite von 0 (null) anhand mehrerer Alternativmuster suchen. Dies lässt eine leistungsstärkere Form von Rückverfolgung zu, die es beispielsweise erlaubt, einen Teilausdruck auf der Grundlage davon zu suchen, ob eine Übereinstimmung mit einem vorherigen Teilausdruck gefunden wurde. Der reguläre Ausdruck im folgenden Beispiel gleicht Absätze ab, die sowohl für die öffentliche als auch für die interne Verwendung vorgesehen sind. Absätze, die nur für die interne Verwendung vorgesehen sind, beginnen mit einem `<PRIVATE>`-Tag. Das Muster für reguläre Ausdrücke `^(?<Pvt>\<PRIVATE\>\s)?(?(Pvt)((\w+\p{P}?\s)+)|((\w+\p{P}?\s)+))\r?$` weist den Inhalt von Absätzen, die für die öffentliche und interne Verwendung vorgesehen sind, mithilfe einer bedingten Auswertung zu, um Erfassungsgruppen zu trennen. Diese Absätze können dann unterschiedlich behandelt werden.

     [!code-csharp[Conceptual.RegularExpressions.Design#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/conditional1.cs#4)]
     [!code-vb[Conceptual.RegularExpressions.Design#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/conditional1.vb#4)]

     Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.

    |Muster|Beschreibung|
    |-------------|-----------------|
    |`^`|Beginnt den Abgleich am Anfang einer Zeile.|
    |`(?<Pvt>\<PRIVATE\>\s)?`|Sucht nach 0 oder 1 Vorkommen der Zeichenfolge `<PRIVATE>`, gefolgt von einem Leerzeichen. Weist die Übereinstimmung der Erfassungsgruppe `Pvt` zu.|
    |`(?(Pvt)((\w+\p{P}?\s)+)`|Wenn die Erfassungsgruppe `Pvt` vorhanden ist, wird nach einem oder mehreren Vorkommen eines oder mehrerer Wortzeichen gesucht, denen 0 oder 1 Interpunktionszeichen und dann ein Leerzeichen folgen. Weist die Teilzeichenfolge der ersten Erfassungsgruppe zu.|
    |<code>&#124;((\w+\p{P}?\s)+))</code>|Wenn die Erfassungsgruppe `Pvt` nicht vorhanden ist, wird nach einem oder mehreren Vorkommen eines oder mehrerer Wortzeichen gesucht, denen 0 oder 1 Interpunktionszeichen und dann ein Leerzeichen folgen. Weist die Teilzeichenfolge der dritten Erfassungsgruppe zu.|
    |`\r?$`|Gleicht das Ende einer Zeile oder das Ende der Zeichenfolge ab.|

     Weitere Informationen zur bedingten Auswertung finden Sie unter [Alternierungskonstrukte](../../../docs/standard/base-types/alternation-constructs-in-regular-expressions.md).

- Ausgleichen von Gruppendefinitionen: `(?<`*Name1*`-`*Name2*`>` *Teilausdruck*`)`. Diese Funktion ermöglicht es der Engine für reguläre Ausdrücke, geschachtelte Konstrukte nachzuverfolgen, z.B. runde Klammern oder öffnende und schließende eckige Klammern. Ein Beispiel finden Sie unter [Gruppierungskonstrukte](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).

- Nicht zurückverfolgender Teilausdruck (auch als gierige Teilausdrücke bezeichnet): `(?>`*Teilausdruck*`)`. Durch diese Funktion kann die Rückverfolgungs-Engine sicherstellen, dass nur die erste Übereinstimmung mit einem Teilausdruck geliefert wird, so als wäre der Teilausdruck unabhängig von dem vollständigen Ausdruck. Wenn Sie dieses Konstrukt nicht verwenden, kann das Verhalten eines Teilausdrucks durch Suchläufe mit Rückverfolgung über den längeren Ausdruck beeinflusst werden. Der reguläre Ausdruck `(a+)\w` stimmt beispielsweise mit einem oder mehreren „a“-Zeichen sowie einem Wortzeichen überein, das der Sequenz von „a“-Zeichen folgt, und weist die Sequenz von „a“-Zeichen der ersten Erfassungsgruppe zu. Wenn das abschließende Zeichen der Eingabezeichenfolge jedoch ebenfalls ein „a“ ist, wird es mit dem Sprachelement `\w` abgeglichen und nicht in die Erfassungsgruppe aufgenommen.

     [!code-csharp[Conceptual.RegularExpressions.Design#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/nonbacktracking2.cs#7)]
     [!code-vb[Conceptual.RegularExpressions.Design#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/nonbacktracking2.vb#7)]

     Der reguläre Ausdruck `((?>a+))\w` verhindert dieses Verhalten. Da alle aufeinander folgenden „a“-Zeichen ohne Rückverfolgung abgeglichen werden, sind alle aufeinander folgenden „a“-Zeichen in der ersten Erfassungsgruppe enthalten. Wenn dem „a“-Zeichen nicht mindestens ein weiteres Zeichen folgt, bei dem es sich nicht um „a“ handelt, liegt keine Übereinstimmung vor.

     [!code-csharp[Conceptual.RegularExpressions.Design#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/nonbacktracking1.cs#8)]
     [!code-vb[Conceptual.RegularExpressions.Design#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/nonbacktracking1.vb#8)]

     Weitere Informationen zu nicht zurückverfolgenden Teilausdrücken finden Sie unter [Gruppierungskonstrukte](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).

- Der Abgleich von rechts nach links, der durch Festlegen der <xref:System.Text.RegularExpressions.RegexOptions.RightToLeft?displayProperty=nameWithType>-Option für eine Suchmethode für <xref:System.Text.RegularExpressions.Regex>-Klassenkonstruktoren oder statische Instanzen angegeben wird. Diese Funktion eignet sich für die Suche von rechts nach links (statt von links nach rechts) oder in Fällen, in denen es effektiver ist, auf der rechten Seite eines Musters mit der Suche zu beginnen. Wie im folgenden Beispiel veranschaulicht, kann mit dem Abgleich von rechts nach links das Verhalten gieriger Quantifizierer geändert werden. Im Beispiel werden zwei Suchen nach einem Satz ausgeführt, der auf eine Zahl endet. Mit der Suche von links nach rechts, für die der gierige Quantifizierer `+` verwendet wird, wird eine der sechs Ziffern im Satz gefunden. Hingegen werden bei der Suche von rechts nach links alle sechs Ziffern gefunden. Eine Beschreibung des Musters für reguläre Ausdrücke finden Sie weiter oben in diesem Abschnitt im Beispiel zur Veranschaulichung träger Quantifizierer.

     [!code-csharp[Conceptual.RegularExpressions.Design#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/rtl1.cs#6)]
     [!code-vb[Conceptual.RegularExpressions.Design#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/rtl1.vb#6)]

     Weitere Informationen zum Abgleich von rechts nach links finden Sie unter [Optionen für reguläre Ausdrücke](../../../docs/standard/base-types/regular-expression-options.md).

- Positives und negatives Lookbehind: `(?<=`*Teilausdruck*`)` für positives Lookbehind und `(?<!`*Teilausdruck*`)` für negatives Lookbehind. Diese Funktion ähnelt dem zuvor in diesem Thema erläuterten Lookahead. Reguläre Ausdrücke gestatten uneingeschränkte Lookbehinds, da eine vollständige Suche nach Übereinstimmungen von rechts nach links möglich ist. Positives und negatives Lookbehind können auch verwendet werden, um das Schachteln von Quantifizierern zu vermeiden, wenn der geschachtelte Teilausdruck eine Obermenge eines äußeren Ausdrucks ist. Reguläre Ausdrücke mit solchen geschachtelten Quantifizierern bieten oft eine schlechte Leistung. Im folgenden Beispiel wird z.B. überprüft, ob eine Zeichenfolge mit einem alphanumerischen Zeichen beginnt und endet und ob ein beliebiges anderes Zeichen in der Zeichenfolge zu einer größeren Teilmenge gehört. Sie bildet einen Teil des regulären Ausdrucks zum Überprüfen von E-Mail-Adressen. Weitere Informationen finden Sie unter [Vorgehensweise: Überprüfen, ob Zeichenfolgen ein gültiges E-Mail-Format aufweisen](../../../docs/standard/base-types/how-to-verify-that-strings-are-in-valid-email-format.md).

     [!code-csharp[Conceptual.RegularExpressions.Design#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/lookbehind1.cs#5)]
     [!code-vb[Conceptual.RegularExpressions.Design#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/lookbehind1.vb#5)]

     Der reguläre Ausdruck ``^[A-Z0-9]([-!#$%&'.*+/=?^`{}|~\w])*(?<=[A-Z0-9])$`` wird entsprechend der Darstellung in der folgenden Tabelle definiert:

    |Muster|Beschreibung|
    |-------------|-----------------|
    |`^`|Beginnt die Suche am Anfang der Zeichenfolge.|
    |`[A-Z0-9]`|Übereinstimmung mit beliebigem numerischen oder alphanumerischen Zeichen. (Beim Vergleich wird die Groß-und Kleinschreibung nicht berücksichtigt.)|
    |<code>([-!#$%&'.*+/=?^\`{}&#124;~\w])\*</code>|Übereinstimmung mit 0 („null“) oder mehr Vorkommen eines beliebigen Wortzeichens oder eines der folgenden Zeichen:  -, !, #, $, %, &, ', ., \*, +, /, =, ?, ^, &#96;, {, }, &#124; oder ~.|
    |`(?<=[A-Z0-9])`|Lookbehind für vorheriges Zeichen, das numerisch oder alphanumerisch sein muss. (Beim Vergleich wird die Groß-und Kleinschreibung nicht berücksichtigt.)|
    |`$`|Beendet die Suche am Ende der Zeichenfolge.|

     Weitere Informationen zu positivem und negativem Lookbehind finden Sie unter [Gruppierungskonstrukte](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).

## <a name="related-articles"></a>Verwandte Artikel

|Titel|Beschreibung|
|-----------|-----------------|
|[Backtracking](../../../docs/standard/base-types/backtracking-in-regular-expressions.md)|Informationen über die Verwendung der Rückverfolgung bei regulären Ausdrücken, um mit Verzweigungen nach alternativen Übereinstimmungen zu suchen.|
|[Kompilierung und Wiederverwendung](../../../docs/standard/base-types/compilation-and-reuse-in-regular-expressions.md)|Informationen zum Kompilieren und Wiederverwenden regulärer Ausdrücke mit dem Ziel der Leistungsverbesserung.|
|[Threadsicherheit](../../../docs/standard/base-types/thread-safety-in-regular-expressions.md)|Informationen zur Threadsicherheit bei regulären Ausdrücken und Erläuterungen zur Notwendigkeit eines synchronisierten Zugriffs auf Objekte in regulären Ausdrücken.|
|[Reguläre Ausdrücke von .NET Framework](../../../docs/standard/base-types/regular-expressions.md)|Übersicht über die programmiersprachenbezogenen Aspekte von regulären Ausdrücken.|
|[Das Objektmodell für reguläre Ausdrücke](../../../docs/standard/base-types/the-regular-expression-object-model.md)|Informationen und Codebeispiele, die die Verwendung von Klassen für reguläre Ausdrücke veranschaulichen.|
|[Beispiele für reguläre Ausdrücke](../../../docs/standard/base-types/regular-expression-examples.md)|Codebeispiele, die die Verwendung regulärer Ausdrücke in üblichen Anwendungen veranschaulichen.|
|[Sprachelemente für reguläre Ausdrücke – Kurzübersicht](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)|Informationen zu Zeichensatz, Operatoren und Konstrukten, mit denen Sie reguläre Ausdrücke definieren können.|

## <a name="reference"></a>Referenz

- <xref:System.Text.RegularExpressions?displayProperty=nameWithType>
