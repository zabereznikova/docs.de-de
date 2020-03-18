---
title: 'Vorgehensweise: Durchsuchen von Zeichenfolgen (C#-Anleitung)'
ms.date: 02/21/2018
helpviewer_keywords:
- searching strings [C#]
- strings [C#], searching with String methods
- strings [C#], searching with regular expressions
ms.assetid: fb1d9a6d-598d-4a35-bd5f-b86012edcb2b
ms.openlocfilehash: 15ea77d13a93d88bd996a22b6fe1aaad81df572d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "74959701"
---
# <a name="how-to-search-strings"></a>Vorgehensweise: Durchsuchen von Zeichenfolgen

Sie können zwei Strategien verwenden, um in Zeichenfolgen nach Text zu suchen. Methoden der <xref:System.String>-Klasse suchen nach einem bestimmten Text. Reguläre Ausdrücke suchen nach Mustern im Text.

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

Der [Zeichenfolgen](../language-reference/builtin-types/reference-types.md#the-string-type)-Typ, der ein Alias für die Klasse <xref:System.String?displayProperty=nameWithType> ist, enthält eine Reihe nützlicher Methoden, um den Inhalt einer Zeichenfolge zu durchsuchen. Dazu zählen <xref:System.String.Contains%2A>, <xref:System.String.StartsWith%2A>, <xref:System.String.EndsWith%2A>, <xref:System.String.IndexOf%2A>, <xref:System.String.LastIndexOf%2A>. Die <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType>-Klasse bietet ein umfangreiches Vokabular zum Suchen nach Mustern im Text. In diesem Artikel lernen Sie diese Techniken kennen und erfahren, wie Sie die am besten geeignete Methode für Ihre Anforderungen auswählen.

## <a name="does-a-string-contain-text"></a>Enthält eine Zeichenfolge Text?

Die Methoden <xref:System.String.Contains%2A?displayProperty=nameWithType>, <xref:System.String.StartsWith%2A?displayProperty=nameWithType> und <xref:System.String.EndsWith%2A?displayProperty=nameWithType> durchsuchen eine Zeichenfolge nach einem bestimmten Text. Das folgende Beispiel zeigt jede dieser Methoden und eine Variante, die einen Suchvorgang verwendet, bei dem die Groß-/Kleinschreibung nicht beachtet wird:

[!code-csharp-interactive[search strings using methods](../../../samples/snippets/csharp/how-to/strings/SearchStrings.cs#1)]

Das obige Beispiel veranschaulicht eine wichtigen Aspekt bei der Verwendung dieser Methoden. Bei Suchvorgängen wird standardmäßig **die Groß-/Kleinschreibung beachtet**. Um einen Suchvorgang anzugeben, bei dem die Groß-/Kleinschreibung nicht beachtet wird, verwenden Sie den Enumerationswert <xref:System.StringComparison.CurrentCultureIgnoreCase?displayProperty=nameWithType>.

## <a name="where-does-the-sought-text-occur-in-a-string"></a>An welcher Stelle einer Zeichenfolge befindet sich der gesuchte Text ?

Die Methoden <xref:System.String.IndexOf%2A> und <xref:System.String.LastIndexOf%2A> suchen ebenfalls nach Text in Zeichenfolgen. Diese Methoden geben die Position des gesuchten Texts zurück. Wenn der Text nicht gefunden wird, geben sie `-1` zurück. Das folgende Beispiel sucht nach dem ersten und letzten Vorkommen des Worts „methods“ und zeigt den Text dazwischen an.
  
[!code-csharp-interactive[search strings for indices](../../../samples/snippets/csharp/how-to/strings/SearchStrings.cs#2)]

## <a name="finding-specific-text-using-regular-expressions"></a>Suchen nach einem bestimmten Text mithilfe von regulären Ausdrücken

Die <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType>-Klasse kann zum durchsuchen von Zeichenfolgen verwendet werden. Die Komplexität dieser Suchvorgänge reicht von sehr einfachen bis hin zu komplizierten Textmustern.

Das folgende Codebeispiel sucht nach dem Wort „the“ oder „their“ in einem Satz, die Groß-/Kleinschreibung wird ignoriert. Die statische Methode <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> führt die Suche aus. Die zu durchsuchende Zeichenfolge und ein Suchmuster werden an die Methode übergeben. In diesem Fall gibt ein drittes Argument an, dass die Groß-/Kleinschreibung nicht beachtet werden soll. Weitere Informationen finden Sie unter <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=nameWithType>.  

Das Suchmuster beschreibt den Text, nach dem Sie suchen. In der folgenden Tabelle werden die einzelnen Elemente des Suchmusters beschrieben. (In der Tabelle unten wird ein einzelnes `\`-Zeichen verwendet. Dieses muss in einer C#-Zeichenfolge durch das Escapezeichen `\\` ersetzt werden.)

| pattern  | Bedeutung     |
| -------- |-------------|
| Verbindung im Abschnitt      | Findet den Text „the“. |
| (eir)?   | Findet 0 oder 1 Vorkommen von „eir“. |
| \s       | Findet Zeichen für Leerraum.    |
  
[!code-csharp-interactive[Search using regular expressions](../../../samples/snippets/csharp/how-to/strings/SearchStrings.cs#3)]
  
> [!TIP]
> Die `string`-Methoden sind bei der Suche nach einer genauen Zeichenfolge in der Regel die bessere Wahl. Reguläre Ausdrücke eignen sich besser, wenn Sie nach einem bestimmten Muster in einer Quellzeichenfolge suchen.

## <a name="does-a-string-follow-a-pattern"></a>Folgt eine Zeichenfolge einem Muster?

Der folgende Code verwendet reguläre Ausdrücke, um das Format jeder Zeichenfolge in einem Array zu überprüfen. Für die Überprüfung ist erforderlich, dass jede Zeichenfolge die Form einer Telefonnummer aufweist, in der drei Gruppen von Ziffern durch Bindestriche getrennt sind, wobei die ersten beiden Gruppen je drei Ziffern enthalten und die dritte Gruppe vier Ziffern umfasst. Das Suchmuster verwendet den regulären Ausdruck `^\\d{3}-\\d{3}-\\d{4}$`. Weitere Informationen finden Sie unter [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](../../standard/base-types/regular-expression-language-quick-reference.md).

| pattern  | Bedeutung                             |
| -------- |-------------------------------------|
| ^        | Findet den Anfang der Zeichenfolge. |
| \d{3}    | Findet genau 3 Ziffernzeichen.  |
| -        | Findet das Zeichen „-“.           |
| \d{3}    | Findet genau 3 Ziffernzeichen.  |
| -        | Findet das Zeichen „-“.           |
| \d{4}    | Findet genau 4 Ziffernzeichen.  |
| $        | Findet das Ende der Zeichenfolge.       |

[!code-csharp-interactive[csProgGuideStrings#4](../../../samples/snippets/csharp/how-to/strings/SearchStrings.cs#4)]

Dieses einzelne Suchmuster findet alle gültigen Zeichenfolgen. Reguläre Ausdrücke eignen sich besser zum Suchen nach Mustern oder zum Überprüfen von Zeichenfolgen anhand eines Musters als für einzelne Zeichenfolgen.

Sie können diese Beispiele ausprobieren, indem Sie sich den Code in unserem [GitHub-Repository](https://github.com/dotnet/samples/tree/master/snippets/csharp/how-to/strings) ansehen. Alternativ dazu können Sie die Beispiele [als ZIP-Datei](https://github.com/dotnet/samples/raw/master/snippets/csharp/how-to/strings.zip) herunterladen.

## <a name="see-also"></a>Weitere Informationen

- [C#-Programmierhandbuch](../programming-guide/index.md)
- [Zeichenfolgen](../programming-guide/strings/index.md)
- [LINQ und Zeichenfolgen](../programming-guide/concepts/linq/linq-and-strings.md)
- <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType>
- [Reguläre Ausdrücke von .NET Framework](../../standard/base-types/regular-expressions.md)
- [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](../../standard/base-types/regular-expression-language-quick-reference.md)
- [Empfohlene Vorgehensweisen für die Verwendung von Zeichenfolgen in .NET](../../standard/base-types/best-practices-strings.md)
