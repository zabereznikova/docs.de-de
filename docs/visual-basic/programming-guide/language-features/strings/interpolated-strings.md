---
title: Interpolierte Zeichenfolgen
ms.date: 10/31/2017
ms.openlocfilehash: c427b48ce58a59ff3878f24f1989db6ac8c8239a
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "91805277"
---
# <a name="interpolated-strings-visual-basic-reference"></a>Interpoliert Zeichen folgen (Visual Basic Referenz)

Zum Erstellen von Zeichenfolgen verwendet.  Eine interpolierte Zeichenfolge sieht wie eine Vorlagenzeichenfolge aus, die *interpolierte Ausdrücke* enthält.  Eine interpolierte Zeichenfolge gibt eine Zeichenfolge zurück, die die interpolierten Ausdrücke, die sie enthält, durch deren Zeichenfolgenrepräsentation ersetzt. Diese Funktion ist in Visual Basic 14 und höheren Versionen verfügbar.

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

Dabei gilt Folgendes:

- *field-width* ist eine Ganzzahl mit Vorzeichen, die die Anzahl von Zeichen in einem Feld angibt. Wenn sie positiv ist, ist das Feld rechtsbündig; wenn sie negativ ist, ist es linksbündig.

- *format-string* ist eine Formatzeichenfolge, die zu dem Objekttyp passt, der formatiert wird. Bei einem <xref:System.DateTime> Wert kann es sich z. b. um eine [Standardformat Zeichenfolge für Datum und Uhrzeit](../../../../standard/base-types/standard-date-and-time-format-strings.md) wie z. b. "d" oder "d" handeln.

> [!IMPORTANT]
> Zwischen `$` und `"` am Anfang der Zeichenfolge dürfen sich keine Leerzeichen befinden. Dies verursacht einen Compilerfehler.

Eine interpolierte Zeichenfolge können Sie überall dort verwenden, wo Sie ein Zeichenfolgenliteral verwenden.  Die interpolierte Zeichenfolge wird immer nach ausgewertet, wenn der Code mit der interpolierten Zeichenfolge ausgeführt wird. So können Sie die Definition und die Auswertung einer interpolierten Zeichenfolge voneinander trennen.

Um eine geschweifte Klammer („{“ oder „}“) in eine interpolierte Zeichenfolge einzuschließen, verwenden Sie zwei geschweifte Klammern („{{“ oder „}}“).  Ausführliche Informationen finden Sie im Abschnitt „Implizite Konvertierungen“.

Wenn die interpolierte Zeichenfolge andere Zeichen mit besonderen Bedeutungen für eine interpolierte Zeichenfolge enthält, wie z.B. Anführungszeichen („), Doppelpunkte (:) oder Kommas (,), sollten diese mit Escapezeichen verwendet werden, wenn sie in Literaltext vorkommen, oder sie sollten in einen Ausdruck eingefügt werden, der durch Klammern getrennt wird, wenn sie Sprachelemente sind, die in einem interpolierten Ausdruck vorkommen. Im folgenden Beispiel werden Anführungszeichen mit Escapezeichen versehen, um Sie in die Ergebnis Zeichenfolge

[!code-vb[interpolated-strings](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings4.vb)]

## <a name="implicit-conversions"></a>Implizite Konvertierungen

Es gibt drei implizite Typkonvertierungen aus einer interpolierten Zeichenfolge:

1. Die Konvertierung einer interpolierten Zeichenfolge in <xref:System.String>. In folgendem Beispiel wird eine Zeichenfolge zurückgegeben, deren interpolierte Zeichenfolgenausdrücke durch deren Zeichenfolgenrepräsentationen ersetzt wurden. Beispiel:

   [!code-vb[interpolated-strings1](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings1.vb)]

   Das ist das endgültige Ergebnis einer Zeichenfolgeninterpretation. Alle Vorkommen von doppelten geschweiften Klammern („{{“ oder „}}“) werden in einzelne geschweifte Klammern konvertiert.

2. Die Konvertierung einer interpolierten Zeichenfolge in eine <xref:System.IFormattable>-Variable, die es Ihnen ermöglicht, mehrere Ergebniszeichenfolgen mit kulturspezifischem Inhalt aus einer einzelnen <xref:System.IFormattable>-Instanz zu erstellen. Dies ist nützlich, wenn sie z.B. die richtigen numerischen und Datumsformate für eine einzelne Kultur einfügen möchten.  Alle Vorkommen von doppelten geschweiften Klammern („{{“ oder „}}“) bleiben bestehen, bis Sie die Zeichenfolge formatieren, indem sie die Methode <xref:System.Object.ToString> implizit oder explizit aufrufen.  Alle enthaltenen Interpolations Ausdrücke werden in {0} , {1} usw. konvertiert.

   Im folgendem Beispiel wird die Reflektion verwendet, um die Member sowie die Felder- und Eigenschaftwerte der <xref:System.IFormattable>-Variablen anzuzeigen, die aus einer interpolierten Zeichenfolge erstellt wird. Außerdem wird die <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>-Variable an die <xref:System.IFormattable>-Methode übergeben.

   [!code-vb[interpolated-strings2](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings2.vb)]

   Beachten Sie, dass die interpolierte Zeichenfolge nur mithilfe von Reflektion überprüft werden kann. Wenn sie an eine Methode zum Formatieren von Zeichenfolgen übergeben wird, wie z.B. <xref:System.Console.WriteLine(System.String)>, werden ihre Formatelemente aufgelöst und die Ergebniszeichenfolge zurückgegeben.

3. Konvertierung einer interpoliert-Zeichenfolge in eine <xref:System.FormattableString> Variable, die eine kombinierte Format Zeichenfolge darstellt. Das Überprüfen der zusammengesetzten Zeichenfolge und wie diese als Ergebniszeichenfolge rendert, hilft Ihnen z.B möglicherweise dabei, sich gegen einen Einschleusungsangriff zu schützen, während Sie eine Abfrage erstellen. A <xref:System.FormattableString> umfasst auch Folgendes:

      - Eine Überladung von <xref:System.FormattableString.ToString>, die eine Ergebniszeichenfolge für das <xref:System.Globalization.CultureInfo.CurrentCulture>-Element erzeugt.

      - Eine <xref:System.FormattableString.Invariant%2A> Methode, die eine Zeichenfolge für den erzeugt <xref:System.Globalization.CultureInfo.InvariantCulture> .

      - Eine <xref:System.FormattableString.ToString(System.IFormatProvider)>-Methode, die eine Ergebniszeichenfolge für eine bestimmte Kultur erzeugt.

    Alle Vorkommen von doppelten geschweiften Klammern ("{{" und "}}") bleiben bestehen, bis Sie formatieren.  Alle enthaltenen Interpolations Ausdrücke werden in {0} , {1} usw. konvertiert.

   [!code-vb[interpolated-strings3](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings3.vb)]

## <a name="see-also"></a>Siehe auch

- <xref:System.IFormattable?displayProperty=nameWithType>
- <xref:System.FormattableString?displayProperty=nameWithType>
- [Sprachreferenz zu Visual Basic](index.md)
