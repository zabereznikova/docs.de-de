---
title: Interpolierte Zeichenfolgen (Visual Basic)
ms.date: 10/31/2017
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f865d5a7167847bf869d70a39570413dac271a2c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="interpolated-strings-visual-basic-reference"></a>Interpolierte Zeichenfolgen (Visual Basic-Referenz)

Zum Erstellen von Zeichenfolgen verwendet.  Eine interpolierte Zeichenfolge sieht wie eine Vorlagenzeichenfolge aus, die *interpolierte Ausdrücke* enthält.  Eine interpolierte Zeichenfolge gibt eine Zeichenfolge zurück, die die interpolierten Ausdrücke, die sie enthält, durch deren Zeichenfolgenrepräsentation ersetzt. Diese Funktion ist in Visual Basic-14 und höher verfügbar.

Die Argumente einer interpolierten Zeichenfolge sind leichter zu verstehen als eine [Zusammengesetzte Formatzeichenfolge](../../../../standard/base-types/composite-formatting.md#composite-format-string).  Die interpolierte Zeichenfolge  
  
```vb  
Console.WriteLine($"Name = {name}, hours = {hours:hh}")
```  
enthält z.B. zwei interpolierte Ausdrücke: „{name}“ und „{hours:hh}“. Die entsprechende zusammengesetzte Zeichenfolge lautet:

```vb
Console.WriteLine("Name = {0}, hours = {1:hh}", name, hours); 
```  

Die Struktur einer interpolierten Zeichenfolge lautet:  
  
```vb  
$"<text> {<interpolated-expression> [,<field-width>] [:<format-string>] } <text> ..."  
```  

Dabei gilt: 

- *field-width* ist eine Ganzzahl mit Vorzeichen, die die Anzahl von Zeichen in einem Feld angibt. Wenn sie positiv ist, ist das Feld rechtsbündig; wenn sie negativ ist, ist es linksbündig. 

- *format-string* ist eine Formatzeichenfolge, die zu dem Objekttyp passt, der formatiert wird. Z. B. für eine <xref:System.DateTime> Wert, es ist möglicherweise ein [Formatzeichenfolge Standardformatbezeichner für Datum und Uhrzeit](~/docs/standard/base-types/standard-date-and-time-format-strings.md) z. B. "D" oder "d".

> [!IMPORTANT]
> Sie sind keine Leerzeichen zwischen den `$` und `"` , der die Zeichenfolge beginnt. Auf diese Weise verursacht einen Compilerfehler.

 Eine interpolierte Zeichenfolge können Sie überall dort verwenden, wo Sie ein Zeichenfolgenliteral verwenden.  Die interpolierte Zeichenfolge wird immer nach ausgewertet, wenn der Code mit der interpolierten Zeichenfolge ausgeführt wird. So können Sie die Definition und die Auswertung einer interpolierten Zeichenfolge voneinander trennen.  
  
 Um eine geschweifte Klammer („{“ oder „}“) in eine interpolierte Zeichenfolge einzuschließen, verwenden Sie zwei geschweifte Klammern („{{“ oder „}}“).  Ausführliche Informationen finden Sie im Abschnitt „Implizite Konvertierungen“.  

Wenn die interpolierte Zeichenfolge andere Zeichen mit besonderen Bedeutungen für eine interpolierte Zeichenfolge enthält, wie z.B. Anführungszeichen („), Doppelpunkte (:) oder Kommas (,), sollten diese mit Escapezeichen verwendet werden, wenn sie in Literaltext vorkommen, oder sie sollten in einen Ausdruck eingefügt werden, der durch Klammern getrennt wird, wenn sie Sprachelemente sind, die in einem interpolierten Ausdruck vorkommen. In folgendem Beispiel werden Anführungszeichen mit Escapezeichen verwendet, um diese in der Ergebniszeichenfolge zu beinhalten; Klammern werden zur Trennung des Ausdrucks `(age == 1 ? "" : "s")` verwendet, damit der Doppelpunkt nicht als Beginn einer Formatzeichenfolge gewertet wird.

[!code-vb[interpolated-strings](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings4.vb)]  

## <a name="implicit-conversions"></a>Implizite Konvertierungen  

Es gibt drei implizite Typkonvertierungen aus einer interpolierten Zeichenfolge:  

1. Die Konvertierung einer interpolierten Zeichenfolge in <xref:System.String>. In folgendem Beispiel wird eine Zeichenfolge zurückgegeben, deren interpolierte Zeichenfolgenausdrücke durch deren Zeichenfolgenrepräsentationen ersetzt wurden. Zum Beispiel:

   [!code-vb[interpolated-strings1](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings1.vb)]  

   Das ist das endgültige Ergebnis einer Zeichenfolgeninterpretation. Alle Vorkommen von doppelten geschweiften Klammern („{{“ oder „}}“) werden in einzelne geschweifte Klammern konvertiert. 

2. Die Konvertierung einer interpolierten Zeichenfolge in eine <xref:System.IFormattable>-Variable, die es Ihnen ermöglicht, mehrere Ergebniszeichenfolgen mit kulturspezifischem Inhalt aus einer einzelnen <xref:System.IFormattable>-Instanz zu erstellen. Dies ist nützlich, wenn sie z.B. die richtigen numerischen und Datumsformate für eine einzelne Kultur einfügen möchten.  Alle Vorkommen von doppelten geschweiften Klammern („{{“ oder „}}“) bleiben bestehen, bis Sie die Zeichenfolge formatieren, indem sie die Methode <xref:System.Object.ToString> implizit oder explizit aufrufen.  Alle enthaltenen Interpolationsausdrücke werden in {0}, \{1\} usw. konvertiert.  

   Im folgendem Beispiel wird die Reflektion verwendet, um die Member sowie die Felder- und Eigenschaftwerte der <xref:System.IFormattable>-Variablen anzuzeigen, die aus einer interpolierten Zeichenfolge erstellt wird. Sie übergibt außerdem die <xref:System.IFormattable> -Variablen an die <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> Methode.

   [!code-vb[interpolated-strings2](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings2.vb)]  

   Beachten Sie, dass die interpolierte Zeichenfolge nur mithilfe von Reflektion überprüft werden kann. Wenn sie in eine Zeichenfolge, die Methode, wie z. B. Formatierung übergeben wird <xref:System.Console.WriteLine(System.String)>, dessen Formatelemente aufgelöst werden, und die Ergebniszeichenfolge zurückgegeben. 

3. Eine interpolierte Zeichenfolge, Konvertierung einer <xref:System.FormattableString> Variable, die eine kombinierte Formatierungszeichenfolge darstellt. Das Überprüfen der zusammengesetzten Zeichenfolge und wie diese als Ergebniszeichenfolge rendert, hilft Ihnen z.B möglicherweise dabei, sich gegen einen Einschleusungsangriff zu schützen, während Sie eine Abfrage erstellen. Ein <xref:System.FormattableString> enthält auch:

      - Ein <xref:System.FormattableString.ToString> Überladung, die erzeugt eine Ergebniszeichenfolge, die für die <xref:System.Globalization.CultureInfo.CurrentCulture>.
      
      - Ein <xref:System.FormattableString.Invariant%2A> -Methode, die erzeugt eine Zeichenfolge für die <xref:System.Globalization.CultureInfo.InvariantCulture>.
      
      - Ein <xref:System.FormattableString.ToString(System.IFormatProvider)> -Methode, die erzeugt eine Ergebniszeichenfolge, die für eine bestimmte Kultur. 
  
    Alle Vorkommen von doppelten geschweiften Klammern ("{{" und "}}") bleiben bestehen, bis Sie formatieren.  Alle enthaltenen Interpolationsausdrücke werden in {0}, \{1\} usw. konvertiert.  

   [!code-vb[interpolated-strings3](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings3.vb)]  

## <a name="see-also"></a>Siehe auch  
f<xref:System.IFormattable?displayProperty=nameWithType>   
 <xref:System.FormattableString?displayProperty=nameWithType>  
 [Sprachreferenz zu Visual Basic](index.md)  
 