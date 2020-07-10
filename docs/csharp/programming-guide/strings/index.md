---
title: Zeichenfolgen – C#-Programmierhandbuch
ms.date: 06/27/2019
helpviewer_keywords:
- C# language, strings
- strings [C#]
ms.assetid: 21580405-cb25-4541-89d5-037846a38b07
ms.openlocfilehash: 7bf5cba51a2e72d3a648f795f018220a452e51f5
ms.sourcegitcommit: 67cf756b033c6173a1bbd1cbd5aef1fccac99e34
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2020
ms.locfileid: "86226594"
---
# <a name="strings-c-programming-guide"></a>Zeichenfolgen (C#-Programmierhandbuch)
Eine Zeichenfolge ist ein Objekt des Typs <xref:System.String>, dessen Wert Text ist. Intern wird der Text als sequenzielle schreibgeschützte Auflistung von <xref:System.Char>-Objekten gespeichert. Es gibt kein mit NULL endendes Zeichen am Ende einer C#-Zeichenfolge. Deshalb kann eine C#-Zeichenfolge eine beliebige Anzahl eingebetteter NULL-Zeichen („\0“) enthalten. Die Eigenschaft <xref:System.String.Length%2A> einer Zeichenfolge stellt die Anzahl von `Char`-Objekten dar, die darin enthalten sind, nicht die Anzahl der Unicode-Zeichen. Verwenden Sie für den Zugriff auf einzelne Unicode-Codepunkte in einer Zeichenfolge das Objekt <xref:System.Globalization.StringInfo>.  
  
## <a name="string-vs-systemstring"></a>String im Vergleich zu System.String  
 In C# ist das Schlüsselwort `string` ein Alias für <xref:System.String>. Aus diesem Grund sind `String` und `string` gleich, und Sie können eine beliebige Benennungskonvention verwenden. Die `String`-Klasse bietet viele Methoden zum sicheren Erstellen, Bearbeiten und Vergleichen von Zeichenfolgen. Außerdem überlädt die Programmiersprache C# einige Operatoren, um allgemeine Zeichenfolgenoperationen zu vereinfachen. Weitere Informationen über das Schlüsselwort finden Sie unter [String](../../language-reference/builtin-types/reference-types.md). Weitere Informationen zum Typ und dessen Methoden finden Sie unter <xref:System.String>.  
  
## <a name="declaring-and-initializing-strings"></a>Deklarieren und Initialisieren von Zeichenfolgen  
 Sie können Zeichenfolgen auf verschiedene Weise deklarieren und Initialisieren, wie im folgenden Beispiel gezeigt:  
  
 [!code-csharp[csProgGuideStrings#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#1)]  
  
 Beachten Sie, dass Sie nicht den [neuen](../../language-reference/operators/new-operator.md) Operator zum Erstellen eines Zeichenfolgenobjekts verwenden, außer wenn Sie die Zeichenfolge mit einem Array von Chars initialisieren.  
  
 Initialisieren Sie eine Zeichenfolge mit dem konstanten Wert <xref:System.String.Empty>, um ein neues <xref:System.String>-Objekt zu erstellen, dessen Zeichenfolge eine Länge von 0 hat. Die Darstellung des Zeichenfolgenliterals einer Zeichenfolge mit einer Länge von 0 ist "". Indem Zeichenfolgen mit dem Wert <xref:System.String.Empty> anstatt [NULL](../../language-reference/keywords/null.md) initialisiert werden, können Sie die Chancen einer auftretenden <xref:System.NullReferenceException> reduzieren. Verwenden Sie die statische Methode <xref:System.String.IsNullOrEmpty%28System.String%29>, um den Wert einer Zeichenfolge zu überprüfen, bevor Sie versuchen, auf sie zuzugreifen.  
  
## <a name="immutability-of-string-objects"></a>Unveränderlichkeit von Zeichenfolgenobjekten  
 Zeichenfolgenobjekte sind *unveränderlich*: sie können nicht geändert werden, nachdem sie erstellt wurden. Alle <xref:System.String>-Methoden und C#-Operatoren, die eine Zeichenfolge scheinbar verändern, geben in Wirklichkeit die Ergebnisse in einem neuen Zeichenfolgenobjekt zurück. Im folgenden Beispiel werden die beiden ursprünglichen Zeichenfolgen nicht geändert, wenn die Inhalte von `s1` und `s2` verkettet werden, um eine einzelne Zeichenfolge zu bilden. Der `+=`-Operator erstellt eine neue Zeichenfolge, die die kombinierten Inhalte enthält. Das neue Objekt wird der Variablen `s1` zugewiesen, und das ursprüngliche Objekt, das `s1` zugewiesen wurde, wird für die Garbage Collection freigegeben, da keine andere Variable einen Verweis darauf enthält.  
  
 [!code-csharp[csProgGuideStrings#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#2)]  
  
 Da eine „Zeichenfolgenänderung“ in Wirklichkeit eine neue Erstellung von Zeichenfolgen ist, müssen Sie vorsichtig sein, wenn Sie Verweise auf Zeichenfolgen erstellen. Wenn Sie einen Verweis auf eine Zeichenfolge erstellen und dann die ursprüngliche Zeichenfolge „ändern“, wird der Verweis weiterhin auf das ursprüngliche Objekt anstelle des neuen Objekts zeigen, das erstellt wurde, als die Zeichenfolge geändert wurde. Der folgende Code veranschaulicht dieses Verhalten:  
  
 [!code-csharp[csProgGuideStrings#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#25)]  
  
 Weitere Informationen zum Erstellen neuer Zeichenfolgen, die auf Änderungen wie beispielsweise Vorgängen zum Suchen und Ersetzen auf der ursprüngliche Zeichenfolge basieren, finden Sie unter [Ändern von Zeichenfolgeninhalten](../../how-to/modify-string-contents.md).  
  
## <a name="regular-and-verbatim-string-literals"></a>Reguläre und ausführliche Zeichenfolgenliterale  
 Verwenden Sie reguläre Zeichenfolgenliterale, wenn Sie von C# bereitgestellte Escapezeichen einbetten müssen, wie im folgenden Beispiel gezeigt:  
  
 [!code-csharp[csProgGuideStrings#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#3)]  
  
 Verwenden Sie ausführliche Zeichenfolgen der Einfachheit und Lesbarkeit halber, wenn der Text der Zeichenfolge umgekehrte Schrägstriche enthält, z.B. in Dateipfaden. Da ausführliche Zeichenfolgen neue Zeilenzeichen als Teil des Texts der Zeichenfolge beibehalten, können sie verwendet werden, um mehrzeilige Zeichenfolgen zu initialisieren. Verwenden Sie doppelte Anführungszeichen, um ein Anführungszeichen in eine ausführliche Zeichenfolge einzubetten. Im folgenden Beispiel werden einige gängige Verwendungszwecke für allgemeine Zeichenfolgen dargestellt:  
  
 [!code-csharp[csProgGuideStrings#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#4)]  
  
## <a name="string-escape-sequences"></a>Zeichenfolgen-Escapesequenzen  
  
|Escapesequenz|Zeichenname|Unicode-Codierung|  
|---------------------|--------------------|----------------------|  
|\\'|Einfaches Anführungszeichen|0x0027|  
|\\"|Doppeltes Anführungszeichen|0x0022|  
|\\\\ |Umgekehrter Schrägstrich|0x005C|  
|\0|Null|0x0000|  
|\a|Warnung|0x0007|  
|\b|Rückschritt|0x0008|  
|\f|Seitenvorschub|0x000C|  
|\n|Zeilenwechsel|0x000A|  
|\r|Wagenrücklauf|0x000D|  
|\t|Horizontaler Tabulator|0x0009|  
|\v|Vertikaler Tabulator|0x000B|  
|\u|Unicode-Escapesequenz (UTF-16)|`\uHHHH` (Bereich: 0000 - FFFF; Beispiel: `\u00E7` = "ç")|  
|\U|Unicode-Escapesequenz (UTF-32)|`\U00HHHHHH` (Bereich: 000000 - 10FFFF; Beispiel: `\U0001F47D` = "&#x1F47D;")|  
|\x|Unicode-Escapesequenz, die ähnlich wie "\u" ist, außer mit variabler Länge|`\xH[H][H][H]` (Bereich: 0 - FFFF; Beispiel: `\x00E7` or `\x0E7` oder `\xE7` = "ç")|  
  
> [!WARNING]
> Wenn Sie die Escapesequenz `\x` verwenden, weniger als vier Hexadezimalziffern angeben und es sich bei den Zeichen, die der Escapesequenz unmittelbar folgen, um gültige Hexadezimalziffern handelt (z. B. 0–9, A–F und a–f), werden diese als Teil der Escapesequenz interpretiert. Die Angabe `\xA1` erzeugt beispielsweise den Wert "&#161;", der dem Codepunkt U+00A1 entspricht. Wenn das nächste Zeichen jedoch „A“ oder „a“ ist, wird die Escapesequenz stattdessen als `\xA1A` interpretiert und erzeugt den Wert "&#x0A1A;", der dem Codepunkt U+0A1A entspricht. In solchen Fällen können Fehlinterpretationen vermieden werden, indem Sie alle vier Hexadezimalziffern (z. B. `\x00A1`) angeben.  
  
> [!NOTE]
> Zum Zeitpunkt der Kompilierung werden ausführliche Zeichenfolgen in normale Zeichenfolgen mit gleichen Escapesequenzen konvertiert. Aus diesem Grund sehen Sie die Escapezeichen, die vom Compiler hinzugefügt werden, und nicht die ausführliche Version aus Ihrem Sourcecode, wenn Sie eine ausführliche Zeichenfolge in Debugger-Überwachungsfenster anzeigen. Die ausführliche Zeichenfolge `@"C:\files.txt"` wird im Überwachungsfenster z.B. als „C:\\\files.txt“ angezeigt.  
  
## <a name="format-strings"></a>Formatzeichenfolgen  
 Eine Formatzeichenfolge ist eine Zeichenfolge, deren Inhalt zur Laufzeit dynamisch bestimmt wird. Formatzeichenfolgen werden erstellt, indem *interpolierte Ausdrücke* oder Platzhalter in geschweifte Klammern innerhalb einer Zeichenfolge eingebettet werden. Der in den Klammern (`{...}`) eingeschlossene Inhalt wird in einen Wert aufgelöst und zur Laufzeit als formatierte Zeichenfolge ausgegeben. Es gibt zwei Methoden zum Erstellen von Formatzeichenfolgen: Zeichenfolgeninterpolation und kombinierte Formatierung.

### <a name="string-interpolation"></a>Zeichenfolgeninterpolierung
In C# 6.0 und höheren Versionen werden [*interpolierte Zeichenfolgen*](../../language-reference/tokens/interpolated.md) durch das Sonderzeichen `$` identifiziert und interpolierte Ausdrücke in geschweifte Klammern eingeschlossen. Wenn Sie noch nicht mit der Zeichenfolgeninterpolation vertraut sind, erhalten Sie im interaktiven Tutorial [Zeichenfolgeninterpolation in C#](../../tutorials/exploration/interpolated-strings.yml) eine kurze Übersicht.

Verwenden Sie die Zeichenfolgeninterpolation, um die Lesbarkeit und die Wartungsfähigkeit Ihres Codes zu verbessern. Mit der Zeichenfolgeninterpolation werden die gleichen Ergebnisse erzielt wie mit der `String.Format`-Methode, es wird jedoch die Benutzerfreundlichkeit und Übersichtlichkeit verbessert.

[!code-csharp[csProgGuideFormatStrings](~/samples/snippets/csharp/programming-guide/strings/Strings_1.cs#StringInterpolation)]

### <a name="composite-formatting"></a>Kombinierte Formatierung
<xref:System.String.Format%2A?displayProperty=nameWithType> verwendet Platzhalter in geschweiften Klammern, um eine Formatzeichenfolge zu erstellen. Dieses Beispiel liefert als Ergebnis eine ähnliche Ausgabe wie die oben verwendete Methode zur Zeichenfolgeninterpolation.
  
[!code-csharp[csProgGuideFormatStrings](~/samples/snippets/csharp/programming-guide/strings/Strings_1.cs#StringFormat)]

Weitere Informationen zum Formatieren von .NET-Typen finden Sie unter [Formatieren von Typen in .NET](../../../standard/base-types/formatting-types.md).
  
## <a name="substrings"></a>Teilzeichenfolgen  
 Eine Teilzeichenfolge ist eine beliebige Sequenz von Zeichen, die in einer Zeichenfolge enthalten ist. Verwenden Sie die <xref:System.String.Substring%2A>-Methode, um eine neue Zeichenfolge aus einem Teil der ursprünglichen Zeichenfolge zu erstellen. Sie können nach einem oder mehreren Vorkommnissen einer Teilzeichenfolge suchen, indem Sie die <xref:System.String.IndexOf%2A>-Methode verwenden. Verwenden Sie die <xref:System.String.Replace%2A>-Methode, um alle Vorkommnisse einer angegebenen Teilzeichenfolge mit einer neuen Zeichenfolge zu ersetzen. Genauso wie die <xref:System.String.Substring%2A>-Methode gibt <xref:System.String.Replace%2A> tatsächlich eine neue Zeichenfolge zurück und ändert nicht die ursprüngliche Zeichenfolge. Weitere Informationen finden Sie unter [Suchen von Zeichenfolgen mithilfe von Zeichenfolgenmethoden](../../how-to/search-strings.md) und [Ändern von Zeichenfolgeninhalten](../../how-to/modify-string-contents.md).
  
 [!code-csharp[csProgGuideStrings#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#7)]  
  
## <a name="accessing-individual-characters"></a>Zugreifen auf einzelne Zeichen  
 Sie können die Arraynotation mit einem Indexwert verwenden, um schreibgeschützten Zugriff auf einzelne Zeichen zu erhalten, so wie in folgendem Beispiel gezeigt:  
  
 [!code-csharp[csProgGuideStrings#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#8)]  
  
 Wenn die <xref:System.String>-Methoden nicht die Funktionen bieten, die Sie zum Bearbeiten einzelner Zeichen in einer Zeichenfolge benötigen, können Sie ein <xref:System.Text.StringBuilder>-Objekt verwenden, um die einzelnen Chars „direkt“ zu bearbeiten und anschließend eine neue Zeichenfolge zu <xref:System.Text.StringBuilder>-Methoden zu speichern. Im folgenden Beispiel wird davon ausgegangen, dass Sie die ursprüngliche Zeichenfolge auf eine bestimmte Weise ändern und die Ergebnisse für die zukünftige Verwendung speichern müssen:  
  
 [!code-csharp[csProgGuideStrings#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#27)]  
  
## <a name="null-strings-and-empty-strings"></a>NULL-Zeichenfolgen und leere Zeichenfolgen  
 Eine leere Zeichenfolge ist eine Instanz eines <xref:System.String?displayProperty=nameWithType>-Objekts, dass 0 Zeichen enthält. Leere Zeichenfolgen werden häufig in verschiedenen Programmierszenarios verwendet, um ein leeres Textfeld darzustellen. Sie können Methoden für leere Zeichenfolgen aufrufen, da sie gültige <xref:System.String?displayProperty=nameWithType>-Objekte sind. Leere Zeichenfolgen werden wie folgt initialisiert:  
  
```csharp  
string s = String.Empty;  
```  
  
 Im Gegensatz dazu, verweist eine NULL-Zeichenfolge nicht auf eine Instanz eines <xref:System.String?displayProperty=nameWithType>-Objekts und jeder Versuch, eine Methode für eine NULL-Zeichenfolge aufzurufen, löst eine <xref:System.NullReferenceException> aus. Allerdings können Sie NULL-Zeichenfolgen in Verkettungs- und Vergleichsoperationen mit anderen Zeichenfolgen verwenden. Die folgenden Beispiele veranschaulichen einige Fälle, in denen ein Verweis auf eine NULL-Zeichenfolge nicht dazu führt, dass eine Ausnahme ausgelöst wird:  
  
 [!code-csharp[csProgGuideStrings#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#20)]  
  
## <a name="using-stringbuilder-for-fast-string-creation"></a>Verwenden von StringBuilder für die schnelle Erstellung von Zeichenfolgen  
 Zeichenfolgenoperationen in .NET werden hochgradig optimiert und wirken sich in den meisten Fällen nicht erheblich auf die Leistung aus. In einigen Szenarios, z.B. in engen Schleifen, die Hunderttausende Male ausgeführt werden, können sich Zeichenfolgenoperationen auf die Leistung auswirken. Die <xref:System.Text.StringBuilder>-Klasse erstellt einen Zeichenfolgenpuffer, der eine verbesserte Leistung mit sich bringt, wenn Ihr Programm viele Zeichenfolgenbearbeitungen durchführt. Mit der <xref:System.Text.StringBuilder>-Zeichenfolge können Sie auch einzelne Zeichen erneut zuweisen, was der integrierte String-Datentyp nicht unterstützt. Dieser Code ändert z.B. den Inhalt einer Zeichenfolge ohne eine neue Zeichenfolge zu erstellen:  
  
 [!code-csharp[csProgGuideStrings#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#15)]  
  
 In diesem Beispiel wird ein <xref:System.Text.StringBuilder>-Objekt zum Erstellen einer Zeichenfolge aus einem Satz von numerischen Typen verwendet:  
  
 [!code-csharp[TestStringBuilder#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/TestStringBuilder.cs)]
  
## <a name="strings-extension-methods-and-linq"></a>Zeichenfolgen, Erweiterungsmethoden und LINQ  
 Da der <xref:System.String>-Typ <xref:System.Collections.Generic.IEnumerable%601> implementiert, können Sie die Erweiterungsmethode verwenden, die in der <xref:System.Linq.Enumerable>-Klasse auf Zeichenfolgen definiert ist. Um „visuelle Überfrachtung“ zu vermeiden, werden diese Methode für den <xref:System.String>-Typ aus IntelliSense ausgeschlossen, nichtsdestotrotz sind sie weiterhin verfügbar. Sie können auch LINQ-Abfrageausdrücke in Zeichenfolgen verwenden. Weitere Informationen finden Sie unter [LINQ und Zeichenfolgen](../concepts/linq/linq-and-strings.md).  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Thema|Beschreibung|  
|-----------|-----------------|  
|[Ändern von Zeichenfolgeninhalten](../../how-to/modify-string-contents.md)|Veranschaulicht Methoden zum Transformieren von Zeichenfolgen und Modifizieren von Zeichenfolgeninhalten.|  
|[Vergleichen von Zeichenfolgen](../../how-to/compare-strings.md)|So führen Sie ordinale und kulturspezifische Zeichenfolgenvergleiche durch.|  
|[Verketten mehrerer Zeichenfolgen](../../how-to/concatenate-multiple-strings.md)|Veranschaulicht verschiedene Möglichkeiten, mehrere Zeichenfolgen zu einer einzigen zu verknüpfen.|
|[Analysieren von Zeichenfolgen mithilfe von String.Split](../../how-to/parse-strings-using-split.md)|Enthält Codebeispiele, die veranschaulichen, wie Sie die `String.Split`-Methode zum Analysieren von Zeichenfolgen verwenden.|  
|[Suchen von Zeichenfolgen](../../how-to/search-strings.md)|Erläutert, wie Sie mit der Suche Zeichenfolgen nach spezifischem Text oder spezifischen Mustern durchsuchen können.|  
|[Bestimmen, ob eine Zeichenfolge einen numerischen Wert darstellt](./how-to-determine-whether-a-string-represents-a-numeric-value.md)|Zeigt, wie Sie sicher eine Zeichenfolge analysieren, um zu sehen, ob diese über einen gültigen numerischen Wert verfügt|  
|[Zeichenfolgeninterpolation](../../language-reference/tokens/interpolated.md)|Beschreibt die Funktion zur Zeichenfolgeninterpolation, die eine zweckmäßige Syntax zum Formatieren von Zeichenfolgen bietet.|
|[Grundlegende Zeichenfolgenoperationen](../../../standard/base-types/basic-string-operations.md)|Stellt Links zu Themen bereit, die <xref:System.String?displayProperty=nameWithType>- und <xref:System.Text.StringBuilder?displayProperty=nameWithType>-Methoden verwenden, um grundlegende Zeichenfolgenoperationen durchzuführen|  
|[Analysieren von Zeichenfolgen in .NET](../../../standard/base-types/parsing-strings.md)|Beschreibt das Konvertieren von Zeichenfolgendarstellungen der .NET-Basistypen in Instanzen der entsprechenden Typen.|  
|[Analysieren von Zeichenfolgen für Datum und Uhrzeit in .NET](../../../standard/base-types/parsing-datetime.md)|Zeigt, wie eine Zeichenfolge wie "01/24/2008" in ein <xref:System.DateTime?displayProperty=nameWithType>-Objekt konvertiert wird|  
|[Vergleichen von Zeichenfolgen](../../../standard/base-types/comparing.md)|Enthält Informationen, wie Zeichenfolgen verglichen werden, und gibt Beispiele in C# und Visual Basic|  
|[Verwenden der StringBuilder-Klasse](../../../standard/base-types/stringbuilder.md)|Beschreibt das Erstellen und Ändern dynamischer Zeichenfolgenobjekte mithilfe der <xref:System.Text.StringBuilder>-Klasse|  
|[LINQ und Zeichenfolgen](../concepts/linq/linq-and-strings.md)|Enthält Informationen zum Ausführen verschiedener Zeichenfolgenoperationen mithilfe von LINQ-Abfragen|  
|[C#-Programmierhandbuch](../index.md)|Enthält Links zu Themen, in denen die Konstrukte der Programmierung in C# beschrieben werden|  
