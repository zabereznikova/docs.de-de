---
title: Interpolierte Zeichenfolgen (C#-Referenz)
ms.date: 10/18/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
ms.assetid: 324f267e-1c61-431a-97ed-852c1530742d
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b8a1fe0be82a0e09d61c66ed463199ff626c9faa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="interpolated-strings-c-reference"></a>Interpolierte Zeichenfolgen (C#-Referenz)

Zum Erstellen von Zeichenfolgen verwendet.  Eine interpolierte Zeichenfolge sieht wie eine Vorlagenzeichenfolge aus, die *interpolierte Ausdrücke* enthält.  Eine interpolierte Zeichenfolge gibt eine Zeichenfolge zurück, die die interpolierten Ausdrücke, die sie enthält, durch deren Zeichenfolgenrepräsentation ersetzt. Diese Funktion ist in c# 6- und neueren Versionen verfügbar.

Die Argumente einer interpolierten Zeichenfolge sind leichter zu verstehen als eine [Zusammengesetzte Formatzeichenfolge](../../../standard/base-types/composite-formatting.md#composite-format-string).  Die interpolierte Zeichenfolge  
  
```csharp  
Console.WriteLine($"Name = {name}, hours = {hours:hh}");
```  
enthält interpolierte Ausdrücken "{name}" und "{Stunde:" hh "}". Die entsprechende zusammengesetzte Zeichenfolge lautet:

```csharp
Console.WriteLine("Name = {0}, hours = {1:hh}", name, hours); 
```  

Die Struktur einer interpolierten Zeichenfolge lautet:  
  
```  
$"<text> {<interpolated-expression> [,<field-width>] [:<format-string>] } <text> ..."  
```  

Dabei gilt: 

- *field-width* ist eine Ganzzahl mit Vorzeichen, die die Anzahl von Zeichen in einem Feld angibt. Wenn sie positiv ist, ist das Feld rechtsbündig; wenn sie negativ ist, ist es linksbündig. 

- *format-string* ist eine Formatzeichenfolge, die zu dem Objekttyp passt, der formatiert wird. Für den Wert <xref:System.DateTime> wäre es beispielsweise eine Standardzeichenfolge für Datum und Zeit wie etwa „D“ und „d“.

> [!IMPORTANT]
> Zwischen `$` und dem `"` am Anfang der Zeichenfolge dürfen keine Leerzeichen gesetzt werden. Dies hätte einen Kompilierzeitfehler zur Folge.

 Eine interpolierte Zeichenfolge können Sie überall dort verwenden, wo Sie ein Zeichenfolgenliteral verwenden.  Die interpolierte Zeichenfolge wird immer nach ausgewertet, wenn der Code mit der interpolierten Zeichenfolge ausgeführt wird. So können Sie die Definition und die Auswertung einer interpolierten Zeichenfolge voneinander trennen.  
  
 Um eine geschweifte Klammer („{“ oder „}“) in eine interpolierte Zeichenfolge einzuschließen, verwenden Sie zwei geschweifte Klammern („{{“ oder „}}“).  Ausführliche Informationen finden Sie im Abschnitt „Implizite Konvertierungen“.  

Wenn die interpolierte Zeichenfolge andere Zeichen mit besonderen Bedeutungen für eine interpolierte Zeichenfolge enthält, wie z.B. Anführungszeichen („), Doppelpunkte (:) oder Kommas (,), sollten diese mit Escapezeichen verwendet werden, wenn sie in Literaltext vorkommen, oder sie sollten in einen Ausdruck eingefügt werden, der durch Klammern getrennt wird, wenn sie Sprachelemente sind, die in einem interpolierten Ausdruck vorkommen. In folgendem Beispiel werden Anführungszeichen mit Escapezeichen verwendet, um diese in der Ergebniszeichenfolge zu beinhalten; Klammern werden zur Trennung des Ausdrucks `(age == 1 ? "" : "s")` verwendet, damit der Doppelpunkt nicht als Beginn einer Formatzeichenfolge gewertet wird.

[!code-csharp[interpolated-strings4](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings4.cs#1)]  

Wörtlich interpoliert Zeichenfolgen verwenden die `$` Zeichen, gefolgt von den `@` Zeichen. Weitere Informationen zu wörtliche Zeichenfolgen, finden Sie unter der [Zeichenfolge](string.md) Thema. Der folgende Code ist eine geänderte Version des vorherigen Ausschnitts mit wörtliche interpolierten Zeichenfolge:

[!code-csharp[interpolated-strings4](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings5.cs#1)]  

Die Formatierungsänderungen sind erforderlich, da wörtliche Zeichenfolgen nicht entsprechen, müssen `\` Escapesequenzen.

> [!IMPORTANT]
> Die `$` Token muss angezeigt werden, bevor die `@` token wörtliche interpolierten Zeichenfolge.


## <a name="implicit-conversions"></a>Implizite Konvertierungen  

Es gibt drei implizite Typkonvertierungen aus einer interpolierten Zeichenfolge:  

1. Die Konvertierung einer interpolierten Zeichenfolge in <xref:System.String>. In folgendem Beispiel wird eine Zeichenfolge zurückgegeben, deren interpolierte Zeichenfolgenausdrücke durch deren Zeichenfolgenrepräsentationen ersetzt wurden. Zum Beispiel:

   [!code-csharp[interpolated-strings1](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings1.cs#1)]  

   Das ist das endgültige Ergebnis einer Zeichenfolgeninterpretation. Alle Vorkommen von doppelten geschweiften Klammern („{{“ oder „}}“) werden in einzelne geschweifte Klammern konvertiert. 

2. Die Konvertierung einer interpolierten Zeichenfolge in eine <xref:System.IFormattable>-Variable, die es Ihnen ermöglicht, mehrere Ergebniszeichenfolgen mit kulturspezifischem Inhalt aus einer einzelnen <xref:System.IFormattable>-Instanz zu erstellen. Dies ist nützlich, wenn sie z.B. die richtigen numerischen und Datumsformate für eine einzelne Kultur einfügen möchten.  Alle Vorkommen von doppelten geschweiften Klammern („{{“ oder „}}“) bleiben bestehen, bis Sie die Zeichenfolge formatieren, indem sie die Methode <xref:System.Object.ToString> implizit oder explizit aufrufen.  Alle enthaltenen Interpolationsausdrücke werden in {0}, \{1\} usw. konvertiert.  

   Im folgendem Beispiel wird die Reflektion verwendet, um die Member sowie die Felder- und Eigenschaftwerte der <xref:System.IFormattable>-Variablen anzuzeigen, die aus einer interpolierten Zeichenfolge erstellt wird. Sie übergibt außerdem die <xref:System.IFormattable> -Variablen an die <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> Methode.

   [!code-csharp[interpolated-strings2](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings2.cs#1)]  

   Beachten Sie, dass die interpolierte Zeichenfolge nur mithilfe von Reflektion überprüft werden kann. Wenn sie in eine Zeichenfolge, die Methode, wie z. B. Formatierung übergeben wird <xref:System.Console.WriteLine(System.String)>, dessen Formatelemente aufgelöst werden, und die Ergebniszeichenfolge zurückgegeben. 

3. Die Konvertierung einer interpolierten Zeichenfolge in eine <xref:System.FormattableString>-Variable, die eine zusammengesetzte Formatzeichenfolge repräsentiert. Das Überprüfen der zusammengesetzten Zeichenfolge und wie diese als Ergebniszeichenfolge rendert, hilft Ihnen z.B möglicherweise dabei, sich gegen einen Einschleusungsangriff zu schützen, während Sie eine Abfrage erstellen. <xref:System.FormattableString> enthält auch <xref:System.FormattableString.ToString>-Überladungen, mit denen Sie Ergebniszeichenfolgen für die Objekte <xref:System.Globalization.CultureInfo.InvariantCulture> und <xref:System.Globalization.CultureInfo.CurrentCulture> erzeugen können.  Alle Vorkommen von doppelten geschweiften Klammern („{{“ oder „}}“) bleiben bestehen, bis Sie die Zeichenfolge formatieren.  Alle enthaltenen Interpolationsausdrücke werden in {0}, \{1\} usw. konvertiert.  

   [!code-csharp[interpolated-strings3](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings3.cs#1)]  

## <a name="language-specification"></a>Sprachspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IFormattable?displayProperty=nameWithType>  
 <xref:System.FormattableString?displayProperty=nameWithType>  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
