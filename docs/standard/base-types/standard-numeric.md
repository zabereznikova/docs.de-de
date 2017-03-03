---
title: "Standardmäßige Zahlenformatzeichenfolgen"
description: "Standardmäßige Zahlenformatzeichenfolgen"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 285faf73-466a-4af0-8eba-7e509958f240
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: d38b5bdfb8429b917e19d74b36f2e33cea49dbca
ms.lasthandoff: 01/18/2017

---

# <a name="standard-numeric-format-strings"></a>Standardmäßige Zahlenformatzeichenfolgen

Standardformatzeichenfolgen für Zahlen werden für die Formatierung allgemeiner numerischer Typen verwendet. Eine standardmäßige Zahlenformatzeichenfolge hat die Form **A**_xx_, wobei Folgendes gilt: 

* **A** ist ein einzelnes alphabetisches Zeichen, das als *Formatbezeichner* bezeichnet wird. Jede Zahlenformatzeichenfolge, die mehr als ein alphabetisches Zeichen (einschließlich Leerzeichen) enthält, wird als benutzerdefinierte Zahlenformatzeichenfolge interpretiert. Weitere Informationen finden Sie unter [Benutzerdefinierte Zahlenformatzeichenfolgen](custom-numeric.md). 

* *xx* ist eine optionale ganze Zahl, die als *Genauigkeitsspezifizierer* bezeichnet wird. Die Genauigkeitsangabe reicht von 0 bis 99 und wirkt sich auf die Anzahl der Ziffern im Ergebnis aus. Beachten Sie, dass die Genauigkeitsangabe die Anzahl der Ziffern in der Zeichenfolgendarstellung einer Zahl steuert. Die Zahl selbst wird nicht gerundet. Verwenden Sie für einen Rundungsvorgang die Methoden [Math.Ceiling](xref:System.Math), [Math.Floor](xref:System.Math) oder [Math.Round](xref:System.Math). 

Wenn der *Genauigkeitsspezifizierer* die Anzahl von Dezimalstellen in der Ergebniszeichenfolge steuert, entsprechen Ergebniszeichenfolgen Zahlen, die von null weg gerundet werden (d.h., es wird [MidpointRounding.AwayFromZero](xref:System.MidpointRounding.AwayFromZero) verwendet). 

> [!NOTE]
> Der Genauigkeitsspezifizierer bestimmt Anzahl von Ziffern in der Ergebniszeichenfolge. Verwenden zum Auffüllen einer Ergebniszeichenfolge mit führenden oder nachgestellten Leerzeichen die Funktion für die [zusammengesetzte Formatierung](composite-format.md), und definieren Sie eine *Ausrichtungskomponente* im Formatelement. 

Standardmäßige numerische Formatzeichenfolgen werden von einigen Überladungen der `ToString`-Methode aller numerischen Typen unterstützt. Sie können z.B. eine Zahlenformatzeichenfolge für die Methoden [ToString(String)](xref:System.Int32.ToString(System.String)) und [ToString(String,IFormatProvider)](xref:System.Int32.ToString(System.String,System.IFormatProvider)) vom Typ [Int32](xref:System.Int32) bereitstellen. Standardmäßige Zahlenformatzeichenfolgen werden auch von der .NET-Funktion für die [zusammengesetzte Formatierung](composite-format.md) unterstützt, die von einigen `Write`- und `WriteLine`-Methoden der Klassen [Console](xref:System.Console) und [StreamWriter](xref:System.IO.StreamWriter) sowie der [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object))-Methode und der [StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object))-Methode verwendet wird. Die Funktion für kombinierte Formatierung ermöglicht es Ihnen, die Zeichenfolgendarstellung mehrerer Datenelemente in eine einzelne Zeichenfolge einzuschließen, die Feldbreite anzugeben und die Zahlen in einem Feld auszurichten. Weitere Informationen finden Sie unter [Zusammengesetzte Formatierung](composite-format.md). 

Die folgenden Tabelle beschreibt die standardmäßigen Zahlenformatbezeichner und zeigt eine Beispielausgabe an, die von den einzelnen Formatbezeichnern erstellt wird. Weitere Informationen über das Verwenden von standardmäßigen Zahlenformatzeichenfolgen finden Sie im Abschnitt [Hinweise](#notes). Der Abschnitt [Beispiel](#example) enthält eine umfassende Abbildung ihrer Verwendung.

|Formatbezeichner|Name|Beschreibung|Beispiele|  
|----------------------|----------|-----------------|--------------|  
|"C" oder "c"|Währung|Ergebnis: Währungswert.<br /><br /> Unterstützt von: Alle numerischen Typen.<br /><br /> Genauigkeitsangabe: Anzahl der Dezimalstellen.<br /><br /> Standardmäßiger Genauigkeitsspezifizierer: Definiert von [NumberFormatInfo.CurrencyDecimalDigits](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits).<br /><br /> |123.456 ("C", en-US) -> $123.46<br /><br /> 123.456 ("C", fr-FR) -> 123,46 €<br /><br /> 123.456 ("C", ja-JP) -> ¥123<br /><br /> -123.456 ("C3", en-US) -> ($123.456)<br /><br /> -123.456 ("C3", fr-FR) -> -123,456 €<br /><br /> -123.456 ("C3", ja-JP) -> -¥123.456|  
|"D" oder "d"|Decimal|Ergebnis: Ganzzahlige Ziffern mit optionalem Minuszeichen.<br /><br /> Unterstützt von: Nur ganzzahlige Typen.<br /><br /> Genauigkeitsangabe: Mindestanzahl von Ziffern.<br /><br /> Standardmäßige Genauigkeitsangabe: Mindestanzahl von erforderlichen Ziffern.<br /><br /> |1234 ("D") -> 1234<br /><br /> -1234 ("D6") -> -001234|  
|"E" oder "e"|Exponential (wissenschaftlich)|Ergebnis: Exponentialschreibweise.<br /><br /> Unterstützt von: Alle numerischen Typen.<br /><br /> Genauigkeitsangabe: Anzahl der Dezimalstellen.<br /><br /> Standardmäßige Genauigkeitsangabe: 6.<br /><br /> |1052.0329112756 ("E", en-US) -> 1.052033E+003<br /><br /> 1052.0329112756 ("e", fr-FR) -> 1,052033e+003<br /><br /> -1052.0329112756 ("e2", en-US) -> -1.05e+003<br /><br /> -1052.0329112756 ("E2", fr_FR) -> -1,05E+003|  
|"F" oder "f"|Festkomma|Ergebnis: Ganze Zahlen und Dezimalzahlen mit optionalem Minuszeichen.<br /><br /> Unterstützt von: Alle numerischen Typen.<br /><br /> Genauigkeitsangabe: Anzahl der Dezimalstellen.<br /><br /> Standardmäßiger Genauigkeitsspezifizierer: Definiert von [NumberFormatInfo.NumberDecimalDigits](xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits).<br /><br /> |1234.567 ("F", en-US) -> 1234.57<br /><br /> 1234.567 ("F", de-DE) -> 1234,57<br /><br /> 1234 ("F1", en-US) -> 1234.0<br /><br /> 1234 ("F1", de-DE) -> 1234,0<br /><br /> -1234.56 ("F4", en-US) -> -1234.5600<br /><br /> -1234.56 ("F4", de-DE) -> -1234,5600|  
|"G" oder "g"|Allgemein|Ergebnis: Die kompaktere Festkomma- oder wissenschaftliche Schreibweise.<br /><br /> Unterstützt von: Alle numerischen Typen.<br /><br /> Genauigkeitsangabe: Anzahl der signifikanten Stellen.<br /><br /> Standardmäßige Genauigkeitsangabe: Abhängig vom numerischen Typ.<br /><br /> |-123.456 ("G", en-US) -> -123.456<br /><br /> -123.456 ("G", sv-SE) -> -123,456<br /><br /> 123.4546 ("G4", en-US) -> 123.5<br /><br /> 123.4546 ("G4", sv-SE) -> 123,5<br /><br /> -1.234567890e-25 ("G", en-US) -> -1.23456789E-25<br /><br /> -1.234567890e-25 ("G", sv-SE) -> -1,23456789E-25|  
|"N" oder "n"|Nummer|Ergebnis: Ganze Zahlen und Dezimalzahlen, Gruppentrennzeichen und ein Dezimaltrennzeichen mit optionalem Minuszeichen.<br /><br /> Unterstützt von: Alle numerischen Typen.<br /><br /> Genauigkeitsangabe: gewünschte Anzahl der Dezimalstellen.<br /><br /> Standardmäßiger Genauigkeitsspezifizierer: Definiert von [NumberFormatInfo.NumberDecimalDigits](xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits).<br /><br /> |1234.567 ("N", en-US) -> 1,234.57<br /><br /> 1234.567 ("N", ru-RU) -> 1 234,57<br /><br /> 1234 ("N1", en-US) -> 1,234.0<br /><br /> 1234 ("N1", ru-RU) -> 1 234,0<br /><br /> -1234.56 ("N3", en-US) -> -1,234.560<br /><br /> -1234.56 ("N3", ru-RU) -> -1 234,560|  
|"P" oder "p"|Prozent|Ergebnis: Die Zahl multipliziert mit 100 und mit einem Prozentzeichen versehen.<br /><br /> Unterstützt von: Alle numerischen Typen.<br /><br /> Genauigkeitsangabe: gewünschte Anzahl der Dezimalstellen.<br /><br /> Standardmäßiger Genauigkeitsspezifizierer: Definiert von [NumberFormatInfo.PercentDecimalDigits](xref:System.Globalization.NumberFormatInfo.PercentDecimalDigits).<br /><br /> |1 ("P", en-US) -> 100.00 %<br /><br /> 1 ("P", fr-FR) -> 100,00 %<br /><br /> -0.39678 ("P1", en-US) -> -39.7 %<br /><br /> -0.39678 ("P1", fr-FR) -> -39,7 %|  
|"R" oder "r"|Schleife|Ergebnis: Eine Zeichenfolge, die eine Schleife zu einem identischen Wert ausführen kann.<br /><br /> Unterstützt von: [Single](xref:System.Single), [Double](xref:System.Double) und [BigInteger](xref:System.Numerics.BigInteger).<br /><br /> Genauigkeitsangabe: Wird ignoriert.<br /><br /> |123456789.12345678 ("R") -> 123456789.12345678<br /><br /> -1234567890.12345678 ("R") -> -1234567890.1234567|  
|"X" oder "x"|Hexadezimal|Ergebnis: Eine Hexadezimalzeichenfolge.<br /><br /> Unterstützt von: Nur ganzzahlige Typen.<br /><br /> Genauigkeitsangabe: Anzahl von Ziffern in der Ergebniszeichenfolge.<br /><br /> |255 ("X") -> FF<br /><br /> -1 ("x") -> ff<br /><br /> 255 ("x4") -> 00ff<br /><br /> -1 ("X4") -> 00FF|  
|Jedes andere einzelne Zeichen|Unbekannter Bezeichner|Ergebnis: Löst zur Laufzeit eine [FormatException](xref:System.FormatException) aus.|| 

## <a name="using-standard-numeric-format-strings"></a>Verwenden von numerischen Standardformatzeichenfolgen

Eine numerische Standardformatzeichenfolge kann verwendet werden, um die Formatierung eines numerischen Werts wie folgt zu definieren:

* Die Zeichenfolge kann an eine Überladung der `ToString`-Methode übergeben werden, die über einen *format*-Parameter verfügt. Im folgenden Beispiel wird ein numerischer Wert in der aktuellen Kultur (en-US) als Währungszeichenfolge formatiert. 

  ```csharp
  decimal value = 123.456m;
  Console.WriteLine(value.ToString("C2"));
  // Displays $123.46
  ```

  ```vb
  Dim value As Decimal = 123.456d
  Console.WriteLine(value.ToString("C2"))         
  ' Displays $123.46
  ```
  
* Die Zeichenfolge kann als *formatString*-Argument in einem Formatelement angegeben werden, das beispielsweise mit den Methoden [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)), [Console.WriteLine](xref:System.Console.WriteLine) und [StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)) verwendet wird. Weitere Informationen finden Sie unter [Zusammengesetzte Formatierung](composite-format.md). Im folgenden Beispiel wird ein Währungswert mit einem Formatelement in eine Zeichenfolge eingefügt.

  ```csharp
  decimal value = 123.456m;
  Console.WriteLine("Your account balance is {0:C2}.", value);
  // Displays "Your account balance is $123.46."
  ```

  ```vb
  Dim value As Decimal = 123.456d
  Console.WriteLine("Your account balance is {0:C2}.", value)
  ' Displays "Your account balance is $123.46."
  ```
  
  Optional können Sie ein alignment-Argument bereitstellen, um die Breite des numerischen Felds anzugeben und festzulegen, ob sein Wert rechts- oder linksbündig ausgerichtet ist. Im folgenden Beispiel wird ein Währungswert in einem 28-stelligen Feld linksbündig und ein Währungswert in einem 14-stelligen Feld rechtsbündig ausgerichtet.
  
  ```csharp
  decimal[] amounts = { 16305.32m, 18794.16m };
  Console.WriteLine("   Beginning Balance           Ending Balance");
  Console.WriteLine("   {0,-28:C2}{1,14:C2}", amounts[0], amounts[1]);
  // Displays:
  //        Beginning Balance           Ending Balance
  //        $16,305.32                      $18,794.16
  ```

  ```vb
  Dim amounts() As Decimal = { 16305.32d, 18794.16d }
  Console.WriteLine("   Beginning Balance           Ending Balance")
  Console.WriteLine("   {0,-28:C2}{1,14:C2}", amounts(0), amounts(1))
  ' Displays:
  '        Beginning Balance           Ending Balance
  '        $16,305.32                      $18,794.16
  ```
  
Die folgenden Abschnitte enthalten ausführliche Informationen zu den einzelnen numerischen Standardformatzeichenfolgen.

## <a name="the-currency-c-format-specifier"></a>Der Formatbezeichner „C“ für Währung

Mit dem Währungsformatbezeichner "C" wird eine Zahl in eine Zeichenfolge konvertiert, die einen Währungswert darstellt. Die Genauigkeitsangabe gibt die gewünschte Anzahl von Dezimalstellen in der Ergebniszeichenfolge an. Wenn der Genauigkeitsspezifizierer fehlt, wird die Standardgenauigkeit von der [NumberFormatInfo.CurrencyDecimalDigits](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits)-Eigenschaft definiert.

Wenn der zu formatierende Wert mehr als die angegebene oder die standardmäßige Anzahl von Dezimalstellen aufweist, wird der Bruchwert in der Ergebniszeichenfolge gerundet. Wenn der Wert rechts von der Anzahl angegebener Dezimalstellen 5 oder größer ist, wird die letzte Ziffer in der Ergebniszeichenfolge in positiver Richtung gerundet.

Die Ergebniszeichenfolge wird von den Formatierungsinformationen des aktuellen [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekts beeinflusst. In der folgenden Tabelle sind die [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Eigenschaften aufgeführt, die die Formatierung der zurückgegebenen Zeichenfolge steuern.

NumberFormatInfo-Eigenschaft | Beschreibung
------------------------- | -----------
[CurrencyPositivePattern](xref:System.Globalization.NumberFormatInfo.CurrencyPositivePattern) | Definiert die Platzierung des Währungssymbols für positive Werte.
[CurrencyNegativePattern](xref:System.Globalization.NumberFormatInfo.CurrencyNegativePattern) | Definiert die Platzierung des Währungssymbols für negative Werte und gibt an, ob das Minuszeichen durch Klammern oder durch die [NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign)-Eigenschaft dargestellt wird.
[NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign) | Definiert das verwendete Minuszeichen, wenn [CurrencyNegativePattern](xref:System.Globalization.NumberFormatInfo.CurrencyNegativePattern) angibt, dass keine Klammern verwendet werden. 
[CurrencySymbol](xref:System.Globalization.NumberFormatInfo.CurrencySymbol) | Definiert das Währungssymbol.
[CurrencyDecimalDigits](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits) | Definiert die Standardanzahl von Dezimalstellen in einem Währungswert. Dieser Wert kann mit der Genauigkeitsangabe überschrieben werden.
[CurrencyDecimalSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator) | Definiert die Zeichenfolge, die ganze Zahlen und Dezimalzahlen trennt.
[CurrencyGroupSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator) | Definiert die Zeichenfolge, die Gruppen von ganzen Zahlen trennt. 
[CurrencyGroupSizes](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSizes) | Definiert die Anzahl von ganzzahligen Ziffern, die in einer Gruppe angezeigt werden.

Im folgenden Beispiel wird ein [Double](xref:System.Double)-Wert mit dem Währungsformatbezeichner formatiert. 

```csharp
double value = 12345.6789;
Console.WriteLine(value.ToString("C", CultureInfo.CurrentCulture));

Console.WriteLine(value.ToString("C3", CultureInfo.CurrentCulture));

Console.WriteLine(value.ToString("C3", 
                  CultureInfo.CreateSpecificCulture("da-DK")));
// The example displays the following output on a system whose
// current culture is English (United States):
//       $12,345.68
//       $12,345.679
//       kr 12.345,679
```

```vb
Dim value As Double = 12345.6789
Console.WriteLine(value.ToString("C", CultureInfo.CurrentCulture))

Console.WriteLine(value.ToString("C3", CultureInfo.CurrentCulture))

Console.WriteLine(value.ToString("C3", _
                  CultureInfo.CreateSpecificCulture("da-DK")))
' The example displays the following output on a system whose
' current culture is English (United States):
'       $12,345.68
'       $12,345.679
'       kr 12.345,679
```

## <a name="the-decimal-d-format-specifier"></a>Der Bezeichner „D“ für Dezimalformat

Der Dezimalformatbezeichner "D" konvertiert Zahl wird in eine Zeichenfolge aus Dezimalzahlen (0-9), der ein Minuszeichen vorangestellt wird, wenn es sich um eine negative Zahl handelt. Dieses Format wird nur bei ganzzahligen Typen unterstützt.

Die Genauigkeitsangabe gibt die gewünschte Mindestanzahl von Ziffern für die resultierende Zeichenfolge an. Bei Bedarf werden links von der Zahl Nullen ergänzt, um die durch die Genauigkeitsangabe bestimmte Anzahl von Ziffern zu erstellen. Bei fehlender Genauigkeitsangabe wird standardmäßig der zur Darstellung der ganzen Zahl ohne führende Nullen erforderliche Minimalwert zugrunde gelegt.

Die Ergebniszeichenfolge wird von den Formatierungsinformationen des aktuellen [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekts beeinflusst. Wie die folgende Tabelle zeigt, wirkt sich eine einzelne Eigenschaft auf die Formatierung der Ergebniszeichenfolge aus. 

NumberFormatInfo-Eigenschaft | Beschreibung
------------------------- | -----------
[NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign) | Definiert die Zeichenfolge, die angibt, dass eine Zahl negativ ist. 

Im folgenden Beispiel wird ein [Int32](xref:System.Int32)-Wert mit dem Dezimalformatbezeichner formatiert.

```csharp
int value; 

value = 12345;
Console.WriteLine(value.ToString("D"));
// Displays 12345
Console.WriteLine(value.ToString("D8"));
// Displays 00012345

value = -12345;
Console.WriteLine(value.ToString("D"));
// Displays -12345
Console.WriteLine(value.ToString("D8"));
// Displays -00012345
```

```vb
Dim value As Integer 

value = 12345
Console.WriteLine(value.ToString("D"))
' Displays 12345   
Console.WriteLine(value.ToString("D8"))
' Displays 00012345

value = -12345
Console.WriteLine(value.ToString("D"))
' Displays -12345
Console.WriteLine(value.ToString("D8"))
' Displays -00012345
```

## <a name="the-exponential-e-format-specifier"></a>Der Bezeichner „E“ für Exponentialformat

Der Exponentialformatbezeichner "E" konvertiert eine Zahl in eine Zeichenfolge, die folgende Form aufweist: "-d.ddd…E+ddd" oder "-d.ddd…e+ddd". Jedes "d" in der Zeichenfolge steht dabei für eine Ziffer (0-9). Die Zeichenfolge beginnt mit einem Minuszeichen, wenn die Zahl negativ ist. Es steht immer genau eine Ziffer vor dem Dezimaltrennzeichen. 

Die Genauigkeitsangabe gibt die gewünschte Anzahl von Ziffern nach dem Dezimaltrennzeichen an. Wenn die Genauigkeitsangabe fehlt, werden als Standard sechs Ziffern nach dem Dezimaltrennzeichen angegeben. 

Die Groß- oder Kleinschreibung des Formatbezeichners gibt an, ob dem Exponenten ein "E" oder ein "e" vorangestellt wird. Der Exponent besteht immer aus einem Plus- oder Minuszeichen und mindestens drei Ziffern. Der Exponent wird ggf. durch Nullen ergänzt, um diesem Mindestwert zu entsprechen.

Die Ergebniszeichenfolge wird von den Formatierungsinformationen des aktuellen [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekts beeinflusst. In der folgenden Tabelle sind die [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Eigenschaften aufgeführt, die die Formatierung der zurückgegebenen Zeichenfolge steuern.

NumberFormatInfo-Eigenschaft | Beschreibung
------------------------- | -----------
[NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign) | Definiert die Zeichenfolge, die angibt, dass eine Zahl sowohl für den Koeffizienten als auch für den Exponenten negativ ist. 
[NumberDecimalSeparator](xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator) | Definiert die Zeichenfolge, die die ganzzahlige Ziffer von Dezimalstellen im Koeffizienten trennt.
[PositiveSign](xref:System.Globalization.NumberFormatInfo.PositiveSign) | Definiert die Zeichenfolge, die angibt, dass ein Exponent positiv ist.

Im folgenden Beispiel wird ein [Double](xref:System.Double)-Wert mit dem Exponentialformatbezeichner formatiert. 

```csharp
double value = 12345.6789;
Console.WriteLine(value.ToString("E", CultureInfo.InvariantCulture));
// Displays 1.234568E+004

Console.WriteLine(value.ToString("E10", CultureInfo.InvariantCulture));
// Displays 1.2345678900E+004

Console.WriteLine(value.ToString("e4", CultureInfo.InvariantCulture));
// Displays 1.2346e+004

Console.WriteLine(value.ToString("E", 
                  CultureInfo.CreateSpecificCulture("fr-FR")));
// Displays 1,234568E+004
```

```vb
Dim value As Double = 12345.6789
Console.WriteLine(value.ToString("E", CultureInfo.InvariantCulture))
' Displays 1.234568E+004

Console.WriteLine(value.ToString("E10", CultureInfo.InvariantCulture))
' Displays 1.2345678900E+004

Console.WriteLine(value.ToString("e4", CultureInfo.InvariantCulture))
' Displays 1.2346e+004

Console.WriteLine(value.ToString("E", _
                  CultureInfo.CreateSpecificCulture("fr-FR")))
' Displays 1,234568E+004
```

## <a name="the-fixed-point-f-format-specifier"></a>Der Bezeichner „F“ für Festkommaformat

Der Festkommaformatbezeichner "F" konvertiert eine Zahl in eine Zeichenfolge, die folgende Form aufweist: "-ddd.ddd…". Jedes "d" steht dabei für eine Ziffer (0-9). Die Zeichenfolge beginnt mit einem Minuszeichen, wenn die Zahl negativ ist. 

Die Genauigkeitsangabe gibt die gewünschte Anzahl von Dezimalstellen an. Bei fehlendem Genauigkeitsspezifizierer wird die numerische Genauigkeit von der [NumberFormatInfo.NumberDecimalDigits](xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits)-Eigenschaft angegeben.

Die Ergebniszeichenfolge wird von den Formatierungsinformationen des aktuellen [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekts beeinflusst. In der folgenden Tabelle sind die Eigenschaften des [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekts aufgeführt, die die Formatierung der Ergebniszeichenfolge steuern.

NumberFormatInfo-Eigenschaft | Beschreibung
------------------------- | -----------
[NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign) | Definiert die Zeichenfolge, die angibt, dass eine Zahl negativ ist.
[NumberDecimalSeparator](xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator) | Definiert die Zeichenfolge, die ganze Zahlen von Dezimalzahlen trennt.
[NumberFormatInfo.NumberDecimalDigits](xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits) | Definiert die Standardanzahl von Dezimalzahlen. Dieser Wert kann mit der Genauigkeitsangabe überschrieben werden.

Im folgenden Beispiel wird ein [Double](xref:System.Double)-Wert und ein [Int32](xref:System.Int32)-Wert mit dem Festkommaformatbezeichner formatiert.

```csharp
int integerNumber;
integerNumber = 17843;
Console.WriteLine(integerNumber.ToString("F", 
                  CultureInfo.InvariantCulture));
// Displays 17843.00

integerNumber = -29541;
Console.WriteLine(integerNumber.ToString("F3", 
                  CultureInfo.InvariantCulture));
// Displays -29541.000

double doubleNumber;
doubleNumber = 18934.1879;
Console.WriteLine(doubleNumber.ToString("F", CultureInfo.InvariantCulture));
// Displays 18934.19

Console.WriteLine(doubleNumber.ToString("F0", CultureInfo.InvariantCulture));
// Displays 18934

doubleNumber = -1898300.1987;
Console.WriteLine(doubleNumber.ToString("F1", CultureInfo.InvariantCulture));  
// Displays -1898300.2

Console.WriteLine(doubleNumber.ToString("F3", 
                  CultureInfo.CreateSpecificCulture("es-ES")));
// Displays -1898300,199 
```

```vb
Dim integerNumber As Integer
integerNumber = 17843
Console.WriteLine(integerNumber.ToString("F", CultureInfo.InvariantCulture))
' Displays 17843.00

integerNumber = -29541
Console.WriteLine(integerNumber.ToString("F3", CultureInfo.InvariantCulture))
' Displays -29541.000

Dim doubleNumber As Double
doubleNumber = 18934.1879
Console.WriteLine(doubleNumber.ToString("F", CultureInfo.InvariantCulture))
' Displays 18934.19

Console.WriteLine(doubleNumber.ToString("F0", CultureInfo.InvariantCulture))
' Displays 18934

doubleNumber = -1898300.1987
Console.WriteLine(doubleNumber.ToString("F1", CultureInfo.InvariantCulture))  
' Displays -1898300.2

Console.WriteLine(doubleNumber.ToString("F3", _ 
                  CultureInfo.CreateSpecificCulture("es-ES")))
' Displays -1898300,199                        
```

## <a name="the-general-g-format-specifier"></a>Der allgemeine Formatbezeichner „G“

Der allgemeine Formatbezeichner „G“ konvertiert eine Zahl abhängig von ihrem Typ und dem Vorhandensein eines Genauigkeitsspezifizierer in die kompaktere Festkomma- oder wissenschaftliche Schreibweise. Die Genauigkeitsangabe definiert die maximale Anzahl von signifikanten Stellen, die in der Ergebniszeichenfolge angezeigt werden können. Wenn die Genauigkeitsangabe fehlt oder 0 (null) ist, wird die Standardgenauigkeit über den Typ der Zahl festgelegt (siehe folgende Tabelle). 

Numerischer Typ | Standardgenauigkeit
------------ | -----------------
[Byte](xref:System.Byte) oder [SByte](xref:System.SByte) | 3 Stellen
[Int16](xref:System.Int16) oder [UInt16](xref:System.UInt16) | 5 Stellen
[Int32](xref:System.Int32) oder [UInt32](xref:System.UInt32) | 10 Stellen
[Int64](xref:System.Int64) | 19 Stellen
[UInt64](xref:System.UInt64) | 20 Stellen
[BigInteger](xref:System.Numerics.BigInteger) | Unbegrenzt (identisch mit „R“)
[Single](xref:System.Single) | 7 Stellen
[Double](xref:System.Double) | 15 Stellen
[Decimal](xref:System.Decimal) | 29 Stellen

Die Festkommanotation wird verwendet, wenn der Exponent, der sich durch Ausdrücken der Zahl in wissenschaftlicher Notation ergibt, größer als –5 und kleiner als die Genauigkeitsangabe ist. Andernfalls wird die wissenschaftliche Notation verwendet. Das Ergebnis enthält ggf. ein Dezimaltrennzeichen. Nachfolgende Nullen nach dem Dezimaltrennzeichen werden weggelassen. Wenn die Genauigkeitsangabe vorhanden ist und die Anzahl der signifikanten Ziffern im Ergebnis die angegebene Genauigkeit übersteigt, werden die überzähligen nachfolgenden Ziffern durch Rundung entfernt. 

Wenn die Zahl jedoch den Typ [Decimal](xref:System.Decimal) aufweist und kein Genauigkeitsspezifizierer angegeben wurde, wird die Festkommaschreibweise in jedem Fall verwendet, und nachfolgende Nullen bleiben erhalten.

Bei Verwendung der wissenschaftlichen Notation wird dem Exponenten im Ergebnis "E" vorangestellt, wenn der Formatbezeichner "G" ist, oder "e", wenn der Formatbezeichner "g" ist. Der Exponent enthält mindestens zwei Ziffern. Dies stellt einen Unterschied zum wissenschaftlichen Notationsformat dar, das vom exponentiellen Formatbezeichner erzeugt wird und mindestens drei Ziffern im Exponenten verwendet.

Die Ergebniszeichenfolge wird von den Formatierungsinformationen des aktuellen [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekts beeinflusst. In der folgenden Tabelle sind die [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Eigenschaften aufgeführt, die die Formatierung der Ergebniszeichenfolge steuern.

NumberFormatInfo-Eigenschaft | Beschreibung
------------------------- | -----------
[NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign) | Definiert die Zeichenfolge, die angibt, dass eine Zahl negativ ist.
[NumberDecimalSeparator](xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator) | Definiert die Zeichenfolge, die ganze Zahlen von Dezimalzahlen trennt.
[PositiveSign](xref:System.Globalization.NumberFormatInfo.PositiveSign) | Definiert die Zeichenfolge, die angibt, dass ein Exponent positiv ist. 

Im folgenden Beispiel werden gemischte Gleitkommawerte mit dem allgemeinen Formatbezeichner formatiert.

```csharp
double number;

number = 12345.6789;      
Console.WriteLine(number.ToString("G", CultureInfo.InvariantCulture));
// Displays  12345.6789
Console.WriteLine(number.ToString("G", 
                  CultureInfo.CreateSpecificCulture("fr-FR")));
// Displays 12345,6789

Console.WriteLine(number.ToString("G7", CultureInfo.InvariantCulture));
// Displays 12345.68 

number = .0000023;
Console.WriteLine(number.ToString("G", CultureInfo.InvariantCulture));
// Displays 2.3E-06       
Console.WriteLine(number.ToString("G", 
                  CultureInfo.CreateSpecificCulture("fr-FR")));
// Displays 2,3E-06

number = .0023;
Console.WriteLine(number.ToString("G", CultureInfo.InvariantCulture));
// Displays 0.0023

number = 1234;
Console.WriteLine(number.ToString("G2", CultureInfo.InvariantCulture));
// Displays 1.2E+03

number = Math.PI;
Console.WriteLine(number.ToString("G5", CultureInfo.InvariantCulture));
// Displays 3.1416    
```

```vb
Dim number As Double

number = 12345.6789      
Console.WriteLine(number.ToString("G", CultureInfo.InvariantCulture))
' Displays  12345.6789
Console.WriteLine(number.ToString("G", _
                  CultureInfo.CreateSpecificCulture("fr-FR")))
' Displays 12345,6789

Console.WriteLine(number.ToString("G7", CultureInfo.InvariantCulture))
' Displays 12345.68 

number = .0000023
Console.WriteLine(number.ToString("G", CultureInfo.InvariantCulture))
' Displays 2.3E-06       
Console.WriteLine(number.ToString("G", _
                  CultureInfo.CreateSpecificCulture("fr-FR")))
' Displays 2,3E-06

number = .0023
Console.WriteLine(number.ToString("G", CultureInfo.InvariantCulture))
' Displays 0.0023

number = 1234
Console.WriteLine(number.ToString("G2", CultureInfo.InvariantCulture))
' Displays 1.2E+03

number = Math.Pi
Console.WriteLine(number.ToString("G5", CultureInfo.InvariantCulture))
' Displays 3.1416
```

## <a name="the-numeric-n-format-specifier"></a>Der Bezeichner „N“ für numerisches Format

Der numerische Formatbezeichner ("N") konvertiert eine Zahl in eine Zeichenfolge mit dem Format "-d,ddd,ddd.ddd…", wobei "-" ggf. ein negatives Zahlensymbol, "d" eine Ziffer (0-9), "'," ein Gruppentrennzeichen und "." ein Dezimaltrennzeichensymbol angibt. Die Genauigkeitsangabe gibt die gewünschte Anzahl von Ziffern nach dem Dezimaltrennzeichen an. Bei fehlendem Genauigkeitsspezifizierer wird die Anzahl der Dezimalstellen von der aktuellen [NumberFormatInfo.NumberDecimalDigits](xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits)-Eigenschaft definiert.

Die Ergebniszeichenfolge wird von den Formatierungsinformationen des aktuellen [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekts beeinflusst. In der folgenden Tabelle sind die [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Eigenschaften aufgeführt, die die Formatierung der Ergebniszeichenfolge steuern.

NumberFormatInfo-Eigenschaft | Beschreibung
------------------------- | -----------
[NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign) | Definiert die Zeichenfolge, die angibt, dass eine Zahl negativ ist.
[NumberNegativePattern](xref:System.Globalization.NumberFormatInfo.NumberNegativePattern) | Definiert das Format von negativen Werten und gibt an, ob das Minuszeichen durch Klammern oder durch die [NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign)-Eigenschaft dargestellt wird.
[NumberGroupSizes](xref:System.Globalization.NumberFormatInfo.NumberGroupSizes) | Definiert die Anzahl von ganzzahligen Ziffern, die zwischen Gruppentrennzeichen angezeigt werden.
[NumberGroupSeparator](xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator) | Definiert die Zeichenfolge, die Gruppen von ganzen Zahlen trennt.
[NumberDecimalSeparator](xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator) | Definiert die Zeichenfolge, die ganze Zahlen von Dezimalzahlen trennt.
[NumberDecimalDigits](xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits) | Definiert die Standardanzahl von Dezimalzahlen. Dieser Wert kann mit einer Genauigkeitsangabe überschrieben werden.

Im folgenden Beispiel werden gemischte Gleitkommawerte mit dem Zahlenformatbezeichner formatiert.

```csharp
double dblValue = -12445.6789;
Console.WriteLine(dblValue.ToString("N", CultureInfo.InvariantCulture));
// Displays -12,445.68
Console.WriteLine(dblValue.ToString("N1", 
                  CultureInfo.CreateSpecificCulture("sv-SE")));
// Displays -12 445,7

int intValue = 123456789;
Console.WriteLine(intValue.ToString("N1", CultureInfo.InvariantCulture));
// Displays 123,456,789.0 
```

```vb
Dim dblValue As Double = -12445.6789
Console.WriteLine(dblValue.ToString("N", CultureInfo.InvariantCulture))
' Displays -12,445.68
Console.WriteLine(dblValue.ToString("N1", _
                  CultureInfo.CreateSpecificCulture("sv-SE")))
' Displays -12 445,7

Dim intValue As Integer = 123456789
Console.WriteLine(intValue.ToString("N1", CultureInfo.InvariantCulture))
' Displays 123,456,789.0 
```

## <a name="the-percent-p-format-specifier"></a>Der Bezeichner „P“ für Prozentformat

Der Prozentformatbezeichner "P" multipliziert eine Zahl mit 100 und konvertiert sie in eine Zeichenfolge, die einen Prozentsatz darstellt. Die Genauigkeitsangabe gibt die gewünschte Anzahl von Dezimalstellen an. Bei fehlendem Genauigkeitsspezifizierer wird die Standardgenauigkeit für Zahlen verwendet, die von der aktuellen [PercentDecimalDigits](xref:System.Globalization.NumberFormatInfo.PercentDecimalDigits)-Eigenschaft angegeben wird.

In der folgenden Tabelle sind die [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Eigenschaften aufgeführt, die die Formatierung der zurückgegebenen Zeichenfolge steuern.

umberFormatInfo-Eigenschaft | Beschreibung
------------------------- | -----------
[PercentPositivePattern](xref:System.Globalization.NumberFormatInfo.PercentPositivePattern) | Definiert die Platzierung des Prozentsymbols für positive Werte.
[PercentNegativePattern](xref:System.Globalization.NumberFormatInfo.PercentNegativePattern) | 
[NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign) | Definiert die Zeichenfolge, die angibt, dass eine Zahl negativ ist.
[PercentSymbol](xref:System.Globalization.NumberFormatInfo.PercentSymbol) | Definiert das Prozentsymbol.
[PercentDecimalDigits](xref:System.Globalization.NumberFormatInfo.PercentDecimalDigits) | Definiert die Standardanzahl von Dezimalstellen in einem Prozentwert. Dieser Wert kann mit der Genauigkeitsangabe überschrieben werden.
[PercentDecimalSeparator](xref:System.Globalization.NumberFormatInfo.PercentDecimalSeparator) | Definiert die Zeichenfolge, die ganze Zahlen und Dezimalzahlen trennt.
[PercentGroupSeparator](xref:System.Globalization.NumberFormatInfo.PercentGroupSeparator) | Definiert die Zeichenfolge, die Gruppen von ganzen Zahlen trennt. 
[PercentGroupSizes](xref:System.Globalization.NumberFormatInfo.PercentGroupSizes) | Definiert die Anzahl von ganzzahligen Ziffern, die in einer Gruppe angezeigt werden.

Im folgenden Beispiel werden gemischte Gleitkommawerte mit dem Prozentformatbezeichner formatiert.

```csharp
double number = .2468013;
Console.WriteLine(number.ToString("P", CultureInfo.InvariantCulture));
// Displays 24.68 %
Console.WriteLine(number.ToString("P", 
                  CultureInfo.CreateSpecificCulture("hr-HR")));
// Displays 24,68%     
Console.WriteLine(number.ToString("P1", CultureInfo.InvariantCulture));
// Displays 24.7 %
```

```vb
Dim number As Double = .2468013
Console.WriteLine(number.ToString("P", CultureInfo.InvariantCulture))
' Displays 24.68 %
Console.WriteLine(number.ToString("P", _
                  CultureInfo.CreateSpecificCulture("hr-HR")))
' Displays 24,68%     
Console.WriteLine(number.ToString("P1", CultureInfo.InvariantCulture))
' Displays 24.7 %
```

## <a name="the-round-trip-r-format-specifier"></a>Der Bezeichner „R“ für Roundtripformat

Der Schleifenformatbezeichner "R" wird verwendet, um sicherzustellen, dass ein in eine Zeichenfolge konvertierter numerischer Wert wieder in denselben numerischen Wert rückkonvertiert wird. Dieses Format wird nur für folgende Typen unterstützt: [Single](xref:System.Single), [Double](xref:System.Double) und [BigInteger](xref:System.Numerics.BigInteger). 

Wenn ein [BigInteger](xref:System.Numerics.BigInteger)-Wert mit diesem Bezeichner formatiert wird, enthält seine Zeichenfolgendarstellung alle signifikanten Stellen im [BigInteger](xref:System.Numerics.BigInteger)-Wert. Wenn ein [Single](xref:System.Single)-Wert oder ein [Double](xref:System.Double)-Wert mit diesem Bezeichner formatiert wird, wird der Wert zuerst mit dem allgemeinen Format getestet, wobei [Double](xref:System.Double) mit einer Genauigkeit von 15 Stellen und [Single](xref:System.Single) mit einer Genauigkeit von 7 Stellen dargestellt wird. Wenn der Wert erfolgreich in den gleichen numerischen Wert rückkonvertiert werden kann, wird er mit dem Bezeichner für das allgemeine Format formatiert. Wenn der Wert jedoch nicht in den gleichen Wert rückkonvertiert werden kann, wird der Wert mit einer Genauigkeit von 17 Ziffern für [Double](xref:System.Double) und 9 Ziffern für [Single](xref:System.Single) formatiert. 

Eine Genauigkeitsangabe kann zwar vorhanden sein, sie wird jedoch ignoriert. Bei diesem Bezeichner hat die Rückkonvertierbarkeit höhere Priorität als die Genauigkeit. 

Die Ergebniszeichenfolge wird von den Formatierungsinformationen des aktuellen [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekts beeinflusst. In der folgenden Tabelle sind die [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Eigenschaften aufgeführt, die die Formatierung der Ergebniszeichenfolge steuern.

NumberFormatInfo-Eigenschaft | Beschreibung
------------------------- | -----------
[NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign) | Definiert die Zeichenfolge, die angibt, dass eine Zahl negativ ist.
[NumberDecimalSeparator](xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator) | Definiert die Zeichenfolge, die ganze Zahlen von Dezimalzahlen trennt.
[PositiveSign](xref:System.Globalization.NumberFormatInfo.PositiveSign) | Definiert die Zeichenfolge, die angibt, dass ein Exponent positiv ist.

 Im folgenden Beispiel werden [Double](xref:System.Double)-Werte mit dem Schleifenformatbezeichner formatiert.

```csharp
double value;

value = Math.PI;
Console.WriteLine(value.ToString("r"));
// Displays 3.1415926535897931
Console.WriteLine(value.ToString("r", 
                  CultureInfo.CreateSpecificCulture("fr-FR")));
// Displays 3,1415926535897931
value = 1.623e-21;
Console.WriteLine(value.ToString("r"));
// Displays 1.623E-21
```

```vb
Dim value As Double

value = Math.Pi
Console.WriteLine(value.ToString("r"))
' Displays 3.1415926535897931
Console.WriteLine(value.ToString("r", _
                  CultureInfo.CreateSpecificCulture("fr-FR")))
' Displays 3,1415926535897931
value = 1.623e-21
Console.WriteLine(value.ToString("r"))
' Displays 1.623E-21
```

## <a name="the-hexadecimal-x-format-specifier"></a>Der Bezeichner „X“ für Hexadezimalformat

Der Hexadezimal-Formatbezeichner "X" konvertiert eine Zahl in eine Zeichenfolge von Hexadezimalzahlen. Die Schreibweise des Formatbezeichners gibt an, ob Groß- oder Kleinbuchstaben für Hexadezimalzahlen verwendet werden sollen, die größer als 9 sind. Verwenden Sie z. B. "X" für "ABCDEF", und "x" für "abcdef". Dieses Format wird nur bei ganzzahligen Typen unterstützt.

Die Genauigkeitsangabe gibt die gewünschte Mindestanzahl von Ziffern für die resultierende Zeichenfolge an. Bei Bedarf werden links von der Zahl Nullen ergänzt, um die durch die Genauigkeitsangabe bestimmte Anzahl von Ziffern zu erstellen.

Die Ergebniszeichenfolge wird von den Formatierungsinformationen des aktuellen [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekts nicht beeinflusst. 

Im folgenden Beispiel werden [Int32](xref:System.Int32)-Werte mit dem Hexadezimal-Formatbezeichner formatiert.

```csharp
int value; 

value = 0x2045e;
Console.WriteLine(value.ToString("x"));
// Displays 2045e
Console.WriteLine(value.ToString("X"));
// Displays 2045E
Console.WriteLine(value.ToString("X8"));
// Displays 0002045E

value = 123456789;
Console.WriteLine(value.ToString("X"));
// Displays 75BCD15
Console.WriteLine(value.ToString("X2"));
// Displays 75BCD15
```

```vb
Dim value As Integer 

value = &h2045e
Console.WriteLine(value.ToString("x"))
' Displays 2045e
Console.WriteLine(value.ToString("X"))
' Displays 2045E
Console.WriteLine(value.ToString("X8"))
' Displays 0002045E

value = 123456789
Console.WriteLine(value.ToString("X"))
' Displays 75BCD15
Console.WriteLine(value.ToString("X2"))
' Displays 75BCD15
```

## <a name="notes"></a>Notizen

### <a name="numberformatinfo-properties"></a>NumberFormatInfo-Eigenschaften

Die Formatierung wird durch die Eigenschaften des aktuellen [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekts beeinflusst, das implizit durch die aktuelle Threadkultur oder explizit durch den [IFormatProvider](xref:System.IFormatProvider)-Parameter der Methode bereitgestellt wird, die die Formatierung aufruft. Geben Sie ein [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)- oder ein [CultureInfo](xref:System.Globalization.CultureInfo)-Objekt für diesen Parameter an. 

### <a name="integral-and-floating-point-numeric-types"></a>Ganzzahlige numerische Typen und numerische Gleitkommatypen

Einige Beschreibungen standardmäßiger Zahlenformatbezeichner verweisen auf ganzzahlige numerische Typen oder numerische Gleitkommatypen. Die ganzzahligen numerischen Typen sind [Byte](xref:System.Byte), [SByte](xref:System.SByte), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32), [UInt64](xref:System.UInt64) und [BigInteger](xref:System.Numerics.BigInteger). Die numerischen Gleitkommatypen sind [Decimal](xref:System.Decimal), [Single](xref:System.Single) und [Double](xref:System.Double). 

### <a name="floating-point-infinities-and-nan"></a>Unendlichkeiten und NaN bei Gleitkommawerten

Wenn der Wert eines [Single](xref:System.Single)- oder [Double](xref:System.Double)-Gleitkommatyps positiv unendlich, negativ unendlich oder keine Zahl (Not a Number, NaN) ist, handelt es sich bei der formatierten Zeichenfolge unabhängig von der Formatzeichenfolge um den Wert der entsprechenden [PositiveInfinitySymbol](xref:System.Globalization.NumberFormatInfo.PositiveInfinitySymbol)-, [NegativeInfinitySymbol](xref:System.Globalization.NumberFormatInfo.NegativeInfinitySymbol)- oder [NaNSymbol](xref:System.Globalization.NumberFormatInfo.NaNSymbol)-Eigenschaft, die durch das derzeit gültige [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekt angegeben wird.

## <a name="example"></a>Beispiel

Durch das folgende Beispiel werden mithilfe der Kultur en-US und allen Standardzahlen-Formatbezeichnern ein ganzzahliger Wert und ein numerischer Gleitkommawert formatiert. In diesem Beispiel werden zwei bestimmte numerische Typen ([Double](xref:System.Double) und [Int32](xref:System.Int32)) verwendet. Die Ergebnisse sind jedoch für alle numerischen Basistypen ([Byte](xref:System.Byte), [SByte](xref:System.SByte), [Int16](xref:System.Int16), [Int64](xref:System.Int64), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32), [UInt64](xref:System.UInt64) und [BigInteger](xref:System.Numerics.BigInteger), [Decimal](xref:System.Decimal) und [Single](xref:System.Single)) ähnlich. 

```csharp
using System;
using System.Globalization;
using System.Threading;

public class NumericFormats
{
   public static void Main()
   {
      // Display string representations of numbers for en-us culture
      CultureInfo ci = new CultureInfo("en-us");

      // Output floating point values
      double floating = 10761.937554;
      Console.WriteLine("C: {0}", 
              floating.ToString("C", ci));           // Displays "C: $10,761.94"
      Console.WriteLine("E: {0}", 
              floating.ToString("E03", ci));         // Displays "E: 1.076E+004"
      Console.WriteLine("F: {0}", 
              floating.ToString("F04", ci));         // Displays "F: 10761.9376"         
      Console.WriteLine("G: {0}",  
              floating.ToString("G", ci));           // Displays "G: 10761.937554"
      Console.WriteLine("N: {0}", 
              floating.ToString("N03", ci));         // Displays "N: 10,761.938"
      Console.WriteLine("P: {0}", 
              (floating/10000).ToString("P02", ci)); // Displays "P: 107.62 %"
      Console.WriteLine("R: {0}", 
              floating.ToString("R", ci));           // Displays "R: 10761.937554"            
      Console.WriteLine();

      // Output integral values
      int integral = 8395;
      Console.WriteLine("C: {0}", 
              integral.ToString("C", ci));           // Displays "C: $8,395.00"
      Console.WriteLine("D: {0}", 
              integral.ToString("D6", ci));          // Displays "D: 008395" 
      Console.WriteLine("E: {0}", 
              integral.ToString("E03", ci));         // Displays "E: 8.395E+003"
      Console.WriteLine("F: {0}", 
              integral.ToString("F01", ci));         // Displays "F: 8395.0"    
      Console.WriteLine("G: {0}",  
              integral.ToString("G", ci));           // Displays "G: 8395"
      Console.WriteLine("N: {0}", 
              integral.ToString("N01", ci));         // Displays "N: 8,395.0"
      Console.WriteLine("P: {0}", 
              (integral/10000.0).ToString("P02", ci)); // Displays "P: 83.95 %"
      Console.WriteLine("X: 0x{0}", 
              integral.ToString("X", ci));           // Displays "X: 0x20CB"
      Console.WriteLine();
   }
}
```

```vb
Option Strict On

Imports System.Globalization
Imports System.Threading

Module NumericFormats
   Public Sub Main()
      ' Display string representations of numbers for en-us culture
      Dim ci As New CultureInfo("en-us")

      ' Output floating point values
      Dim floating As Double = 10761.937554
      Console.WriteLine("C: {0}", _
              floating.ToString("C", ci))           ' Displays "C: $10,761.94"
      Console.WriteLine("E: {0}", _
              floating.ToString("E03", ci))         ' Displays "E: 1.076E+004"
      Console.WriteLine("F: {0}", _
              floating.ToString("F04", ci))         ' Displays "F: 10761.9376"         
      Console.WriteLine("G: {0}", _ 
              floating.ToString("G", ci))           ' Displays "G: 10761.937554"
      Console.WriteLine("N: {0}", _
              floating.ToString("N03", ci))         ' Displays "N: 10,761.938"
      Console.WriteLine("P: {0}", _
              (floating/10000).ToString("P02", ci)) ' Displays "P: 107.62 %"
      Console.WriteLine("R: {0}", _
              floating.ToString("R", ci))           ' Displays "R: 10761.937554"            
      Console.WriteLine()

      ' Output integral values
      Dim integral As Integer = 8395
      Console.WriteLine("C: {0}", _
              integral.ToString("C", ci))           ' Displays "C: $8,395.00"
      Console.WriteLine("D: {0}", _
              integral.ToString("D6"))              ' Displays "D: 008395" 
      Console.WriteLine("E: {0}", _
              integral.ToString("E03", ci))         ' Displays "E: 8.395E+003"
      Console.WriteLine("F: {0}", _
              integral.ToString("F01", ci))         ' Displays "F: 8395.0"    
      Console.WriteLine("G: {0}", _ 
              integral.ToString("G", ci))           ' Displays "G: 8395"
      Console.WriteLine("N: {0}", _
              integral.ToString("N01", ci))         ' Displays "N: 8,395.0"
      Console.WriteLine("P: {0}", _
              (integral/10000).ToString("P02", ci)) ' Displays "P: 83.95 %"
      Console.WriteLine("X: 0x{0}", _
              integral.ToString("X", ci))           ' Displays "X: 0x20CB"
      Console.WriteLine()
   End Sub
End Module
```

## <a name="see-also"></a>Siehe auch

[System.Globalization.NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)

[Benutzerdefinierte Zahlenformatzeichenfolgen](custom-numeric.md)

[Formatierung von Typen](formatting-types.md)

[Gewusst wie: Auffüllen einer Zahl mit führenden Nullen](pad-number.md)

[Kombinierte Formatierung](composite-format.md)

