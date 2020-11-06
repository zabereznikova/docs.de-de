---
title: Kombinierte Formatierung
description: Lernen Sie die kombinierte Formatierung in .NET kennen, die als Eingabe eine Liste von Objekten und eine kombinierte Formatzeichenfolge akzeptiert, die festgelegten Text mit indizierten Platzhaltern enthält.
ms.date: 10/26/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parameter specifiers
- strings [.NET], alignment
- format specifiers, composite formatting
- strings [.NET], composite
- composite formatting
- objects [.NET], formatting multiple objects
ms.assetid: 87b7d528-73f6-43c6-b71a-f23043039a49
ms.openlocfilehash: e15452016aa61cf44950e8b9e7fca58f23471ae7
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "92889464"
---
# <a name="composite-formatting"></a>Kombinierte Formatierung

Die Funktion für die kombinierte Formatierung in .NET verwendet als Eingabe eine Liste von Objekten und eine kombinierte Formatzeichenfolge. Eine kombinierte Formatzeichenfolge besteht aus festgelegtem Text mit indizierten Platzhaltern, so genannten Formatelementen, die den Objekten in der Liste entsprechen. Der Formatierungsvorgang liefert eine Ergebniszeichenfolge, die sich aus dem ursprünglichen festgelegten Text und der Zeichenfolgendarstellung der Objekte in der Liste zusammensetzt.  
  
> [!IMPORTANT]
> Anstelle kombinierter Formatzeichenfolgen können Sie *interpolierte Zeichenfolgen* verwenden, wenn die von Ihnen verwendete Sprache und Sprachversion diese unterstützen. Eine interpolierte Zeichenfolge ist eine Zeichenfolge, die *interpolierte Ausdrücke* enthält. Jeder interpolierte Ausdruck wird mit dem Wert des Ausdrucks aufgelöst und in die Ergebniszeichenfolge aufgenommen, wenn die Zeichenfolge zugewiesen wird. Weitere Informationen finden Sie unter [Zeichenfolgeninterpolation (C#-Referenz)](../../csharp/language-reference/tokens/interpolated.md) und [Interpolierte Zeichenfolgen (Visual Basic-Referenz)](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md).

Die Funktion für kombinierte Formatierung wird beispielsweise von folgenden Methoden unterstützt:  
  
- <xref:System.String.Format%2A?displayProperty=nameWithType>, die eine formatierte Ergebniszeichenfolge zurückgibt.  
  
- <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>, die eine formatierte Ergebniszeichenfolge an ein <xref:System.Text.StringBuilder>-Objekt anfügt.
- Einige Überladungen der <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>-Methode, die eine formatierte Ergebniszeichenfolge in der Konsole anzeigen.  
  
- Einige Überladungen <xref:System.IO.TextWriter.WriteLine%2A?displayProperty=nameWithType>-Methode, die die formatierte Ergebniszeichenfolge in einen Stream oder eine Datei schreiben. Die von <xref:System.IO.TextWriter> abgeleiteten Klassen wie <xref:System.IO.StreamWriter> und <xref:System.Web.UI.HtmlTextWriter> verwenden auch diese Funktionen.  
  
- <xref:System.Diagnostics.Debug.WriteLine%28System.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>, die eine formatierte Meldung an Ablaufverfolgungslistener ausgibt.  
  
- Die Methoden <xref:System.Diagnostics.Trace.TraceError%28System.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.TraceInformation%28System.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> und <xref:System.Diagnostics.Trace.TraceWarning%28System.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>, die formatierte Meldungen an Ablaufverfolgungslistener ausgeben.  
  
- Die <xref:System.Diagnostics.TraceSource.TraceInformation%28System.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>-Methode, die eine Informationsmethode in Ablaufverfolgungslistener schreibt.  
  
## <a name="composite-format-string"></a>Kombinierte Formatzeichenfolge  
 Eine kombinierte Formatzeichenfolge und eine Objektliste dienen als Argumente von Methoden, die das Feature für die kombinierte Formatierung unterstützen. Die Quellzeichenfolge besteht aus 0 (null) oder mehreren Einheiten festgelegten Texts mit mindestens einem Formatelement. Der festgelegte Text ist eine von Ihnen ausgewählte beliebige Zeichenfolge. Jedes Formatelement entspricht einem Objekt oder einer geschachtelten Struktur in der Liste. Die Funktion für die kombinierte Formatierung gibt eine neue Ergebniszeichenfolge zurück, in der jedes Formatelement durch die Zeichenfolgendarstellung des entsprechenden Objekts in der Liste ersetzt wird.  
  
 Betrachten Sie das folgende <xref:System.String.Format%2A>-Codefragment:  
  
 [!code-csharp[Formatting.Composite#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/Composite1.cs#1)]
 [!code-vb[Formatting.Composite#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/Composite1.vb#1)]  
  
 Der feste Text ist „`Name =`“ und „`, hours =`“. Die Formatelemente sind „`{0}`“ mit dem Index 0, was dem Objekt `name` entspricht, und „`{1:hh}`“ mit dem Index 1, was dem Objekt `DateTime.Now` entspricht.  
  
## <a name="format-item-syntax"></a>Formatelementsyntax  
 Alle Formatelemente weisen die folgende Form auf und bestehen aus folgenden Komponenten:  
  
 `{` *Index* [`,`*Ausrichtung* ][`:`*formatString* ]`}`  
  
 Die übereinstimmenden geschweiften Klammern ("{" and "}") sind erforderlich.  
  
### <a name="index-component"></a>Indexkomponente  
 Bei der obligatorischen Komponente *Index* , dem so genannten Parameterbezeichner, handelt es sich um eine bei 0 (null) beginnende Zahl, mit der ein entsprechendes Element in der Objektliste angegeben wird. Das bedeutet, dass das Formatelement mit dem Parameterbezeichner 0 (null) das erste Objekt in der Liste formatiert, und das Formatelement mit dem Parameterbezeichner 1 formatiert das zweite Objekt in der Liste usw. Das folgende Beispiel enthält vier von null bis drei nummerierte Parameterbezeichner zur Darstellung von Primzahlen, die kleiner als zehn sind:  
  
 [!code-csharp[Formatting.Composite#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/index1.cs#7)]
 [!code-vb[Formatting.Composite#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/index1.vb#7)]  
  
 Mehrere Formatelemente können auf dasselbe Element in der Objektliste verweisen, indem derselbe Parameterbezeichner festgelegt wird. Sie können beispielsweise denselben numerischen Wert im hexadezimalen, im wissenschaftlichen und im Zahlenformat formatieren, indem Sie eine kombinierte Formatzeichenfolge wie die Folgende angeben: „0x{0:X} {0:E} {0:N}“ wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[Formatting.Composite#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/index1.cs#10)]
 [!code-vb[Formatting.Composite#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/index1.vb#10)]  
  
 Jedes Formatelement kann auf ein beliebiges Objekt in der Liste verweisen. Wenn beispielsweise drei Objekte vorliegen, können Sie das zweite, erste und dritte Objekt formatieren, indem Sie eine kombinierte Formatzeichenfolge wie die folgende angeben: „{1} {0} {2}“. Ein Objekt, auf das kein Formatelement verweist, wird ignoriert. Eine <xref:System.FormatException> wird zur Laufzeit ausgelöst, wenn ein Parameterbezeichner auf ein Element außerhalb der Grenzen der Objektliste verweist.  
  
### <a name="alignment-component"></a>Ausrichtungskomponente  
 Bei der optionalen Komponente *Ausrichtung* handelt es sich um eine ganze Zahl mit Vorzeichen, die die gewünschte formatierte Feldbreite angibt. Wenn der Wert für *Ausrichtung* kleiner als die Länge der formatierten Zeichenfolge ist, wird *Ausrichtung* ignoriert, und die Länge der formatierten Zeichenfolge wird als Feldbreite verwendet. Die formatierten Daten im Feld werden bei einem positiven Wert für *Ausrichtung* rechtsbündig und bei einem negativen Wert für *Ausrichtung* linksbündig ausgerichtet. Wenn Füllzeichen erforderlich sind, werden Leerräume verwendet. Das Komma ist erforderlich, wenn *Ausrichtung* angegeben wird.  
  
 Im folgenden Beispiel werden zwei Arrays definiert, ein Array mit den Namen der Mitarbeiter und ein Array mit den Arbeitsstunden der Mitarbeiter über einen Zeitraum von zwei Wochen. Die kombinierte Formatzeichenfolge richtet die Namen in einem Feld mit 20 Zeichen linksbündig aus, und die Stunden werden in einem Feld mit 5 Zeichen rechtsbündig ausgerichtet. Beachten Sie, dass auch die Standardformatzeichenfolge "N1" verwendet wird, um die Stunden mit einer Dezimalstelle zu formatieren.  
  
 [!code-csharp[Formatting.Composite#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/alignment1.cs#8)]
 [!code-vb[Formatting.Composite#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/alignment1.vb#8)]  
  
### <a name="format-string-component"></a>Formatzeichenfolgen-Komponente  
 Die optionale Komponente *Formatzeichenfolge* ist eine Formatzeichenfolge, die für den formatierten Objekttyp geeignet ist. Geben Sie eine standardmäßige oder eine benutzerdefinierte numerische Formatzeichenfolge an, wenn das entsprechende Objekt ein numerischer Wert ist. Geben Sie eine standardmäßige oder eine benutzerdefinierte Formatzeichenfolge für Datum und Uhrzeit an, wenn das entsprechende Objekt ein <xref:System.DateTime>-Objekt ist. Geben Sie eine [Enumerationsformatzeichenfolge](enumeration-format-strings.md) an, wenn das entsprechende Objekt ein Enumerationswert ist. Wenn *Formatzeichenfolge* nicht festgelegt ist, wird der allgemeine Formatbezeichner („G“) für einen numerischen, Datums- und Uhrzeit- oder Enumerationstyp verwendet. Der Doppelpunkt ist erforderlich, wenn *Formatzeichenfolge* angegeben wird.  
  
 Die folgende Tabelle listet Typen oder Kategorien von Typen in der .NET-Klassenbibliothek auf, die mehrere vordefinierte Formatzeichenfolgen unterstützen, und stellt Links zu Themen bereit, die diese unterstützten Formatzeichenfolgen auflisten. Beachten Sie, dass die Zeichenfolgenformatierung ein erweiterbarer Mechanismus ist, der es ermöglicht, neue Formatzeichenfolgen für alle vorhandenen Typen zu definieren und einen Satz von Formatzeichenfolgen zu definieren, der von einem anwendungsdefinierten Typ unterstützt wird. Weitere Informationen finden Sie unter den Themen zur <xref:System.IFormattable>-Schnittstelle und <xref:System.ICustomFormatter>-Schnittstelle.  
  
|Typ oder Typkategorie|Siehe|  
|---------------------------|---------|  
|Datums-/Zeittypen (<xref:System.DateTime>, <xref:System.DateTimeOffset>)|[Standard-Formatzeichenfolgen für Datum und Uhrzeit](standard-date-and-time-format-strings.md)<br /><br /> [Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit](custom-date-and-time-format-strings.md)|  
|Enumerationstypen (alle Typen abgeleitet von <xref:System.Enum?displayProperty=nameWithType>)|[Enumerationsformatzeichenfolgen](enumeration-format-strings.md)|  
|Numerische Typen (<xref:System.Numerics.BigInteger>, <xref:System.Byte>, <xref:System.Decimal>, <xref:System.Double>, <xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.SByte>, <xref:System.Single>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64>)|[Standardmäßige Zahlenformatzeichenfolgen](standard-numeric-format-strings.md)<br /><br /> [Benutzerdefinierte Zahlenformatzeichenfolgen](custom-numeric-format-strings.md)|  
|<xref:System.Guid>|<xref:System.Guid.ToString%28System.String%29?displayProperty=nameWithType>|  
|<xref:System.TimeSpan>|[TimeSpan-Standardformatzeichenfolgen](standard-timespan-format-strings.md)<br /><br /> [Benutzerdefinierte TimeSpan-Formatzeichenfolgen](custom-timespan-format-strings.md)|  
  
### <a name="escaping-braces"></a>Versehen von geschweiften Klammern mit Escapezeichen  
 Öffnende und schließende geschweifte Klammern werden als Beginn und Ende eines Formatelements interpretiert. Deshalb müssen Sie eine Escapesequenz verwenden, um eine literale öffnende bzw. schließende geschweifte Klammer anzuzeigen. Geben Sie zwei öffnende geschweifte Klammern ("{{") im festgelegten Text an, um eine öffnende geschweifte Klammer ("{") anzuzeigen, und geben Sie entsprechend zwei schließende geschweifte Klammern ("}}") an, um eine schließende geschweifte Klammer ("}") anzuzeigen. Geschweifte Klammern in einem Formatelement werden sequenziell in der Reihenfolge interpretiert, in der sie angetroffen werden. Die Interpretation geschachtelter geschweifter Klammern wird nicht unterstützt.  
  
 Die Art und Weise, wie geschweifte Klammern mit Escapezeichen interpretiert werden, kann zu unerwarteten Ergebnissen führen. Betrachten Sie beispielsweise das Formatelement „{{{0:D}}}“, das eine öffnende geschweifte Klammer anzeigen soll, einen numerischen Wert, der als Dezimalzahl formatiert ist, und eine schließende geschweifte Klammer. Das Formatelement wird aber tatsächlich wie folgt interpretiert:  
  
1. Die ersten beiden öffnenden geschweiften Klammern ("{{") werden mit Escapezeichen versehen und ergeben eine öffnende geschweifte Klammer.  
  
2. Die nächsten drei Zeichen ("{0":) werden als Anfang eines Formatelements interpretiert.  
  
3. Das nächste Zeichen ("D") wird als Formatbezeichner für das numerische Standarddezimalformat interpretiert, und die nächsten beiden geschweiften Klammern mit Escapezeichen ergeben eine einzelne geschweifte Klammer. Da die entstehende Zeichenfolge ("D}") kein numerischer Standardformatbezeichner ist, wird sie als benutzerdefinierte Formatzeichenfolge interpretiert, d. h., es wird die Literalzeichenfolge "D}" angezeigt.  
  
4. Die letzte geschweifte Klammer ("}") wird als Ende des Formatelements interpretiert.  
  
5. Das Endergebnis, das angezeigt wird, ist die Literalzeichenfolge "{D}". Der numerische Wert, der formatiert werden sollte, wird nicht angezeigt.  
  
 Eine Möglichkeit, Code zu schreiben und dabei Probleme mit falsch interpretierten geschweiften Klammern und Formatelementen zu vermeiden, ist die separate Formatierung der geschweiften Klammern und Formatelemente. Zeigen Sie also beim ersten Formatierungsvorgang eine literale öffnende geschweifte Klammer, beim nächsten Formatierungsvorgang das Ergebnis des Formatelements und beim letzten Formatierungsvorgang eine literale schließende geschweifte Klammer an. Dieser Ansatz wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-csharp[Formatting.Composite#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/Escaping1.cs#2)]
 [!code-vb[Formatting.Composite#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/Escaping1.vb#2)]  
  
### <a name="processing-order"></a>Verarbeitungsreihenfolge  
 Wenn der Aufruf der Methode für die kombinierte Formatierung ein <xref:System.IFormatProvider>-Argument enthält, dessen Wert nicht `null` ist, ruft die Laufzeit die <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType>-Methode auf, um eine <xref:System.ICustomFormatter>-Implementierung anzufordern. Wenn die Methode eine <xref:System.ICustomFormatter>-Implementierung zurückgeben kann, wird diese während des gesamten Aufrufs der Methode zur kombinierten Formatierung zwischengespeichert.
  
 Jeder Wert in der Parameterliste, der einem Formatelement entspricht, wird wie folgt in eine Zeichenfolge konvertiert:  
  
1. Wenn der zu formatierende Wert `null` ist, wird eine leere Zeichenfolge (<xref:System.String.Empty?displayProperty=nameWithType>) zurückgegeben.  
  
2. Wenn eine <xref:System.ICustomFormatter>-Implementierung verfügbar ist, ruft die Laufzeit die <xref:System.ICustomFormatter.Format%2A>-Methode auf. Sie übergibt den *formatString* -Wert des Formatelements, sofern vorhanden, oder andernfalls `null` zusammen mit der <xref:System.IFormatProvider>-Implementierung an die Methode. Wenn durch den Aufruf der <xref:System.ICustomFormatter.Format%2A?displayProperty=nameWithType>-Methode `null` zurückgegeben wird, wird der nächste Schritt ausgeführt. Andernfalls wird das Ergebnis des <xref:System.ICustomFormatter.Format%2A?displayProperty=nameWithType>-Aufrufs zurückgegeben.
  
3. Wenn der Wert die <xref:System.IFormattable>-Schnittstelle implementiert, wird die <xref:System.IFormattable.ToString%28System.String%2CSystem.IFormatProvider%29>-Methode der Schnittstelle aufgerufen. Der *Formatzeichenfolge* -Wert wird, sofern im Formatelement vorhanden, an die Methode übergeben. Ist dies nicht der Fall, wird `null` übergeben. Das <xref:System.IFormatProvider>-Argument wird wie folgt bestimmt:  
  
    - Bei einem numerischen Wert fordert die Laufzeit im Fall, dass eine Methode zur kombinierten Formatierung mit einem <xref:System.IFormatProvider>-Argument ungleich NULL aufgerufen wird, ein <xref:System.Globalization.NumberFormatInfo>-Objekt von ihrer <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType>-Methode an. Wenn sie keines bereitstellen kann, wenn der Wert des Arguments `null` ist, oder wenn die Methode zur kombinierten Formatierung keinen <xref:System.IFormatProvider>-Parameter hat, wird das <xref:System.Globalization.NumberFormatInfo>-Objekt für die aktuelle Threadkultur verwendet.  
  
    - Bei einem Datums- und Uhrzeitwert fordert die Laufzeit im Fall, dass eine Methode zur kombinierten Formatierung mit einem <xref:System.IFormatProvider>-Argument ungleich NULL aufgerufen wird, ein <xref:System.Globalization.DateTimeFormatInfo>-Objekt von ihrer <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType>-Methode an. Wenn sie keines bereitstellen kann, wenn der Wert des Arguments `null` ist, oder wenn die Methode zur kombinierten Formatierung keinen <xref:System.IFormatProvider>-Parameter hat, wird das <xref:System.Globalization.DateTimeFormatInfo>-Objekt für die aktuelle Threadkultur verwendet.  
  
    - Bei Objekten anderer Typen wird beim Aufruf einer kombinierten Formatierungsmethode mit einem <xref:System.IFormatProvider>-Argument der zugehörige Wert direkt an die <xref:System.IFormattable.ToString%2A?displayProperty=nameWithType>-Implementierung übergeben. Andernfalls wird `null` an die <xref:System.IFormattable.ToString%2A?displayProperty=nameWithType>-Implementierung übergeben.  
  
4. Die parameterlose `ToString`-Methode des Typs, die entweder <xref:System.Object.ToString?displayProperty=nameWithType> überschreibt oder das Verhalten ihrer Basisklasse erbt, wird aufgerufen. In diesem Fall wird die von der *formatString* -Komponente im Formatelement angegebene Formatzeichenfolge (sofern vorhanden) ignoriert.  
  
 Die Ausrichtung wird angewendet, nachdem die vorhergehenden Schritte durchgeführt wurden.  
  
## <a name="code-examples"></a>Codebeispiele  
 Das folgende Beispiel stellt eine Zeichenfolge dar, die mit der kombinierten Formatierung erstellt wurde, und eine weitere, die mit der `ToString`-Methode eines Objekts erstellt wurde. Beide Formatierungen führen zum gleichen Ergebnis.  
  
 [!code-csharp[Formatting.Composite#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/Composite1.cs#3)]
 [!code-vb[Formatting.Composite#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/Composite1.vb#3)]  
  
 Wenn das aktuelle Datum ein Donnerstag im Mai ist, lautet der Wert beider Zeichenfolgen im vorherigen Beispiel `Thursday May` in der Kultur Englisch (USA).  
  
 <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> stellt die gleiche Funktionalität wie <xref:System.String.Format%2A?displayProperty=nameWithType> bereit. Der einzige Unterschied zwischen den beiden Methoden besteht darin, dass <xref:System.String.Format%2A?displayProperty=nameWithType> das Ergebnis als Zeichenfolge zurückgibt, während <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> das Ergebnis in den Ausgabestrom schreibt, der dem <xref:System.Console>-Objekt zugeordnet ist. Im folgenden Beispiel wird der Wert von <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> mit der `MyInt`-Methode als Währungswert formatiert.  
  
 [!code-csharp[Formatting.Composite#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/Composite1.cs#4)]
 [!code-vb[Formatting.Composite#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/Composite1.vb#4)]  
  
 Das folgende Beispiel veranschaulicht die Formatierung mehrerer Objekte, wobei ein Objekt auf zwei Arten formatiert wird.  
  
 [!code-csharp[Formatting.Composite#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/Composite1.cs#5)]
 [!code-vb[Formatting.Composite#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/Composite1.vb#5)]  
  
 Das folgende Beispiel veranschaulicht die Verwendung der Ausrichtung beim Formatieren. Die zu formatierenden Argumente werden zwischen senkrechte Striche (&#124;) platziert, um die resultierende Ausrichtung zu kennzeichnen.  
  
 [!code-csharp[Formatting.Composite#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/Composite1.cs#6)]
 [!code-vb[Formatting.Composite#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/Composite1.vb#6)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Console.WriteLine%2A>
- <xref:System.String.Format%2A?displayProperty=nameWithType>
- [Zeichenfolgeninterpolation (C#)](../../csharp/language-reference/tokens/interpolated.md)
- [Zeichenfolgeninterpolation (Visual Basic)](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md)
- [Formatierung von Typen](formatting-types.md)
- [Standardmäßige Zahlenformatzeichenfolgen](standard-numeric-format-strings.md)
- [Benutzerdefinierte Zahlenformatzeichenfolgen](custom-numeric-format-strings.md)
- [Standardformatzeichenfolgen für Datum und Uhrzeit](standard-date-and-time-format-strings.md)
- [Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit](custom-date-and-time-format-strings.md)
- [TimeSpan-Standardformatzeichenfolgen](standard-timespan-format-strings.md)
- [Benutzerdefinierte TimeSpan-Formatzeichenfolgen](custom-timespan-format-strings.md)
- [Enumerationsformatzeichenfolgen](enumeration-format-strings.md)
