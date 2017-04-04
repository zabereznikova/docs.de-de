---
title: Formatierung von Typen
description: Formatierung von Typen
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: cf497639-9f91-45cb-836f-998d1cea2f43
translationtype: Human Translation
ms.sourcegitcommit: b967d8e55347f44a012e4ad8e916440ae228c8ec
ms.openlocfilehash: e9b8ad13a48dd43236769b130d6f8a75b7b023ca
ms.lasthandoff: 03/10/2017

---

# <a name="formatting-types"></a>Formatierung von Typen

Bei der Formatierung wird eine Instanz einer Klasse, Struktur oder eines Enumerationswerts in die entsprechende Zeichenfolgendarstellung konvertiert. Die resultierende Zeichenfolge kann dann häufig Benutzern angezeigt oder sie kann deserialisiert werden, um den ursprünglichen Datentyp wiederherzustellen. Diese Konvertierung kann eine Reihe von Problemen beinhalten:

* Die Art, wie diese Werte intern gespeichert werden, spiegelt nicht notwendigerweise die Art wider, wie die Benutzer sie anzeigen möchten. Eine Telefonnummer könnte beispielsweise wie folgt gespeichert werden: **8009999999**. Dies ist jedoch wenig benutzerfreundlich. Stattdessen sollte die Telefonnummer wie folgt angezeigt werden: **800-999-9999**. Ein Beispiel für die Formatierung einer Zahl auf diese Weise finden Sie im Abschnitt [Benutzerdefinierte Formatzeichenfolgen](#custom-format-strings). 

* Manchmal ist die Konvertierung eines Objekts in seine Zeichenfolgendarstellung nicht intuitiv. Beispielsweise ist nicht klar, wie die Zeichenfolgendarstellung eines **Temperature**-Objekts oder eines **Person**-Objekts aussehen sollte. Ein Beispiel für die Formatierung eines **Temperature**-Objekts auf verschiedene Weise finden Sie im Abschnitt [Standardformatzeichenfolgen](#standard-format-strings).

* Oft ist für Werte eine kulturabhängige Formatierung erforderlich. In einer Anwendung, die zum Darstellen von Währungswerten Zahlen verwendet, sollten numerische Zeichenfolgen beispielsweise das Währungssymbol der aktuellen Kultur, das Gruppentrennzeichen (in den meisten Kulturen das Tausendertrennzeichen) und das Dezimaltrennzeichen einschließen. Ein Beispiel finden Sie im Abschnitt [Kulturabhängige Formatierung mit Formatanbietern und der IFormatProvider-Schnittstelle](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface). 

* Unter Umständen muss ein Wert in einer Anwendung auf unterschiedliche Arten angezeigt werden. Beispielsweise stellt eine Anwendung einen Enumerationsmember möglicherweise dar, indem eine Zeichenfolgendarstellung des Namens oder des zugrunde liegende Werts angezeigt wird. Ein Beispiel für die Formatierung eines Members der [DayOfWeek](xref:System.DayOfWeek)-Enumeration auf unterschiedliche Weise finden Sie im Abschnitt [Standardformatzeichenfolgen](#standard-format-strings).

.NET bietet eine umfangreiche Formatierungsunterstützung, die es Entwicklern ermöglicht, diese Anforderungen zu erfüllen. 

> [!NOTE]
> Durch das Formatieren wird der Wert eines Typs in eine Zeichenfolgendarstellung konvertiert. Die Analyse ist die Umkehroperation zum Formatieren. In einem Analysevorgang wird eine Instanz eines Datentyps aus seiner Zeichenfolgendarstellung erstellt. Informationen zum Konvertieren von Zeichenfolgen in andere Datentypen finden Sie unter [Analysieren von Zeichenfolgen](parsing-strings.md).

Diese Übersicht enthält folgende Abschnitte:

* [Formatierung in .NET](#formatting-in-net)

* [Standardformatierung mit der ToString-Methode](#default-formatting-using-the-tostring-method)

* [Überschreiben der ToString-Methode](#overriding-the-tostring-method)

* [ToString-Methode und Formatzeichenfolgen](#the-tostring-method-and-format-strings)

    * [Standardformatzeichenfolgen](#standard-format-strings)
    
    * [Benutzerdefinierte Formatzeichenfolgen](#custom-format-strings)
    
    * [Formatzeichenfolgen und .NET-Typen](#format-strings-and-net-types)
    
* [Kulturabhängige Formatierung mit Formatanbietern und der IFormatProvider-Schnittstelle](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface)

    * [Kulturabhängige Formatierung von numerischen Werten](#culture-sensitive-formatting-of-numeric-values)
    
    * [Kulturabhängige Formatierung von Datums- und Uhrzeitwerten](#culture-sensitive-formatting-of-date-and-time-values)
    
* [IFormattable-Schnittstelle](#the-iformattable-interface)

* [Kombinierte Formatierung](#composite-formatting)

* [Benutzerdefinierte Formatierung mit ICustomFormatter](#custom-formatting-with-icustomformatter)

* [Verwandte Themen](#related-topics)

* [Referenz](#reference)

## <a name="formatting-in-net"></a>Formatierung in .NET

Der grundlegende Mechanismus für die Formatierung ist die Standardimplementierung der [Object.ToString](xref:System.Object.ToString)-Methode, die im Abschnitt [Standardformatierung mit der ToString-Methode](#default-formatting-using-the-tostring-method) weiter unten in diesem Thema erläutert wird. .NET bietet jedoch mehrere Möglichkeiten, die Standardformatierungsunterstützung zu ändern und zu erweitern. Hierzu gehört Folgendes:

* Überschreiben der [Object.ToString](xref:System.Object.ToString)-Methode, um eine benutzerdefinierte Zeichenfolgendarstellung des Werts eines Objekts zu definieren. Weitere Informationen erhalten Sie im Abschnitt [Überschreiben der ToString-Methode](#overriding-the-tostring-method) weiter unten in diesem Thema.

* Definieren von Formatbezeichnern, die es ermöglichen, dass die Zeichenfolgendarstellung des Werts eines Objekts mehrere Formate annehmen kann. Der Formatbezeichner "X" in der folgenden Anweisung konvertiert beispielsweise eine ganze Zahl in die Zeichenfolgendarstellung eines Hexadezimalwerts.

  ```csharp
  int integerValue = 60312;
  Console.WriteLine(integerValue.ToString("X"));   // Displays EB98.
  ```

  ```vb
  Dim integerValue As Integer = 60312
  Console.WriteLine(integerValue.ToString("X"))   ' Displays EB98.
  ```
  
  Weitere Informationen zu Formatbezeichnern finden Sie im Abschnitt [ToString-Methode und Formatzeichenfolgen](#the-tostring-method-and-format-strings).
  
* Verwenden von Formatanbietern, die Formatierungskonventionen einer bestimmten Kultur nutzen. Beispielsweise zeigt die folgende Anweisung einen Währungswert unter Verwendung der Formatierungskonventionen der Kultur en-US an. 

  ```csharp
  double cost = 1632.54; 
  Console.WriteLine(cost.ToString("C", 
                  new System.Globalization.CultureInfo("en-US")));   
  // The example displays the following output:
  //       $1,632.54
  ```

  ```vb
  Dim cost As Double = 1632.54
  Console.WriteLine(cost.ToString("C", New System.Globalization.CultureInfo("en-US")))
  ' The example displays the following output:
  '       $1,632.54
  ```
  
  Weitere Informationen zum Formatieren mit Formatanbietern finden Sie im Abschnitt [Kulturabhängige Formatierung mit Formatanbietern und der IFormatProvider-Schnittstelle](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface).  
  
* Implementieren der [IFormattable](xref:System.IFormattable)-Schnittstelle zur Unterstützung der Zeichenfolgenkonvertierung mit der [Convert](xref:System.Convert)-Klasse sowie der zusammengesetzten Formatierung. Weitere Informationen finden Sie im Abschnitt [IFormattable-Schnittstelle](#the-iformattable-interface).

* Verwenden der kombinierten Formatierung, um die Zeichenfolgendarstellung eines Werts in einer größeren Zeichenfolge einzubetten. Weitere Informationen finden Sie im Abschnitt [Zusammengesetzte Formatierung](#composite-formatting).

* Implementieren von [ICustomFormatter](xref:System.ICustomFormatter) und [IFormatProvider](xref:System.IFormatProvider), um eine vollständige Formatierungslösung bereitzustellen. Weitere Informationen finden Sie im Abschnitt [Benutzerdefinierte Formatierung mit ICustomFormatter](#custom-formatting-with-icustomformatter).

In den folgenden Abschnitten werden diese Methoden zum Konvertieren eines Objekts in seine Zeichenfolgendarstellung ausführlicher erläutert.

## <a name="default-formatting-using-the-tostring-method"></a>Standardformatierung mit der ToString-Methode

Jeder von [System.Object](xref:System.Object) abgeleitete Typ erbt automatisch eine parameterlose [ToString](xref:System.Object.ToString)-Methode, die standardmäßig den Namen des Typs zurückgibt. Das folgende Beispiel veranschaulicht die [ToString](xref:System.Object.ToString)-Standardmethode. Dabei wird eine Klasse mit dem Namen `Automobile` ohne Implementierung definiert. Wenn die Klasse instanziiert und die zugehörige [ToString](xref:System.Object.ToString)-Methode aufgerufen wird, wird der Typname angezeigt. Beachten Sie, dass die [ToString](xref:System.Object.ToString)-Methode im Beispiel nicht explizit aufgerufen wird. Die [Console.WriteLine(Object)](xref:System.Console.WriteLine(System.Object))-Methode ruft implizit die [ToString](xref:System.Object.ToString)-Methode des Objekts auf, das ihr als Argument übergeben wird. 

```csharp
using System;

public class Automobile
{
   // No implementation. All members are inherited from Object.
}

public class Example
{
   public static void Main()
   {
      Automobile firstAuto = new Automobile();
      Console.WriteLine(firstAuto);
   }
}
// The example displays the following output:
//       Automobile
```

```vb 
Public Class Automobile
   ' No implementation. All members are inherited from Object.
End Class

Module Example
   Public Sub Main()
      Dim firstAuto As New Automobile()
      Console.WriteLine(firstAuto)
   End Sub
End Module
' The example displays the following output:
'       Automobile
```

Da alle Typen außer Schnittstellen von [Object](xref:System.Object) abgeleitet werden, wird diese Funktionalität automatisch für Ihre benutzerdefinierten Klassen oder Strukturen bereitgestellt. Die Funktionalität der [ToString](xref:System.Object.ToString)-Standardmethode ist jedoch begrenzt: Sie identifiziert zwar den Typ, stellt jedoch keine Informationen zu einer Instanz des Typs bereit. Um eine Zeichenfolgendarstellung eines Objekts bereitzustellen, die Informationen zum Objekt enthält, müssen Sie die [ToString](xref:System.Object.ToString)-Methode überschreiben.

> [!NOTE]
> Strukturen erben vom [ValueType](xref:System.ValueType), der wiederum vom [Object](xref:System.Object) abgeleitet wird. [ValueType](xref:System.ValueType) überschreibt zwar [Object.ToString](xref:System.Object.ToString), aber die Implementierung ist identisch.

## <a name="overriding-the-tostring-method"></a>Überschreiben der ToString-Methode

Das Anzeigen des Namens eines Typs ist oft nur von geringem Nutzen und ermöglicht Consumern der Typen keine Unterscheidung zwischen den einzelnen Instanzen. Sie können jedoch die [ToString](xref:System.Object.ToString)-Methode überschreiben, um eine nützlichere Darstellung eines Objektwerts bereitzustellen. Das folgende Beispiel definiert ein `Temperature`-Objekt und überschreibt die [ToString](xref:System.Object.ToString)-Methode, um die Temperatur in Grad Celsius anzuzeigen.

```csharp
using System;

public class Temperature
{
   private decimal temp;

   public Temperature(decimal temperature)
   {
      this.temp = temperature;   
   }

   public override string ToString()
   {
      return this.temp.ToString("N1") + "°C";
   }
}

public class Example
{
   public static void Main()
   {
      Temperature currentTemperature = new Temperature(23.6m);
      Console.WriteLine("The current temperature is " +
                        currentTemperature.ToString());
   }
}
// The example displays the following output:
//       The current temperature is 23.6°C.
```

```vb
Public Class Temperature
   Private temp As Decimal

   Public Sub New(temperature As Decimal)
      Me.temp = temperature
   End Sub

   Public Overrides Function ToString() As String
      Return Me.temp.ToString("N1") + "°C"   
   End Function
End Class

Module Example
   Public Sub Main()
      Dim currentTemperature As New Temperature(23.6d)
      Console.WriteLine("The current temperature is " +
                        currentTemperature.ToString())
   End Sub
End Module
' The example displays the following output:
'       The current temperature is 23.6°C.
```

In .NET wurde die [ToString](xref:System.Object.ToString)-Methode jedes primitiven Werttyps überschrieben, um den Wert des Objekts statt seines Namens anzuzeigen. In der folgenden Tabelle wird die Überschreibung für den jeweiligen primitiven Typ angezeigt. Beachten Sie, dass die meisten der überschriebenen Methoden eine andere Überladung der [ToString](xref:System.Object.ToString)-Methode aufrufen und dabei den Formatbezeichner „G“ übergeben, der das allgemeine Format des Typs definiert, sowie ein [IFormatProvider](xref:System.IFormatProvider)-Objekt, das die aktuelle Kultur darstellt.

Typ | ToString-Überschreibung
---- | -----------------
[Boolean](xref:System.Boolean) | Gibt entweder [Boolean.TrueString](xref:System.Boolean.TrueString) oder [Boolean.FalseString](xref:System.Boolean.FalseString) zurück.
[Byte](xref:System.Byte) | Ruft `Byte.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den [Byte](xref:System.Byte)-Wert für die aktuelle Kultur zu formatieren.
[Char](xref:System.Char) | Gibt das Zeichen als Zeichenfolge zurück.
[DateTime](xref:System.DateTime) | Ruft `DateTime.ToString("G", DatetimeFormatInfo.CurrentInfo)` auf, um den Datums- und Uhrzeitwert für die aktuelle Kultur zu formatieren. 
[Decimal](xref:System.Decimal) | Ruft `Decimal.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den [Decimal](xref:System.Decimal)-Wert für die aktuelle Kultur zu formatieren.
[Double](xref:System.Double) | Ruft `Double.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den [Double](xref:System.Double)-Wert für die aktuelle Kultur zu formatieren.
[Int16](xref:System.Int16) | Ruft `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den [Int16](xref:System.Int16)-Wert für die aktuelle Kultur zu formatieren.
[Int32](xref:System.Int32) | Ruft `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den [Int32](xref:System.Int32)-Wert für die aktuelle Kultur zu formatieren.
[Int64](xref:System.Int64) | Ruft `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den [Int64](xref:System.Int64)-Wert für die aktuelle Kultur zu formatieren.
[SByte](xref:System.SByte) | Ruft `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den [SByte](xref:System.SByte)- | Wert für die aktuelle Kultur zu formatieren.
[Single](xref:System.Single) | Ruft `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den [Single](xref:System.Single)-Wert für die aktuelle Kultur zu formatieren.
[UInt32](xref:System.UInt32) | Ruft `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den [UInt32](xref:System.UInt32)-Wert für die aktuelle Kultur zu formatieren.
[UInt32](xref:System.UInt32) | Ruft `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den [UInt32](xref:System.UInt32)-Wert für die aktuelle Kultur zu formatieren.
[UInt64](xref:System.UInt64) | Ruft `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den [UInt64](xref:System.UInt64)-Wert für die aktuelle Kultur zu formatieren.

## <a name="the-tostring-method-and-format-strings"></a>ToString-Methode und Formatzeichenfolgen

Wenn ein Objekt über eine einzelne Zeichenfolgendarstellung verfügt, ist das Verwenden der [ToString](xref:System.Object.ToString)-Standardmethode oder das Überschreiben von [ToString](xref:System.Object.ToString) angemessen. Der Wert eines Objekts weist jedoch häufig mehrere Darstellungen auf. Beispielsweise kann die Temperatur in Grad Fahrenheit, Grad Celsius oder Kelvin ausgedrückt werden. Entsprechend kann der ganzzahlige Wert 10 unterschiedlich dargestellt werden, z. B. als 10, 10.0, 1.0e01 oder $10.00.

Damit ein einzelner Wert mehrere Zeichenfolgendarstellungen aufweisen kann, verwendet .NET Formatzeichenfolgen. Eine Formatzeichenfolge ist eine Zeichenfolge, die einen oder mehrere vordefinierte Formatbezeichner enthält. Dies sind einzelne Zeichen oder Gruppen von Zeichen, die definieren, wie die [ToString](xref:System.Object.ToString)-Methode die Ausgabe formatieren soll. Die Formatzeichenfolge wird dann als Parameter an die [ToString](xref:System.Object.ToString)-Methode des Objekts übergeben und bestimmt, wie die Zeichenfolgendarstellung des Werts dieses Objekts angezeigt werden soll.

Alle numerischen Typen sowie die Datums- und Uhrzeittypen und die Enumerationstypen in .NET unterstützen einen vordefinierten Satz von Formatbezeichnern. Sie können auch Formatzeichenfolgen verwenden, um mehrere Zeichenfolgendarstellungen der anwendungsdefinierten Datentypen zu definieren.

### <a name="standard-format-strings"></a>Standardformatzeichenfolgen

Standardformatzeichenfolgen enthalten einen einzelnen Formatbezeichner. Dabei handelt es sich um ein alphabetisches Zeichen, das die Zeichenfolgendarstellung des Objekts definiert, auf das es angewendet wird. Außerden enthalten sie einen optionalen Genauigkeitsbezeichner, der angibt, wie viele Stellen in der Ergebniszeichenfolge angezeigt werden. Wenn der Genauigkeitsbezeichner nicht angegeben oder nicht unterstützt wird, entspricht ein Standardformatbezeichner einer Standardformatzeichenfolge. 

.NET definiert einen Satz von Standardformatbezeichnern für alle numerischen Typen, alle Datums- und Uhrzeittypen und alle Enumerationstypen. Beispielsweise definieren die einzelnen Kategorien den Standardformatbezeichner "G", der eine allgemeine Zeichenfolgendarstellung für einen Wert dieses Typs definiert.

Standardformatzeichenfolgen für Enumerationstypen steuern die Zeichenfolgendarstellung eines Werts direkt. Die an die [ToString](xref:System.Object.ToString)-Methode eines Enumerationswerts übergebenen Formatzeichenfolgen bestimmen, ob der Wert mit seinem Zeichenfolgennamen (Formatbezeichner „G“ und „F“), seinem zugrunde liegenden ganzzahligen Wert (Formatbezeichner „D“) oder seinem Hexadezimalwert (Formatbezeichner „X“) angezeigt wird. Das folgende Beispiel veranschaulicht die Verwendung von Standardformatzeichenfolgen zum Formatieren eines [DayOfWeek](xref:System.DayOfWeek)-Enumerationswerts. 

```csharp
DayOfWeek thisDay = DayOfWeek.Monday;
string[] formatStrings = {"G", "F", "D", "X"};

foreach (string formatString in formatStrings)
   Console.WriteLine(thisDay.ToString(formatString));
// The example displays the following output:
//       Monday
//       Monday
//       1
//       00000001
```

```vb
Dim thisDay As DayOfWeek = DayOfWeek.Monday
Dim formatStrings() As String = {"G", "F", "D", "X"}

For Each formatString As String In formatStrings
   Console.WriteLine(thisDay.ToString(formatString))
Next
' The example displays the following output:
'       Monday
'       Monday
'       1
'       00000001
```

Weitere Informationen über Enumerationsformatzeichenfolgen finden Sie unter [Enumerationsformatzeichenfolgen](enumeration-format.md).

Standardformatzeichenfolgen für numerische Typen definieren normalerweise eine Ergebniszeichenfolge, deren genaue Darstellung von einem oder mehreren Eigenschaftswerten gesteuert wird. Beispielsweise formatiert der Formatbezeichner "C" eine Zahl als Währungswert. Wenn Sie die [ToString](xref:System.Object.ToString)-Methode mit dem Formatbezeichner „C“ als einzigem Parameter aufrufen, werden die folgenden Eigenschaftswerte des [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekts der aktuellen Kultur verwendet, um die Zeichenfolgendarstellung des numerischen Werts zu definieren:

* Die [CurrencySymbol](xref:System.Globalization.NumberFormatInfo.CurrencySymbol)-Eigenschaft, die das Währungssymbol der aktuellen Kultur angibt.

* Die [CurrencyNegativePattern](xref:System.Globalization.NumberFormatInfo.CurrencyNegativePattern)- oder [CurrencyPositivePattern](xref:System.Globalization.NumberFormatInfo.CurrencyPositivePattern)-Eigenschaft, die eine Ganzzahl zurückgibt, die Folgendes bestimmt: 

    * Die Platzierung des Währungssymbols.
    
    * Ob negative Werte durch ein führendes negatives Vorzeichen, ein nachfolgendes negatives Vorzeichen oder durch Klammern angegeben werden.
    
    * Ob zwischen dem numerischen Wert und dem Währungssymbol ein Leerzeichen angezeigt wird.
    
* Die [CurrencyDecimalDigits](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits)-Eigenschaft, die die Anzahl der Dezimalstellen in der Ergebniszeichenfolge definiert.

* Die [CurrencyDecimalSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator)-Eigenschaft, die das Dezimaltrennzeichen in der Ergebniszeichenfolge definiert.

* Die [CurrencyGroupSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator)-Eigenschaft, die das Gruppentrennzeichen definiert.

* Die [CurrencyGroupSizes](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSizes)-Eigenschaft, die in jeder Gruppe die Anzahl der Stellen links vom Dezimaltrennzeichen definiert.

* Die [NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign)-Eigenschaft, die das negative Vorzeichen bestimmt, das in der Ergebniszeichenfolge verwendet wird, wenn negative Werte nicht mit Klammern angegeben werden.

Darüber hinaus enthalten numerische Formatzeichenfolgen möglicherweise einen Genauigkeitsbezeichner. Die Bedeutung dieses Bezeichners ist abhängig von der Formatzeichenfolge, mit der er verwendet wird. In aller Regel wird dadurch jedoch entweder die Gesamtzahl der Stellen oder die Anzahl der Dezimalstellen angegeben, die in der Ergebniszeichenfolge erscheinen soll. So werden im folgenden Beispiel die numerische Standardzeichenfolge "X4" sowie ein Genauigkeitsbezeichner angegeben, um einen Zeichenfolgenwert mit vier Hexadezimalzahlen zu erstellen.

```csharp
byte[] byteValues = { 12, 163, 255 };
foreach (byte byteValue in byteValues)
   Console.WriteLine(byteValue.ToString("X4"));
// The example displays the following output:
//       000C
//       00A3
//       00FF
```

```vb
Dim byteValues() As Byte = { 12, 163, 255 }
For Each byteValue As Byte In byteValues
   Console.WriteLine(byteValue.ToString("X4"))
Next
' The example displays the following output:
'       000C
'       00A3
'       00FF
```

Weitere Informationen zu Standard-Zahlenformatzeichenfolgen finden Sie unter [Standard-Zahlenformatzeichenfolgen](standard-numeric.md). 

Standardformatzeichenfolgen für Datums- und Uhrzeitwerte sind Aliase für benutzerdefinierte Formatzeichenfolgen, die von einer bestimmten [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Klasse gespeichert werden. Beispielsweise werden durch Aufrufen der [ToString](xref:System.Object.ToString)-Methode eines Datums- und Uhrzeitwerts mit dem Formatbezeichner „D“ das Datum und die Uhrzeit mit der benutzerdefinierten Formatzeichenfolge angezeigt, die in der [DateTimeFormatInfo.LongDatePattern](xref:System.Globalization.DateTimeFormatInfo.LongDatePattern)-Eigenschaft der aktuellen Kultur gespeichert ist. (Weitere Informationen zu benutzerdefinierten Formatzeichenfolgen finden Sie im Abschnitt [Benutzerdefinierte Formatzeichenfolgen](#custom-format-strings).) Diese Beziehung wird anhand des folgenden Beispiels veranschaulicht.

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      DateTime date1 = new DateTime(2017, 6, 30);
      Console.WriteLine("D Format Specifier:     {0:D}", date1);
      string longPattern = CultureInfo.CurrentCulture.DateTimeFormat.LongDatePattern;
      Console.WriteLine("'{0}' custom format string:     {1}", 
                        longPattern, date1.ToString(longPattern));
   }
}
// The example displays the following output when run on a system whose
// current culture is en-US:
//    D Format Specifier:     Tuesday, June 30, 2017
//    'dddd, MMMM dd, yyyy' custom format string:     Tuesday, June 30, 2017
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim date1 As Date = #6/30/2009#
      Console.WriteLine("D Format Specifier:     {0:D}", date1)
      Dim longPattern As String = CultureInfo.CurrentCulture.DateTimeFormat.LongDatePattern
      Console.WriteLine("'{0}' custom format string:     {1}", _
                        longPattern, date1.ToString(longPattern))
   End Sub
End Module
' The example displays the following output when run on a system whose
' current culture is en-US:
'    D Format Specifier:     Tuesday, June 30, 2009
'    'dddd, MMMM dd, yyyy' custom format string:     Tuesday, June 30, 2009
```

Weitere Informationen zu Standard-Zahlenformatzeichenfolgen finden Sie unter [Standardformatzeichenfolgen für Datum und Uhrzeit](standard-datetime.md).

Sie können Standardformatzeichenfolgen auch verwenden, um die Zeichenfolgendarstellung eines anwendungsdefinierten Objekts anzugeben, die von der `ToString(String)`-Methode des Objekts erstellt wird. Sie können die spezifischen Standardformatbezeichner definieren, die von dem Objekt unterstützt werden, und Sie können angeben, ob die Groß- und Kleinschreibung beachtet werden soll. Ihre Implementierung der `ToString(String)`-Methode sollte Folgendes unterstützen:

* Den Formatbezeichner "G", der ein übliches oder allgemeines Format des Objekts darstellt. Die parameterlose Überladung der `ToString`-Methode des Objekts sollte die zugehörige `ToString(String)`-Überladung aufrufen und die Standardformatzeichenfolge "G" übergeben.

* Unterstützung für einen Formatbezeichner, der gleich einem NULL-Verweis ist. Ein Formatbezeichner, der gleich einem NULL-Verweis ist, sollte als äquivalent mit dem "G"-Formatbezeichner angesehen werden.

Beispielsweise kann eine `Temperature`-Klasse die Temperatur in Grad Celsius intern speichern und Formatbezeichner verwenden, um den Wert des `Temperature`-Objekts in Grad Celsius, Grad Fahrenheit und Kelvin darzustellen. Dies wird im folgenden Beispiel veranschaulicht.

```csharp
using System;

public class Temperature
{
   private decimal m_Temp;

   public Temperature(decimal temperature)
   {
      this.m_Temp = temperature;
   }

   public decimal Celsius
   {
      get { return this.m_Temp; }
   }

   public decimal Kelvin
   {
      get { return this.m_Temp + 273.15m; }   
   }

   public decimal Fahrenheit
   {
      get { return Math.Round(((decimal) (this.m_Temp * 9 / 5 + 32)), 2); }
   }

   public override string ToString()
   {
      return this.ToString("C");
   }

   public string ToString(string format)
   {  
      // Handle null or empty string.
      if (String.IsNullOrEmpty(format)) format = "C";
      // Remove spaces and convert to uppercase.
      format = format.Trim().ToUpperInvariant();      

      // Convert temperature to Fahrenheit and return string.
      switch (format)
      {
         // Convert temperature to Fahrenheit and return string.
         case "F":
            return this.Fahrenheit.ToString("N2") + " °F";
         // Convert temperature to Kelvin and return string.
         case "K":
            return this.Kelvin.ToString("N2") + " K";
         // return temperature in Celsius.
         case "G":
         case "C":
            return this.Celsius.ToString("N2") + " °C";
         default:
            throw new FormatException(String.Format("The '{0}' format string is not supported.", format));
      }      
   }
}

public class Example
{
   public static void Main()
   {
      Temperature temp1 = new Temperature(0m);
      Console.WriteLine(temp1.ToString());
      Console.WriteLine(temp1.ToString("G"));
      Console.WriteLine(temp1.ToString("C"));
      Console.WriteLine(temp1.ToString("F"));
      Console.WriteLine(temp1.ToString("K"));

      Temperature temp2 = new Temperature(-40m);
      Console.WriteLine(temp2.ToString());
      Console.WriteLine(temp2.ToString("G"));
      Console.WriteLine(temp2.ToString("C"));
      Console.WriteLine(temp2.ToString("F"));
      Console.WriteLine(temp2.ToString("K"));

      Temperature temp3 = new Temperature(16m);
      Console.WriteLine(temp3.ToString());
      Console.WriteLine(temp3.ToString("G"));
      Console.WriteLine(temp3.ToString("C"));
      Console.WriteLine(temp3.ToString("F"));
      Console.WriteLine(temp3.ToString("K"));

      Console.WriteLine(String.Format("The temperature is now {0:F}.", temp3));
   }
}
// The example displays the following output:
//       0.00 °C
//       0.00 °C
//       0.00 °C
//       32.00 °F
//       273.15 K
//       -40.00 °C
//       -40.00 °C
//       -40.00 °C
//       -40.00 °F
//       233.15 K
//       16.00 °C
//       16.00 °C
//       16.00 °C
//       60.80 °F
//       289.15 K
//       The temperature is now 16.00 °C.
```

```vb
Public Class Temperature
   Private m_Temp As Decimal

   Public Sub New(temperature As Decimal)
      Me.m_Temp = temperature
   End Sub

   Public ReadOnly Property Celsius() As Decimal
      Get
         Return Me.m_Temp
      End Get   
   End Property

   Public ReadOnly Property Kelvin() As Decimal
      Get
         Return Me.m_Temp + 273.15d   
      End Get
   End Property

   Public ReadOnly Property Fahrenheit() As Decimal
      Get
         Return Math.Round(CDec(Me.m_Temp * 9 / 5 + 32), 2)
      End Get      
   End Property

   Public Overrides Function ToString() As String
      Return Me.ToString("C")
   End Function

   Public Overloads Function ToString(format As String) As String  
      ' Handle null or empty string.
      If String.IsNullOrEmpty(format) Then format = "C"
      ' Remove spaces and convert to uppercase.
      format = format.Trim().ToUpperInvariant()      

      Select Case format
         Case "F"
           ' Convert temperature to Fahrenheit and return string.
            Return Me.Fahrenheit.ToString("N2") & " °F"
         Case "K"
            ' Convert temperature to Kelvin and return string.
            Return Me.Kelvin.ToString("N2") & " K"
         Case "C", "G"
            ' Return temperature in Celsius.
            Return Me.Celsius.ToString("N2") & " °C"
         Case Else
            Throw New FormatException(String.Format("The '{0}' format string is not supported.", format))
      End Select      
   End Function
End Class

Public Module Example
   Public Sub Main()
      Dim temp1 As New Temperature(0d)
      Console.WriteLine(temp1.ToString())
      Console.WriteLine(temp1.ToString("G"))
      Console.WriteLine(temp1.ToString("C"))
      Console.WriteLine(temp1.ToString("F"))
      Console.WriteLine(temp1.ToString("K"))

      Dim temp2 As New Temperature(-40d)
      Console.WriteLine(temp2.ToString())
      Console.WriteLine(temp2.ToString("G"))
      Console.WriteLine(temp2.ToString("C"))
      Console.WriteLine(temp2.ToString("F"))
      Console.WriteLine(temp2.ToString("K"))

      Dim temp3 As New Temperature(16d)
      Console.WriteLine(temp3.ToString())
      Console.WriteLine(temp3.ToString("G"))
      Console.WriteLine(temp3.ToString("C"))
      Console.WriteLine(temp3.ToString("F"))
      Console.WriteLine(temp3.ToString("K"))

      Console.WriteLine(String.Format("The temperature is now {0:F}.", temp3))
   End Sub
End Module
' The example displays the following output:
'       0.00 °C
'       0.00 °C
'       0.00 °C
'       32.00 °F
'       273.15 K
'       -40.00 °C
'       -40.00 °C
'       -40.00 °C
'       -40.00 °F
'       233.15 K
'       16.00 °C
'       16.00 °C
'       16.00 °C
'       60.80 °F
'       289.15 K
'       The temperature is now 16.00 °C.
```

### <a name="custom-format-strings"></a>Benutzerdefinierte Formatzeichenfolgen

Zusätzlich zu den Standardformatzeichenfolgen definiert .NET benutzerdefinierte Formatzeichenfolgen für numerische Werte und Datums- und Uhrzeitwerte. Eine benutzerdefinierte Formatzeichenfolge besteht aus einem oder mehreren benutzerdefinierten Formatbezeichnern, die die Zeichenfolgendarstellung eines Werts definieren. Beispielsweise konvertiert die benutzerdefinierte Datums- und Uhrzeitformatzeichenfolge "yyyy/mm/dd hh:mm:ss.ffff t zzz" ein Datum für die Kultur en-US wie folgt in die entsprechende Zeichenfolgendarstellung: "2008/11/15 07:45:00.0000 P -08:00". Analog konvertiert die benutzerdefinierte Formatzeichenfolge "0000" den ganzzahligen Wert 12 in "0012". Eine vollständige Liste benutzerdefinierter Formatzeichenfolgen finden Sie unter [Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit](custom-datetime.md) und [Benutzerdefinierte Zahlenformatzeichenfolgen](custom-numeric.md).

Wenn eine Formatzeichenfolge aus einem einzelnen benutzerdefinierten Formatbezeichner besteht, sollte dem Formatbezeichner das Prozentsymbol (%) vorangestellt werden, um Verwechslungen mit einem Standardformatbezeichner zu vermeiden. Im folgenden Beispiel wird der benutzerdefinierte Formatbezeichner "M" verwendet, um eine einstellige oder zweistellige Ziffer für einen bestimmten Tag des Monats anzuzeigen.

```csharp
DateTime date1 = new DateTime(2009, 9, 8);
Console.WriteLine(date1.ToString("%M"));       
// Displays 9
```

```vb
Dim date1 As Date = #09/08/2009#
Console.WriteLine(date1.ToString("%M"))      ' Displays 9
```

Viele Standardformatzeichenfolgen für Datums- und Uhrzeitwerte sind Aliase für benutzerdefinierte Formatzeichenfolgen, die von Eigenschaften des [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekts definiert werden. Benutzerdefinierte Formatzeichenfolgen ermöglichen außerdem eine hohe Flexibilität beim Bereitstellen von anwendungsdefinierter Formatierung für numerische Werte oder Datums- und Uhrzeitwerte. Sie können eigene benutzerdefinierte Ergebniszeichenfolgen für numerische Werte und für Datums- und Uhrzeitwerte definieren, indem Sie mehrere benutzerdefinierte Formatbezeichner zu einer einzelnen benutzerdefinierten Formatzeichenfolge kombinieren. Im folgenden Beispiel wird eine benutzerdefinierte Formatzeichenfolge definiert, die im Anschluss an den Namen des Monats, den Tag und das Jahr den Tag der Woche in Klammern anzeigt.

```csharp
string customFormat = "MMMM dd, yyyy (dddd)";
DateTime date1 = new DateTime(2009, 8, 28);
Console.WriteLine(date1.ToString(customFormat));   
// The example displays the following output if run on a system
// whose language is English:
//       August 28, 2009 (Friday) 
```

```vb
Dim customFormat As String = "MMMM dd, yyyy (dddd)"
Dim date1 As Date = #8/28/2009#
Console.WriteLine(date1.ToString(customFormat))   
' The example displays the following output if run on a system
' whose language is English:
'       August 28, 2009 (Friday) 
```

Das folgende Beispiel definiert eine benutzerdefinierte Formatzeichenfolge, die einen [Int64](xref:System.Int64)-Wert als standardmäßige, siebenstellige US-Telefonnummer mit der Ortsvorwahl anzeigt. 

```csharp
using System;

public class Example
{
   public static void Main()
   {
      long number = 8009999999;
      string fmt = "000-000-0000";
      Console.WriteLine(number.ToString(fmt));
   }
}
// The example displays the following output:
//        800-999-9999
```

```vb
Module Example
   Public Sub Main()
      Dim number As Long = 8009999999
      Dim fmt As String = "000-000-0000"
      Console.WriteLine(number.ToString(fmt))
   End Sub
End Module
' The example displays the following output:

' The example displays the following output:
'       800-999-9999
```

Standardformatzeichenfolgen decken i. d. R. die meisten der Formatierungsanforderungen für anwendungsdefinierte Typen ab. Sie können jedoch auch benutzerdefinierte Formatbezeichner definieren, um Typen zu formatieren. 

### <a name="format-strings-and-net-types"></a>Formatzeichenfolgen und .NET-Typen

Alle numerischen Typen (also die Typen [Byte](xref:System.Byte), [Decimal](xref:System.Decimal), [Double](xref:System.Double), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [SByte](xref:System.SByte), [Single](xref:System.Single), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32), [UInt64](xref:System.UInt64) und [BigInteger](xref:System.Numerics.BigInteger)) sowie die Typen [DateTime](xref:System.DateTime), [DateTimeOffset](xref:System.DateTimeOffset), [TimeSpan](xref:System.TimeSpan) und [Guid](xref:System.Guid) und alle Enumerationstypen unterstützen die Formatierung mit Formatzeichenfolgen. Informationen zu bestimmten Formatzeichenfolgen, die von jedem Typ unterstützt werden, finden Sie in den folgenden Themen: 

Titel | Definition
----- | ----------
[Standard-Zahlenformatzeichenfolgen](standard-numeric.md) | Beschreibt als Standard verwendete Formatzeichenfolgen, mit denen häufig verwendete Zeichenfolgenentsprechungen von numerischen Werten erstellt werden. 
[Benutzerdefinierte Zahlenformatzeichenfolgen](custom-numeric.md) | Beschreibt benutzerdefinierte Formatzeichenfolgen, die anwendungsspezifische Formate für numerische Werte erstellen.
[Standardformatzeichenfolgen für Datum und Uhrzeit](standard-datetime.md) | Beschreibt als Standard verwendete Formatzeichenfolgen, mit denen häufig verwendete Zeichenfolgenentsprechungen von [DateTime](xref:System.DateTime)-Werten erstellt werden.
[Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit](custom-datetime.md) | Beschreibt benutzerdefinierte Formatzeichenfolgen, die anwendungsspezifische Formate für [DateTime](xref:System.DateTime)-Werte erstellen.
[TimeSpan-Standardformatzeichenfolgen](standard-timespan.md) | Beschreibt als Standard verwendete Formatzeichenfolgen, mit denen häufig verwendete Zeichenfolgenentsprechungen von Zeitintervallen erstellt werden.
[Benutzerdefinierte TimeSpan-Formatzeichenfolgen](custom-timespan.md) | Beschreibt benutzerdefinierte Formatzeichenfolgen, die anwendungsspezifische Formate für Zeitintervalle erstellen.
[Enumerationsformatzeichenfolgen](enumeration-format.md) | Beschreibt als Standard verwendete Formatzeichenfolgen, mit denen Zeichenfolgenentsprechungen von Enumerationswerten erstellt werden.
[Guid.ToString(String)](xref:System.Guid.ToString(System.String)) | Beschreibt Standardformatzeichenfolgen für [Guid](xref:System.Guid)-Werte.

## <a name="culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface"></a>Kulturabhängige Formatierung mit Formatanbietern und der IFormatProvider-Schnittstelle

Obwohl Sie mit Formatbezeichnern die Formatierung von Objekten anpassen können, sind für eine sinnvolle Zeichenfolgendarstellung von Objekten oft zusätzliche Formatierungsinformationen erforderlich. Beispielsweise ist für das Formatieren einer Zahl als Währungswert mit der Standardformatzeichenfolge "C" oder mit einer benutzerdefinierten Formatzeichenfolge wie "$ #,#.00" mindestens erforderlich, dass Informationen über das richtige Währungssymbol, das richtige Gruppentrennzeichen und das richtige Dezimaltrennzeichen verfügbar sind, um in die formatierte Zeichenfolge eingeschlossen zu werden. In .NET werden diese zusätzlichen Formatierungsinformationen durch die [IFormatProvider](xref:System.IFormatProvider)-Schnittstelle verfügbar gemacht. Diese wird als Parameter für eine oder mehrere Überladungen der `ToString`-Methode von numerischen Typen sowie von Datums- und Uhrzeittypen bereitgestellt. [IFormatProvider](xref:System.IFormatProvider)-Implementierungen werden in .NET verwendet, um eine kulturabhängige Formatierung zu unterstützen. Das folgende Beispiel veranschaulicht, wie sich die Zeichenfolgendarstellung eines Objekts ändert, wenn die Formatierung mit drei [IFormatProvider](xref:System.IFormatProvider)-Objekten erfolgt, die verschiedene Kulturen darstellen.

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      decimal value = 1603.42m;
      Console.WriteLine(value.ToString("C3", new CultureInfo("en-US")));
      Console.WriteLine(value.ToString("C3", new CultureInfo("fr-FR")));
      Console.WriteLine(value.ToString("C3", new CultureInfo("de-DE")));
   }
}
// The example displays the following output:
//       $1,603.420
//       1 603,420 €
//       1.603,420 €
```

```vb
Imports System.Globalization

Public Module Example
   Public Sub Main()
      Dim value As Decimal = 1603.42d
      Console.WriteLine(value.ToString("C3", New CultureInfo("en-US")))
      Console.WriteLine(value.ToString("C3", New CultureInfo("fr-FR")))
      Console.WriteLine(value.ToString("C3", New CultureInfo("de-DE")))
   End Sub
End Module
' The example displays the following output:
'       $1,603.420
'       1 603,420 €
'       1.603,420 €
```

Die [IFormatProvider](xref:System.IFormatProvider)-Schnittstelle enthält eine Methode: [GetFormat(Type)](xref:System.IFormatProvider.GetFormat(System.Type)). Diese weist einen einzigen Parameter auf, der den Typ des Objekts angibt, das Formatierungsinformationen bereitstellt. Wenn die Methode ein Objekt dieses Typs bereitstellen kann, wird dieses zurückgegeben. Andernfalls wird ein NULL-Verweis zurückgegeben.

[IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) ist eine Rückrufmethode. Wenn Sie eine `ToString`-Methodenüberladung aufrufen, die einen [IFormatProvider](xref:System.IFormatProvider)-Parameter enthält, wird die [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type))-Methode dieses [IFormatProvider](xref:System.IFormatProvider)-Objekts aufgerufen. Die [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type))-Methode ist dafür zuständig, ein Objekt zurückzugeben, das die notwendigen Formatierungsinformationen, wie vom *formatType*-Parameter angegeben, für die `ToString`-Methode bereitstellt. 

Eine Reihe von Formatierungs- oder Zeichenfolgenkonvertierungsmethoden enthalten einen Parameter vom Typ [IFormatProvider](xref:System.IFormatProvider). In vielen Fällen wird der Wert des Parameters beim Aufrufen der Methode jedoch ignoriert. In der folgenden Tabelle sind einige Formatierungsmethoden aufgeführt, die den Parameter und den Typ des [Type](xref:System.Type)-Objekts verwenden, das an die [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type))-Methode übergeben wird. 

Methode | Typ des *formatType*-Parameters
------ | ------------------------------
`ToString`-Methode für numerische Typen | [System.Globalization.NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)
`ToString`-Methode für Datums- und Uhrzeittypen | [System.Globalization.DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)
[String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) | [System.ICustomFormatter](xref:System.ICustomFormatter)
[StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)) | [System.ICustomFormatter](xref:System.ICustomFormatter)

.NET stellt drei Klassen bereit, die [IFormatProvider](xref:System.IFormatProvider) implementieren: 

* [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), eine Klasse, die Formatierungsinformationen für Datums- und Uhrzeitwerte für eine bestimmte Kultur bereitstellt. Die [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type))-Implementierung der Klasse gibt eine Instanz von sich selbst zurück.

* [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), eine Klasse, die numerische Formatierungsinformationen für eine bestimmte Kultur bereitstellt. Die [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type))-Implementierung der Klasse gibt eine Instanz von sich selbst zurück.

* [CultureInfo](xref:System.Globalization.CultureInfo). Die zugehörige [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type))-Implementierung kann ein [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekt zurückgeben, um numerische Formatierungsinformationen bereitzustellen, oder ein [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekt, um Formatierungsinformationen für Datums- und Uhrzeitwerte bereitzustellen. 

Sie können auch einen eigenen Formatanbieter implementieren, um eine dieser Klassen zu ersetzen. Die `GetFormat`-Methode Ihrer Implementierung muss jedoch ein Objekt eines in der vorangehenden Tabelle aufgeführten Typs zurückgeben, um Formatierungsinformationen für die `ToString`-Methode bereitzustellen.

### <a name="culture-sensitive-formatting-of-numeric-values"></a>Kulturabhängige Formatierung von numerischen Werten

Standardmäßig ist die Formatierung von numerischen Werten kulturabhängig. Wenn Sie beim Aufrufen einer Formatierungsmethode keine Kultur angeben, werden die Formatierungskonventionen der aktuellen Threadkultur verwendet. Dies wird im folgenden Beispiel veranschaulicht, das die aktuelle Threadkultur viermal ändert und anschließend die [Decimal.ToString(String)](xref:System.Decimal.ToString(System.String))-Methode aufruft. In allen Fällen gibt die Ergebniszeichenfolge die Formatierungskonventionen der aktuellen Kultur wieder. Dies liegt daran, dass die `ToString`- und `ToString(String)`-Methoden die Aufrufe der `ToString(String, IFormatProvider)`-Methode jedes numerischen Typs umschließen. 

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string[] cultureNames = { "en-US", "fr-FR", "es-MX", "de-DE" };
      Decimal value = 1043.17m;

      foreach (var cultureName in cultureNames) {
         // Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName);
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name);
         Console.WriteLine(value.ToString("C2"));
         Console.WriteLine();
      }   
   }
}
// The example displays the following output:
//       The current culture is en-US
//       $1,043.17
//       
//       The current culture is fr-FR
//       1 043,17 €
//       
//       The current culture is es-MX
//       $1,043.17
//       
//       The current culture is de-DE
//       1.043,17 €
```

```vb
Imports System.Globalization
Imports System.Threading 

Module Example
   Public Sub Main()
      Dim cultureNames() As String = { "en-US", "fr-FR", "es-MX", "de-DE" }
      Dim value As Decimal = 1043.17d 

      For Each cultureName In cultureNames
         ' Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName)
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name)
         Console.WriteLine(value.ToString("C2"))
         Console.WriteLine()
      Next                  
   End Sub
End Module
' The example displays the following output:
'       The current culture is en-US
'       $1,043.17
'       
'       The current culture is fr-FR
'       1 043,17 €
'       
'       The current culture is es-MX
'       $1,043.17
'       
'       The current culture is de-DE
'       1.043,17 €
```

Sie können einen numerischen Wert für eine bestimmte Kultur auch formatieren, indem Sie eine `ToString`-Überladung aufrufen, die einen *provider*-Parameter aufweist, und ihr eins der folgenden Objekte übergeben: 

* Ein [CultureInfo](xref:System.Globalization.CultureInfo)-Objekt, das die Kultur darstellt, deren Formatierungskonventionen verwendet werden sollen. Die zugehörige [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type))-Methode gibt den Wert der [CultureInfo.NumberFormat](xref:System.Globalization.CultureInfo.NumberFormat)-Eigenschaft zurück, bei der es sich um das [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekt handelt, das kulturspezifische Formatierungsinformationen für numerische Werte bereitstellt.

* Ein [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekt, das die kulturspezifischen Formatierungskonventionen definiert, die verwendet werden sollen. Die zugehörige [GetFormat](xref:System.Globalization.NumberFormatInfo.GetFormat(System.Type))-Methode gibt eine Instanz von sich selbst zurück.

Im folgenden Beispiel werden [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekte verwendet, die die Kulturen „Englisch (USA)“ und „Englisch (Großbritannien)“ sowie die neutralen Kulturen „Französisch“ und „Russisch“ darstellen, um eine Gleitkommazahl zu formatieren.

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {                                                                                                    
      Double value = 1043.62957;
      string[] cultureNames = { "en-US", "en-GB", "ru", "fr" };

      foreach (var name in cultureNames) {
         NumberFormatInfo nfi = CultureInfo.CreateSpecificCulture(name).NumberFormat;
         Console.WriteLine("{0,-6} {1}", name + ":", value.ToString("N3", nfi));
      }   
   }
}
// The example displays the following output:
//       en-US: 1,043.630
//       en-GB: 1,043.630
//       ru:    1 043,630
//       fr:    1 043,630
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim value As Double = 1043.62957
      Dim cultureNames() As String = { "en-US", "en-GB", "ru", "fr" }

      For Each name In cultureNames
         Dim nfi As NumberFormatInfo = CultureInfo.CreateSpecificCulture(name).NumberFormat
         Console.WriteLine("{0,-6} {1}", name + ":", value.ToString("N3", nfi))
      Next   
   End Sub
End Module
' The example displays the following output:
'       en-US: 1,043.630
'       en-GB: 1,043.630
'       ru:    1 043,630
'       fr:    1 043,630
```

### <a name="culture-sensitive-formatting-of-date-and-time-values"></a>Kulturabhängige Formatierung von Datums- und Uhrzeitwerten

Standardmäßig ist die Formatierung von Daten- und Uhrzeitwerten kulturabhängig. Wenn Sie beim Aufrufen einer Formatierungsmethode keine Kultur angeben, werden die Formatierungskonventionen der aktuellen Threadkultur verwendet. Dies wird im folgenden Beispiel veranschaulicht, das die aktuelle Threadkultur viermal ändert und anschließend die [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String))-Methode aufruft. In allen Fällen gibt die Ergebniszeichenfolge die Formatierungskonventionen der aktuellen Kultur wieder. Dies liegt daran, dass die Methoden [DateTime.ToString()](xref:System.DateTime.ToString), [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String)), [DateTimeOffset.ToString()](xref:System.DateTimeOffset.ToString(System.String)) und [DateTimeOffset.ToString(String)](xref:System.DateTimeOffset.ToString(System.String)) Aufrufe der Methoden [DateTime.ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) und [DateTimeOffset.ToString(String, IFormatProvider)](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider)) umschließen.

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string[] cultureNames = { "en-US", "fr-FR", "es-MX", "de-DE" };
      DateTime dateToFormat = new DateTime(2012, 5, 28, 11, 30, 0);

      foreach (var cultureName in cultureNames) {
         // Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName);
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name);
         Console.WriteLine(dateToFormat.ToString("F"));
         Console.WriteLine();
      }   
   }
}
// The example displays the following output:
//       The current culture is en-US
//       Monday, May 28, 2012 11:30:00 AM
//       
//       The current culture is fr-FR
//       lundi 28 mai 2012 11:30:00
//       
//       The current culture is es-MX
//       lunes, 28 de mayo de 2012 11:30:00 a.m.
//       
//       The current culture is de-DE
//       Montag, 28. Mai 2012 11:30:00
```

```vb
Imports System.Globalization
Imports System.Threading 

Module Example
   Public Sub Main()
      Dim cultureNames() As String = { "en-US", "fr-FR", "es-MX", "de-DE" }
      Dim dateToFormat As Date = #5/28/2012 11:30AM#

      For Each cultureName In cultureNames
         ' Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName)
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name)
         Console.WriteLine(dateToFormat.ToString("F"))
         Console.WriteLine()
      Next                  
   End Sub
End Module
' The example displays the following output:
'       The current culture is en-US
'       Monday, May 28, 2012 11:30:00 AM
'       
'       The current culture is fr-FR
'       lundi 28 mai 2012 11:30:00
'       
'       The current culture is es-MX
'       lunes, 28 de mayo de 2012 11:30:00 a.m.
'       
'       The current culture is de-DE
'       Montag, 28. Mai 2012 11:30:00
```

Sie können einen Datums- und Uhrzeitwert für eine bestimmte Kultur auch formatieren, indem Sie eine [DateTime.ToString](xref:System.DateTime.ToString(System.String,System.IFormatProvider))- oder [DateTimeOffset.ToString](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider))-Überladung aufrufen, die einen provider-Parameter aufweist, und ihr eins der folgenden Objekte übergeben: 

* Ein [CultureInfo](xref:System.Globalization.CultureInfo)-Objekt, das die Kultur darstellt, deren Formatierungskonventionen verwendet werden sollen. Die zugehörige [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type))-Methode gibt den Wert der [CultureInfo.NumberFormat](xref:System.Globalization.CultureInfo.NumberFormat)-Eigenschaft zurück, bei der es sich um das [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekt handelt, das kulturspezifische Formatierungsinformationen für numerische Werte bereitstellt.

* Ein [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekt, das die kulturspezifischen Formatierungskonventionen definiert, die verwendet werden sollen. Die zugehörige [GetFormat](xref:System.Globalization.DateTimeFormatInfo.GetFormat(System.Type))-Methode gibt eine Instanz von sich selbst zurück.

Im folgenden Beispiel werden [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekte verwendet, die die Kulturen „Englisch (USA)“ und „Englisch (Großbritannien)“ sowie die neutralen Kulturen „Französisch“ und „Russisch“ darstellen, um ein Datum zu formatieren. 

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {                                                                                                    
      DateTime dat1 = new DateTime(2012, 5, 28, 11, 30, 0);
      string[] cultureNames = { "en-US", "en-GB", "ru", "fr" };

      foreach (var name in cultureNames) {
         DateTimeFormatInfo dtfi = CultureInfo.CreateSpecificCulture(name).DateTimeFormat;
         Console.WriteLine("{0}: {1}", name, dat1.ToString(dtfi));
      }   
   }
}
// The example displays the following output:
//       en-US: 5/28/2012 11:30:00 AM
//       en-GB: 28/05/2012 11:30:00
//       ru: 28.05.2012 11:30:00
//       fr: 28/05/2012 11:30:00
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim dat1 As Date = #5/28/2012 11:30AM#
      Dim cultureNames() As String = { "en-US", "en-GB", "ru", "fr" }

      For Each name In cultureNames
         Dim dtfi As DateTimeFormatInfo = CultureInfo.CreateSpecificCulture(name).DateTimeFormat
         Console.WriteLine("{0}: {1}", name, dat1.ToString(dtfi))
      Next   
   End Sub
End Module
' The example displays the following output:
'       en-US: 5/28/2012 11:30:00 AM
'       en-GB: 28/05/2012 11:30:00
'       ru: 28.05.2012 11:30:00
'       fr: 28/05/2012 11:30:00
```

## <a name="the-iformattable-interface"></a>IFormattable-Schnittstelle

Typen, die die `ToString`-Methode mit einer Formatzeichenfolge und einem [IFormatProvider](xref:System.IFormatProvider)-Parameter überladen, implementieren üblicherweise auch die [IFormattable](xref:System.IFormattable)-Schnittstelle. Diese Schnittstelle verfügt über einen einzelnen Member, [IFormattable.ToString(String, IFormatProvider)](xref:System.IFormattable.ToString(System.String,System.IFormatProvider)), der sowohl eine Formatzeichenfolge als auch einen Formatanbieter als Parameter enthält.

Das Implementieren der [IFormattable](xref:System.IFormattable)-Schnittstelle für die anwendungsdefinierte Klasse bietet zwei Vorteile: 

* Unterstützung der Zeichenfolgenkonvertierung durch die [Convert](xref:System.Convert)-Klasse. Aufrufe der Methoden [Convert.ToString(Object)](xref:System.Convert.ToString(System.Object)) und [Convert.ToString(Object, IFormatProvider)](xref:System.Convert.ToString(System.Object,System.IFormatProvider)) rufen automatisch Ihre [IFormattable](xref:System.IFormattable)-Implementierung auf.

* Unterstützung für kombinierte Formatierung. Wenn ein Formatelement, das eine Formatzeichenfolge enthält, verwendet wird, um den benutzerdefinierten Typ zu formatieren, ruft die Common Language Runtime automatisch Ihre [IFormattable](xref:System.IFormattable)-Implementierung auf und übergibt die Formatzeichenfolge. Weitere Informationen zur zusammengesetzten Formatierung mit Methoden wie `String.Format` oder `Console.WriteLine` finden Sie im Abschnitt [Zusammengesetzte Formatierung](#composite-formatting).

Im folgenden Beispiel wird eine `Temperature`-Klasse definiert, die die [IFormattable](xref:System.IFormattable)-Schnittstelle implementiert. Die Formatbezeichner "C" oder "G" werden darin unterstützt, um die Temperatur in Celsius anzuzeigen, der Formatbezeichner "F", um die Temperatur in Fahrenheit anzuzeigen, und der Formatbezeichner "KB", um die Temperatur in Kelvin anzuzeigen.

```csharp
using System;
using System.Globalization;

public class Temperature : IFormattable
{
   private decimal m_Temp;

   public Temperature(decimal temperature)
   {
      this.m_Temp = temperature;
   }

   public decimal Celsius
   {
      get { return this.m_Temp; }
   }

   public decimal Kelvin
   {
      get { return this.m_Temp + 273.15m; }   
   }

   public decimal Fahrenheit
   {
      get { return Math.Round((decimal) this.m_Temp * 9 / 5 + 32, 2); }
   }

   public override string ToString()
   {
      return this.ToString("G", null);
   }

   public string ToString(string format)
   {
      return this.ToString(format, null);
   }

   public string ToString(string format, IFormatProvider provider)  
   {
      // Handle null or empty arguments.
      if (String.IsNullOrEmpty(format)) format = "G";
      // Remove any white space and convert to uppercase.
      format = format.Trim().ToUpperInvariant();

      if (provider == null) provider = NumberFormatInfo.CurrentInfo;

      switch (format)
      {
         // Convert temperature to Fahrenheit and return string.
         case "F":
            return this.Fahrenheit.ToString("N2", provider) + "°F";
         // Convert temperature to Kelvin and return string.
         case "K":
            return this.Kelvin.ToString("N2", provider) + "K";
         // Return temperature in Celsius.
         case "C":
         case "G":
            return this.Celsius.ToString("N2", provider) + "°C";
         default:
            throw new FormatException(String.Format("The '{0}' format string is not supported.", format));
      }      
   }
}
```

```vb
Imports System.Globalization

Public Class Temperature : Implements IFormattable
   Private m_Temp As Decimal

   Public Sub New(temperature As Decimal)
      Me.m_Temp = temperature
   End Sub

   Public ReadOnly Property Celsius() As Decimal
      Get
         Return Me.m_Temp
      End Get   
   End Property

   Public ReadOnly Property Kelvin() As Decimal
      Get
         Return Me.m_Temp + 273.15d   
      End Get
   End Property

   Public ReadOnly Property Fahrenheit() As Decimal
      Get
         Return Math.Round(CDec(Me.m_Temp * 9 / 5 + 32), 2)
      End Get      
   End Property

   Public Overrides Function ToString() As String
      Return Me.ToString("G", Nothing)
   End Function

   Public Overloads Function ToString(format As String) As String
      Return Me.ToString(format, Nothing)
   End Function

   Public Overloads Function ToString(format As String, provider As IFormatProvider) As String _  
      Implements IFormattable.ToString

      ' Handle null or empty arguments.
      If String.IsNullOrEmpty(format) Then format = "G"
      ' Remove any white space and convert to uppercase.
      format = format.Trim().ToUpperInvariant()

      If provider Is Nothing Then provider = NumberFormatInfo.CurrentInfo

      Select Case format
         ' Convert temperature to Fahrenheit and return string.
         Case "F"
            Return Me.Fahrenheit.ToString("N2", provider) & "°F"
         ' Convert temperature to Kelvin and return string.
         Case "K"
            Return Me.Kelvin.ToString("N2", provider) & "K"
         ' Return temperature in Celsius.
         Case "C", "G"
            Return Me.Celsius.ToString("N2", provider) & "°C"
         Case Else
            Throw New FormatException(String.Format("The '{0}' format string is not supported.", format))
      End Select      
   End Function
End Class
```

Im folgenden Beispiel wird ein `Temperature`-Objekt instanziiert. Anschließend wird die [ToString](xref:System.Convert.ToString(System.Object,System.IFormatProvider))-Methode aufgerufen, und es werden mehrere zusammengesetzte Formatzeichenfolgen verwendet, um andere Zeichenfolgendarstellungen eines `Temperature`-Objekts zu erhalten. Die einzelnen Methoden rufen jeweils die [IFormattable](xref:System.IFormattable)-Implementierung der `Temperature`-Klasse auf.

```csharp
public class Example
{
   public static void Main()
   {
      Temperature temp1 = new Temperature(22m);
      Console.WriteLine(Convert.ToString(temp1, new CultureInfo("ja-JP")));
      Console.WriteLine("Temperature: {0:K}", temp1);
      Console.WriteLine("Temperature: {0:F}", temp1);
      Console.WriteLine(String.Format(new CultureInfo("fr-FR"), "Temperature: {0:F}", temp1));
   }
}
// The example displays the following output:
//       22.00°C
//       Temperature: 295.15°K
//       Temperature: 71.60°F
//       Temperature: 71,60°F
```

```vb
Public Module Example
   Public Sub Main()
      Dim temp1 As New Temperature(22d)
      Console.WriteLine(Convert.ToString(temp1, New CultureInfo("ja-JP")))
      Console.WriteLine("Temperature: {0:K}", temp1)
      Console.WriteLine("Temperature: {0:F}", temp1)
      Console.WriteLine(String.Format(New CultureInfo("fr-FR"), "Temperature: {0:F}", temp1)) 
   End Sub
End Module
' The example displays the following output:
'       22.00°C
'       Temperature: 295.15°K
'       Temperature: 71.60°F
'       Temperature: 71,60°F
```

## <a name="composite-formatting"></a>Kombinierte Formatierung

Einige Methoden wie `String.Format` und `StringBuilder.AppendFormat` unterstützen die kombinierte Formatierung. Eine kombinierte Formatzeichenfolge ist eine Vorlage, die verwendet wird, um eine einzelne Zeichenfolge zurückzugeben, die die Zeichenfolgendarstellung von 0 (null), einem oder mehreren Objekten beinhaltet. Jedes Objekt wird in der kombinierten Formatzeichenfolge durch ein indiziertes Formatelement dargestellt. Der Index des Formatelements entspricht der Position des Objekts, das es in der Parameterliste der Methode darstellt. Indizes sind nullbasiert. Beispielsweise wird im folgenden Aufruf der `String.Format`-Methode das erste Formatelement `{0:D}` durch die Zeichenfolgendarstellung von `thatDate` ersetzt. Das zweite Formatelement `{1}` wird durch die Zeichenfolgendarstellung `item1` ersetzt, und das dritte Formatelement `{2:C2}` wird durch die Zeichenfolgendarstellung von `item1.Value` ersetzt.

```csharp
result = String.Format("On {0:d}, the inventory of {1} was worth {2:C2}.", 
                       thatDate, item1, item1.Value);
Console.WriteLine(result);                            
// The example displays output like the following if run on a system
// whose current culture is en-US:
//       On 5/1/2009, the inventory of WidgetA was worth $107.44.
```

```vb
result = String.Format("On {0:d}, the inventory of {1} was worth {2:C2}.", _
                       thatDate, item1, item1.Value)
Console.WriteLine(result)                            
' The example displays output like the following if run on a system
' whose current culture is en-US:
'       On 5/1/2009, the inventory of WidgetA was worth $107.44.
```

Zusätzlich zum Ersetzen eines Formatelements durch die Zeichenfolgendarstellung seines entsprechenden Objekts können Sie mit Formatelementen auch Folgendes steuern: 

* Die spezifische Art, in der ein Objekt als Zeichenfolge dargestellt wird, wenn das Objekt die [IFormattable](xref:System.IFormattable)-Schnittstelle implementiert und Formatzeichenfolgen unterstützt. Zu diesem Zweck geben Sie nach dem Index des Formatelements einen Doppelpunkt (:) ein, gefolgt von einer gültigen Formatzeichenfolge. Im vorherigen Beispiel wurde hierzu ein Datumswert mit der Formatzeichenfolge „d“ (kurzes Datumsmuster) formatiert (z.B. `{0:d}`), und ein numerischer Wert wurde mit der Formatzeichenfolge „C2“ formatiert (z.B. `{2:C2}`, um die Zahl als Währungswert mit zwei Dezimalstellen darzustellen). 

* Die Breite des Felds, das die Zeichenfolgendarstellung des Objekts enthält, und die Ausrichtung der Zeichenfolgendarstellung in diesem Feld. Hierzu geben Sie nach dem Index des Formatelements ein Komma (,) ein, gefolgt von der Feldbreite. Die Zeichenfolge wird rechtsbündig in dem Feld ausgerichtet, wenn die Feldbreite ein positiver Wert ist, und linksbündig, wenn die Feldbreite ein negativer Wert ist. Im folgenden Beispiel werden Datumswerte in einem 20 Zeichen breiten Feld linksbündig ausgerichtet, und Dezimalwerte mit einer Hinterkommastelle werden in einem 11 Zeichen breiten Feld rechtsbündig ausgerichtet. 

```csharp
DateTime startDate = new DateTime(2015, 8, 28, 6, 0, 0);
decimal[] temps = { 73.452m, 68.98m, 72.6m, 69.24563m,
                   74.1m, 72.156m, 72.228m };
Console.WriteLine("{0,-20} {1,11}\n", "Date", "Temperature");
for (int ctr = 0; ctr < temps.Length; ctr++)
   Console.WriteLine("{0,-20:g} {1,11:N1}", startDate.AddDays(ctr), temps[ctr]);

// The example displays the following output:
//       Date                 Temperature
//
//       8/28/2015 6:00 AM           73.5
//       8/29/2015 6:00 AM           69.0
//       8/30/2015 6:00 AM           72.6
//       8/31/2015 6:00 AM           69.2
//       9/1/2015 6:00 AM            74.1
//       9/2/2015 6:00 AM            72.2
//       9/3/2015 6:00 AM            72.2
```

```vb
Dim startDate As New Date(2015, 8, 28, 6, 0, 0)
Dim temps() As Decimal = { 73.452, 68.98, 72.6, 69.24563,
                           74.1, 72.156, 72.228 }
Console.WriteLine("{0,-20} {1,11}", "Date", "Temperature")
Console.WriteLine()
For ctr As Integer = 0 To temps.Length - 1
   Console.WriteLine("{0,-20:g} {1,11:N1}", startDate.AddDays(ctr), temps(ctr))
Next
' The example displays the following output:
'       Date                 Temperature
'
'       8/28/2015 6:00 AM           73.5
'       8/29/2015 6:00 AM           69.0
'       8/30/2015 6:00 AM           72.6
'       8/31/2015 6:00 AM           69.2
'       9/1/2015 6:00 AM            74.1
'       9/2/2015 6:00 AM            72.2
'       9/3/2015 6:00 AM            72.2
```

Beachten Sie, dass, wenn sowohl die Ausrichtungszeichenfolge-Komponente als auch die Formatzeichenfolgen-Komponente vorhanden ist, die erste der letzteren vorausgeht (z. B. `{0,-20:g}`). 

Weitere Informationen zur zusammengesetzten Formatierung finden Sie unter [Zusammengesetzte Formatierung](composite-format.md).

## <a name="custom-formatting-with-icustomformatter"></a>Benutzerdefinierte Formatierung mit ICustomFormatter

Zwei zusammengesetzte Formatierungsmethoden, [String.Format(IFormatProvider, String, Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object[])) und [StringBuilder.AppendFormat(IFormatProvider, String, Object[])](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)), enthalten einen Parameter für den Formatanbieter, der eine benutzerdefinierte Formatierung unterstützt. Wenn eine dieser Formatierungsmethoden aufgerufen wird, übergibt sie ein [Type](xref:System.Type)-Objekt, das eine [ICustomFormatter](xref:System.ICustomFormatter)-Schnittstelle für die `GetFormat`-Methode des Formatanbieters darstellt. Die `GetFormat`-Methode ist dann dafür zuständig, die [ICustomFormatter](xref:System.ICustomFormatter)-Implementierung zurückzugeben, die die benutzerdefinierte Formatierung bereitstellt.

Die [ICustomFormatter](xref:System.ICustomFormatter)-Schnittstelle verfügt über eine einzelne Methode, [Format(String, Object, IFormatProvider)](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)), die von einer zusammengesetzten Formatierungsmethode automatisch einmal für jedes Formatelement in einer zusammengesetzten Formatzeichenfolge aufgerufen wird. Die [Format(String, Object, IFormatProvider)](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider))-Methode verfügt über drei Parameter: eine Formatzeichenfolge, die das *formatString*-Argument in einem Formatelement darstellt, ein Objekt zum Formatieren und ein [IFormatProvider](xref:System.IFormatProvider)-Objekt, das Formatierungsdienste bereitstellt. In der Regel implementiert die Klasse, die [ICustomFormatter](xref:System.ICustomFormatter) implementiert, auch [IFormatProvider](xref:System.IFormatProvider). Dieser letzte Parameter stellt daher einen Verweis auf die benutzerdefinierte Formatierungsklasse selbst dar. Die Methode gibt eine benutzerdefinierte formatierte Zeichenfolgendarstellung des Objekts zurück, das formatiert werden soll. Wenn die Methode das Objekt nicht formatieren kann, sollte ein NULL-Verweis zurückgegeben werden.

Im folgenden Beispiel wird eine [ICustomFormatter](xref:System.ICustomFormatter)-Implementierung mit dem Namen `ByteByByteFormatter` bereitgestellt, die ganzzahlige Werte als Sequenz von zweistelligen Hexadezimalwerten gefolgt von einem Leerzeichen anzeigt.

```csharp
public class ByteByByteFormatter : IFormatProvider, ICustomFormatter
{
   public object GetFormat(Type formatType)
   { 
      if (formatType == typeof(ICustomFormatter))
         return this;
      else
         return null;
   }

   public string Format(string format, object arg, 
                          IFormatProvider formatProvider)
   {   
      if (! formatProvider.Equals(this)) return null;

      // Handle only hexadecimal format string.
      if (! format.StartsWith("X")) return null;

      byte[] bytes;
      string output = null;

      // Handle only integral types.
      if (arg is Byte) 
         bytes = BitConverter.GetBytes((Byte) arg);
      else if (arg is Int16)
         bytes = BitConverter.GetBytes((Int16) arg);
      else if (arg is Int32)
         bytes = BitConverter.GetBytes((Int32) arg);
      else if (arg is Int64)   
         bytes = BitConverter.GetBytes((Int64) arg);
      else if (arg is SByte)
         bytes = BitConverter.GetBytes((SByte) arg);
      else if (arg is UInt16)
         bytes = BitConverter.GetBytes((UInt16) arg);
      else if (arg is UInt32)
         bytes = BitConverter.GetBytes((UInt32) arg);
      else if (arg is UInt64)
         bytes = BitConverter.GetBytes((UInt64) arg);
      else
         return null;

      for (int ctr = bytes.Length - 1; ctr >= 0; ctr--)
         output += String.Format("{0:X2} ", bytes[ctr]);   

      return output.Trim();
   }
}
```

```vb
Public Class ByteByByteFormatter : Implements IFormatProvider, ICustomFormatter
   Public Function GetFormat(formatType As Type) As Object _
                   Implements IFormatProvider.GetFormat
      If formatType Is GetType(ICustomFormatter) Then
         Return Me
      Else
         Return Nothing
      End If
   End Function

   Public Function Format(fmt As String, arg As Object, 
                          formatProvider As IFormatProvider) As String _
                          Implements ICustomFormatter.Format

      If Not formatProvider.Equals(Me) Then Return Nothing

      ' Handle only hexadecimal format string.
      If Not fmt.StartsWith("X") Then 
            Return Nothing
      End If

      ' Handle only integral types.
      If Not typeof arg Is Byte AndAlso
         Not typeof arg Is Int16 AndAlso
         Not typeof arg Is Int32 AndAlso
         Not typeof arg Is Int64 AndAlso
         Not typeof arg Is SByte AndAlso
         Not typeof arg Is UInt16 AndAlso
         Not typeof arg Is UInt32 AndAlso
         Not typeof arg Is UInt64 Then _
            Return Nothing

      Dim bytes() As Byte = BitConverter.GetBytes(arg)
      Dim output As String = Nothing

      For ctr As Integer = bytes.Length - 1 To 0 Step -1
         output += String.Format("{0:X2} ", bytes(ctr))   
      Next

      Return output.Trim()
   End Function
End Class
```

Im folgenden Beispiel werden mit der `ByteByByteFormatter`-Klasse Ganzzahlwerte formatiert. Beachten Sie, dass die [ICustomFormatter.Format](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider))-Methode im zweiten Aufruf der [String.Format(IFormatProvider, String, Object[])](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider))-Methode mehr als einmal aufgerufen wird und dass der [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Standardanbieter im dritten Methodenaufruf verwendet wird, da die `.ByteByByteFormatter.Format`-Methode die Formatzeichenfolge „N0“ nicht erkennt und einen NULL-Verweis zurückgibt.

```csharp
public class Example
{
   public static void Main()
   {
      long value = 3210662321; 
      byte value1 = 214;
      byte value2 = 19;

      Console.WriteLine(String.Format(new ByteByByteFormatter(), "{0:X}", value));
      Console.WriteLine(String.Format(new ByteByByteFormatter(), "{0:X} And {1:X} = {2:X} ({2:000})", 
                                      value1, value2, value1 & value2));                                
      Console.WriteLine(String.Format(new ByteByByteFormatter(), "{0,10:N0}", value));
   }
}
// The example displays the following output:
//       00 00 00 00 BF 5E D1 B1
//       00 D6 And 00 13 = 00 12 (018)
//       3,210,662,321
```

```vb
Public Module Example
   Public Sub Main()
      Dim value As Long = 3210662321 
      Dim value1 As Byte = 214
      Dim value2 As Byte = 19

      Console.WriteLine((String.Format(New ByteByByteFormatter(), "{0:X}", value)))
      Console.WriteLine((String.Format(New ByteByByteFormatter(), "{0:X} And {1:X} = {2:X} ({2:000})", 
                                      value1, value2, value1 And value2)))                                
      Console.WriteLine(String.Format(New ByteByByteFormatter(), "{0,10:N0}", value))
   End Sub
End Module
' The example displays the following output:
'       00 00 00 00 BF 5E D1 B1
'       00 D6 And 00 13 = 00 12 (018)
'       3,210,662,321
```

## <a name="related-topics"></a>Verwandte Themen

Titel | Definition
----- | ----------
[Standard-Zahlenformatzeichenfolgen](standard-numeric.md) | Beschreibt als Standard verwendete Formatzeichenfolgen, mit denen häufig verwendete Zeichenfolgenentsprechungen von numerischen Werten erstellt werden. 
[Benutzerdefinierte Zahlenformatzeichenfolgen](custom-numeric.md) | Beschreibt benutzerdefinierte Formatzeichenfolgen, die anwendungsspezifische Formate für numerische Werte erstellen.
[Standardformatzeichenfolgen für Datum und Uhrzeit](standard-datetime.md) |  Beschreibt als Standard verwendete Formatzeichenfolgen, mit denen häufig verwendete Zeichenfolgenentsprechungen von [DateTime](xref:System.DateTime)-Werten erstellt werden.
[Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit](custom-datetime.md) | Beschreibt benutzerdefinierte Formatzeichenfolgen, die anwendungsspezifische Formate für [DateTime](xref:System.DateTime)-Werte erstellen.
[TimeSpan-Standardformatzeichenfolgen](standard-timespan.md) | Beschreibt als Standard verwendete Formatzeichenfolgen, mit denen häufig verwendete Zeichenfolgenentsprechungen von Zeitintervallen erstellt werden.
[Benutzerdefinierte TimeSpan-Formatzeichenfolgen](custom-timespan.md) | Beschreibt benutzerdefinierte Formatzeichenfolgen, die anwendungsspezifische Formate für Zeitintervalle erstellen.
[Enumerationsformatzeichenfolgen](enumeration-format.md) | Beschreibt als Standard verwendete Formatzeichenfolgen, mit denen Zeichenfolgenentsprechungen von Enumerationswerten erstellt werden.
[Kombinierte Formatierung](composite-format.md) | Beschreibt die Einbettung eines oder mehrerer formatierter Werte in eine Zeichenfolge. Die Zeichenfolge kann anschließend in der Konsole angezeigt oder in einen Stream geschrieben werden.
[Durchführen von Formatierungsvorgängen](performing-formatting-operations.md) | Enthält Themen, in denen schrittweise Anleitungen zum Ausführen bestimmter Formatierungsvorgänge vorgestellt werden.
[Analysieren von Zeichenfolgen](parsing-strings.md) | Beschreibt, wie Objekte mit den Werten initialisiert werden, die durch Zeichenfolgenentsprechungen dieser Objekte beschrieben werden. Das Verarbeiten ist die Umkehroperation zum Formatieren.

## <a name="reference"></a>Verweis

[System.IFormattable](xref:System.IFormattable)

[System.IFormatProvider](xref:System.IFormatProvider)

[System.ICustomFormatter](xref:System.ICustomFormatter)

