---
title: "Einzelheiten zum Verhalten regul&#228;rer Ausdr&#252;cke | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Reguläre Ausdrücke, Verhalten"
  - "Reguläre Ausdrücke von .NET Framework, Verhalten"
ms.assetid: 0ee1a6b8-caac-41d2-917f-d35570021b10
caps.latest.revision: 27
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 27
---
# Einzelheiten zum Verhalten regul&#228;rer Ausdr&#252;cke
Das .NET Framework\-Modul für reguläre Ausdrücke \(Suchmodul\) ist ein zurückverfolgendes Modul zur Suche mithilfe regulärer Ausdrücke, das ein herkömmliches NFA \(Nondeterministic Finite Automaton\)\-Modul beinhaltet, wie es auch von Perl, Python, Emacs und Tcl verwendet wird.  Dadurch unterscheidet es sich von schnelleren, aber vom Umfang her beschränkten DFA \(Deterministic Finite Automaton\)\-Modulen, die reine reguläre Ausdrücke verwenden, wie z. B. awk, egrep oder lex.  Es unterscheidet sie außerdem von standardisierten, aber langsameren POSIX NFAs.  Im folgenden Abschnitt werden die drei Typen von Modulen für reguläre Ausdrücke beschrieben, und es wird erklärt, warum reguläre Ausdrücke in .NET Framework mit einem herkömmlichen NFA\-Modul implementiert werden.  
  
## Vorteile des NFA\-Moduls  
 Wenn von DFA\-Modulen Mustervergleiche ausgeführt werden, wird deren Verarbeitungsreihenfolge durch die Eingabezeichenfolge bestimmt.  Das Modul beginnt am Anfang der Eingabezeichenfolge und setzt den Vorgang schrittweise fort, um zu bestimmen, ob das nächste Zeichen dem Muster des regulären Ausdrucks entspricht.  Es kann gewährleistet werden, dass eine Übereinstimmung mit der längstmöglichen Zeichenfolge gefunden wird.  Da niemals dasselbe Zeichen zweimal getestet wird, unterstützen DFA\-Module keine Rückverfolgung.  Da jedoch DFA\-Module nur endliche Zustände enthalten, können sie keine Muster mit Rückverweisen finden. Teilausdrücke werden auch nicht gefunden, da DFA\-Module keine explizite Erweiterung erstellen.  
  
 Im Gegensatz zu DFA\-Modulen wird bei Mustervergleichen durch herkömmliche NFA\-Module die Verarbeitungsreihenfolge durch das Muster des regulären Ausdrucks bestimmt.  Beim Verarbeiten eines bestimmten Sprachelements verwendet das Modul gierige Vergleiche, d. h., es wird eine Übereinstimmung mit einem möglichst großen Teil der Eingabezeichenfolge gesucht.  Jedoch wird auch der Zustand gespeichert, nachdem erfolgreich eine Übereinstimmung mit einem Teilausdruck gefunden wurde.  Wenn keine Übereinstimmung gefunden wurde, kann das Modul zu einem gespeicherten Zustand zurückkehren, um weitere Vergleiche auszuführen.  Dieser Prozess, bei dem eine erfolgreiche Teilausdrucksuche verlassen wird, um spätere Sprachelemente im regulären Ausdruck ebenfalls finden zu können, wird als Rückverfolgung oder *Backtracking* bezeichnet.  NFA\-Module verwenden die Rückverfolgung, um alle möglichen Erweiterungen eines regulären Ausdrucks in einer bestimmten Reihenfolge zu testen und die erste Übereinstimmung zu akzeptieren.  Da ein herkömmliches NFA\-Modul im Falle eines erfolgreichen Suchergebnisses eine spezielle Erweiterung eines regulären Ausdrucks erstellt, können Teilausdrücke ausgewertet und somit Übereinstimmungen mit Rückverweisen gefunden werden.  Allerdings kann ein herkömmliches NFA aufgrund der Rückverfolgung den gleichen Zustand über unterschiedliche Pfade mehrmals erreichen.  Das Resultat ist im ungünstigsten Fall ein exponentiell verlangsamtes Laufzeitverhalten.  Da von einem herkömmlichen NFA\-Modul das erste Suchergebnis akzeptiert wird, bleiben weitere \(möglicherweise längere\) Übereinstimmungen möglicherweise unentdeckt.  
  
 POSIX\-NFA\-Module arbeiten wie herkömmliche NFA\-Module, jedoch mit einem Unterschied: Die Rückverfolgung wird so lange fortgesetzt, bis gewährleistet ist, dass die längstmögliche Übereinstimmung gefunden wurde.  Aus diesem Grund ist ein POSIX\-NFA\-Modul langsamer als ein herkömmliches NFA\-Modul. Außerdem ist es bei Verwendung eines POSIX\-NFA\-Moduls nicht möglich, durch eine Änderung der Reihenfolge bei der Rückwärtssuche einem kürzeren Suchergebnis Vorrang vor einem längeren zu geben.  
  
 Programmierer bevorzugen meist herkömmliche NFA\-Module, da sie eine umfassendere Kontrolle des Zeichenfolgenvergleichs bieten als DFA\- oder POSIX\-NFA\-Module.  Obwohl sie im ungünstigsten Fall langsam sind, kann durch die Verwendung von Suchmustern, die Mehrdeutigkeiten vermeiden und das Zurückverfolgen einschränken, ein lineares oder polynomisches Laufzeitverhalten erreicht werden.  Anders ausgedrückt werden bei NFA\-Modulen zwar Kompromisse bei der Leistung zugunsten von Funktionalität und Flexibilität eingegangen, doch bieten sie meist eine gute bis akzeptable Leistung, wenn ein regulärer Ausdruck gut geschrieben wurde und Fälle vermieden werden, in denen die Rückverfolgung die Leistung exponentiell beeinträchtigt.  
  
> [!NOTE]
>  Weitere Informationen über die durch eine übermäßige Rückverfolgung verursachten Leistungseinbußen sowie über Methoden, einen regulären Ausdruck zur Umgehung dieses Problems zu erstellen, finden Sie unter [Backtracking](../../../docs/standard/base-types/backtracking-in-regular-expressions.md).  
  
## Funktionen des .NET Framework\-Moduls  
 Um die Vorteile eines herkömmlichen NFA\-Moduls voll ausschöpfen zu können, enthält das .NET Framework\-Modul für reguläre Ausdrücke einen vollständigen Satz von Konstrukten, mit deren Hilfe Programmierer das Rückverfolgungsmodul steuern können.  Diese Konstrukte können dazu verwendet werden, Übereinstimmungen schneller zu finden oder spezielle Erweiterungen eines regulären Ausdrucks anderen vorzuziehen.  
  
 Weitere Funktionen des .NET Framework\-Moduls für reguläre Ausdrücke:  
  
-   Verzögerte Quantifizierer: `??`, `*?`, `+?`, `{`*n*`,`*m*`}?`.  Diese Konstrukte veranlassen das Rückverfolgungsmodul, zuerst die kleinste Anzahl von Wiederholungen zu durchsuchen.  Im Gegensatz dazu wird bei "gierigen" Quantifizierern die maximale Anzahl an Wiederholungen zuerst berücksichtigt.  Das folgende Beispiel veranschaulicht die Unterschiede zwischen beiden:  Mit einem regulären Ausdruck wird nach einem Satz gesucht, der auf eine Zahl endet, und zum Erfassen dieser Zahl ist eine Erfassungsgruppe vorgesehen.  Der reguläre Ausdruck `.+(\d+)\.` schließt den gierigen Quantifizierer `.+` ein, der bewirkt, dass das Modul für reguläre Ausdrücke nur die letzte Ziffer der Zahl erfasst.  Im Gegensatz dazu schließt der reguläre Ausdruck `.+?(\d+)\.` den verzögerten Quantifizierer `.+?` ein, der bewirkt, dass das Modul für reguläre Ausdrücke die gesamte Zahl erfasst.  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/lazy1.cs#1)]
     [!code-vb[Conceptual.RegularExpressions.Design#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/lazy1.vb#1)]  
  
     Die gierigen und trägen Versionen dieses regulären Ausdrucks sind wie in der folgenden Tabelle gezeigt definiert.\`  
  
    |Muster|**Beschreibung**|  
    |------------|----------------------|  
    |`.+` \(gieriger Quantifizierer\)|Sucht nach mindestens einem Vorkommen eines beliebigen Zeichens.  Dadurch sucht das Modul für reguläre Ausdrücke nach einer Übereinstimmung mit der gesamten Zeichenfolge und führt dann bei Bedarf die Rückverfolgung aus, um im Rest des Musters eine Übereinstimmung zu finden.|  
    |`.+?` \(träger Quantifizierer\)|Sucht nach mindestens einem Vorkommen eines beliebigen Zeichens, findet jedoch eine möglichst kurze Übereinstimmung.|  
    |`(\d+)`|Sucht nach mindestens einem numerischen Zeichen und weist dieses der ersten Erfassungsgruppe zu.|  
    |`\.`|Entsprechung für einen Punkt finden.|  
  
     Weitere Informationen zu trägen Quantifizierern finden Sie unter [Quantifizierer](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md).  
  
-   Positives Lookahead: `(?=`*subexpression*`)`.  Diese Funktion ermöglicht es dem Rückverfolgungsmodul, nach dem Finden eines Teilausdrucks zu derselben Textstelle zurückzukehren.  Um einen Text vollständig zu durchsuchen, empfiehlt es sich, unterschiedliche Muster von derselben Startposition aus anzuwenden.  Zudem kann das Modul überprüfen, ob eine Teilzeichenfolge am Ende der Übereinstimmung vorhanden ist, ohne dass die Teilzeichenfolge im übereinstimmenden Text enthalten ist.  Im folgenden Beispiel werden die Wörter in einem Satz, denen keine Interpunktionszeichen folgen, mithilfe eines positiven Lookaheads extrahiert.  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/lookahead1.cs#2)]
     [!code-vb[Conceptual.RegularExpressions.Design#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/lookahead1.vb#2)]  
  
     Der reguläre Ausdruck `\b[A-Z]+\b(?=\P{P})` ist wie in der folgenden Tabelle gezeigt definiert.  
  
    |Muster|**Beschreibung**|  
    |------------|----------------------|  
    |`\b`|Der Vergleich beginnt an einer Wortgrenze.|  
    |`[A-Z]+`|Sucht ein\- oder mehrmals nach einer Übereinstimmung mit einem beliebigen Buchstabenzeichen.  Da die <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=fullName>\-Methode mit der <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>\-Option aufgerufen wird, wird beim Vergleich die Groß\-\/Kleinschreibung nicht beachtet.|  
    |`\b`|Der Vergleich endet an einer Wortgrenze.|  
    |`(?=\P{P})`|Lookahead, um zu bestimmen, ob es sich beim nächsten Zeichen um ein Interpunktionszeichen handelt.  Andernfalls ist der Vergleich erfolgreich.|  
  
     Weitere Informationen zu positiven Lookaheadassertions finden Sie unter [Gruppierungskonstrukte](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
-   Negatives Lookahead: `(?!`*subexpression*`)`.  Diese Funktion ermöglicht es, nur dann eine Übereinstimmung mit einem Ausdruck zu erhalten, wenn ein Teilausdruck kein Ergebnis liefert.  Dies ist bei einer verzweigten Suche besonders effektiv, da oftmals einfacher ist, einen Ausdruck für einen auszuschließenden Fall anzugeben als einen Ausdruck für Fälle, die eingeschlossen werden sollen.  Beispielsweise ist es schwierig, einen Ausdruck für Wörter zu schreiben, die nicht mit "un" beginnen.  Im folgenden Beispiel erfolgt der Ausschluss mithilfe eines negativen Lookaheads.  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/lookahead2.cs#3)]
     [!code-vb[Conceptual.RegularExpressions.Design#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/lookahead2.vb#3)]  
  
     Das Muster für reguläre Ausdrücke `\b(?!non)\w+\b` wird entsprechend der folgenden Tabelle definiert:  
  
    |Muster|**Beschreibung**|  
    |------------|----------------------|  
    |`\b`|Der Vergleich beginnt an einer Wortgrenze.|  
    |`(?!non)`|Lookahead, um sicherzustellen, dass die aktuelle Zeichenfolge nicht mit "non" beginnt.  Andernfalls wird keine Übereinstimmung gefunden.|  
    |`(\w+)`|Übereinstimmung mit mindestens einem Wortzeichen.|  
    |`\b`|Der Vergleich endet an einer Wortgrenze.|  
  
     Weitere Informationen zu negativen Lookaheadassertions finden Sie unter [Gruppierungskonstrukte](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
-   Bedingte Auswertung: `(?(`*expression*`)`*yes* `|` *no* `)` und `(?(`*name*`)`*yes* `|` *no* `)`, wobei *expression* einen zu suchenden Teilausdruck, *name* den Namen einer Erfassungsgruppe, *yes* die zu suchende Zeichenfolge, wenn *expression* gefunden wurde, oder *name* eine gültige, nicht leere Erfassungsgruppe ist und *no* den zu suchenden Teilausdruck ist, wenn *expression* nicht gefunden wurde, oder *name* keine gültige, nicht leere Erfassungsgruppe ist.  Mit dieser Funktion kann das Modul je nach Ergebnis einer vorherigen Teilausdrucksuche oder Ergebnis einer Assertion mit einer Breite von 0 \(null\) mit mehr als einem Alternativmuster suchen.  Dies lässt eine leistungsstärkere Form von Rückverfolgung zu, die es beispielsweise erlaubt, einen Teilausdruck auf der Grundlage davon zu suchen, ob eine Übereinstimmung mit einem vorherigen Teilausdruck gefunden wurde.  Der reguläre Ausdruck im folgenden Beispiel stimmt mit Absätzen überein, die für die öffentliche und die interne Verwendung vorgesehen sind.  Absätze, die nur für die interne Verwendung vorgesehen sind, beginnen mit einem `<PRIVATE>`\-Tag.  Das Muster für reguläre Ausdrücke `^(?<Pvt>\<PRIVATE\>\s)?(?(Pvt)((\w+\p{P}?\s)+)|((\w+\p{P}?\s)+))\r?$` weist den Inhalt von Absätzen, die für die öffentliche und interne Verwendung vorgesehen sind, mithilfe einer bedingten Auswertung zu, um Erfassungsgruppen zu trennen.  Diese Absätze können dann unterschiedlich behandelt werden.  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/conditional1.cs#4)]
     [!code-vb[Conceptual.RegularExpressions.Design#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/conditional1.vb#4)]  
  
     Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.  
  
    |Muster|**Beschreibung**|  
    |------------|----------------------|  
    |`^`|Beginnt die Suche am Anfang einer Zeile.|  
    |`(?<Pvt>\<PRIVATE\>\s)?`|Sucht nach 0 oder 1 Vorkommen der Zeichenfolge `<PRIVATE>`, gefolgt von einem Leerzeichen.  Weist die Übereinstimmung der Erfassungsgruppe `Pvt` zu.|  
    |`(?(Pvt)((\w+\p{P}?\s)+)`|Wenn die Erfassungsgruppe `Pvt` vorhanden ist, wird nach einem oder mehreren Vorkommen eines oder mehrerer Wortzeichen gesucht, denen 0 oder 1 Interpunktionszeichen und dann ein Leerzeichen folgen.  Weist Sie die Teilzeichenfolge der ersten Erfassungsgruppe zu.|  
    |`&#124;((\w+\p{P}?\s)+))`|Wenn die Erfassungsgruppe `Pvt` nicht vorhanden ist, wird nach einem oder mehreren Vorkommen eines oder mehrerer Wortzeichen gesucht, denen 0 oder 1 Interpunktionszeichen und dann ein Leerzeichen folgen.  Weist Sie die Teilzeichenfolge der dritten Erfassungsgruppe zu.|  
    |`\r?$`|Sucht nach dem Ende einer Zeile oder dem Ende der Zeichenfolge.|  
  
     \(Weitere Informationen zur bedingten Auswertung finden Sie unter [Alternierungskonstrukte](../../../docs/standard/base-types/alternation-constructs-in-regular-expressions.md).  
  
-   Ausgleichsgruppendefinitionen: `(?<`*name1*`-`*name2*`>` *subexpression*`)`.  Diese Funktion ermöglicht es dem Modul für reguläre Ausdrücke, geschachtelte Konstrukte, z. B. runde Klammern oder öffnende und schließende eckige Klammern, nachzuverfolgen.  Ein Beispiel finden Sie unter [Gruppierungskonstrukte](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
-   Nicht zurückverfolgende Teilausdrücke \(auch als gierige Teilausdrücke bezeichnet\): `(?>`*subexpression*`)`.  Durch diese Funktion wird bei der Rückverfolgung sichergestellt, dass nur die erste Übereinstimmung mit einem Teilausdruck geliefert wird, so als wäre der Teilausdruck unabhängig von dem vollständigen Ausdruck.  Wenn Sie dieses Konstrukt nicht verwenden, kann das Verhalten eines Teilausdrucks durch zurückverfolgende Suchläufe über den längeren Ausdruck beeinflusst werden.  Der reguläre Ausdruck `(a+)\w` stimmt beispielsweise mit einem oder mehreren "a"\-Zeichen sowie einem Wortzeichen überein, das der Sequenz von "a"\-Zeichen folgt, und weist die Sequenz von "a"\-Zeichen der ersten Erfassungsgruppe zu. Wenn das abschließende Zeichen der Eingabezeichenfolge jedoch ebenfalls ein "a" ist, wird es vom Sprachelement `\w` verglichen und nicht in die Erfassungsgruppe aufgenommen.  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/nonbacktracking2.cs#7)]
     [!code-vb[Conceptual.RegularExpressions.Design#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/nonbacktracking2.vb#7)]  
  
     Der reguläre Ausdruck `((?>a+))\w` verhindert dieses Verhalten.  Da alle aufeinander folgenden "a"\-Zeichen ohne Rückverfolgung gefunden werden, sind alle aufeinander folgenden "a"\-Zeichen in der ersten Erfassungsgruppe enthalten.  Wenn dem "a"\-Zeichen nicht mindestens ein weiteres Zeichen folgt, bei dem es sich nicht um "a" handelt, liegt keine Übereinstimmung vor.  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/nonbacktracking1.cs#8)]
     [!code-vb[Conceptual.RegularExpressions.Design#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/nonbacktracking1.vb#8)]  
  
     Weitere Informationen zu nicht zurückverfolgenden Teilausdrücken finden Sie unter [Gruppierungskonstrukte](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
-   Suchen von rechts nach links, das durch Festlegen der <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>\-Option für eine Suchmethode für <xref:System.Text.RegularExpressions.Regex>\-Klassenkonstruktoren oder statische Instanzen angegeben wird.  Diese Funktion eignet sich für die Suche von rechts nach links \(statt von links nach rechts\) oder in Fällen, in denen es effektiver ist, auf der rechten Seite eines Musters mit der Suche zu beginnen.  Wie im folgenden Beispiel veranschaulicht, kann mit Suchen von rechts nach links das Verhalten gieriger Quantifizierer geändert werden.  Im Beispiel werden zwei Suchen nach einem Satz ausgeführt, der auf eine Zahl endet.  Mit der Suche von links nach rechts, für die der gierige Quantifizierer `+` verwendet wird, wird eine der sechs Ziffern im Satz gefunden. Hingegen werden bei der Suche von rechts nach links alle sechs Ziffern gefunden.  Eine Beschreibung des Musters für den regulären Ausdruck finden Sie weiter oben in diesem Abschnitt im Beispiel zur Veranschaulichung träger Quantifizierer.  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/rtl1.cs#6)]
     [!code-vb[Conceptual.RegularExpressions.Design#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/rtl1.vb#6)]  
  
     Weitere Informationen zur Suche von rechts nach links finden Sie unter [Optionen für reguläre Ausdrücke](../../../docs/standard/base-types/regular-expression-options.md).  
  
-   Positives und negatives Lookbehind: `(?<=`*subexpression*`)` für positives Lookbehind und `(?<!`\-*subexpression*`)` für negatives Lookbehind.  Diese Funktion ähnelt dem zuvor in diesem Thema erläuterten Lookahead.  Reguläre Ausdrücke gestatten uneingeschränkte Lookbehinds, da eine vollständige Suche nach Übereinstimmungen von rechts nach links möglich ist.  Positives und negatives Lookbehind können auch verwendet werden, um das Schachteln von Quantifizierern zu vermeiden, wenn der geschachtelte Teilausdruck eine Obermenge eines äußeren Ausdrucks ist.  Reguläre Ausdrücke mit solchen geschachtelten Quantifizierern bieten oft eine schlechte Leistung.  Im folgenden Beispiel wird beispielsweise überprüft, ob eine Zeichenfolge mit einem alphanumerischen Zeichen beginnt und endet und ob ein beliebiges anderes Zeichen in der Zeichenfolge zu einer größeren Teilmenge gehört.  Sie bildet einen Teil des regulären Ausdrucks zum Überprüfen von E\-Mail\-Adressen. Weitere Informationen finden Sie unter [Gewusst wie: Überprüfen, ob Zeichenfolgen ein gültiges E\-Mail\-Format aufweisen](../../../docs/standard/base-types/how-to-verify-that-strings-are-in-valid-email-format.md).  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/lookbehind1.cs#5)]
     [!code-vb[Conceptual.RegularExpressions.Design#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/lookbehind1.vb#5)]  
  
     Der reguläre Ausdruck `^[A-Z0-9]([-!#$%&'.*+/=?^`{}|~\w])*(?<=[A-Z0-9])$` ist wie in der folgenden Tabelle gezeigt definiert.  
  
    |Muster|**Beschreibung**|  
    |------------|----------------------|  
    |`^`|Beginnt die Suche am Anfang der Zeichenfolge.|  
    |`[A-Z0-9]`|Vergleichen Sie numerische oder alphanumerische Zeichen. \(Beim Vergleich wird die Groß\- und Kleinschreibung nicht berücksichtigt.\)|  
    |`([-!#$%&'.*+/=?^`{}&#124;~\w])*`|Übereinstimmung mit keinem oder mehreren Vorkommen eines beliebigen Wortzeichens oder einem der folgenden Zeichen: \-\!, \#, $, % &, '., \*, \+,\/, \=?, ^, \`, {,}, &#124;oder &#124;.|  
    |`(?<=[A-Z0-9])`|Lookbehind für vorheriges Zeichen, das numerisch oder alphanumerisch sein muss. \(Beim Vergleich wird die Groß\- und Kleinschreibung nicht berücksichtigt.\)|  
    |`$`|Beendet die Suche am Ende der Zeichenfolge.|  
  
     Weitere Informationen zu positivem und negativem Lookbehind finden Sie unter [Gruppierungskonstrukte](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
## Verwandte Themen  
  
|Titel|**Beschreibung**|  
|-----------|----------------------|  
|[Backtracking](../../../docs/standard/base-types/backtracking-in-regular-expressions.md)|Informationen über die Verwendung des Backtrackings bei regulären Ausdrücken, um mit Verzweigungen nach alternativen Übereinstimmungen zu suchen.|  
|[Kompilierung und Wiederverwendung](../../../docs/standard/base-types/compilation-and-reuse-in-regular-expressions.md)|Informationen zum Kompilieren und Wiederverwenden von regulären Ausdrücken mit dem Ziel der Leistungsverbesserung.|  
|[Threadsicherheit](../../../docs/standard/base-types/thread-safety-in-regular-expressions.md)|Informationen zur Threadsicherheit bei regulären Ausdrücken und Erläuterungen zur Notwendigkeit eines synchronisierten Zugriffs auf reguläre Ausdrücke.|  
|[Reguläre Ausdrücke von .NET Framework](../../../docs/standard/base-types/regular-expressions.md)|Enthält eine Übersicht über die programmiersprachenbezogenen Aspekte von regulären Ausdrücken.|  
|[Das Objektmodell für reguläre Ausdrücke](../../../docs/standard/base-types/the-regular-expression-object-model.md)|Ausführliche Informationen und Codebeispiele, die die Verwendung von Klassen für reguläre Ausdrücke veranschaulichen.|  
|[Beispiele für reguläre Ausdrücke](../../../docs/standard/base-types/regular-expression-examples.md)|Einige Codebeispiele, die die Verwendung regulärer Ausdrücke in üblichen Anwendungen veranschaulichen.|  
|[Sprachelemente für reguläre Ausdrücke – Kurzübersicht](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)|Informationen zu Zeichensatz, Operatoren und Konstrukten, mit denen Sie reguläre Ausdrücke definieren können.|  
  
## Verweis  
 <xref:System.Text.RegularExpressions?displayProperty=fullName>