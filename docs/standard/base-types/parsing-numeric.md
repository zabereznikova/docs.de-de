---
title: Analysieren numerischer Zeichenfolgen in .NET
description: Analysieren numerischer Zeichenfolgen in .NET
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: e393430a-731a-49fa-83de-ff7ed52d5704
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 209d24d32eb3b235ff2fde2ef11ffd0ee4e930cf

---

# <a name="parsing-numeric-strings-in-net"></a>Analysieren numerischer Zeichenfolgen in .NET

Alle numerischen Typen weisen zwei statische Analysemethoden auf, `Parse` und `TryParse`, mit denen Sie die Zeichenfolgendarstellung einer Zahl in einen numerischen Typ konvertieren können. Mit diesen Methoden können Sie Zeichenfolgen analysieren, die mithilfe der Formatzeichenfolgen erstellt wurden, die unter [Standardformatzeichenfolgen für Zahlen](standard-numeric.md) und [Benutzerdefinierte Zahlenformatzeichenfolgen](custom-numeric.md) dokumentiert sind. In der Standardeinstellung können die Methoden `Parse` und `TryParse` Zeichenfolgen, die nur Vorkommastellen enthalten, erfolgreich in ganzzahlige Werte konvertieren. Sie können Zeichenfolgen, die Vor- und Nachkommastellen, Gruppentrennzeichen und ein Dezimaltrennzeichen enthalten, erfolgreich in Gleitkommawerte konvertieren. Die `Parse`-Methode löst eine Ausnahme aus, wenn der Vorgang einen Fehler verursacht, wohingegen die `TryParse`-Methode `false` zurückgibt.

## <a name="parsing-and-format-providers"></a>Analyse und Formatanbieter

In der Regel unterscheiden sich die Zeichenfolgendarstellungen numerischer Werte je nach Kultur. Elemente numerischer Zeichenfolgen wie Währungssymbole, Gruppentrennzeichen (oder Tausendertrennzeichen) und Dezimaltrennzeichen variieren alle je nach Kultur. Analysemethoden verwenden entweder implizit oder explizit einen Formatanbieter, der diese kulturspezifischen Variationen erkennt. Wird in einem Aufruf der `Parse`- oder der `TryParse`-Methode kein Formatanbieter angegeben, so wird der der aktuellen Threadkultur zugeordnete Formatanbieter verwendet (das von der [NumberFormatInfo.CurrentInfo](xref:System.Globalization.NumberFormatInfo.CurrentInfo)-Eigenschaft zurückgegebene [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekt). 

Ein Formatanbieter wird durch eine [IFormatProvider](xref:System.Globalization.NumberFormatInfo.CurrentInfo)-Implementierung dargestellt. Diese Schnittstelle verfügt über einen einzelnen Member, die [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type))-Methode, deren einziger Parameter ein [Type](xref:System.Type)-Objekt ist, das den zu formatierenden Typ darstellt. Diese Methode gibt das Objekt mit den Formatierungsinformationen zurück. .NET unterstützt die folgenden beiden [IFormatProvider](xref:System.Globalization.NumberFormatInfo.CurrentInfo)-Implementierungen zur Analyse numerischer Zeichenfolgen:

* Ein [CultureInfo](xref:System.Globalization.CultureInfo)-Objekt, dessen [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type))-Methode ein [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekt zurückgibt, das kulturspezifische Formatierungsinformationen bereitstellt.

* Ein [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekt, dessen [NumberFormatInfo.GetFormat](xref:System.Globalization.NumberFormatInfo.GetFormat(System.Type))-Methode sich selbst zurückgibt.

Im folgenden Beispiel wird versucht, jede Zeichenfolge in einem Array in einen [Double](xref:System.Double)-Wert zu konvertieren. Zuerst wird versucht, die Zeichenfolge anhand eines Formatanbieters zu analysieren, der die Konventionen der Kultur „Englisch (USA)“ wiedergibt. Wenn dieser Vorgang eine [FormatException](xref:System.FormatException) auslöst, wird versucht, die Zeichenfolge anhand eines Formatanbieters zu analysieren, der die Konventionen der Kultur „Französisch (Frankreich)“ darstellt.

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      string[] values = { "1,304.16", "$1,456.78", "1,094", "152", 
                          "123,45 €", "1 304,16", "Ae9f" };
      double number;
      CultureInfo culture = null;

      foreach (string value in values) {
         try {
            culture = CultureInfo.CreateSpecificCulture("en-US");
            number = Double.Parse(value, culture);
            Console.WriteLine("{0}: {1} --> {2}", culture.Name, value, number);
         }   
         catch (FormatException) {
            Console.WriteLine("{0}: Unable to parse '{1}'.", 
                              culture.Name, value);
            culture = CultureInfo.CreateSpecificCulture("fr-FR");
            try {
               number = Double.Parse(value, culture);
               Console.WriteLine("{0}: {1} --> {2}", culture.Name, value, number);
            }
            catch (FormatException) {
               Console.WriteLine("{0}: Unable to parse '{1}'.", 
                                 culture.Name, value);
            }
         }
         Console.WriteLine();
      }   
   }
}
// The example displays the following output:
//    en-US: 1,304.16 --> 1304.16
//    
//    en-US: Unable to parse '$1,456.78'.
//    fr-FR: Unable to parse '$1,456.78'.
//    
//    en-US: 1,094 --> 1094
//    
//    en-US: 152 --> 152
//    
//    en-US: Unable to parse '123,45 €'.
//    fr-FR: Unable to parse '123,45 €'.
//    
//    en-US: Unable to parse '1 304,16'.
//    fr-FR: 1 304,16 --> 1304.16
//    
//    en-US: Unable to parse 'Ae9f'.
//    fr-FR: Unable to parse 'Ae9f'.
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim values() As String = { "1,304.16", "$1,456.78", "1,094", "152", 
                                 "123,45 €", "1 304,16", "Ae9f" }
      Dim number As Double
      Dim culture As CultureInfo = Nothing

      For Each value As String In values
         Try
            culture = CultureInfo.CreateSpecificCulture("en-US")
            number = Double.Parse(value, culture)
            Console.WriteLine("{0}: {1} --> {2}", culture.Name, value, number)
         Catch e As FormatException
            Console.WriteLine("{0}: Unable to parse '{1}'.", 
                              culture.Name, value)
            culture = CultureInfo.CreateSpecificCulture("fr-FR")
            Try
               number = Double.Parse(value, culture)
               Console.WriteLine("{0}: {1} --> {2}", culture.Name, value, number)
            Catch ex As FormatException
               Console.WriteLine("{0}: Unable to parse '{1}'.", 
                                 culture.Name, value)
            End Try
         End Try
         Console.WriteLine()
      Next
   End Sub
End Module
' The example displays the following output:
'    en-US: 1,304.16 --> 1304.16
'    
'    en-US: Unable to parse '$1,456.78'.
'    fr-FR: Unable to parse '$1,456.78'.
'    
'    en-US: 1,094 --> 1094
'    
'    en-US: 152 --> 152
'    
'    en-US: Unable to parse '123,45 €'.
'    fr-FR: Unable to parse '123,45 €'.
'    
'    en-US: Unable to parse '1 304,16'.
'    fr-FR: 1 304,16 --> 1304.16
'    
'    en-US: Unable to parse 'Ae9f'.
'    fr-FR: Unable to parse 'Ae9f'.
```

## <a name="parsing-and-numberstyles-values"></a>Analyse und NumberStyles-Werte

Die Stilelemente (z.B. Leerzeichen, Gruppentrennzeichen und Dezimaltrennzeichen), die der Analysevorgang verarbeiten kann, werden durch einen [NumberStyles](xref:System.Globalization.NumberStyles)-Enumerationswert definiert. Standardmäßig werden Zeichenfolgen, die ganzzahlige Werte darstellen, über den [NumberStyles.Integer](xref:System.Globalization.NumberStyles.Integer)-Wert analysiert, der nur Ziffern, vorangestellte und nachfolgende Leerzeichen sowie ein Vorzeichen zulässt. Zeichenfolgen, die Gleitkommawerte darstellen, werden mithilfe einer Kombination der Werte [NumberStyles.Float](xref:System.Globalization.NumberStyles.Float) und [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands) analysiert. Dieser zusammengesetzte Stil lässt Dezimalstellen sowie vorangestellte und nachfolgende Leerzeichen, ein Vorzeichen, ein Dezimaltrennzeichen, ein Gruppentrennzeichen und einen Exponenten zu. Durch den Aufruf einer Überladung der `Parse`- oder der `TryParse`-Methode mit einem Parameter vom Typ [NumberStyles](xref:System.Globalization.NumberStyles) und durch Festlegen von [NumberStyles](xref:System.Globalization.NumberStyles)-Flags können Sie die Stilelemente steuern, die in der Zeichenfolge vorhanden sein dürfen, damit der Analysevorgang erfolgreich durchgeführt werden kann. 

Beispielsweise kann eine Zeichenfolge, die ein Gruppentrennzeichen enthält, nicht mithilfe der [Int32.Parse(String)](xref:System.Int32.Parse(System.String))-Methode in einen [Int32](xref:System.Int32)-Wert konvertiert werden. Die Konvertierung ist jedoch erfolgreich, wenn Sie das [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands)-Flag verwenden, wie im folgenden Beispiel veranschaulicht.

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      string value = "1,304";
      int number;
      IFormatProvider provider = CultureInfo.CreateSpecificCulture("en-US");
      if (Int32.TryParse(value, out number))
         Console.WriteLine("{0} --> {1}", value, number);
      else
         Console.WriteLine("Unable to convert '{0}'", value);

      if (Int32.TryParse(value, NumberStyles.Integer | NumberStyles.AllowThousands, 
                        provider, out number))
         Console.WriteLine("{0} --> {1}", value, number);
      else
         Console.WriteLine("Unable to convert '{0}'", value);
   }
}
// The example displays the following output:
//       Unable to convert '1,304'
//       1,304 --> 1304
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim value As String = "1,304"
      Dim number As Integer
      Dim provider As IFormatProvider = CultureInfo.CreateSpecificCulture("en-US")
      If Int32.TryParse(value, number) Then
         Console.WriteLine("{0} --> {1}", value, number)
      Else
         Console.WriteLine("Unable to convert '{0}'", value)
      End If

      If Int32.TryParse(value, NumberStyles.Integer Or NumberStyles.AllowThousands, 
                        provider, number) Then
         Console.WriteLine("{0} --> {1}", value, number)
      Else
         Console.WriteLine("Unable to convert '{0}'", value)
      End If
   End Sub
End Module
' The example displays the following output:
'       Unable to convert '1,304'
'       1,304 --> 1304
```

> **Warnung**
>
> Beim Analysevorgang werden immer die Formatierungskonventionen einer bestimmten Kultur verwendet. Wenn Sie keine Kultur durch Übergabe eines [CultureInfo](xref:System.Globalization.CultureInfo)- oder [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekts angeben, wird die dem aktuellen Thread zugeordnete Kultur verwendet.
 
Die folgende Tabelle enthält die Member der [NumberStyles](xref:System.Globalization.NumberStyles)-Enumeration und beschreibt, wie diese sich auf den Analysevorgang auswirken.

NumberStyles-Wert | Auswirkung auf die zu analysierende Zeichenfolge
------------------ | --------------------------------- 
[NumberStyles.None](xref:System.Globalization.NumberStyles.None) | Nur Ziffern sind zulässig.
[NumberStyles.AllowDecimalPoint](xref:System.Globalization.NumberStyles.AllowDecimalPoint) | Das Dezimaltrennzeichen und Nachkommastellen sind zulässig. Für ganzzahlige Werte ist nur 0 (null) als Nachkommastelle zulässig. Gültige Dezimaltrennzeichen werden über die [NumberFormatInfo.NumberDecimalSeparator](xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator)- oder die [NumberFormatInfo.CurrencyDecimalSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator)-Eigenschaft festgelegt.
[NumberStyles.AllowExponent](xref:System.Globalization.NumberStyles.AllowExponent) | Das Zeichen „e“ oder „E“ kann zum Angeben der Exponentialschreibweise verwendet werden.
[NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite) | Vorangestellte Leerzeichen sind zulässig.
[NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite) | Nachfolgende Leerzeichen sind zulässig.
[NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign) | Ein positives oder negatives Vorzeichen kann numerischen Zeichen vorangestellt werden.
[NumberStyles.AllowTrailingSign](xref:System.Globalization.NumberStyles.AllowTrailingSign) | Ein positives oder negatives Vorzeichen kann numerischen Zeichen nachfolgen.
[NumberStyles.AllowParentheses](xref:System.Globalization.NumberStyles.AllowParentheses) | Klammern können zum Festlegen negativer Werte verwendet werden.
[NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands) | Das Gruppentrennzeichen ist zulässig. Das Gruppentrennzeichen wird durch die [NumberFormatInfo.NumberGroupSeparator](xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator)- oder die [NumberFormatInfo.CurrencyGroupSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator)-Eigenschaft festgelegt.
[NumberStyles.AllowCurrencySymbol](xref:System.Globalization.NumberStyles.AllowCurrencySymbol) | Das Währungssymbol ist zulässig. Das Währungssymbol wird über die [NumberFormatInfo.CurrencySymbol](xref:System.Globalization.NumberFormatInfo.CurrencySymbol)-Eigenschaft definiert.
[NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier) | Die zu analysierende Zeichenfolge wird als Hexadezimalzahl interpretiert. Sie kann die Hexadezimalzeichen 0 bis 9, A bis F und a bis f enthalten. Dieses Flag kann nur für die Analyse ganzzahliger Werte verwendet werden.
 
Darüber hinaus stellt die [NumberStyles](xref:System.Globalization.NumberStyles)-Enumeration die folgenden zusammengesetzten Stile bereit, die mehrere [NumberStyles](xref:System.Globalization.NumberStyles)-Flags umfassen. 

Zusammengesetzter NumberStyles-Wert | Umfasst folgende Member
---------------------------- | ---------------- 
[NumberStyles.Integer](xref:System.Globalization.NumberStyles.Integer) | Enthält die Stile [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite) und [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign). Dies ist der Standardstil für die Analyse ganzzahliger Werte.
[NumberStyles.Number](xref:System.Globalization.NumberStyles.Number) | Enthält die Stile [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign), [NumberStyles.AllowTrailingSign](xref:System.Globalization.NumberStyles.AllowTrailingSign), [NumberStyles.AllowDecimalPoint](xref:System.Globalization.NumberStyles.AllowDecimalPoint) und [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands).
[NumberStyles.Float](xref:System.Globalization.NumberStyles.Float) | Enthält die Stile [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign), [NumberStyles.AllowDecimalPoint](xref:System.Globalization.NumberStyles.AllowDecimalPoint) und [NumberStyles.AllowExponent](xref:System.Globalization.NumberStyles.AllowExponent).
[NumberStyles.Currency](xref:System.Globalization.NumberStyles.Currency) | Enthält alle Stile mit Ausnahme von [NumberStyles.AllowExponent](xref:System.Globalization.NumberStyles.AllowExponent) und [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier).
[NumberStyles.Any](xref:System.Globalization.NumberStyles.Any) | Enthält alle Stile mit Ausnahme von [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier).
[NumberStyles.HexNumber](xref:System.Globalization.NumberStyles.HexNumber) | Enthält die Stile [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite) und [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier).
 
## <a name="parsing-and-unicode-digits"></a>Analyse und Unicode-Ziffern

Der Unicode-Standard definiert Codepunkte für Ziffern in verschiedenen Schreibsystemen. Beispielsweise stehen Codepunkte von U+0030 bis U+0039 für die grundlegenden lateinischen Ziffern 0 bis 9, Codepunkte von U+09E6 bis U+09EF für die Bangla-Ziffern 0 bis 9 und Codepunkte von U+FF10 bis U+FF19 für Ziffern voller Breite von 0 bis 9. Allerdings werden von den Analysemethoden nur die grundlegenden lateinischen Ziffern von 0 bis 9 mit den Codepunkten von U+0030 bis U+0039 erkannt. Wenn einer numerische Analysemethode eine Zeichenfolge übergeben wird, die andere Ziffern enthält, löst die Methode eine [FormatException](xref:System.FormatException) aus.

Im folgenden Beispiel wird die [Int32.Parse](xref:System.Int32.Parse(System.String))-Methode zum Analysieren von Zeichenfolgen verwendet, die aus Ziffern unterschiedlicher Schreibsysteme bestehen. Wie die Ausgabe des Beispiels zeigt, verläuft die Analyse der grundlegenden lateinischen Ziffern erfolgreich, aber der Versuch zum Analysieren der vollbreiten, der arabisch-indischen und der Bangla-Ziffern verursacht einen Fehler.

```csharp
using System;

public class Example
{
   public static void Main()
   {
      string value;
      // Define a string of basic Latin digits 1-5.
      value = "\u0031\u0032\u0033\u0034\u0035";
      ParseDigits(value);

      // Define a string of Fullwidth digits 1-5.
      value = "\uFF11\uFF12\uFF13\uFF14\uFF15";
      ParseDigits(value);

      // Define a string of Arabic-Indic digits 1-5.
      value = "\u0661\u0662\u0663\u0664\u0665";
      ParseDigits(value);

      // Define a string of Bangla digits 1-5.
      value = "\u09e7\u09e8\u09e9\u09ea\u09eb";
      ParseDigits(value);
   }

   static void ParseDigits(string value)
   {
      try {
         int number = Int32.Parse(value);
         Console.WriteLine("'{0}' --> {1}", value, number);
      }   
      catch (FormatException) {
         Console.WriteLine("Unable to parse '{0}'.", value);      
      }     
   }
}
// The example displays the following output:
//       '12345' --> 12345
//       Unable to parse '１２３４５'.
//       Unable to parse '١٢٣٤٥'.
//       Unable to parse '১২৩৪৫'.
```

```vb
Module Example
   Public Sub Main()
      Dim value As String
      ' Define a string of basic Latin digits 1-5.
      value = ChrW(&h31) + ChrW(&h32) + ChrW(&h33) + ChrW(&h34) + ChrW(&h35)
      ParseDigits(value)

      ' Define a string of Fullwidth digits 1-5.
      value = ChrW(&hff11) + ChrW(&hff12) + ChrW(&hff13) + ChrW(&hff14) + ChrW(&hff15)
      ParseDigits(value)

      ' Define a string of Arabic-Indic digits 1-5.
      value = ChrW(&h661) + ChrW(&h662) + ChrW(&h663) + ChrW(&h664) + ChrW(&h665)
      ParseDigits(value)

      ' Define a string of Bangla digits 1-5.
      value = ChrW(&h09e7) + ChrW(&h09e8) + ChrW(&h09e9) + ChrW(&h09ea) + ChrW(&h09eb)
      ParseDigits(value)
   End Sub

   Sub ParseDigits(value As String)
      Try
         Dim number As Integer = Int32.Parse(value)
         Console.WriteLine("'{0}' --> {1}", value, number)
      Catch e As FormatException
         Console.WriteLine("Unable to parse '{0}'.", value)      
      End Try     
   End Sub
End Module
' The example displays the following output:
'       '12345' --> 12345
'       Unable to parse '１２３４５'.
'       Unable to parse '١٢٣٤٥'.
'       Unable to parse '১২৩৪৫'.
```

## <a name="see-also"></a>Siehe auch

[System.Globalization.NumberStyles](xref:System.Globalization.NumberStyles)

[Analysieren von Zeichenfolgen in .NET](parsing-strings.md)

[Formatieren von Typen in .NET](formatting-types.md)




<!--HONumber=Nov16_HO3-->


