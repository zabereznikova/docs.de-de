---
title: Zusammengesetzte Formatierung
description: Zusammengesetzte Formatierung
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/25/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: a01efc8f-c242-4535-bd32-acd0032d9590
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 15c549f5df0b6de8164e05f50855006996a47fac

---

# <a name="composite-formatting"></a>Zusammengesetzte Formatierung

Die Funktion für die kombinierte Formatierung in .NET verwendet als Eingabe eine Liste von Objekten und eine kombinierte Formatzeichenfolge. Eine kombinierte Formatzeichenfolge besteht aus festgelegtem Text mit indizierten Platzhaltern, so genannten Formatelementen, die den Objekten in der Liste entsprechen. Der Formatierungsvorgang liefert eine Ergebniszeichenfolge, die sich aus dem ursprünglichen festgelegten Text und der Zeichenfolgendarstellung der Objekte in der Liste zusammensetzt. 

Die Funktion für kombinierte Formatierung wird beispielsweise von folgenden Methoden unterstützt: 

* [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)), die eine formatierte Ergebniszeichenfolge zurückgibt. 

* [StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider, System.String, System.Object), die eine formatierte Ergebniszeichenfolge einem [StringBuilder](xref:System.Text.StringBuilder)-Objekt anfügt.

* Einige Überladungen der [Console](xref:System.Console)`WriteLine`-Methode, die eine formatierte Ergebniszeichenfolge in der Konsole anzeigen.  

* Einige Überladungen der [TextWriter](xref:System.IO.TextWriter)`WriteLine`-Methode, die die formatierte Ergebniszeichenfolge in einen Stream oder eine Datei schreiben. Die von [TextWriter](xref:System.IO.TextWriter) abgeleiteten Klassen, z.B. [StreamWriter](xref:System.IO.StreamWriter), verwenden auch diese Funktionen.

* [Debug.WriteLine(String, Object[])](xref:System.Diagnostics.Debug.WriteLine(System.String,System.Object[])), die eine formatierte Meldung an Ablaufverfolgungslistener ausgibt. 

* Die [Trace.TraceError(String, Object[])](xref:System.Diagnostics.Trace.TraceError(System.String,System.Object[]))-, [Trace.TraceInformation(String, Object[])](xref:System.Diagnostics.Trace.TraceInformation(System.String,System.Object[]))- und [Trace.TraceWarning(String, Object[])](xref:System.Diagnostics.Trace.TraceWarning(System.String,System.Object[]))-Methode, die formatierte Meldungen an Ablaufverfolgungslistener ausgeben. 

* Die [TraceSource.TraceInformation(String, Object[])](xref:System.Diagnostics.TraceSource.TraceInformation(System.String,System.Object[]))-Methode, die eine Informationsmethode in Ablaufverfolgungslistener schreibt. 

## <a name="composite-format-string"></a>Kombinierte Formatzeichenfolge

Eine kombinierte Formatzeichenfolge und eine Objektliste dienen als Argumente von Methoden, die das Feature für die kombinierte Formatierung unterstützen. Die Quellzeichenfolge besteht aus 0 (null) oder mehreren Einheiten festgelegten Texts mit mindestens einem Formatelement. Der festgelegte Text ist eine von Ihnen ausgewählte beliebige Zeichenfolge. Jedes Formatelement entspricht einem Objekt oder einer geschachtelten Struktur in der Liste. Die Funktion für die kombinierte Formatierung gibt eine neue Ergebniszeichenfolge zurück, in der jedes Formatelement durch die Zeichenfolgendarstellung des entsprechenden Objekts in der Liste ersetzt wird.

Berücksichtigen Sie das folgende [Format](xref:System.String.Format(System.String.Format(System.IFormatProvider,System.String,System.Object))-Codefragment.

```csharp
string name = "Fred";
String.Format("Name = {0}, hours = {1:hh}", name, DateTime.Now);
```

```vb
Dim name As String = "Fred"
String.Format("Name = {0}, hours = {1:hh}", name, DateTime.Now)
```

Der feste Text ist `"Name = "` und `", hours = "`. Die Formatelemente sind `"{0}"` mit dem Index 0, was dem Objekt `name` entspricht, und `"{1:hh}"` mit dem Index 1, was dem Objekt `DateTime.Now` entspricht.

## <a name="format-item-syntax"></a>Formatelementsyntax

Alle Formatelemente weisen die folgende Form auf und bestehen aus folgenden Komponenten:

__{__*Index*[,*Ausrichtung*][:*Formatzeichenfolge*]__}__

Die übereinstimmenden geschweiften Klammern ("{" and "}") sind erforderlich. 
 
### <a name="index-component"></a>Indexkomponente

Bei der obligatorischen Komponente *Index*, dem so genannten Parameterbezeichner, handelt es sich um eine bei 0 (null) beginnende Zahl, mit der ein entsprechendes Element in der Objektliste angegeben wird. Das bedeutet, dass das Formatelement mit dem Parameterbezeichner 0 (null) das erste Objekt in der Liste formatiert, und das Formatelement mit dem Parameterbezeichner 1 formatiert das zweite Objekt in der Liste usw. Das folgende Beispiel enthält vier von null bis drei nummerierte Parameterbezeichner zur Darstellung von Primzahlen, die kleiner als zehn sind: 

```csharp
string primes;
primes = String.Format("Prime numbers less than 10: {0}, {1}, {2}, {3}",
                       2, 3, 5, 7 );
Console.WriteLine(primes);
// The example displays the following output:
//      Prime numbers less than 10: 2, 3, 5, 7
```

```vb
Dim primes As String
primes = String.Format("Prime numbers less than 10: {0}, {1}, {2}, {3}",
                       2, 3, 5, 7 )
Console.WriteLine(primes)
' The example displays the following output:
'      Prime numbers less than 10: 2, 3, 5, 7
```

Mehrere Formatelemente können auf dasselbe Element in der Objektliste verweisen, indem derselbe Parameterbezeichner festgelegt wird. Sie können beispielsweise denselben numerischen Wert im hexadezimalen, im wissenschaftlichen und im Zahlenformat formatieren, indem Sie eine kombinierte Formatzeichenfolge wie z. B. "0x{0:X} {0:E} {0:N}" angeben, wie im folgenden Beispiel dargestellt. 

```csharp
string multiple = String.Format("0x{0:X} {0:E} {0:N}",
                                Int64.MaxValue);
Console.WriteLine(multiple);
// The example displays the following output:
//      0x7FFFFFFFFFFFFFFF 9.223372E+018 9,223,372,036,854,775,807.00
```

```vb
Dim multiple As String = String.Format("0x{0:X} {0:E} {0:N}",
                                       Int64.MaxValue)
Console.WriteLine(multiple)
' The example displays the following output:
'      0x7FFFFFFFFFFFFFFF 9.223372E+018 9,223,372,036,854,775,807.00
```

Jedes Formatelement kann auf ein beliebiges Objekt in der Liste verweisen. Wenn beispielsweise drei Objekte vorliegen, können Sie das zweite, erste und dritte Objekt formatieren, indem Sie eine kombinierte Formatzeichenfolge wie die Folgende angeben: "{1} {0} {2}". Ein Objekt, auf das kein Formatelement verweist, wird ignoriert. Eine [FormatException](xref:System.FormatException) wird zur Laufzeit ausgelöst, wenn ein Parameterbezeichner auf ein Element außerhalb der Grenzen der Objektliste verweist.

### <a name="alignment-component"></a>Ausrichtungskomponente

Bei der optionalen Komponente *Ausrichtung* handelt es sich um eine ganze Zahl mit Vorzeichen, die die gewünschte formatierte Feldbreite angibt. Wenn der Wert für *Ausrichtung* kleiner als die Länge der formatierten Zeichenfolge ist, wird *Ausrichtung* ignoriert, und die Länge der formatierten Zeichenfolge wird als Feldbreite verwendet. Die formatierten Daten im Feld werden bei einem positiven Wert für *Ausrichtung* rechtsbündig und bei einem negativen Wert für *Ausrichtung* linksbündig ausgerichtet. Wenn Füllzeichen erforderlich sind, werden Leerräume verwendet. Das Komma ist erforderlich, wenn *Ausrichtung* angegeben wird.

Im folgenden Beispiel werden zwei Arrays definiert, ein Array mit den Namen der Mitarbeiter und ein Array mit den Arbeitsstunden der Mitarbeiter über einen Zeitraum von zwei Wochen. Die kombinierte Formatzeichenfolge richtet die Namen in einem Feld mit 20 Zeichen linksbündig aus, und die Stunden werden in einem Feld mit 5 Zeichen rechtsbündig ausgerichtet. Beachten Sie, dass auch die Standardformatzeichenfolge "N1" verwendet wird, um die Stunden mit einer Dezimalstelle zu formatieren. 

```csharp
using System;

public class Example
{
   public static void Main()
   {
      string[] names = { "Adam", "Bridgette", "Carla", "Daniel",
                         "Ebenezer", "Francine", "George" };
      decimal[] hours = { 40, 6.667m, 40.39m, 82, 40.333m, 80,
                                 16.75m };

      Console.WriteLine("{0,-20} {1,5}\n", "Name", "Hours");
      for (int ctr = 0; ctr < names.Length; ctr++)
         Console.WriteLine("{0,-20} {1,5:N1}", names[ctr], hours[ctr]);

   }
}
// The example displays the following output:
//       Name                 Hours
//
//       Adam                  40.0
//       Bridgette              6.7
//       Carla                 40.4
//       Daniel                82.0
//       Ebenezer              40.3
//       Francine              80.0
//       George                16.8
```

```vb
Module Example
   Public Sub Main()
      Dim names() As String = { "Adam", "Bridgette", "Carla", "Daniel",
                                "Ebenezer", "Francine", "George" }
      Dim hours() As Decimal = { 40, 6.667d, 40.39d, 82, 40.333d, 80,
                                 16.75d }

      Console.WriteLine("{0,-20} {1,5}", "Name", "Hours")
      Console.WriteLine()
      For ctr As Integer = 0 To names.Length - 1
         Console.WriteLine("{0,-20} {1,5:N1}", names(ctr), hours(ctr))
      Next
   End Sub
End Module
' The example displays the following output:
'       Name                 Hours
'
'       Adam                  40.0
'       Bridgette              6.7
'       Carla                 40.4
'       Daniel                82.0
'       Ebenezer              40.3
'       Francine              80.0
'       George                16.8
```

### <a name="format-string-component"></a>Formatzeichenfolgen-Komponente

Die optionale Komponente *Formatzeichenfolge* ist eine Formatzeichenfolge, die für den formatierten Objekttyp geeignet ist. Geben Sie eine standardmäßige oder eine benutzerdefinierte numerische Formatzeichenfolge an, wenn das entsprechende Objekt ein numerischer Wert ist. Geben Sie eine standardmäßige oder eine benutzerdefinierte Formatvorlage für Datum und Uhrzeit an, wenn das entsprechende Objekt ein [DateTime](xref:System.DateTime)-Objekt ist. Geben Sie eine [Enumerations-Formatzeichenfolge](enumeration-format.md) an, wenn das entsprechende Objekt ein Enumerationswert ist. Wenn *Formatzeichenfolge* nicht festgelegt ist, wird der allgemeine Formatbezeichner („G“) für einen numerischen, Datums- und Uhrzeit- oder Enumerationstyp verwendet. Der Doppelpunkt ist erforderlich, wenn *Formatzeichenfolge* angegeben wird.

Die folgende Tabelle listet Typen oder Kategorien von Typen in der .NET Framework-Klassenbibliothek auf, die einen vordefinierten Satz von Formatzeichenfolgen unterstützen, und stellt Links zu Themen bereit, die die unterstützten Formatzeichenfolgen auflisten. Beachten Sie, dass die Zeichenfolgenformatierung ein erweiterbarer Mechanismus ist, der es ermöglicht, neue Formatzeichenfolgen für alle vorhandenen Typen zu definieren und einen Satz von Formatzeichenfolgen zu definieren, der von einem anwendungsdefinierten Typ unterstützt wird. Weitere Informationen finden Sie unter den Schnittstellenthemen [IFormattable](xref:System.IFormattable) und [ICustomFormatter](xref:System.ICustomFormatter). 

Typ oder Typkategorie | Siehe
--------------------- | ---
Datums- und Uhrzeittypen ([DateTime](xref:System.DateTime), [DateTimeOffset](xref:System.DateTimeOffset)) | [Standardformatzeichenfolgen für Datum und Uhrzeit](standard-datetime.md), [Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit](custom-datetime.md)
Enumerationstypen (alle Typen abgeleitet von [System.Enum](xref:System.Enum)) | [Enumerationsformatzeichenfolgen](enumeration-format.md)
Numerische Typen ([BigInteger](xref:System.Numerics.BigInteger), [Byte](xref:System.Byte), [Decimal](xref:System.Decimal), [Double](xref:System.Double), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [SByte](xref:System.SByte), [Single](xref:System.Single), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32), [UInt64](xref:System.UInt64)) | [Standard Numeric Format Strings](standard-numeric.md) (Standardmäßige numerische Formatzeichenfolgen), [Custom Numeric Format Strings](custom-numeric.md) (Benutzerdefinierte numerische Formatzeichenfolgen)
[Guid](xref:System.Guid) | [Guid.ToString(String)](xref:System.Guid.ToString(System.String))
[TimeSpan](xref:System.TimeSpan) | [Standard TimeSpan Format Strings](standard-timespan.md) (Standardmäßige TimeSpan-Formatzeichenfolgen), [Custom TimeSpan Format Strings](custom-timespan.md) (Benutzerdefinierte TimeSpan-Formatzeichenfolgen)

### <a name="escaping-braces"></a>Versehen von geschweiften Klammern mit Escapezeichen

Öffnende und schließende geschweifte Klammern werden als Beginn und Ende eines Formatelements interpretiert. Deshalb müssen Sie eine Escapesequenz verwenden, um eine literale öffnende bzw. schließende geschweifte Klammer anzuzeigen. Geben Sie zwei öffnende geschweifte Klammern ("{{") im festgelegten Text an, um eine öffnende geschweifte Klammer ("{") anzuzeigen, und geben Sie entsprechend zwei schließende geschweifte Klammern ("}}") an, um eine schließende geschweifte Klammer ("}") anzuzeigen. Geschweifte Klammern in einem Formatelement werden sequenziell in der Reihenfolge interpretiert, in der sie angetroffen werden. Die Interpretation geschachtelter geschweifter Klammern wird nicht unterstützt. 

Die Art und Weise, wie geschweifte Klammern mit Escapezeichen interpretiert werden, kann zu unerwarteten Ergebnissen führen. Im folgenden Beispiel gibt es das Formatelement "{{{0:D}}}", das eine öffnende geschweifte Klammer anzeigen soll, einen numerischen Wert, der als Dezimalzahl formatiert ist, und eine schließende geschweifte Klammer. Das Formatelement wird aber tatsächlich wie folgt interpretiert: 

1. Die ersten beiden öffnenden geschweiften Klammern ("{{") werden mit Escapezeichen versehen und ergeben eine öffnende geschweifte Klammer. 

2. Die nächsten drei Zeichen ("{0":) werden als Anfang eines Formatelements interpretiert.

3. Das nächste Zeichen ("D") wird als Formatbezeichner für das numerische Standarddezimalformat interpretiert, und die nächsten beiden geschweiften Klammern mit Escapezeichen ergeben eine einzelne geschweifte Klammer. Da die entstehende Zeichenfolge ("D}") kein numerischer Standardformatbezeichner ist, wird sie als benutzerdefinierte Formatzeichenfolge interpretiert, d. h., es wird die Literalzeichenfolge "D}" angezeigt. 

4. Die letzte geschweifte Klammer ("}") wird als Ende des Formatelements interpretiert. 

5. Das Endergebnis, das angezeigt wird, ist die Literalzeichenfolge "{D}". Der numerische Wert, der formatiert werden sollte, wird nicht angezeigt.

Eine Möglichkeit, Code zu schreiben und dabei Probleme mit falsch interpretierten geschweiften Klammern und Formatelementen zu vermeiden, ist die separate Formatierung der geschweiften Klammern und Formatelemente. Zeigen Sie also beim ersten Formatierungsvorgang eine literale öffnende geschweifte Klammer, beim nächsten Formatierungsvorgang das Ergebnis des Formatelements und beim letzten Formatierungsvorgang eine literale schließende geschweifte Klammer an. Dieser Ansatz wird anhand des folgenden Beispiels veranschaulicht.

```csharp
int value = 6324;
string output = string.Format("{0}{1:D}{2}", 
                             "{", value, "}");
Console.WriteLine(output);
// The example displays the following output:
//       {6324} 
```

```vb
Dim value As Integer = 6324
Dim output As String = String.Format("{0}{1:D}{2}", _
                                     "{", value, "}")
Console.WriteLine(output)   
' The example displays the following output:
'       {6324}
```

### <a name="processing-order"></a>Verarbeitungsreihenfolge

Wenn der Aufruf der Methode für die kombinierte Formatierung ein [IFormatProvider](xref:System.IFormatProvider)-Argument enthält, dessen Wert nicht NULL ist, ruft die Laufzeit die [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type))-Methode auf, um eine [ICustomFormatter](xref:System.ICustomFormatter)-Implementierung anzufordern. Wenn die Methode eine [ICustomFormatter](xref:System.ICustomFormatter)-Implementierung zurückgeben kann, wird sie für die spätere Verwendung zwischengespeichert. 

Jeder Wert in der Parameterliste, der einem Formatelement entspricht, wird anhand der folgenden Schritte in eine Zeichenfolge konvertiert. Wenn eine Bedingung in den ersten drei Schritten zu true ausgewertet wird, wird die Zeichenfolgendarstellung des Werts in diesem Schritt zurückgegeben, und nachfolgende Schritte werden nicht ausgeführt.

1. Wenn der zu formatierende Wert `null` ist, wird eine leere Zeichenfolge ("") zurückgegeben. 

2. Wenn eine [ICustomFormatter](xref:System.ICustomFormatter)-Implementierung verfügbar ist, ruft die Laufzeit die [Format](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider))-Methode auf. Sie übergibt den *Formatzeichenfolge*-Wert des Formatelements, sofern vorhanden, oder andernfalls `null` zusammen mit der [IFormatProvider](xref:System.IFormatProvider)-Implementierung an die Methode. 

3. Wenn der Wert die [IFormattable](xref:System.IFormattable)-Schnittstelle implementiert, wird die [ToString(String,IFormatProvider)](xref:System.IFormattable.ToString(System.String,System.IFormatProvider))-Methode der Schnittstelle aufgerufen. Der *Formatzeichenfolge*-Wert wird, sofern im Formatelement vorhanden, an die Methode übergeben. Ist dies nicht der Fall, wird `null` übergeben. Das [IFormatProvider](xref:System.IFormatProvider)-Argument wird wie folgt bestimmt:

    *   Bei einem numerischen Wert fordert die Laufzeit im Fall, dass eine Methode zur kombinierten Formatierung mit einem [IFormatProvider](xref:System.IFormatProvider)-Argument ungleich NULL aufgerufen wird, ein [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekt von ihrer [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type))-Methode an. Wenn sie keines bereitstellen kann, wenn der Wert des Arguments `null` ist, oder wenn die Methode zur kombinierten Formatierung keinen [IFormatProvider](xref:System.IFormatProvider)-Parameter hat, wird das [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekt für die aktuelle Threadkultur verwendet. 
    
    * Bei einem Datums- und Uhrzeitwert fordert die Laufzeit im Fall, dass eine Methode zur kombinierten Formatierung mit einem [IFormatProvider](xref:System.IFormatProvider)-Argument ungleich NULL aufgerufen wird, ein [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekt von ihrer [IFormatProvider.GetFormat](xref:System.IFormatProvider._GetFormat(System.Type)-Methode an. Wenn sie keines bereitstellen kann, wenn der Wert des Arguments `null` ist, oder wenn die Methode zur kombinierten Formatierung keinen [IFormatProvider](xref:System.IFormatProvider)-Parameter hat, wird das [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekt für die aktuelle Threadkultur verwendet. 
    
    * Bei Objekten anderer Typen wird im Fall, dass eine kombinierte Formatierung mit einem [IFormatProvider](xref:System.IFormatProvider)-Argument aufgerufen wird, der Wert (einschließlich `null`, wenn kein [IFormatProvider](xref:System.IFormatProvider)-Objekt bereitgestellt wird) direkt an die [IFormattable.ToString](xref:System.IFormattable.ToString(System.String,System.IFormatProvider))-Implementierung übergeben. Andernfalls wird ein [CultureInfo](xref:System.Globalization.CultureInfo)-Objekt, das die aktuelle Threadkultur darstellt, an die [IFormattable.ToString](xref:System.IFormattable.ToString(System.String,System.IFormatProvider))-Implementierung übergeben. 
    
4. Die parameterlose `ToString`-Methode des Typs, die entweder [Object.ToString()](xref:System.Object.ToString) überschreibt oder das Verhalten ihrer Basisklasse erbt, wird aufgerufen. In diesem Fall wird die von der *Formatzeichenfolge*-Komponente im Formatelement angegebene Formatzeichenfolge (sofern vorhanden) ignoriert.

Die Ausrichtung wird angewendet, nachdem die vorhergehenden Schritte durchgeführt wurden. 

## <a name="code-examples"></a>Codebeispiele

Das folgende Beispiel stellt eine Zeichenfolge dar, die mit der kombinierten Formatierung erstellt wurde, und eine weitere, die mit der `ToString`-Methode eines Objekts erstellt wurde. Beide Formatierungen führen zum gleichen Ergebnis. 

```csharp
string FormatString1 = String.Format("{0:dddd MMMM}", DateTime.Now);
string FormatString2 = DateTime.Now.ToString("dddd MMMM");
```

```vb
Dim FormatString1 As String = String.Format("{0:dddd MMMM}", DateTime.Now)
Dim FormatString2 As String = DateTime.Now.ToString("dddd MMMM")
```

Wenn das aktuelle Datum ein Donnerstag im Mai ist, lautet der Wert beider Zeichenfolgen im vorherigen Beispiel `Thursday May` in der Kultur Englisch (USA).

[Console.WriteLine](xref:System.Console.WriteLine) macht die gleiche Funktionalität wie [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) verfügbar. Der einzige Unterschied zwischen den beiden Methoden besteht darin, dass [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) das Ergebnis als Zeichenfolge zurückgibt, während [Console.WriteLine](xref:System.Console.WriteLine) das Ergebnis in den Ausgabestrom schreibt, der dem [Console](xref:System.Console)-Objekt zugeordnet ist. Im folgenden Beispiel wird der Wert von `MyInt` mit der [Console.WriteLine](xref:System.Console.WriteLine)-Methode als Währungswert formatiert.

```csharp
int MyInt = 100;
Console.WriteLine("{0:C}", MyInt);
// The example displays the following output 
// if en-US is the current culture:
//        $100.00
```

```vb
Dim MyInt As Integer = 100
Console.WriteLine("{0:C}", MyInt)
' The example displays the following output
' if en-US is the current culture:
'        $100.00
```

Das folgende Beispiel veranschaulicht die Formatierung mehrerer Objekte, wobei ein Objekt auf zwei Arten formatiert wird.

```csharp
string myName = "Fred";
Console.WriteLine(String.Format("Name = {0}, hours = {1:hh}, minutes = {1:mm}",
      myName, DateTime.Now));
// Depending on the current time, the example displays output like the following:
//    Name = Fred, hours = 11, minutes = 30                 
```

```vb
Dim myName As String = "Fred"
Console.WriteLine(String.Format("Name = {0}, hours = {1:hh}, minutes = {1:mm}", _
                  myName, DateTime.Now))
' Depending on the current time, the example displays output like the following:
'    Name = Fred, hours = 11, minutes = 30
```

Das folgende Beispiel veranschaulicht die Verwendung der Ausrichtung beim Formatieren. Die zu formatierenden Argumente werden zwischen senkrechte Striche („|“) platziert, um die resultierende Ausrichtung zu kennzeichnen.

```csharp
string myFName = "Fred";
string myLName = "Opals";
int myInt = 100;
string FormatFName = String.Format("First Name = |{0,10}|", myFName);
string FormatLName = String.Format("Last Name = |{0,10}|", myLName);
string FormatPrice = String.Format("Price = |{0,10:C}|", myInt); 
Console.WriteLine(FormatFName);
Console.WriteLine(FormatLName);
Console.WriteLine(FormatPrice);
Console.WriteLine();

FormatFName = String.Format("First Name = |{0,-10}|", myFName);
FormatLName = String.Format("Last Name = |{0,-10}|", myLName);
FormatPrice = String.Format("Price = |{0,-10:C}|", myInt);
Console.WriteLine(FormatFName);
Console.WriteLine(FormatLName);
Console.WriteLine(FormatPrice);
// The example displays the following output on a system whose current
// culture is en-US:
//          First Name = |      Fred|
//          Last Name = |     Opals|
//          Price = |   $100.00|
//
//          First Name = |Fred      |
//          Last Name = |Opals     |
//          Price = |$100.00   |
```

```vb
Dim myFName As String = "Fred"
Dim myLName As String = "Opals"

Dim myInt As Integer = 100
Dim FormatFName As String = String.Format("First Name = |{0,10}|", myFName)
Dim FormatLName As String = String.Format("Last Name = |{0,10}|", myLName)
Dim FormatPrice As String = String.Format("Price = |{0,10:C}|", myInt)
Console.WriteLine(FormatFName)
Console.WriteLine(FormatLName)
Console.WriteLine(FormatPrice)
Console.WriteLine()

FormatFName = String.Format("First Name = |{0,-10}|", myFName)
FormatLName = String.Format("Last Name = |{0,-10}|", myLName)
FormatPrice = String.Format("Price = |{0,-10:C}|", myInt)
Console.WriteLine(FormatFName)
Console.WriteLine(FormatLName)
Console.WriteLine(FormatPrice)
' The example displays the following output on a system whose current
' culture is en-US:
'          First Name = |      Fred|
'          Last Name = |     Opals|
'          Price = |   $100.00|
'
'          First Name = |Fred      |
'          Last Name = |Opals     |
'          Price = |$100.00   |
```

## <a name="see-also"></a>Siehe auch

[Console.WriteLine](xref:System.Console.WriteLine)

[String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object))

[Formatierung von Typen](formatting-types.md)

[Standardformatzeichenfolgen für Datum und Uhrzeit](standard-datetime.md)

[Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit](custom-datetime.md)

[Enumerationsformatzeichenfolgen](enumeration-format.md)

[Standard-Zahlenformatzeichenfolgen](standard-numeric.md)

[Benutzerdefinierte Zahlenformatzeichenfolgen](custom-numeric.md)

[TimeSpan-Standardformatzeichenfolgen](standard-timespan.md)

[Benutzerdefinierte TimeSpan-Formatzeichenfolgen](custom-timespan.md)



<!--HONumber=Nov16_HO3-->


