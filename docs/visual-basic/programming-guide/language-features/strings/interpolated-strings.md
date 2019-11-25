---
title: Interpolierte Zeichenfolgen
ms.date: 10/31/2017
ms.openlocfilehash: d1220f3804d571f6da229dc5dfa099a22ab1478d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344329"
---
# <a name="interpolated-strings-visual-basic-reference"></a>Interpolated Strings (Visual Basic Reference)

Zum Erstellen von Zeichenfolgen verwendet.  Eine interpolierte Zeichenfolge sieht wie eine Vorlagenzeichenfolge aus, die *interpolierte Ausdrücke* enthält.  Eine interpolierte Zeichenfolge gibt eine Zeichenfolge zurück, die die interpolierten Ausdrücke, die sie enthält, durch deren Zeichenfolgenrepräsentation ersetzt. This feature is available in Visual Basic 14 and later versions.

Die Argumente einer interpolierten Zeichenfolge sind leichter zu verstehen als eine [Zusammengesetzte Formatzeichenfolge](../../../../standard/base-types/composite-formatting.md#composite-format-string).  Die interpolierte Zeichenfolge

```vb
Console.WriteLine($"Name = {name}, hours = {hours:hh}")
```

enthält z.B. zwei interpolierte Ausdrücke: „{name}“ und „{hours:hh}“. Die entsprechende zusammengesetzte Zeichenfolge lautet:

```vb
Console.WriteLine("Name = {0}, hours = {1:hh}", name, hours)
```

Die Struktur einer interpolierten Zeichenfolge lautet:

```vb
$"<text> {<interpolated-expression> [,<field-width>] [:<format-string>] } <text> ..."
```

Dabei gilt:

- *field-width* ist eine Ganzzahl mit Vorzeichen, die die Anzahl von Zeichen in einem Feld angibt. Wenn sie positiv ist, ist das Feld rechtsbündig; wenn sie negativ ist, ist es linksbündig.

- *format-string* ist eine Formatzeichenfolge, die zu dem Objekttyp passt, der formatiert wird. For example, for a <xref:System.DateTime> value, it could be a [standard date and time format string](../../../../standard/base-types/standard-date-and-time-format-strings.md) such as "D" or "d".

> [!IMPORTANT]
> Zwischen `$` und `"` am Anfang der Zeichenfolge dürfen sich keine Leerzeichen befinden. Doing so causes a compiler error.

Eine interpolierte Zeichenfolge können Sie überall dort verwenden, wo Sie ein Zeichenfolgenliteral verwenden.  Die interpolierte Zeichenfolge wird immer nach ausgewertet, wenn der Code mit der interpolierten Zeichenfolge ausgeführt wird. So können Sie die Definition und die Auswertung einer interpolierten Zeichenfolge voneinander trennen.

Um eine geschweifte Klammer („{“ oder „}“) in eine interpolierte Zeichenfolge einzuschließen, verwenden Sie zwei geschweifte Klammern („{{“ oder „}}“).  Ausführliche Informationen finden Sie im Abschnitt „Implizite Konvertierungen“.

Wenn die interpolierte Zeichenfolge andere Zeichen mit besonderen Bedeutungen für eine interpolierte Zeichenfolge enthält, wie z.B. Anführungszeichen („), Doppelpunkte (:) oder Kommas (,), sollten diese mit Escapezeichen verwendet werden, wenn sie in Literaltext vorkommen, oder sie sollten in einen Ausdruck eingefügt werden, der durch Klammern getrennt wird, wenn sie Sprachelemente sind, die in einem interpolierten Ausdruck vorkommen. In folgendem Beispiel werden Anführungszeichen mit Escapezeichen verwendet, um diese in der Ergebniszeichenfolge zu beinhalten; Klammern werden zur Trennung des Ausdrucks `(age == 1 ? "" : "s")` verwendet, damit der Doppelpunkt nicht als Beginn einer Formatzeichenfolge gewertet wird.

[!code-vb[interpolated-strings](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings4.vb)]

## <a name="implicit-conversions"></a>Implizite Konvertierungen

Es gibt drei implizite Typkonvertierungen aus einer interpolierten Zeichenfolge:

1. Die Konvertierung einer interpolierten Zeichenfolge in <xref:System.String>. In folgendem Beispiel wird eine Zeichenfolge zurückgegeben, deren interpolierte Zeichenfolgenausdrücke durch deren Zeichenfolgenrepräsentationen ersetzt wurden. Beispiel:

   [!code-vb[interpolated-strings1](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings1.vb)]

   Das ist das endgültige Ergebnis einer Zeichenfolgeninterpretation. Alle Vorkommen von doppelten geschweiften Klammern („{{“ oder „}}“) werden in einzelne geschweifte Klammern konvertiert.

2. Die Konvertierung einer interpolierten Zeichenfolge in eine <xref:System.IFormattable>-Variable, die es Ihnen ermöglicht, mehrere Ergebniszeichenfolgen mit kulturspezifischem Inhalt aus einer einzelnen <xref:System.IFormattable>-Instanz zu erstellen. Dies ist nützlich, wenn sie z.B. die richtigen numerischen und Datumsformate für eine einzelne Kultur einfügen möchten.  Alle Vorkommen von doppelten geschweiften Klammern („{{“ oder „}}“) bleiben bestehen, bis Sie die Zeichenfolge formatieren, indem sie die Methode <xref:System.Object.ToString> implizit oder explizit aufrufen.  All contained interpolation expressions are converted to {0}, {1}, and so on.

   Im folgendem Beispiel wird die Reflektion verwendet, um die Member sowie die Felder- und Eigenschaftwerte der <xref:System.IFormattable>-Variablen anzuzeigen, die aus einer interpolierten Zeichenfolge erstellt wird. Außerdem wird die <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>-Variable an die <xref:System.IFormattable>-Methode übergeben.

   [!code-vb[interpolated-strings2](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings2.vb)]

   Beachten Sie, dass die interpolierte Zeichenfolge nur mithilfe von Reflektion überprüft werden kann. Wenn sie an eine Methode zum Formatieren von Zeichenfolgen übergeben wird, wie z.B. <xref:System.Console.WriteLine(System.String)>, werden ihre Formatelemente aufgelöst und die Ergebniszeichenfolge zurückgegeben.

3. Conversion of an interpolated string to a <xref:System.FormattableString> variable that represents a composite format string. Das Überprüfen der zusammengesetzten Zeichenfolge und wie diese als Ergebniszeichenfolge rendert, hilft Ihnen z.B möglicherweise dabei, sich gegen einen Einschleusungsangriff zu schützen, während Sie eine Abfrage erstellen. A <xref:System.FormattableString> also includes:

      - Eine Überladung von <xref:System.FormattableString.ToString>, die eine Ergebniszeichenfolge für das <xref:System.Globalization.CultureInfo.CurrentCulture>-Element erzeugt.

      - A <xref:System.FormattableString.Invariant%2A> method that produces a string for the <xref:System.Globalization.CultureInfo.InvariantCulture>.

      - Eine <xref:System.FormattableString.ToString(System.IFormatProvider)>-Methode, die eine Ergebniszeichenfolge für eine bestimmte Kultur erzeugt.

    All occurrences of double curly braces ("{{" and "}}") remain as double curly braces until you format.  All contained interpolation expressions are converted to {0}, {1}, and so on.

   [!code-vb[interpolated-strings3](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings3.vb)]

## <a name="see-also"></a>Siehe auch

- <xref:System.IFormattable?displayProperty=nameWithType>
- <xref:System.FormattableString?displayProperty=nameWithType>
- [Sprachreferenz zu Visual Basic](index.md)
