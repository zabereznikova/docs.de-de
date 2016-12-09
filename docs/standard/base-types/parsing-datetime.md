---
title: "Analysieren von Zeichenfolgen für Datum und Uhrzeit in .NET"
description: "Analysieren von Zeichenfolgen für Datum und Uhrzeit in .NET"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: e61514cd-5329-4eb8-b122-482fffb54ab7
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 8b0c5a64db50163d196017ebb410e454eb5a6af9

---

# <a name="parsing-date-and-time-strings-in-net"></a>Analysieren von Zeichenfolgen für Datum und Uhrzeit in .NET

Durch die Analyse wird die Zeichenfolgendarstellung eines Datums und einer Uhrzeit in ein entsprechendes [DateTime](xref:System.DateTime)-Objekt konvertiert. Die Methoden [Parse](xref:System.DateTime.Parse(System.String)) und [TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) konvertieren beliebige aus mehreren gängigen Darstellungen von Datum und Uhrzeit. Die Methoden [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) und [TryParseExact](xref:System.DateTime.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTime@)) konvertieren eine Zeichenfolgendarstellung entsprechend dem Muster, das durch eine Formatzeichenfolge für Datum und Uhrzeit angegeben wird. (Informationen hierzu finden Sie in den Themen [Standardformatzeichenfolgen für Datum und Uhrzeit](standard-datetime.md) und [Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit](custom-datetime.md).) 

Die Analyse wird durch die Eigenschaften eines Formatanbieters beeinflusst. Dieser stellt Informationen wie die Zeichenfolgen, die als Datums- und Zeittrennzeichen verwendet werden, und die Namen von Monaten, Tagen und Zeiträumen bereit. Der Formatanbieter ist das aktuelle [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekts, das implizit durch die aktuelle Threadkultur oder explizit durch den [IFormatProvider](xref:System.IFormatProvider)-Parameter einer Analysemethode bereitgestellt wird. Für den [IFormatProvider](xref:System.IFormatProvider)-Parameter geben Sie ein [CultureInfo](xref:System.Globalization.CultureInfo)-Objekt, das eine Kultur darstellt, oder ein [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekt an. 

Die Zeichenfolgendarstellung eines zu analysierenden Datums muss den Monat und mindestens einen Tag oder das Jahr enthalten. Die Zeichenfolgendarstellung einer Uhrzeit muss die Stundenangabe und mindestens die Minuten oder den AM/PM-Kennzeichner enthalten. Bei der Analyse werden jedoch nach Möglichkeit Standardwerte für ausgelassene Komponenten ergänzt. Für ein fehlendes Datum wird standardmäßig das aktuelle Datum eingesetzt, für eine fehlende Jahresangabe das aktuelle Jahr, für einen fehlenden Monatstag der erste Tag im Monat, und für eine fehlende Uhrzeit wird standardmäßig Mitternacht angenommen. 

Wenn die Zeichenfolgendarstellung nur eine Uhrzeit angibt, wird durch die Analyse ein [DateTime](xref:System.DateTime)-Objekt zurückgegeben, dessen [Year](xref:System.DateTime.Year)-, [Month](xref:System.DateTime.Month)- und [Day](xref:System.DateTime.Day)-Eigenschaften auf die entsprechenden Werte der Eigenschaft [Today](xref:System.DateTime.Today) festgelegt sind. Wenn jedoch die [DateTimeStyles.NoCurrentDateDefault](xref:System.Globalization.DateTimeStyles.NoCurrentDateDefault)-Konstante in der Analysemethode angegeben wird, werden die year-, month- und day-Eigenschaften auf den Wert 1 festgelegt.

Zusätzlich zu einer Datums- und Zeitkomponente kann die Zeichenfolgendarstellung einer Datums- und Uhrzeitangabe einen Zeitraum enthalten, der angibt, um wie viel die Zeit von der koordinierten Weltzeit (UTC) abweicht. Beispielsweise definiert die Zeichenfolge „2/14/2007 5:32:00 -7:00“ eine Uhrzeit, die sieben Stunden vor UTC liegt. Wenn die Abweichung in der Zeichenfolgendarstellung einer Uhrzeit fehlt, gibt die Analyse ein [DateTime](xref:System.DateTime)-Objekt zurück, dessen [Kind](xref:System.DateTime.Kind)-Eigenschaft auf [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified) festgelegt ist. Wird eine Abweichung angegeben, gibt die Analyse ein [DateTime](xref:System.DateTime)-Objekt zurück, dessen [Kind](xref:System.DateTime.Kind)-Eigenschaft auf [Local](xref:System.DateTimeKind.Local) festgelegt ist und dessen Wert an die lokale Zeitzone des Computers angepasst wird. Sie können dieses Verhalten ändern, indem Sie eine [DateTimeStyles](xref:System.Globalization.DateTimeStyles)-Konstante mit der Analysemethode verwenden.

Der Formatanbieter wird auch zum Interpretieren mehrdeutiger numerischer Datumsangaben verwendet. Beispielsweise ist nicht eindeutig zu erkennen, welche Komponenten des in der Zeichenfolge „02/03/04“ dargestellten Datums für den Monat, den Tag und das Jahr stehen. In diesem Fall werden die Komponenten entsprechend der Reihenfolge ähnlicher Datumsformate im Formatanbieter interpretiert. 

## <a name="parse"></a>Parse

Das folgende Codebeispiel veranschaulicht die Verwendung der `Parse`-Methode zum Konvertieren einer Zeichenfolge in einen `DateTime`-Wert. In diesem Beispiel wird die dem aktuellen Thread zugeordnete Kultur zum Durchführen der Analyse verwendet. Wenn die [CultureInfo](xref:System.Globalization.CultureInfo), die der aktuellen Kultur zugeordnet ist, die Eingabezeichenfolge nicht analysieren kann, wird eine [FormatException](xref:System.FormatException) ausgelöst.

```csharp
string MyString = "Jan 1, 2009";
DateTime MyDateTime = DateTime.Parse(MyString);
Console.WriteLine(MyDateTime);
// Displays the following output on a system whose culture is en-US:
//       1/1/2009 12:00:00 AM
```

```vb
Dim MyString As String = "Jan 1, 2009"
Dim MyDateTime As DateTime = DateTime.Parse(MyString)
Console.WriteLine(MyDateTime)
' Displays the following output on a system whose culture is en-US:
'       1/1/2009 12:00:00 AM
```

Sie können auch eine `CultureInfo` angeben, die auf eine der durch dieses Objekt definierten Kulturen festgelegt ist, oder Sie können eines der [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Standardobjekte angeben, das von der [CultureInfo.DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat)-Eigenschaft zurückgegeben wird. Im folgenden Codebeispiel wird ein Formatanbieter verwendet, um eine deutsche Zeichenfolge in einen `DateTime`-Wert zu analysieren. Eine `CultureInfo`, die für die Kultur „de-DE“ steht, wird definiert und mit der zu analysierenden Zeichenfolge übergeben, um eine erfolgreiche Analyse dieser Zeichenfolge sicherzustellen. Hierdurch wird jegliche Einstellung in der `CurrentCulture` von `CurrentThread` ausgeschlossen.

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      CultureInfo MyCultureInfo = new CultureInfo("de-DE");
      string MyString = "12 Juni 2008";
      DateTime MyDateTime = DateTime.Parse(MyString, MyCultureInfo);
      Console.WriteLine(MyDateTime);
   }
}
// The example displays the following output:
//       6/12/2008 12:00:00 AM
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim MyCultureInfo As CultureInfo = new CultureInfo("de-DE")
      Dim MyString As String = "12 Juni 2008"
      Dim MyDateTime As DateTime = DateTime.Parse(MyString, MyCultureInfo)
      Console.WriteLine(MyDateTime)
   End Sub
End Module
' The example displays the following output:
'       6/12/2008 12:00:00 AM
```

Auch wenn Sie Überladungen der [Parse](xref:System.DateTime.Parse(System.String))-Methode zur Angabe benutzerdefinierter Formatanbieter verwenden können, werden nicht dem Standard entsprechende Formatanbieter nicht von der Methode unterstützt. Um ein Datum und eine Uhrzeit in einem nicht dem Standard entsprechenden Format zu analysieren, verwenden Sie stattdessen die [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider))-Methode.

Im folgenden Codebeispiel wird anhand der [DateTimeStyles](xref:System.Globalization.DateTimeStyles)-Enumeration angegeben, dass die aktuellen Datums- und Uhrzeitinformationen dem `DateTime`-Wert nicht hinzugefügt werden sollen für Felder, die nicht durch die Zeichenfolge definiert werden.

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      CultureInfo MyCultureInfo = new CultureInfo("de-DE");
      string MyString = "12 Juni 2008";
      DateTime MyDateTime = DateTime.Parse(MyString, MyCultureInfo, 
                                           DateTimeStyles.NoCurrentDateDefault);
      Console.WriteLine(MyDateTime);
   }
}
// The example displays the following output if the current culture is en-US:
//      6/12/2008 12:00:00 AM
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim MyCultureInfo As CultureInfo = new CultureInfo("de-DE")
      Dim MyString As String = "12 Juni 2008"
      Dim MyDateTime As DateTime = DateTime.Parse(MyString, MyCultureInfo)
      Console.WriteLine(MyDateTime)
   End Sub
End Module
' The example displays the following output:
'       6/12/2008 12:00:00 AM
```

## <a name="parseexact"></a>ParseExact

Die Methode [DateTime.ParseExact]((Xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) konvertiert eine Zeichenfolge, die einem bestimmten Zeichenfolgenmuster für ein `DateTime`-Objekt entspricht. Wenn eine Zeichenfolge, die nicht der angegebenen Form entspricht, an diese Methode übergeben wird, wird eine [FormatException](xref:System.FormatException) ausgelöst. Sie können einen der Standardformatbezeichner für Datum und Uhrzeit oder eine begrenzte Kombination der benutzerdefinierten Formatbezeichner für Datum und Uhrzeit angeben. Mithilfe der benutzerdefinierten Formatbezeichner können Sie eine benutzerdefinierte Erkennungszeichenfolge erstellen. Erläuterungen zu den Bezeichnern finden Sie in den Themen [Standardformatzeichenfolgen für Datum und Uhrzeit](standard-datetime.md) und [Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit](custom-datetime.md). 

Jede Überladung der [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider))-Methode enthält auch einen [IFormatProvider](xref:System.IFormatProvider)-Parameter, der normalerweise kulturspezifische Informationen zur Formatierung der Zeichenfolge enthält. In der Regel handelt es sich bei diesem [IFormatProvider](xref:System.IFormatProvider)-Objekt um ein [CultureInfo](xref:System.Globalization.CultureInfo)-Objekt, das eine Standardkultur darstellt, bzw. um ein [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekt, das von der [CultureInfo.DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat)-Eigenschaft zurückgegeben wird. Im Gegensatz zu anderen Funktionen zur Datums- und Uhrzeitanalyse unterstützt diese Methode jedoch auch einen [IFormatProvider](xref:System.IFormatProvider), der ein nicht dem Standard entsprechendes Datums- und Zeitformat definiert. 

Im folgenden Codebeispiel wird die `ParseExact`-Methode an ein zu analysierendes Zeichenfolgenobjekt übergeben, gefolgt von einem Formatbezeichner, gefolgt von einem `CultureInfo`-Objekt. Diese `ParseExact`-Methode kann nur Zeichenfolgen analysieren, die in der en-US-Kultur das lange Datumsmuster aufweisen.

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      CultureInfo MyCultureInfo = new CultureInfo("en-US");
      string[] MyString = {" Friday, April 10, 2009", "Friday, April 10, 2009"};
      foreach (string dateString in MyString)
      {
         try {
            DateTime MyDateTime = DateTime.ParseExact(dateString, "D", MyCultureInfo);
            Console.WriteLine(MyDateTime);
         }
         catch (FormatException) {
            Console.WriteLine("Unable to parse '{0}'", dateString);
         }
      }
   }
}
// The example displays the following output:
//       Unable to parse ' Friday, April 10, 2009'
//       4/10/2009 12:00:00 AM
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim MyCultureInfo As CultureInfo = new CultureInfo("en-US")
      Dim MyString() As String = {" Friday, April 10, 2009", "Friday, April 10, 2009"}
      For Each dateString As String In MyString
         Try
            Dim MyDateTime As DateTime = DateTime.ParseExact(dateString, "D", _
                                                             MyCultureInfo)
            Console.WriteLine(MyDateTime)
         Catch e As FormatException
            Console.WriteLine("Unable to parse '{0}'", dateString)
         End Try
      Next
   End Sub
End Module
' The example displays the following output:
'       Unable to parse ' Friday, April 10, 2009'
'       4/10/2009 12:00:00 AM
```

## <a name="see-also"></a>Siehe auch

[Analysieren von Zeichenfolgen in .NET](parsing-strings.md)

[Formatieren von Typen in .NET](formatting-types.md)

[Typkonvertierung in .NET](type-conversion.md)




<!--HONumber=Nov16_HO3-->


