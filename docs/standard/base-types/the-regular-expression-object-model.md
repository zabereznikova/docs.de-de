---
title: Das Objektmodell für reguläre Ausdrücke
description: Erfahren Sie mehr über das Objektmodell für reguläre Ausdrücke in .NET. Arbeiten Sie mit der Engine für reguläre Ausdrücke sowie Objekten und Sammlungen zum Durchführen von Vergleichen, Gruppieren und Erfassen.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- searching with regular expressions, backreferences
- Regex class
- Match class
- pattern-matching with regular expressions, backreferences
- .NET Framework regular expressions, classes
- CaptureCollection class
- Group class
- characters [.NET Framework], backreferences
- substrings
- .NET Framework regular expressions, backreferences
- searching with regular expressions, classes
- backreferences
- Capture class
- repeating groups of characters
- MatchCollection class
- parsing text with regular expressions, backreferences
- regular expressions [.NET Framework]
- characters [.NET Framework], regular expressions
- classes [.NET Framework], regular expression
- regular expressions [.NET Framework], classes
- characters [.NET Framework], metacharacters
- metacharacters, regular expression classes
- metacharacters, backreferences
- parsing text with regular expressions, classes
- regular expressions [.NET Framework], backreferences
- strings [.NET Framework], regular expressions
- pattern-matching with regular expressions, classes
- GroupCollection class
ms.assetid: 49a21470-64ca-4b5a-a889-8e24e3c0af7e
ms.openlocfilehash: 43672b85ecb64a15179881ec23c7fadd13d64868
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768052"
---
# <a name="the-regular-expression-object-model"></a>Das Objektmodell für reguläre Ausdrücke
<a name="introduction"></a> In diesem Thema wird das Objektmodell beschrieben, das beim Arbeiten mit regulären .NET-Ausdrücken verwendet wird. Es enthält die folgenden Abschnitte:  
  
- [The Regular Expression Engine (Die Engine für reguläre Ausdrücke)](#Engine)  
  
- [The MatchCollection and Match Objects (Die MatchCollection- und Match-Objekte)](#Match_and_MCollection)  
  
- [The Group Collection (Die Gruppenauflistung)](#GroupCollection)  
  
- [The Captured Group (Die erfasste Gruppe)](#the_captured_group)  
  
- [The Capture Collection (Die Erfassungsauflistung)](#CaptureCollection)  
  
- [The Individual Capture (Die einzelne Erfassung)](#the_individual_capture)  
  
<a name="Engine"></a>
## <a name="the-regular-expression-engine"></a>Die Engine für reguläre Ausdrücke  
 Die Engine für reguläre Ausdrücke in .NET wird durch die <xref:System.Text.RegularExpressions.Regex>-Klasse dargestellt. Die Engine für reguläre Ausdrücke ist für das Analysieren und Kompilieren eines regulären Ausdrucks sowie für das Ausführen von Vorgängen zuständig, die dem Muster eines regulären Ausdrucks mit einer Eingabezeichenfolge entsprechen. Die Engine ist die zentrale Komponente im .NET-Objektmodell für reguläre Ausdrücke.  
  
 Die Engine für reguläre Ausdrücke kann auf zwei verschiedene Arten verwendet werden:  
  
- Durch Aufrufen der statischen Methoden der <xref:System.Text.RegularExpressions.Regex>-Klasse. Die Methodenparameter schließen die Eingabezeichenfolge und das Muster eines regulären Ausdrucks ein. Die Engine für reguläre Ausdrücke führt eine Zwischenspeicherung der regulären Ausdrücke aus, die in statischen Methodenaufrufen verwendet werden. Daher zeigen wiederholte Aufrufe von statischen regulären Ausdrucksmethoden, für die der gleiche reguläre Ausdruck verwendet wird, eine relativ gute Leistung.  
  
- Durch Instanziieren eines <xref:System.Text.RegularExpressions.Regex>-Objekts und durch Übergeben eines regulären Ausdrucks an den Klassenkonstruktor. In diesem Fall ist das <xref:System.Text.RegularExpressions.Regex>-Objekt unveränderlich (schreibgeschützt) und stellt eine Engine für reguläre Ausdrücke dar, das eng an einen einzelnen regulären Ausdruck gekoppelt ist. Da von <xref:System.Text.RegularExpressions.Regex>-Instanzen verwendete reguläre Ausdrücke nicht zwischengespeichert werden, sollte ein <xref:System.Text.RegularExpressions.Regex>-Objekt nicht mehrmals mit dem gleichen regulären Ausdruck instanziiert werden.  
  
 Sie können die Methoden der <xref:System.Text.RegularExpressions.Regex>-Klasse aufrufen, um die folgenden Vorgänge auszuführen:  
  
- Bestimmen, ob eine Zeichenfolge mit einem Muster eines regulären Ausdrucks übereinstimmt.  
  
- Extrahieren einer einzelnen Übereinstimmung oder der ersten Übereinstimmung.  
  
- Extrahieren aller Übereinstimmungen.  
  
- Ersetzen einer übereinstimmenden Teilzeichenfolge.  
  
- Teilen einer einzelnen Zeichenfolge in ein Zeichenfolgenarray.  
  
 Diese Vorgänge werden in den folgenden Abschnitten beschrieben.  
  
### <a name="matching-a-regular-expression-pattern"></a>Vergleich eines Muster eines regulären Ausdrucks  
 Von der <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType>-Methode wird `true` zurückgegeben, falls die Zeichenfolge mit dem Muster übereinstimmt, bzw. `false`, wenn dies nicht der Fall ist. Die <xref:System.Text.RegularExpressions.Regex.IsMatch%2A>-Methode wird häufig dazu verwendet, um Zeichenfolgeneingaben zu überprüfen. Durch den folgende Code wird z. B. sichergestellt, dass eine Zeichenfolge mit einer gültigen Sozialunterstützungsnummer in den USA übereinstimmt.  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/validate1.cs#1)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/validate1.vb#1)]  
  
 Das Muster für reguläre Ausdrücke `^\d{3}-\d{2}-\d{4}$` wird entsprechend der folgenden Tabelle interpretiert:  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`^`|Entsprechung für den Anfang der Eingabezeichenfolge finden.|  
|`\d{3}`|Entsprechung für drei Dezimalstellen finden.|  
|`-`|Entsprechung für einen Bindestrich finden.|  
|`\d{2}`|Entsprechung für zwei Dezimalstellen finden.|  
|`-`|Entsprechung für einen Bindestrich finden.|  
|`\d{4}`|Entsprechung für vier Dezimalstellen finden.|  
|`$`|Entsprechung für das Ende der Eingabezeichenfolge finden.|  
  
### <a name="extracting-a-single-match-or-the-first-match"></a>Extrahieren einer einzelnen Übereinstimmung oder der ersten Übereinstimmung  
 Von der <xref:System.Text.RegularExpressions.Regex.Match%2A?displayProperty=nameWithType>-Methode wird ein <xref:System.Text.RegularExpressions.Match>-Objekt zurückgegeben, das Informationen zur ersten Teilzeichenfolge enthält, die mit einem Muster eines regulären Ausdrucks übereinstimmt. Wenn die `Match.Success`-Eigenschaft `true` zurückgibt und angibt, dass eine Übereinstimmung gefunden wurde, können Sie Informationen zu nachfolgenden Übereinstimmungen abrufen, indem Sie die <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType>-Methode aufrufen. Diese Methodenaufrufe können fortgesetzt werden, bis die `Match.Success`-Eigenschaft `false` zurückgibt. Im folgenden Code wird zum Beispiel mithilfe der <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%29?displayProperty=nameWithType>-Methode das erste Vorkommen eines doppelt vorhandenen Worts in einer Zeichenfolge gesucht. Anschließend wird die <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType>-Methode aufgerufen, um zusätzliche Vorkommen zu suchen. Im Beispiel wird die `Match.Success`-Eigenschaft nach jedem Methodenaufruf überprüft, um zu bestimmen, ob die aktuelle Übereinstimmung erfolgreich war, und ob ein Aufruf der <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType>-Methode folgen soll.  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/match1.cs#2)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/match1.vb#2)]  
  
 Das Muster für reguläre Ausdrücke `\b(\w+)\W+(\1)\b` wird entsprechend der folgenden Tabelle interpretiert:  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`\b`|Beginnt den Vergleich an einer Wortgrenze.|  
|`(\w+)`|Übereinstimmung mit mindestens einem Wortzeichen. Dies ist die erste Erfassungsgruppe.|  
|`\W+`|Entsprechung für mindestens ein Nicht-Wortzeichen finden.|  
|`(\1)`|Entsprechung für die erste erfasste Zeichenfolge finden. Dies ist die zweite Erfassungsgruppe.|  
|`\b`|Beendet den Vergleich an einer Wortgrenze.|  
  
### <a name="extracting-all-matches"></a>Extrahieren aller Übereinstimmungen  
 Von der <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType>-Methode wird ein <xref:System.Text.RegularExpressions.MatchCollection>-Objekt zurückgegeben, das Informationen zu allen Übereinstimmungen enthält, die von der Engine für reguläre Ausdrücke in der Eingabezeichenfolge gefunden wurden. Zum Beispiel kann das vorherige Beispiel neu geschrieben werden, um die <xref:System.Text.RegularExpressions.Regex.Matches%2A>-Methode anstelle der <xref:System.Text.RegularExpressions.Regex.Match%2A>-Methode und der <xref:System.Text.RegularExpressions.Match.NextMatch%2A>-Methode aufzurufen.  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/matches1.cs#3)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/matches1.vb#3)]  
  
### <a name="replacing-a-matched-substring"></a>Ersetzen einer übereinstimmenden Teilzeichenfolge  
 Die <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType>-Methode ersetzt jede Teilzeichenfolge, die mit dem Muster eines regulären Ausdrucks mit einer angegebenen Zeichenfolge oder einem Muster eines regulären Ausdrucks übereinstimmt, und gibt die gesamte Eingabezeichenfolge mit Ersetzungen zurück. Beispielsweise fügt der folgende Code ein US-Währungssymbol vor einer Dezimalzahl in einer Zeichenfolge hinzu.  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/replace1.cs#4)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/replace1.vb#4)]  
  
 Das Muster für reguläre Ausdrücke `\b\d+\.\d{2}\b` wird entsprechend der folgenden Tabelle interpretiert:  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`\b`|Der Vergleich beginnt an einer Wortgrenze.|  
|`\d+`|Entsprechung für mindestens eine Dezimalstelle finden.|  
|`\.`|Entsprechung für einen Punkt finden.|  
|`\d{2}`|Entsprechung für zwei Dezimalstellen finden.|  
|`\b`|Der Vergleich endet an einer Wortgrenze.|  
  
 Das Ersetzungsmuster `$$$&` wird gemäß der Darstellung in der folgenden Tabelle interpretiert.  
  
|Muster|Ersetzungszeichenfolge|  
|-------------|------------------------|  
|`$$`|Das Dollarzeichen ($).|  
|`$&`|Die gesamte abgeglichene Teilzeichenfolge.|  
  
### <a name="splitting-a-single-string-into-an-array-of-strings"></a>Aufteilen einer einzelnen Zeichenfolge in ein Zeichenfolgenarray  
 Mit der <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType>-Methode wird die Eingabezeichenfolge an den Stellen aufgeteilt, die durch eine Übereinstimmung bei einem regulären Ausdruck definiert wurde. Im folgenden Code werden z. B. die Elemente in ein Zeichenfolgenarray in einer nummerierten Liste eingefügt.  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/split1.cs#5)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/split1.vb#5)]  
  
 Das Muster für reguläre Ausdrücke `\b\d{1,2}\.\s` wird entsprechend der folgenden Tabelle interpretiert:  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`\b`|Der Vergleich beginnt an einer Wortgrenze.|  
|`\d{1,2}`|Entsprechung für eine oder zwei Dezimalstellen finden.|  
|`\.`|Entsprechung für einen Punkt finden.|  
|`\s`|Entsprechung für ein Leerraumzeichen finden.|  
  
<a name="Match_and_MCollection"></a>
## <a name="the-matchcollection-and-match-objects"></a>Die MatchCollection- und Match-Objekte  
 Regex-Methoden geben zwei Objekte zurück, die Teil des Objektmodells für einen regulären Ausdruck sind: das <xref:System.Text.RegularExpressions.MatchCollection>-Objekt und das <xref:System.Text.RegularExpressions.Match>-Objekt.  
  
<a name="the_match_collection"></a>
### <a name="the-match-collection"></a>Die Match-Auflistung  
 Die <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType>-Methode gibt ein <xref:System.Text.RegularExpressions.MatchCollection>-Objekt zurück, das <xref:System.Text.RegularExpressions.Match>-Objekte enthält, die alle Übereinstimmungen darstellen, die die Engine für reguläre Ausdrücke gefunden hat, und zwar in der Reihenfolge, in der sie in der Eingabezeichenfolge auftreten. Wenn keine Übereinstimmungen vorhanden sind, gibt die Methode ein <xref:System.Text.RegularExpressions.MatchCollection>-Objekt ohne Member zurück. Die <xref:System.Text.RegularExpressions.MatchCollection.Item%2A?displayProperty=nameWithType>-Eigenschaft ermöglicht den Zugriff auf einzelne Member der Auflistung nach Index, von null bis eins weniger als es dem Wert der <xref:System.Text.RegularExpressions.MatchCollection.Count%2A?displayProperty=nameWithType>-Eigenschaft entspricht. <xref:System.Text.RegularExpressions.MatchCollection.Item%2A> ist der Indexer (in C#) und die Standardeigenschaft der Auflistung (in Visual Basic).  
  
 Der Aufruf der <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType>-Methode füllt standardmäßig das <xref:System.Text.RegularExpressions.MatchCollection>-Objekt mithilfe verzögerter Auswertung auf. Zugriff auf Eigenschaften, die eine vollständig aufgefüllte Auflistung erfordern, z. B. die <xref:System.Text.RegularExpressions.MatchCollection.Count%2A?displayProperty=nameWithType>-Eigenschaft und die <xref:System.Text.RegularExpressions.MatchCollection.Item%2A?displayProperty=nameWithType>-Eigenschaft, führt möglicherweise zu Leistungseinbußen. Daher wird empfohlen, dass Sie auf die Auflistung mit dem <xref:System.Collections.IEnumerator>-Objekt zugreifen, das von der <xref:System.Text.RegularExpressions.MatchCollection.GetEnumerator%2A?displayProperty=nameWithType>-Methode zurückgegeben wird. Einzelne Sprachen stellen Konstrukte bereit, z.B. `For Each` in Visual Basic und `foreach` in C#, die die <xref:System.Collections.IEnumerator>-Schnittstelle der Auflistung umschließen.  
  
 Im folgenden Beispiel wird mithilfe der <xref:System.Text.RegularExpressions.Regex.Matches%28System.String%29?displayProperty=nameWithType>-Methode ein <xref:System.Text.RegularExpressions.MatchCollection>-Objekt mit sämtlichen Übereinstimmungen aufgefüllt, die in einer Eingabezeichenfolge gefunden wurden. Im Beispiel wird die Auflistung aufgeführt, die Übereinstimmungen werden in ein Zeichenfolgenarray kopiert, und die Zeichenpositionen werden in einem ganzzahligen Array erfasst.  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/matchcollection1.cs#6)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/matchcollection1.vb#6)]  
  
<a name="the_match"></a>
### <a name="the-match"></a>Die Übereinstimmung  
 Die <xref:System.Text.RegularExpressions.Match>-Klasse stellt das Ergebnis einer einzelnen regulären Ausdrucksübereinstimmung dar. Es gibt zwei Möglichkeiten für den Zugriff auf <xref:System.Text.RegularExpressions.Match>-Objekte:  
  
- Sie können von dem <xref:System.Text.RegularExpressions.MatchCollection>-Objekt abgerufen werden, das von der <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType>-Methode zurückgegeben wird. Um einzelne <xref:System.Text.RegularExpressions.Match>-Objekte abzurufen, durchlaufen Sie die Auflistung mit einem `foreach`-Konstrukt (in C#) oder einem `For Each`...`Next`-Konstrukt (in Visual Basic), oder rufen Sie mithilfe der <xref:System.Text.RegularExpressions.MatchCollection.Item%2A?displayProperty=nameWithType>-Eigenschaft ein bestimmtes <xref:System.Text.RegularExpressions.Match>-Objekt Objekt nach Index oder Name ab. Sie können auch einzelne <xref:System.Text.RegularExpressions.Match>-Objekte aus der Auflistung abrufen, indem Sie die Auflistung nach dem Index durchlaufen, von 0 (null) bis eins weniger, als es der Anzahl der Objekte in der Auflistung entspricht. Bei dieser Methode wird jedoch keine verzögerte Auswertung genutzt, da dabei auf die <xref:System.Text.RegularExpressions.MatchCollection.Count%2A?displayProperty=nameWithType>-Eigenschaft zugegriffen wird.  
  
     Im folgenden Beispiel werden einzelne <xref:System.Text.RegularExpressions.Match>-Objekte aus einem <xref:System.Text.RegularExpressions.MatchCollection>-Objekt abgerufen, indem die Auflistung mit einem `foreach`- oder `For Each`...`Next`-Konstrukt durchlaufen wird. Der reguläre Ausdruck stimmt mit der Zeichenfolge "abc" in der Eingabezeichenfolge überein.  
  
     [!code-csharp[Conceptual.RegularExpressions.ObjectModel#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/match2.cs#7)]
     [!code-vb[Conceptual.RegularExpressions.ObjectModel#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/match2.vb#7)]  
  
- Durch Aufrufen der <xref:System.Text.RegularExpressions.Regex.Match%2A?displayProperty=nameWithType>-Methode, die ein <xref:System.Text.RegularExpressions.Match>-Objekt zurückgibt, das die erste Übereinstimmung in einer Zeichenfolge oder einem Teil einer Zeichenfolge darstellt. Sie können bestimmen, ob die Übereinstimmung gefunden wurde, indem der Wert der `Match.Success`-Eigenschaft abgerufen wird. Um <xref:System.Text.RegularExpressions.Match>-Objekte abzurufen, die nachfolgende Übereinstimmungen darstellen, rufen Sie die <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType>-Methode wiederholt auf, bis die `Success`-Eigenschaft des zurückgegebenen <xref:System.Text.RegularExpressions.Match>-Objekts `false` ist.  
  
     Im folgenden Beispiel werden die <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%29?displayProperty=nameWithType>-Methode und die <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType>-Methode verwendet, um die Zeichenfolge "abc" in der Eingabezeichenfolge abzugleichen.  
  
     [!code-csharp[Conceptual.RegularExpressions.ObjectModel#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/match3.cs#8)]
     [!code-vb[Conceptual.RegularExpressions.ObjectModel#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/match3.vb#8)]  
  
 Zwei Eigenschaften der <xref:System.Text.RegularExpressions.Match>-Klasse geben Auflistungsobjekte zurück:  
  
- Die <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType>-Eigenschaft gibt ein <xref:System.Text.RegularExpressions.GroupCollection>-Objekt zurück, das Informationen zu den Teilzeichenfolgen enthält, die mit Erfassungsgruppen im Muster eines regulären Ausdrucks übereinstimmen.  
  
- Die `Match.Captures`-Eigenschaft gibt ein <xref:System.Text.RegularExpressions.CaptureCollection>-Objekt mit eingeschränkter Verwendung zurück. Die Auflistung wird nicht für ein <xref:System.Text.RegularExpressions.Match>-Objekt aufgefüllt, dessen `Success`-Eigenschaft `false` ist. Andernfalls enthält es ein einzelnes <xref:System.Text.RegularExpressions.Capture>-Objekt, das über die gleichen Informationen wie das <xref:System.Text.RegularExpressions.Match>-Objekt verfügt.  
  
 Weitere Informationen zu diesen Objekten finden Sie in den Abschnitten [Die Gruppensammlung](#GroupCollection) und [Die Erfassungssammlung](#CaptureCollection) im weiteren Verlauf dieses Themas.  
  
 Zwei zusätzliche Eigenschaften der <xref:System.Text.RegularExpressions.Match>-Klasse stellen Informationen zur Übereinstimmung bereit. Die `Match.Value`-Eigenschaft gibt die Teilzeichenfolge in der Eingabezeichenfolge zurück, die mit dem Muster eines regulären Ausdrucks übereinstimmt. Die `Match.Index`-Eigenschaft gibt die nullbasierte Anfangsposition der entsprechenden Zeichenfolge in der Eingabezeichenfolge zurück.  
  
 Die <xref:System.Text.RegularExpressions.Match>-Klasse besitzt ebenfalls zwei Methoden zum Mustervergleich:  
  
- Die <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType>-Methode sucht die Übereinstimmung nach der Übereinstimmung, die durch das aktuelle <xref:System.Text.RegularExpressions.Match>-Objekt dargestellt wird, und gibt ein <xref:System.Text.RegularExpressions.Match>-Objekt zurück, das diese Übereinstimmung darstellt.  
  
- Die <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType>-Methode führt einen angegebenen Ersetzungsvorgang in der entsprechenden Zeichenfolge aus und gibt das Ergebnis zurück.  
  
 Im folgenden Beispiel werden mit der <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType>-Methode jeder Zahl, die zwei Bruchzahlen enthält, ein $-Symbol und ein Leerzeichen vorangestellt.  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/result1.cs#9)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/result1.vb#9)]  
  
 Das Muster für reguläre Ausdrücke `\b\d+(,\d{3})*\.\d{2}\b` wird entsprechend der folgenden Tabelle definiert:  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`\b`|Der Vergleich beginnt an einer Wortgrenze.|  
|`\d+`|Entsprechung für mindestens eine Dezimalstelle finden.|  
|`(,\d{3})*`|Entsprechung für null oder mehr Vorkommen eines Kommas finden, auf das Dezimalstellen folgen.|  
|`\.`|Entsprechung für das Dezimaltrennzeichenzeichen finden.|  
|`\d{2}`|Entsprechung für zwei Dezimalstellen finden.|  
|`\b`|Der Vergleich endet an einer Wortgrenze.|  
  
 Der Ersatzmuster-`$$ $&` gibt an, dass die übereinstimmende Teilzeichenfolge durch ein Dollarzeichensymbol ($) (das `$$`-Muster), ein Leerzeichen und den Wert der Übereinstimmung (das `$&`-Muster) ersetzt werden soll.  
  
 [Zurück nach oben](#introduction)  
  
<a name="GroupCollection"></a>
## <a name="the-group-collection"></a>Die Gruppenauflistung  
 Die <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType>-Eigenschaft gibt ein <xref:System.Text.RegularExpressions.GroupCollection>-Objekt zurück, das <xref:System.Text.RegularExpressions.Group>-Objekte enthält, die erfasste Gruppen in einer einzelnen Übereinstimmung darstellen. Das erste <xref:System.Text.RegularExpressions.Group>-Objekt in der Auflistung (an Index 0) stellt die gesamte Übereinstimmung dar. Jedes Objekt, das folgt, stellt die Ergebnisse einer einzelnen Erfassungsgruppe dar.  
  
 Sie können einzelne <xref:System.Text.RegularExpressions.Group>-Objekte in der Auflistung mit der <xref:System.Text.RegularExpressions.GroupCollection.Item%2A?displayProperty=nameWithType>-Eigenschaft abrufen. Sie können unbenannte Gruppen durch ihre Ordnungsposition in der Auflistung abrufen und benannte Gruppen entweder nach dem Namen oder nach der Ordnungsposition abrufen. Unbenannte Erfassungen werden zuerst in der Auflistung angezeigt und werden von links nach rechts in der Reihenfolge indiziert, in der sie im Muster eines regulären Ausdrucks angezeigt werden. Benannte Erfassungen werden nach unbenannten Erfassungen von links nach rechts in der Reihenfolge indiziert, in der sie im Muster eines regulären Ausdrucks angezeigt werden. Um festzustellen, welche nummerierten Gruppen in der Auflistung verfügbar sind, die für eine bestimmte Methode für Übereinstimmungen mit regulären Ausdrücken zurückgegeben wird, können Sie die Instanzenmethode <xref:System.Text.RegularExpressions.Regex.GetGroupNumbers%2A?displayProperty=nameWithType> aufrufen. Um festzustellen, welche benannten Gruppen in der Auflistung verfügbar sind, können Sie die Instanzenmethode <xref:System.Text.RegularExpressions.Regex.GetGroupNames%2A?displayProperty=nameWithType> aufrufen. Beide Methoden sind besonders nützlich in Allzweckroutinen, die die von beliebigen regulären Ausdrücken gefundenen Übereinstimmungen analysieren.  
  
 Die <xref:System.Text.RegularExpressions.GroupCollection.Item%2A?displayProperty=nameWithType>-Eigenschaft ist der Indexer der Auflistung in C# und der Standardeigenschaft des Auflistungsobjekts in Visual Basic. Dies bedeutet, dass auf diese einzelnen <xref:System.Text.RegularExpressions.Group>-Objekte wie folgt nach Index (oder nach Name bei benannten Gruppen) zugegriffen werden kann:  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/groupsyntax1.cs#13)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/groupsyntax1.vb#13)]  
  
 Im folgenden Beispiel wird ein regulärer Ausdruck definiert, der Gruppierungskonstrukte verwendet, um Monat, Tag und Jahr eines Datums zu erfassen.  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/groupcollection1.cs#10)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/groupcollection1.vb#10)]  
  
 Das Muster für reguläre Ausdrücke `\b(\w+)\s(\d{1,2}),\s(\d{4})\b` wird entsprechend der folgenden Tabelle definiert:  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`\b`|Der Vergleich beginnt an einer Wortgrenze.|  
|`(\w+)`|Übereinstimmung mit mindestens einem Wortzeichen. Dies ist die erste Erfassungsgruppe.|  
|`\s`|Entsprechung für ein Leerraumzeichen finden.|  
|`(\d{1,2})`|Entsprechung für eine oder zwei Dezimalstellen finden. Dies ist die zweite Erfassungsgruppe.|  
|`,`|Entsprechung für ein Komma finden.|  
|`\s`|Entsprechung für ein Leerraumzeichen finden.|  
|`(\d{4})`|Entsprechung für vier Dezimalstellen finden. Dies ist die dritte Erfassungsgruppe.|  
|`\b`|Beendet den Vergleich an einer Wortgrenze.|  
  
 [Zurück nach oben](#introduction)  
  
<a name="the_captured_group"></a>
## <a name="the-captured-group"></a>Die erfasste Gruppe  
 Die <xref:System.Text.RegularExpressions.Group>-Klasse stellt das von einer einzelnen Erfassungsgruppe erfassten Ergebnis dar. Gruppenobjekte, die die Erfassungsgruppen darstellen, die in einem regulären Ausdruck definiert werden, werden von der <xref:System.Text.RegularExpressions.GroupCollection.Item%2A>-Eigenschaft des <xref:System.Text.RegularExpressions.GroupCollection>-Objekts zurückgegeben, das von der <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType>-Eigenschaft zurückgegeben wurde. Die <xref:System.Text.RegularExpressions.GroupCollection.Item%2A>-Eigenschaft ist der Indexer (in C#) und die Standardeigenschaft (in Visual Basic) <xref:System.Text.RegularExpressions.Group>-Klasse. Sie können auch einzelne Member abrufen, indem Sie die Auflistung mit dem `foreach`- oder dem `For Each`-Konstrukt durchlaufen. Ein Beispiel finden Sie im vorherigen Abschnitt.  
  
 Im folgenden Beispiel werden verschachtelte Gruppierungskonstrukte verwendet, um Teilzeichenfolgen in Gruppen aufzuzeichnen. Das Muster eines regulären Ausdrucks `(a(b))c` stimmt mit der Zeichenfolge "abc" überein. Es weist die Teilzeichenfolgen "ab" der ersten Erfassungsgruppe und die Teilzeichenfolge "b" der zweiten Erfassungsgruppe zu.  
  
 [!code-csharp[RegularExpressions.Classes#6](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Classes/cs/Example.cs#6)]
 [!code-vb[RegularExpressions.Classes#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Classes/vb/Example.vb#6)]  
  
 Im folgenden Codebeispiel werden benannte Gruppierungskonstrukte verwendet, um Teilzeichenfolgen in einer Zeichenfolge zu erfassen, die Daten im Format "DATENNAME:WERT" enthält. Durch den regulären Ausdruck werden diese am Doppelpunkt (:) getrennt.  
  
 [!code-csharp[RegularExpressions.Classes#8](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Classes/cs/Example.cs#8)]
 [!code-vb[RegularExpressions.Classes#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Classes/vb/Example.vb#8)]  
  
 Das Muster für reguläre Ausdrücke `^(?<name>\w+):(?<value>\w+)` wird entsprechend der folgenden Tabelle definiert:  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`^`|Beginnt den Vergleich am Anfang der Eingabezeichenfolge.|  
|`(?<name>\w+)`|Übereinstimmung mit mindestens einem Wortzeichen. Der Name dieser Erfassungsgruppe ist `name`.|  
|`:`|Entsprechung für einen Doppelpunkt finden.|  
|`(?<value>\w+)`|Übereinstimmung mit mindestens einem Wortzeichen. Der Name dieser Erfassungsgruppe ist `value`.|  
  
 Die Eigenschaften der <xref:System.Text.RegularExpressions.Group>-Klasse enthalten Informationen zur erfassten Gruppe: Die `Group.Value`-Eigenschaft enthält die erfasste Teilzeichenfolge, die `Group.Index`-Eigenschaft gibt die Anfangsposition der erfassten Gruppe im Eingabetext an, die `Group.Length`-Eigenschaft enthält die Länge des erfassten Texts, und die `Group.Success`-Eigenschaft gibt an, ob eine Teilzeichenfolge dem Muster entsprach, das durch die Erfassungsgruppe definiert wurde.  
  
 Durch Anwenden von Quantifizierern auf eine Gruppe (weitere Informationen finden Sie unter [Quantifizierer](quantifiers-in-regular-expressions.md)) wird die Beziehung einer Erfassung pro Erfassungsgruppe in zweierlei Hinsicht geändert:  
  
- Wenn der `*`-Quantifizierer oder der `*?`-Quantifizierer (der null oder mehr Übereinstimmungen angibt) für eine Gruppe übernommen wird, verfügt eine Erfassungsgruppe möglicherweise über keine Übereinstimmung in der Eingabezeichenfolge. Wenn kein erfasster Text vorhanden ist, werden die Eigenschaften des <xref:System.Text.RegularExpressions.Group>-Objekts entsprechend der Darstellung in der folgenden Tabelle festgelegt.  
  
    |Gruppeneigenschaft|Wert|  
    |--------------------|-----------|  
    |`Success`|`false`|  
    |`Value`|<xref:System.String.Empty?displayProperty=nameWithType>|  
    |`Length`|0|  
  
     Dies wird im folgenden Beispiel veranschaulicht. Im Muster eines regulären Ausdrucks `aaa(bbb)*ccc` kann es für die erste Erfassungsgruppe (die Teilzeichenfolge "bbb") null oder mehrere Übereinstimmungen geben. Da die Eingabezeichenfolge "aaaccc" dem Muster entspricht, weist die Erfassungsgruppe keine Übereinstimmung auf.  
  
     [!code-csharp[Conceptual.RegularExpressions.ObjectModel#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/nocapture1.cs#11)]
     [!code-vb[Conceptual.RegularExpressions.ObjectModel#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/nocapture1.vb#11)]  
  
- Quantifizierer können mit mehreren Vorkommen eines Musters übereinstimmen, das durch eine Erfassungsgruppe definiert wird. In diesem Fall enthalten die `Value`-Eigenschaft und die `Length`-Eigenschaft eines <xref:System.Text.RegularExpressions.Group>-Objekts nur Informationen zur letzten erfassten Teilzeichenfolge. Der folgende reguläre Ausdruck entspricht z. B. einem einzelnen Satz, der mit einem Punkt endet. Es werden zwei Gruppierungskonstrukte verwendet: Mit dem ersten Konstrukt werden einzelne Wörter mit einem Leerstellenzeichen erfasst und mit dem zweiten einzelne Wörter. Wie die Ausgabe des Beispiels zeigt, erfasst die zweite Erfassungsgruppe nur das letzte Wort, obwohl mit dem regulären Ausdruck ein vollständiger Satz erfasst wird.  
  
     [!code-csharp[Conceptual.RegularExpressions.ObjectModel#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/lastcapture1.cs#12)]
     [!code-vb[Conceptual.RegularExpressions.ObjectModel#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/lastcapture1.vb#12)]  
  
 [Zurück nach oben](#introduction)  
  
<a name="CaptureCollection"></a>
## <a name="the-capture-collection"></a>Die Erfassungsauflistung  
 Das <xref:System.Text.RegularExpressions.Group>-Objekt enthält nur Informationen zur letzten Erfassung. Allerdings sind alle Erfassungen, die von einer Erfassungsgruppe gemacht wurden, nach wie vor über das <xref:System.Text.RegularExpressions.CaptureCollection>-Objekt verfügbar, das von der <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType>-Eigenschaft zurückgegeben wird. Jeder Member der Auflistung ist ein <xref:System.Text.RegularExpressions.Capture>-Objekt, das eine von dieser Erfassungsgruppe gemachte Erfassung darstellt, und zwar in der Reihenfolge, in der sie erfasst wurden (und daher in der Reihenfolge, in der die erfassten Zeichenfolgen von links nach rechts in der Eingabezeichenfolge abgeglichen wurden). Einzelne <xref:System.Text.RegularExpressions.Capture>-Objekte können auf zwei unterschiedliche Arten aus der Auflistung abgerufen werden:  
  
- Durch das Durchlaufen der Sammlung mit einem Konstrukt wie `foreach` (in C#) oder `For Each` (in Visual Basic).  
  
- Mit der <xref:System.Text.RegularExpressions.CaptureCollection.Item%2A?displayProperty=nameWithType>-Eigenschaft, um ein bestimmtes Objekt nach Index abzurufen. Die <xref:System.Text.RegularExpressions.CaptureCollection.Item%2A>-Eigenschaft ist die Standardeigenschaft des <xref:System.Text.RegularExpressions.CaptureCollection>-Objekts (in Visual Basic) oder Indexer (in C#).  
  
 Wenn ein Quantifizierer nicht für eine Erfassungsgruppe übernommen wird, enthält das <xref:System.Text.RegularExpressions.CaptureCollection>-Objekt ein einzelnes <xref:System.Text.RegularExpressions.Capture>-Objekt, das von geringem Interesse ist, da es Informationen zur gleichen Übereinstimmung wie das <xref:System.Text.RegularExpressions.Group>-Objekt enthält. Wenn ein Quantifizierer für eine Erfassungsgruppe übernommen wird, enthält das <xref:System.Text.RegularExpressions.CaptureCollection>-Objekt alle von der Erfassungsgruppe gemachten Erfassungen, und der letzte Member der Auflistung stellt die gleiche Erfassung wie das <xref:System.Text.RegularExpressions.Group>-Objekt dar.  
  
 Wenn Sie zum Beispiel das Muster `((a(b))c)+` eines regulären Ausdrucks verwenden (wobei der +-Quantifizierer mindestens eine Übereinstimmung angibt), um Übereinstimmungen von der Zeichenfolge "abcabcabc" zu erfassen, enthält das <xref:System.Text.RegularExpressions.CaptureCollection>-Objekt für jedes <xref:System.Text.RegularExpressions.Group>-Objekt drei Member.  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/capturecollection1.cs#14)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/capturecollection1.vb#14)]  
  
 Im folgenden Beispiel wird der reguläre Ausdruck `(Abc)+` verwendet, um mindestens eine aufeinanderfolgende Ausführung der Zeichenfolge "Abc" in der Zeichenfolge "XYZAbcAbcAbcXYZAbcAb" zu suchen. Das Beispiel veranschaulicht die Verwendung der <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType>-Eigenschaft, um mehrere Gruppen erfasster Teilzeichenfolgen zurückzugeben.  
  
 [!code-csharp[RegularExpressions.Classes#5](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Classes/cs/Example.cs#5)]
 [!code-vb[RegularExpressions.Classes#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Classes/vb/Example.vb#5)]  
  
 [Zurück nach oben](#introduction)  
  
<a name="the_individual_capture"></a>
## <a name="the-individual-capture"></a>Die einzelne Erfassung  
 Die <xref:System.Text.RegularExpressions.Capture>-Klasse enthält die Ergebnisse einer einzelnen Teilausdrucksuche. Die <xref:System.Text.RegularExpressions.Capture.Value%2A?displayProperty=nameWithType>-Eigenschaft enthält den übereinstimmenden Text, und die <xref:System.Text.RegularExpressions.Capture.Index%2A?displayProperty=nameWithType>-Eigenschaft gibt die nullbasierte Position in der Eingabezeichenfolge an, bei der die übereinstimmende Teilzeichenfolge beginnt.  
  
 Im folgenden Beispiel wird eine Eingabezeichenfolge hinsichtlich der Temperatur ausgewählter Orte analysiert. Ein Komma (",") wird verwendet, um einen Ort und seine Temperatur zu trennen. Ein Semikolon ("";) dient zum Trennen der Daten zu einzelnen Orten. Die gesamte Eingabezeichenfolge stellt eine einzelne Übereinstimmung dar. Im Muster `((\w+(\s\w+)*),(\d+);)+` eines regulären Ausdrucks, mit dem die Zeichenfolge analysiert wird, wird der Ortsname der zweiten Erfassungsgruppe und die Temperatur der vierten Erfassungsgruppe zugewiesen.  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#16](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/capture1.cs#16)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/capture1.vb#16)]  
  
 Der reguläre Ausdruck wird entsprechend der Darstellung in der folgenden Tabelle definiert:  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`\w+`|Übereinstimmung mit mindestens einem Wortzeichen.|  
|`(\s\w+)*`|Entsprechung für null oder mehr Vorkommen eines Leerstellenzeichens finden, auf das mindestens ein Wortzeichen folgt. Dieses Muster entspricht Ortsnamen, die aus mehreren Wörtern bestehen. Dies ist die dritte Erfassungsgruppe.|  
|`(\w+(\s\w+)*)`|Entsprechung für mindestens ein Wortzeichen finden, auf das null oder mehr Vorkommen eines Leerstellenzeichens folgen und mindestens ein Wortzeichen. Dies ist die zweite Erfassungsgruppe.|  
|`,`|Entsprechung für ein Komma finden.|  
|`(\d+)`|Entsprechung für mindestens eine Stelle finden. Dies ist die vierte Erfassungsgruppe.|  
|`;`|Entsprechung für ein Semikolon finden.|  
|`((\w+(\s\w+)*),(\d+);)+`|Entsprechung für das Muster eines Worts finden, auf das alle weiteren Wörter folgen, auf die ein Komma, mindestens eine Ziffer und ein Semikolon folgen (mindestens einmal). Dies ist die erste Erfassungsgruppe.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Text.RegularExpressions>
- [Reguläre Ausdrücke von .NET](regular-expressions.md)
- [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](regular-expression-language-quick-reference.md)
