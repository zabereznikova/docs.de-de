---
title: Benutzerdefinierte Zahlenformatzeichenfolgen
description: Benutzerdefinierte Zahlenformatzeichenfolgen
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/25/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 7b1c16ee-956f-4e9c-8502-c3dd6598c51d
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 2d5a051efd074d02f2a5e9ff03c11e1d9a202d7f

---

# <a name="custom-numeric-format-strings"></a>Benutzerdefinierte Zahlenformatzeichenfolgen

Sie können eine aus einem oder mehreren benutzerdefinierten Zahlenbezeichnern bestehende benutzerdefinierte numerische Formatzeichenfolge erstellen, um anzugeben, wie numerische Daten formatiert werden sollen. Eine benutzerdefinierte Zahlenformatzeichenfolge wird wie jede Formatzeichenfolge definiert, bei der es sich nicht um eine [standardmäßige Zahlenformatzeichenfolge](standard-numeric.md) handelt. 

Benutzerdefinierte numerische Formatzeichenfolgen werden von einigen Überladungen der `ToString`-Methode aller numerischen Typen unterstützt. Sie können z.B. eine Zahlenformatzeichenfolge für die Methoden [ToString(String)](xref:System.Int32.ToString(System.String)) und [ToString(String,IFormatProvider)](xref:System.Int32.ToString(System.String,System.IFormatProvider)) vom Typ [Int32](xref:System.Int32) bereitstellen. Benutzerdefinierte Zahlenformatzeichenfolgen werden auch von der .NET Framework-Funktion für die [zusammengesetzte Formatierung](composite-format.md) unterstützt, die von einigen `Write`- und `WriteLine`-Methoden der Klassen [Console](xref:System.Console) und [StreamWriter](xref:System.IO.StreamWriter) sowie der [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object))-Methode und der [StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object))-Methode verwendet wird.

Die folgenden Tabelle beschreibt die benutzerdefinierten Zahlenformatbezeichner und zeigt eine Beispielausgabe an, die von den einzelnen Formatbezeichnern erstellt wird. Weitere Informationen über das Verwenden von benutzerdefinierten Zahlenformatzeichenfolgen finden Sie im Abschnitt [Hinweise](#notes). Der Abschnitt [Beispiel](#example) enthält eine umfassende Abbildung ihrer Verwendung.

Formatbezeichner | Name | Beschreibung | Beispiele
---------------- | ---- | ----------- | --------
"0" | 0-Platzhalter | Ersetzt die Ziffer 0 ggf. durch eine entsprechende vorhandene Ziffer; andernfalls wird die Ziffer 0 in der Ergebniszeichenfolge angezeigt. | `1234.5678 ("00000") -> 01235`; `0.45678 ("0.00", en-US) -> 0.46`; `0.45678 ("0.00", fr-FR) -> 0,46`
"#" | Ziffernplatzhalter | Ersetzt das "#"-Symbol ggf. durch eine entsprechende vorhandene Ziffer; andernfalls wird keine Ziffer in der Ergebniszeichenfolge angezeigt. Beachten Sie, dass keine Ziffer in der Ergebniszeichenfolge angezeigt wird, wenn die entsprechende Ziffer in der Eingabezeichenfolge eine nicht signifikante 0 ist. Zum Beispiel: 0003 ("####") -> 3. | `1234.5678 ("#####") -> 1235`; `0.45678 ("#.##", en-US) -> .46`; `0.45678 ("#.##", fr-FR) -> ,46`
"." | Dezimaltrennzeichen | Bestimmt die Position des Dezimaltrennzeichens in der Ergebniszeichenfolge. | `0.45678 ("0.00", en-US) -> 0.46`; `0.45678 ("0.00", fr-FR) -> 0,46`
"," | Gruppentrennzeichen und Zahlenskalierung | Das Zeichen wird sowohl als Bezeichner für Gruppentrennzeichen als auch als Bezeichner für Zahlenskalierung verwendet. Bei einer Verwendung als Bezeichner für Gruppentrennzeichen wird ein lokalisiertes Trennzeichen zwischen die einzelnen Gruppen eingefügt. Bei einer Verwendung als Bezeichner für Zahlenskalierung wird eine Zahl für jedes angegebene Zeichen durch 1000 geteilt. | Bezeichner für Gruppentrennzeichen: `2147483647 ("##,#", en-US) -> 2,147,483,647`;`2147483647 ("##,#", es-ES) -> 2.147.483.647`. Bezeichner für Skalierung: `2147483647 ("#,#,,", en-US) -> 2,147`; `2147483647 ("#,#,,", es-ES) -> 2.147`
"%" | Prozentplatzhalter | Multipliziert eine Zahl mit 100 und fügt ein lokalisiertes Prozentsymbol in die Ergebniszeichenfolge ein. | `0.3697 ("%#0.00", en-US) -> %36.97`; `0.3697 ("%#0.00", el-GR) -> %36,97`; `0.3697 ("##.0 %", en-US) -> 37.0 %`; `0.3697 ("##.0 %", el-GR) -> 37,0 %`
"‰" | Promilleplatzhalter | Multipliziert eine Zahl mit 1000 und fügt ein lokalisiertes Promillesymbol in die Ergebniszeichenfolge ein. | `0.03697 ("#0.00‰", en-US) -> 36.97‰`; `0.03697 ("#0.00‰", ru-RU) -> 36,97‰`
"E0", "E+0", "E-0", "e0", "e+0", "e-0" | Exponentialschreibweise | Formatiert das Ergebnis mit der Exponentialschreibweise, wenn mindestens einmal 0 (null) darauf folgt. Die Groß- oder Kleinschreibung ("E" oder "e") gibt die Schreibweise des Symbols für den Exponenten in der Ergebniszeichenfolge an. Die Anzahl der Nullen, die auf das Zeichen "E" oder auf das Zeichen "e" folgen, bestimmt die Mindestanzahl der Ziffern im Exponenten. Ein Pluszeichen (+) gibt an, dass dem Exponenten immer ein Vorzeichen vorausgeht. Ein Minuszeichen (-) gibt an, dass nur negativen Exponenten ein Vorzeichen vorausgeht. | `987654 ("#0.0e0") -> 98.8e4`; `1503.92311 ("0.0##e+00") -> 1.504e+03`; `1.8901385E-16 ("0.0e+00") -> 1.9e-16`
\ | Escapezeichen | Das Zeichen, das auf das Escapezeichen folgt, wird als Literal und nicht als benutzerdefinierter Formatbezeichner interpretiert. | `987654 ("\###00\#") -> #987654#`
'string', "string" | Zeichenfolgenliteraltrennzeichen | Gibt an, dass die eingeschlossenen Zeichen unverändert in die Ergebniszeichenfolge kopiert werden sollen. | `68 ("# ' degrees'") -> 68 degrees`
; | Abschnittstrennzeichen | Definiert Abschnitte mit separaten Formatzeichenfolgen für positive und negative Zahlen sowie Nullen. | `12.345 ("#0.0#;(#0.0#);-\0-") -> 12.35`; `0 ("#0.0#;(#0.0#);-\0-") -> -0-`; `-12.345 ("#0.0#;(#0.0#);-\0-") -> (12.35)`; `12.345 ("#0.0#;(#0.0#)") -> 12.35`; `0 ("#0.0#;(#0.0#)") -> 0.0 ; -12.345 ("#0.0#;(#0.0#)") -> (12.35)`
Andere | Alle anderen Zeichen | Das Zeichen wird unverändert in die Ergebniszeichenfolge kopiert. | `68 ("# °") -> 68 °`

Die folgenden Abschnitte enthalten ausführliche Informationen zu den einzelnen benutzerdefinierten Zahlenformatbezeichnern.

## <a name="the-0-custom-specifier"></a>Der benutzerdefinierte Bezeichner "0"

Der benutzerdefinierte Formatbezeichner "0" dient als 0-Platzhalterzeichen. Wenn der zu formatierende Wert über eine Ziffer an der Stelle verfügt, an der die Ziffer 0 in der Formatzeichenfolge steht, wird diese Ziffer in die Ergebniszeichenfolge kopiert; andernfalls erscheint die Ziffer 0 in der Ergebniszeichenfolge. Die Positionen der Ziffer 0, die am weitesten links vor dem Dezimaltrennzeichen steht, und die Position der Ziffer 0, die am weitesten rechts hinter dem Dezimaltrennzeichen steht, bestimmen den Bereich der Ziffern, die immer in der Ergebniszeichenfolge enthalten sind. 

Mit dem Bezeichner "00" wird der Wert immer auf die direkt dem Dezimaltrennzeichen vorausgehende Zahl aufgerundet. Eine Formatierung des Werts 34.5 mit "00" ergibt z. B. den Wert 35.

Im folgenden Beispiel werden mehrere Werte angezeigt, die mit benutzerdefinierten Formatzeichenfolgen formatiert werden, in denen 0-Platzhalter enthalten sind.

```csharp
double value;

value = 123;
Console.WriteLine(value.ToString("00000"));
Console.WriteLine(String.Format("{0:00000}", value));
// Displays 00123

value = 1.2;
Console.WriteLine(value.ToString("0.00", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                "{0:0.00}", value));
// Displays 1.20

Console.WriteLine(value.ToString("00.00", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:00.00}", value));
// Displays 01.20

CultureInfo daDK = CultureInfo.CreateSpecificCulture("da-DK");
Console.WriteLine(value.ToString("00.00", daDK)); 
Console.WriteLine(String.Format(daDK, "{0:00.00}", value));
// Displays 01,20

value = .56;
Console.WriteLine(value.ToString("0.0", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0.0}", value));
// Displays 0.6

value = 1234567890;
Console.WriteLine(value.ToString("0,0", CultureInfo.InvariantCulture)); 
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0,0}", value)); 
// Displays 1,234,567,890      

CultureInfo elGR = CultureInfo.CreateSpecificCulture("el-GR");
Console.WriteLine(value.ToString("0,0", elGR)); 
Console.WriteLine(String.Format(elGR, "{0:0,0}", value));   
// Displays 1.234.567.890

value = 1234567890.123456;
Console.WriteLine(value.ToString("0,0.0", CultureInfo.InvariantCulture));   
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0,0.0}", value));   
// Displays 1,234,567,890.1  

value = 1234.567890;
Console.WriteLine(value.ToString("0,0.00", CultureInfo.InvariantCulture));  
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0,0.00}", value));  
// Displays 1,234.57
```

```vb
Dim value As Double

value = 123
Console.WriteLine(value.ToString("00000"))
Console.WriteLine(String.Format("{0:00000}", value))
' Displays 00123

value = 1.2
Console.Writeline(value.ToString("0.00", CultureInfo.InvariantCulture))
Console.Writeline(String.Format(CultureInfo.InvariantCulture, 
                  "{0:0.00}", value))
' Displays 1.20
Console.WriteLine(value.ToString("00.00", CultureInfo.InvariantCulture))
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:00.00}", value))
' Displays 01.20
Dim daDK As CultureInfo = CultureInfo.CreateSpecificCulture("da-DK")
Console.WriteLine(value.ToString("00.00", daDK))
Console.WriteLine(String.Format(daDK, "{0:00.00}", value))
' Displays 01,20

value = .56
Console.WriteLine(value.ToString("0.0", CultureInfo.InvariantCulture))
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0.0}", value))
' Displays 0.6

value = 1234567890
Console.WriteLine(value.ToString("0,0", CultureInfo.InvariantCulture))  
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0,0}", value))  
' Displays 1,234,567,890      
Dim elGR As CultureInfo = CultureInfo.CreateSpecificCulture("el-GR")
Console.WriteLine(value.ToString("0,0", elGR))
Console.WriteLine(String.Format(elGR, "{0:0,0}", value))    
' Displays 1.234.567.890

value = 1234567890.123456
Console.WriteLine(value.ToString("0,0.0", CultureInfo.InvariantCulture))    
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0,0.0}", value))    
' Displays 1,234,567,890.1  

value = 1234.567890
Console.WriteLine(value.ToString("0,0.00", CultureInfo.InvariantCulture))   
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0,0.00}", value))   
' Displays 1,234.57
```

## <a name="the-custom-specifier"></a>Der benutzerdefinierte Bezeichner "#"

Der benutzerdefinierte Bezeichner "#" dient als Platzhaltersymbol für Ziffern. Wenn der zu formatierende Wert über eine Ziffer an der Stelle verfügt, an der das "#"-Symbol in der Formatzeichenfolge steht, wird diese Ziffer in die Ergebniszeichenfolge kopiert. Andernfalls wird an dieser Position nichts in der Ergebniszeichenfolge gespeichert. 

Beachten Sie, dass dieser Bezeichner nie die Ziffer 0 anzeigt, wenn es sich nicht um eine signifikante Ziffer handelt, auch wenn die Ziffer 0 die einzige Ziffer in der Zeichenfolge ist. Die Ziffer 0 wird nur angezeigt, wenn es sich um eine signifikante Ziffer in der angezeigten Zahl handelt. 

Mit der Formatzeichenfolge "##" wird der Wert immer auf die direkt dem Dezimaltrennzeichen vorausgehende Zahl aufgerundet. Eine Formatierung des Werts 34.5 mit "##" ergibt z. B. den Wert 35.

Im folgenden Beispiel werden mehrere Werte angezeigt, die mit benutzerdefinierten Formatzeichenfolgen formatiert werden, in denen Ziffernplatzhalter enthalten sind.

```csharp
double value;

value = 1.2;
Console.WriteLine(value.ToString("#.##", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#.##}", value));
// Displays 1.2

value = 123;
Console.WriteLine(value.ToString("#####"));
Console.WriteLine(String.Format("{0:#####}", value));
// Displays 123

value = 123456;
Console.WriteLine(value.ToString("[##-##-##]"));      
Console.WriteLine(String.Format("{0:[##-##-##]}", value));      
// Displays [12-34-56]

value = 1234567890;
Console.WriteLine(value.ToString("#"));
Console.WriteLine(String.Format("{0:#}", value));
// Displays 1234567890

Console.WriteLine(value.ToString("(###) ###-####"));
Console.WriteLine(String.Format("{0:(###) ###-####}", value));
// Displays (123) 456-7890
```

```vb
Dim value As Double

value = 1.2
Console.WriteLine(value.ToString("#.##", CultureInfo.InvariantCulture))
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#.##}", value))
' Displays 1.2

value = 123
Console.WriteLine(value.ToString("#####"))
Console.WriteLine(String.Format("{0:#####}", value))
' Displays 123

value = 123456
Console.WriteLine(value.ToString("[##-##-##]"))      
Console.WriteLine(String.Format("{0:[##-##-##]}", value))      
' Displays [12-34-56]

value = 1234567890
Console.WriteLine(value.ToString("#"))
Console.WriteLine(String.Format("{0:#}", value))
' Displays 1234567890

Console.WriteLine(value.ToString("(###) ###-####"))
Console.WriteLine(String.Format("{0:(###) ###-####}", value))
' Displays (123) 456-7890
```

Verwenden Sie die Funktion für die [zusammengesetzte Formatierung](composite-format.md), und geben Sie eine Feldbreite an, wie im folgenden Beispiel veranschaulicht, um eine Ergebniszeichenfolge zurückzugeben, in der fehlende Ziffern oder führende Nullen durch Leerzeichen ersetzt werden.

```csharp
using System;

public class Example
{
   public static void Main()
   {
      Double value = .324;
      Console.WriteLine("The value is: '{0,5:#.###}'", value);
   }
}
// The example displays the following output if the current culture
// is en-US:
//      The value is: ' .324'
```

```vb
Module Example
   Public Sub Main()
      Dim value As Double = .324
      Console.WriteLine("The value is: '{0,5:#.###}'", value)
   End Sub
End Module
' The example displays the following output if the current culture
' is en-US:
'      The value is: ' .324'
```

## <a name="the-custom-specifier"></a>Der benutzerdefinierte Bezeichner  ".".

Der benutzerdefinierte Formatbezeichner "." fügt ein lokalisiertes Dezimaltrennzeichen in die Ergebniszeichenfolge ein. Der erste Punkt in der Formatzeichenfolge bestimmt die Position des Dezimaltrennzeichens im formatierten Wert; alle weiteren Punkte werden ignoriert. 

Das Zeichen, das als Dezimaltrennzeichen in der Ergebniszeichenfolge verwendet wird, muss nicht immer ein Punkt sein. Es wird von der [NumberDecimalSeparator](xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator)-Eigenschaft des [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekts festgelegt, das die Formatierung steuert.

Im folgenden Beispiel wird der "."-Formatbezeichner verwendet, um die Position des Dezimalzeichens in mehreren Ergebniszeichenfolgeketten zu definieren.

```csharp
double value;

value = 1.2;
Console.WriteLine(value.ToString("0.00", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0.00}", value));
// Displays 1.20

Console.WriteLine(value.ToString("00.00", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:00.00}", value));
// Displays 01.20

Console.WriteLine(value.ToString("00.00", 
                CultureInfo.CreateSpecificCulture("da-DK")));
Console.WriteLine(String.Format(CultureInfo.CreateSpecificCulture("da-DK"),
                "{0:00.00}", value));
// Displays 01,20

value = .086;
Console.WriteLine(value.ToString("#0.##%", CultureInfo.InvariantCulture)); 
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#0.##%}", value)); 
// Displays 8.6%

value = 86000;
Console.WriteLine(value.ToString("0.###E+0", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                "{0:0.###E+0}", value));
// Displays 8.6E+4
```

```vb
Dim value As Double

  value = 1.2
  Console.Writeline(value.ToString("0.00", CultureInfo.InvariantCulture))
  Console.Writeline(String.Format(CultureInfo.InvariantCulture, 
                                  "{0:0.00}", value))
  ' Displays 1.20

  Console.WriteLine(value.ToString("00.00", CultureInfo.InvariantCulture))
  Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                  "{0:00.00}", value))
  ' Displays 01.20

  Console.WriteLine(value.ToString("00.00", _
                    CultureInfo.CreateSpecificCulture("da-DK")))
  Console.WriteLine(String.Format(CultureInfo.CreateSpecificCulture("da-DK"),
                    "{0:00.00}", value))
  ' Displays 01,20

  value = .086
  Console.WriteLine(value.ToString("#0.##%", CultureInfo.InvariantCulture)) 
  Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                  "{0:#0.##%}", value)) 
  ' Displays 8.6%

  value = 86000
  Console.WriteLine(value.ToString("0.###E+0", CultureInfo.InvariantCulture))
  Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                    "{0:0.###E+0}", value))
' Displays 8.6E+4
```

## <a name="the-custom-specifier"></a>Der benutzerdefinierte Bezeichner ","

Das Zeichen "," dient sowohl als Bezeichner für Gruppentrennzeichen als auch als Bezeichner für Zahlenskalierung. 

* Bezeichner für Gruppentrennzeichen: Wenn eines oder mehrere Kommas zwischen zwei Ziffernplatzhaltern (0 oder #) angegeben sind, die die ganzzahligen Ziffern einer Zahl formatieren, wird zwischen jeder Zahlengruppe im ganzzahligen Teil der Ausgabe ein Gruppentrennzeichen eingefügt. 

  Die Eigenschaften [NumberGroupSeparator](xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator) und [NumberGroupSizes](xref:System.Globalization.NumberFormatInfo.NumberGroupSizes) des aktuellen [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekts bestimmen das als Zahlengruppentrennzeichen verwendete Zeichen und die Größe der einzelnen Zahlengruppen. Wenn z. B. zum Formatieren der Zahl 1000 die Zeichenfolge "#,#" und die invariante Kultur verwendet werden, lautet die Ausgabe "1,000".
  
* Bezeichner für Zahlenskalierung: Wenn direkt links neben dem expliziten oder impliziten Dezimaltrennzeichen eines oder mehrere Kommas angegeben sind, wird die zu formatierende Zahl bei jedem Vorkommen eines Kommas durch 1000 dividiert. Wenn z. B. zum Formatieren der Zahl 100 Millionen die Zeichenfolge "0,," verwendet wird, lautet die Ausgabe "100". 

Sie können in der gleichen Formatzeichenfolge sowohl Bezeichner für Gruppentrennzeichen als auch für Zahlenskalierung verwenden. Wenn z. B. zum Formatieren der Zahl 1 Milliarde die Zeichenfolge "#,0,," und die invariante Kultur verwendet werden, lautet die Ausgabe "1,000". 

Im folgenden Beispiel wird die Verwendung des Kommas als Gruppentrennzeichen veranschaulicht.

```csharp
double value = 1234567890;
Console.WriteLine(value.ToString("#,#", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#,#}", value));
// Displays 1,234,567,890      

Console.WriteLine(value.ToString("#,##0,,", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#,##0,,}", value));
// Displays 1,235
```

```vb
Dim value As Double = 1234567890
Console.WriteLine(value.ToString("#,#", CultureInfo.InvariantCulture))
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#,#}", value))
' Displays 1,234,567,890      

Console.WriteLine(value.ToString("#,##0,,", CultureInfo.InvariantCulture))
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#,##0,,}", value))
' Displays 1,235
```

Das folgende Beispiel veranschaulicht der Verwendung des Kommas als Bezeichner für die Zahlenskalierung.

```csharp
double value = 1234567890;
Console.WriteLine(value.ToString("#,,", CultureInfo.InvariantCulture)); 
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#,,}", value)); 
// Displays 1235   

Console.WriteLine(value.ToString("#,,,", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#,,,}", value));
// Displays 1  

Console.WriteLine(value.ToString("#,##0,,", CultureInfo.InvariantCulture));       
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#,##0,,}", value));       
// Displays 1,235
```  

```vb
Dim value As Double = 1234567890
  Console.WriteLine(value.ToString("#,,", CultureInfo.InvariantCulture))    
  Console.WriteLine(String.Format(CultureInfo.InvariantCulture, "{0:#,,}", value))  
  ' Displays 1235   

  Console.WriteLine(value.ToString("#,,,", CultureInfo.InvariantCulture))
  Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                  "{0:#,,,}", value))
' Displays 1  

  Console.WriteLine(value.ToString("#,##0,,", CultureInfo.InvariantCulture))       
  Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                  "{0:#,##0,,}", value))       
' Displays 1,235
```

## <a name="the-custom-specifier"></a>Der benutzerdefinierte Bezeichner "%"

Wenn eine Formatzeichenfolge ein Prozentzeichen (%) enthält, wird die Zahl vor dem Formatieren mit 100 multipliziert. Das lokalisierte Prozentzeichen wird in der Zahl an der Stelle eingefügt, an der % in der Formatzeichenfolge steht. Das verwendete Prozentzeichen wird von der [PercentSymbol](xref:System.Globalization.NumberFormatInfo.PercentSymbol)-Eigenschaft des aktuellen [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekts definiert.

Im folgenden Beispiel werden mehrere benutzerdefinierte Formatzeichenfolgen definiert, in denen der benutzerdefinierte Bezeichner "%" enthalten ist.

```csharp
double value = .086;
Console.WriteLine(value.ToString("#0.##%", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#0.##%}", value));
// Displays 8.6%     
```

```vb
Dim value As Double = .086
Console.WriteLine(value.ToString("#0.##%", CultureInfo.InvariantCulture))
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#0.##%}", value))
' Displays 8.6% 
```

## <a name="the-custom-specifier"></a>Der benutzerdefinierte Bezeichner "‰"

Wenn eine Formatzeichenfolge ein Promillezeichen (‰ oder \u2030) enthält, wird die Zahl vor dem Formatieren mit 1.000 multipliziert. Das entsprechende Promillesymbol wird in der Rückgabezeichenfolge an der Stelle eingefügt, an der das Symbol ‰ in der Formatzeichenfolge steht. Das verwendete Promillezeichen wird von der [NumberFormatInfo.PerMilleSymbol](xref:System.Globalization.NumberFormatInfo.PerMilleSymbol)-Eigenschaft des Objekts definiert, das kulturspezifische Formatierungsinformationen zur Verfügung stellt.

Im folgenden Beispiel wird eine benutzerdefinierte Formatzeichenfolge mit dem benutzerdefinierten Bezeichner "‰" definiert.

```csharp
double value = .00354;
string perMilleFmt = "#0.## " + '\u2030';
Console.WriteLine(value.ToString(perMilleFmt, CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:" + perMilleFmt + "}", value));
// Displays 3.54‰   
```

```vb
Dim value As Double = .00354
Dim perMilleFmt As String = "#0.## " & ChrW(&h2030)
Console.WriteLine(value.ToString(perMilleFmt, CultureInfo.InvariantCulture))
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:" + perMilleFmt + "}", value))
' Displays 3.54 ‰
```

## <a name="the-e-and-e-custom-specifiers"></a>Die benutzerdefinierten Bezeichner "E" und "e"

Wenn die Formatzeichenfolge die Zeichenfolge "E", "E+", "E-", "e", "e+" oder "e-" enthält und direkt danach mindestens einmal die Ziffer 0, wird die Zahl mit der wissenschaftlichen Notation formatiert und ein "E" bzw. "e" zwischen der Zahl und dem Exponenten eingefügt. Die Anzahl der Nullen nach dem Bezeichner für die wissenschaftliche Notation bestimmt die Mindestanzahl der Ziffern, die für den Exponenten ausgegeben werden. Das "E+"-Format und das "e+"-Format geben an, dass immer ein Vorzeichen (Plus oder Minus) vor dem Exponenten steht. Die Formate "E", "E-", "e" oder "e-" geben an, dass nur vor negativen Exponenten ein Vorzeichen steht.

Im folgenden Beispiel werden mehrere numerische Werte mit den Bezeichnern für die wissenschaftliche Notation formatiert.

```csharp
double value = 86000;
Console.WriteLine(value.ToString("0.###E+0", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0.###E+0}", value));
// Displays 8.6E+4

Console.WriteLine(value.ToString("0.###E+000", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0.###E+000}", value));
// Displays 8.6E+004

Console.WriteLine(value.ToString("0.###E-000", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0.###E-000}", value));
// Displays 8.6E004
```

```vb
Dim value As Double = 86000
Console.WriteLine(value.ToString("0.###E+0", CultureInfo.InvariantCulture))
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0.###E+0}", value))
' Displays 8.6E+4

Console.WriteLine(value.ToString("0.###E+000", CultureInfo.InvariantCulture))
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0.###E+000}", value))
' Displays 8.6E+004

Console.WriteLine(value.ToString("0.###E-000", CultureInfo.InvariantCulture))
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0.###E-000}", value))
' Displays 8.6E004
```

## <a name="the-escape-character"></a>Das "\"-Escapezeichen

Die Symbole "#", "0", ".", ",", "%" und "‰" in einer Formatzeichenfolge werden als Formatbezeichner und nicht als Literalzeichen interpretiert. Je nach Position in einer benutzerdefinierten Formatzeichenfolge können das Zeichen "E" bzw. "e" und die Symbole "+" und "-" auch als Formatbezeichner interpretiert werden. 

Um zu verhindern, dass ein Zeichen als Formatbezeichner interpretiert wird, können Sie einen umgekehrten Schrägstrich als Escapezeichen voranstellen. Das Escapezeichen gibt an, dass das folgende Zeichen ein Zeichenliteral ist, das unverändert in der Ergebniszeichenfolge enthalten sein soll.

Um einen umgekehrten Schrägstrich in eine Ergebniszeichenfolge einzuschließen, müssen Sie diesen mit einem weiteren umgekehrten Schrägstrich versehen, der als Escapezeichen dient (\\). 

> [!NOTE]
> Einige Compiler, wie z.B. der C#-Compiler, interpretieren möglicherweise auch einen einzelnen umgekehrten Schrägstrich als Escapezeichen. Um sicherzustellen, dass eine Zeichenfolge bei der Formatierung ordnungsgemäß interpretiert wird, können Sie der Zeichenfolge in C# das Literalzeichen für wörtliche Zeichenfolgen (@-Zeichen) voranstellen, oder Sie können jedem umgekehrten Schrägstrich einen weiteren umgekehrten Schrägstrich voranstellen. Beide Verfahren werden im folgenden C#-Codebeispiel veranschaulicht.

Im folgenden Beispiel wird das Escapezeichen verwendet, um zu verhindern, dass der Formatierungsvorgang die Zeichen "#", "0" und "\" als Escapezeichen oder als Formatbezeichner interpretiert. Das Beispiel verwendet einen zusätzlichen umgekehrten Schrägstrich, um sicherzustellen, dass ein umgekehrter Schrägstrich als Literalzeichen interpretiert wird.

```csharp
int value = 123;
Console.WriteLine(value.ToString("\\#\\#\\# ##0 dollars and \\0\\0 cents \\#\\#\\#"));
Console.WriteLine(String.Format("{0:\\#\\#\\# ##0 dollars and \\0\\0 cents \\#\\#\\#}",
                                value));
// Displays ### 123 dollars and 00 cents ###

Console.WriteLine(value.ToString(xref:"\#\#\# ##0 dollars and \0\0 cents \#\#\#"));
Console.WriteLine(String.Format(xref:"{0:\#\#\# ##0 dollars and \0\0 cents \#\#\#}",
                                value));
// Displays ### 123 dollars and 00 cents ###

Console.WriteLine(value.ToString("\\\\\\\\\\\\ ##0 dollars and \\0\\0 cents \\\\\\\\\\\\"));
Console.WriteLine(String.Format("{0:\\\\\\\\\\\\ ##0 dollars and \\0\\0 cents \\\\\\\\\\\\}",
                                value));
// Displays \\\ 123 dollars and 00 cents \\\

Console.WriteLine(value.ToString(xref:"\\\\\\ ##0 dollars and \0\0 cents \\\\\\"));
Console.WriteLine(String.Format(xref:"{0:\\\\\\ ##0 dollars and \0\0 cents \\\\\\}",
                                value));
// Displays \\\ 123 dollars and 00 cents \\\
```

```vb
Dim value As Integer = 123
Console.WriteLine(value.ToString("\#\#\# ##0 dollars and \0\0 cents \#\#\#"))
Console.WriteLine(String.Format("{0:\#\#\# ##0 dollars and \0\0 cents \#\#\#}", 
                                value))
' Displays ### 123 dollars and 00 cents ###

Console.WriteLine(value.ToString("\\\\\\ ##0 dollars and \0\0 cents \\\\\\"))
Console.WriteLine(String.Format("{0:\\\\\\ ##0 dollars and \0\0 cents \\\\\\}", 
                                value))
' Displays \\\ 123 dollars and 00 cents \\\
```

## <a name="the-section-separator"></a>Das Abschnittstrennzeichen ";"

Das Semikolon (;) ist ein bedingter Formatbezeichner, der Zahlen unterschiedlich formatiert, je nachdem, ob sein Wert positiv, negativ oder 0 (null) ist. Dafür kann eine benutzerdefinierte Formatzeichenfolge bis zu drei durch Semikolons getrennte Abschnitte enthalten. Diese Abschnitte werden in der folgenden Tabelle beschrieben. 

Anzahl der Abschnitte | Beschreibung
------------------ | -----------
Ein Abschnitt | Die Formatzeichenfolge gilt für alle Werte.
Zwei Abschnitte | Der erste Abschnitt gilt für positive Werte und Nullen, der zweite Abschnitt für negative Werte. Wenn die zu formatierende Zahl negativ ist, aber nach dem Runden entsprechend dem Format im zweiten Abschnitt 0 ist, wird die resultierende 0 entsprechend dem ersten Abschnitt formatiert.
Drei Abschnitte | Der erste Abschnitt gilt für positive Werte, der zweite Abschnitt für negative Werte und der dritte Abschnitt für Nullen. Wenn der zweite Abschnitt leer ist (zwischen den Semikolons wird nichts angegeben), wird der erste Abschnitt auf alle Werte angewendet, die nicht 0 (null) sind. Wenn die zu formatierende Zahl nicht 0 ist, aber nach dem Runden entsprechend dem Format im ersten oder im zweiten Abschnitt 0 ist, wird die resultierende 0 entsprechend dem dritten Abschnitt formatiert.

Abschnittstrennzeichen ignorieren alle bereits vorhandenen Formatierungen für Zahlen, wenn der letzte Wert formatiert wird. Negative Werte werden z. B. immer ohne Minuszeichen angezeigt, wenn Abschnittstrennzeichen verwendet werden. Wenn der letzte formatierte Wert ein Minuszeichen aufweisen soll, muss das Minuszeichen explizit als Teil des benutzerdefinierten Formatbezeichners aufgenommen werden. 

Im folgenden Beispiel wird der Formatbezeichner ";" verwendet, um positive und negative Zahlen sowie Nullen unterschiedlich zu formatieren.

```csharp
double posValue = 1234;
double negValue = -1234;
double zeroValue = 0;

string fmt2 = "##;(##)";
string fmt3 = "##;(##);**Zero**";

Console.WriteLine(posValue.ToString(fmt2));  
Console.WriteLine(String.Format("{0:" + fmt2 + "}", posValue));    
// Displays 1234

Console.WriteLine(negValue.ToString(fmt2));  
Console.WriteLine(String.Format("{0:" + fmt2 + "}", negValue));    
// Displays (1234)

Console.WriteLine(zeroValue.ToString(fmt3)); 
Console.WriteLine(String.Format("{0:" + fmt3 + "}", zeroValue));
// Displays **Zero**
```

```vb
Dim posValue As Double = 1234
Dim negValue As Double = -1234
Dim zeroValue As Double = 0

Dim fmt2 As String = "##;(##)"
Dim fmt3 As String = "##;(##);**Zero**"

Console.WriteLine(posValue.ToString(fmt2))   
Console.WriteLine(String.Format("{0:" + fmt2 + "}", posValue))    
' Displays 1234

Console.WriteLine(negValue.ToString(fmt2))   
Console.WriteLine(String.Format("{0:" + fmt2 + "}", negValue))    
' Displays (1234)

Console.WriteLine(zeroValue.ToString(fmt3))  
Console.WriteLine(String.Format("{0:" + fmt3 + "}", zeroValue))
' Displays **Zero**
```

## <a name="notes"></a>Notizen

### <a name="floating-point-infinities-and-nan"></a>Unendlichkeiten und NaN bei Gleitkommawerten

Wenn der Wert eines [Single](xref:System.Single)- oder [Double](xref:System.Double)-Gleitkommatyps positiv unendlich, negativ unendlich oder keine Zahl (Not a Number, NaN) ist, handelt es sich bei der formatierten Zeichenfolge unabhängig von der Formatzeichenfolge um den Wert der entsprechenden [PositiveInfinitySymbol](xref:System.Globalization.NumberFormatInfo.PositiveInfinitySymbol)-, [NegativeInfinitySymbol](xref:System.Globalization.NumberFormatInfo.NegativeInfinitySymbol)- oder [NaNSymbol](xref:System.Globalization.NumberFormatInfo.NaNSymbol)-Eigenschaft, die durch das derzeit gültige [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekt angegeben wird. 

### <a name="rounding-and-fixed-point-format-strings"></a>Rundung bei Formatzeichenfolgen mit Festkomma

Bei Formatzeichenfolgen mit Festkomma (d. h. Formatzeichenfolgen, die keine Zeichen im wissenschaftlichen Notationsformat enthalten) werden die Zahlen auf die Anzahl von Dezimalstellen gerundet, die rechts neben dem Dezimaltrennzeichen als Ziffernplatzhalter vorhanden sind. Wenn die Formatzeichenfolge kein Dezimaltrennzeichen enthält, wird die Zahl auf die nächste ganze Zahl gerundet. Wenn die Zahl über mehr Ziffern verfügt, als Ziffernplatzhalter links neben dem Dezimaltrennzeichen stehen, werden die zusätzlichen Ziffern direkt vor dem ersten Ziffernplatzhalter in die Ergebniszeichenfolge kopiert.

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden zwei benutzerdefinierte numerische Formatzeichenfolgen veranschaulicht. In beiden Fällen zeigt der Ziffernplatzhalter (#) die numerischen Daten an, und alle anderen Zeichen werden in die Ergebniszeichenfolge kopiert.

```csharp
double number1 = 1234567890;
string value1 = number1.ToString("(###) ###-####");
Console.WriteLine(value1);

int number2 = 42;
string value2 = number2.ToString("My Number = #");
Console.WriteLine(value2);
// The example displays the following output:
//       (123) 456-7890
//       My Number = 42
```

```vb
Dim number1 As Double = 1234567890
Dim value1 As String = number1.ToString("(###) ###-####")
Console.WriteLine(value1)

Dim number2 As Integer = 42
Dim value2 As String = number2.ToString("My Number = #")
Console.WriteLine(value2)
' The example displays the following output:
'       (123) 456-7890
'       My Number = 42
```

## <a name="see-also"></a>Siehe auch

[System.Globalization.NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)

[Formatierung von Typen](formatting-types.md)

[Standard-Zahlenformatzeichenfolgen](standard-numeric.md)

[Gewusst wie: Auffüllen einer Zahl mit führenden Nullen](pad-number.md)

[Kombinierte Formatierung](composite-format.md)




<!--HONumber=Nov16_HO3-->


