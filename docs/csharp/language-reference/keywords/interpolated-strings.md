---
title: "Interpolierte Zeichenfolgen (C#- und Visual Basic-Referenz) | Microsoft Docs"
ms.date: "2017-02-03"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
ms.assetid: 324f267e-1c61-431a-97ed-852c1530742d
caps.latest.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 9
---
# Interpolierte Zeichenfolgen (C#- und Visual Basic-Referenz)
Zum Erstellen von Zeichenfolgen verwendet.  Ein Ausdruck für eine interpolierte Zeichenfolge sieht wie eine Vorlagenzeichenfolge aus, die Ausdrücke enthält.  Ein Ausdruck für eine interpolierte Zeichenfolge erstellt eine Zeichenfolge durch Ersetzen der enthaltenen Ausdrücke durch die ToString\-Darstellungen der Ergebnisse dieser Ausdrücke.  Eine interpolierte Zeichenfolge ist in Bezug auf die Argumente leichter zu verstehen als eine [Kombinierte Formatierung](../Topic/Composite%20Formatting.md).  Im Folgenden ein Beispiel für eine interpolierte Zeichenfolge:  
  
```c#  
Console.WriteLine($"Name = {name}, hours = {hours:hh}")  
```  
  
 Die Struktur einer interpolierten Zeichenfolge lautet wie folgt:  
  
```  
$ " <text> { <interpolation-expression> <optional-comma-field-width> <optional-colon-format> } <text> ... } "  
```  
  
 Eine interpolierte Zeichenfolge können Sie überall dort verwenden, wo Sie ein Zeichenfolgenliteral verwenden.  Wenn bei der Ausführung Ihres Programms der Code mit dem interpolierten Zeichenfolgenliteral ausgeführt würde, berechnet der Code ein neues Zeichenfolgenliteral durch Auswertung der Interpolationsausdrücke.  Diese Berechnung erfolgt jedes Mal, wenn der Code mit der interpolierten Zeichenfolge ausgeführt wird.  
  
 Um eine geschweifte Klammer \(„{“ oder „}“\) in eine interpolierte Zeichenfolge einzuschließen, verwenden Sie zwei geschweifte Klammern \(„{{“ oder „}}“\).  Ausführliche Informationen finden Sie im Abschnitt „Implizite Konvertierungen“.  
  
## Implizite Konvertierungen  
 Folgendes sind implizite Typkonvertierungen aus einer interpolierten Zeichenfolge:  
  
```c#  
var s = $"hello, {name}" System.IFormattable s = $"Hello, {name}" System.FormattableString s = $"Hello, {name}"  
  
```  
  
 Das erste Beispiel erzeugt einen `string`\-Wert, in dem alle Werte der Zeichenfolgeninterpolierungen berechnet wurden.  Es ist das Endergebnis und weist den Typ „Zeichenfolge“ auf.  Alle Vorkommen von doppelten geschweiften Klammern \(„{{“ oder „}}“\) werden in einzelne geschweifte Klammern konvertiert.  
  
 Das zweite Beispiel führt zu einer <xref:System.IFormattable>\-Variable, die es ermöglicht, die Zeichenfolge mit invariantem Kontext zu konvertieren.  Dies ist hilfreich, um numerische und Datenformate korrekt in verschiedenen Sprachen darzustellen.  Alle Vorkommen von doppelten geschweiften Klammern \(„{{“ oder „}}“\) bleiben bestehen, bis Sie die Zeichenfolge mit ToString formatieren.  Alle enthaltenen Interpolationsausdrücke werden in {0}, \\{1\\} usw. konvertiert.  
  
```c#  
s.ToString(null, System.Globalization.CultureInfo.InvariantCulture);  
```  
  
 Das dritte Beispiel führt zu einer <xref:System.FormattableString>, mit der Sie die Objekte untersuchen können, die aus den Berechnungen der Interpolation entstehen.  Durch das Überprüfen von Objekten und ihrer Wiedergabe als Zeichenfolgen können Sie sich z. B. vor Injection\-Angriffen schützen, wenn Sie eine Abfrage erstellen.  Mit <xref:System.FormattableString> stehen Ihnen Hilfsvorgänge zur Verfügung, um die Zeichenfolgenergebnisse InvariantCulture und CurrentCulture zu erzielen.  Alle Vorkommen von doppelten geschweiften Klammern \(„{{“ oder „}}“\) bleiben bestehen, bis Sie die Zeichenfolge formatieren.  Alle enthaltenen Interpolationsausdrücke werden in {0}, \\{1\\} usw. konvertiert.  
  
## Beispiele  
  
```c#  
$"Name = {name}, hours = {hours:hh}" var s = $"hello, {name}" System.IFormattable s = $"Hello, {name}" System.FormattableString s = $"Hello, {name}" $"{person.Name, 20} is {person.Age:D3} year {(p.Age == 1 ? "" : "s")} old."  
  
```  
  
 Sie müssen die Anführungszeichen in den enthaltenen Interpolationsausdrücken nicht in Anführungszeichen setzen, da die interpolierten Zeichenfolgenausdrücke mit „$“ beginnen und der Compiler die enthaltenen Interpolationsausdrücke als ausbalancierten Text durchsucht, bis ein Komma, Doppelpunkt oder eine schließende geschweifte Klammer gefunden wird.  Aus denselben Gründen wurden im letzten Beispiel Klammern verwendet, damit sich der bedingte Ausdruck \(`p.Age == 1 ? "" : "s"`\) innerhalb des Interpolationsausdrucks befindet, ohne dass der Doppelpunkt eine Formatspezifikation startet.  Außerhalb des enthaltenen Interpolationsausdrucks \(aber innerhalb des interpolierten Zeichenfolgenausdrucks\) versehen Sie Anführungszeichen wie gewohnt mit Escapezeichen.  
  
## Syntax  
  
```  
expression: interpolated-string-expression interpolated-string-expression: interpolated-string-start interpolations interpolated-string-end interpolations: single-interpolation single-interpolation interpolated-string-mid interpolations single-interpolation: interpolation-start interpolation-start : regular-string-literal interpolation-start: expression expression , expression  
  
```  
  
## Sprachspezifikationen  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
 Weitere Informationen finden Sie unter [Visual Basic Language Reference](../../../visual-basic/language-reference/index.md).  
  
## Siehe auch  
 <xref:System.IFormattable?displayProperty=fullName>   
 <xref:System.FormattableString?displayProperty=fullName>   
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Visual Basic Language Reference](../../../visual-basic/language-reference/index.md)   
 [Visual Basic Programming Guide](../../../visual-basic/programming-guide/index.md)