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
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: f0131baa0874880b6697458426da5ae9ce1705b7
ms.contentlocale: de-de
ms.lasthandoff: 03/02/2017

---

# <a name="parsing-date-and-time-strings-in-net"></a><span data-ttu-id="8494f-104">Analysieren von Zeichenfolgen für Datum und Uhrzeit in .NET</span><span class="sxs-lookup"><span data-stu-id="8494f-104">Parsing date and time strings in .NET</span></span>

<span data-ttu-id="8494f-105">Durch die Analyse wird die Zeichenfolgendarstellung eines Datums und einer Uhrzeit in ein entsprechendes [DateTime](xref:System.DateTime)-Objekt konvertiert.</span><span class="sxs-lookup"><span data-stu-id="8494f-105">Parsing methods convert the string representation of a date and time to an equivalent [DateTime](xref:System.DateTime) object.</span></span> <span data-ttu-id="8494f-106">Die Methoden [Parse](xref:System.DateTime.Parse(System.String)) und [TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) konvertieren beliebige aus mehreren gängigen Darstellungen von Datum und Uhrzeit.</span><span class="sxs-lookup"><span data-stu-id="8494f-106">The [Parse](xref:System.DateTime.Parse(System.String)) and [TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) methods convert any of several common representations of a date and time.</span></span> <span data-ttu-id="8494f-107">Die Methoden [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) und [TryParseExact](xref:System.DateTime.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTime@)) konvertieren eine Zeichenfolgendarstellung entsprechend dem Muster, das durch eine Formatzeichenfolge für Datum und Uhrzeit angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8494f-107">The [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) and [TryParseExact](xref:System.DateTime.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTime@)) methods convert a string representation that conforms to the pattern specified by a date and time format string.</span></span> <span data-ttu-id="8494f-108">(Informationen hierzu finden Sie in den Themen [Standardformatzeichenfolgen für Datum und Uhrzeit](standard-datetime.md) und [Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit](custom-datetime.md).)</span><span class="sxs-lookup"><span data-stu-id="8494f-108">(See the topics on [standard date and time format strings](standard-datetime.md) and [custom date and time format strings](custom-datetime.md).)</span></span> 

<span data-ttu-id="8494f-109">Die Analyse wird durch die Eigenschaften eines Formatanbieters beeinflusst. Dieser stellt Informationen wie die Zeichenfolgen, die als Datums- und Zeittrennzeichen verwendet werden, und die Namen von Monaten, Tagen und Zeiträumen bereit.</span><span class="sxs-lookup"><span data-stu-id="8494f-109">Parsing is influenced by the properties of a format provider that supplies information such as the strings used for date and time separators, and the names of months, days, and eras.</span></span> <span data-ttu-id="8494f-110">Der Formatanbieter ist das aktuelle [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekts, das implizit durch die aktuelle Threadkultur oder explizit durch den [IFormatProvider](xref:System.IFormatProvider)-Parameter einer Analysemethode bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="8494f-110">The format provider is the current [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object, which is provided implicitly by the current thread culture or explicitly by the [IFormatProvider](xref:System.IFormatProvider) parameter of a parsing method.</span></span> <span data-ttu-id="8494f-111">Für den [IFormatProvider](xref:System.IFormatProvider)-Parameter geben Sie ein [CultureInfo](xref:System.Globalization.CultureInfo)-Objekt, das eine Kultur darstellt, oder ein [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekt an.</span><span class="sxs-lookup"><span data-stu-id="8494f-111">For the [IFormatProvider](xref:System.IFormatProvider) parameter, specify a [CultureInfo](xref:System.Globalization.CultureInfo) object, which represents a culture, or a [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object.</span></span> 

<span data-ttu-id="8494f-112">Die Zeichenfolgendarstellung eines zu analysierenden Datums muss den Monat und mindestens einen Tag oder das Jahr enthalten.</span><span class="sxs-lookup"><span data-stu-id="8494f-112">The string representation of a date to be parsed must include the month and at least a day or year.</span></span> <span data-ttu-id="8494f-113">Die Zeichenfolgendarstellung einer Uhrzeit muss die Stundenangabe und mindestens die Minuten oder den AM/PM-Kennzeichner enthalten.</span><span class="sxs-lookup"><span data-stu-id="8494f-113">The string representation of a time must include the hour and at least minutes or the AM/PM designator.</span></span> <span data-ttu-id="8494f-114">Bei der Analyse werden jedoch nach Möglichkeit Standardwerte für ausgelassene Komponenten ergänzt.</span><span class="sxs-lookup"><span data-stu-id="8494f-114">However, parsing supplies default values for omitted components if possible.</span></span> <span data-ttu-id="8494f-115">Für ein fehlendes Datum wird standardmäßig das aktuelle Datum eingesetzt, für eine fehlende Jahresangabe das aktuelle Jahr, für einen fehlenden Monatstag der erste Tag im Monat, und für eine fehlende Uhrzeit wird standardmäßig Mitternacht angenommen.</span><span class="sxs-lookup"><span data-stu-id="8494f-115">A missing date defaults to the current date, a missing year defaults to the current year, a missing day of the month defaults to the first day of the month, and a missing time defaults to midnight.</span></span> 

<span data-ttu-id="8494f-116">Wenn die Zeichenfolgendarstellung nur eine Uhrzeit angibt, wird durch die Analyse ein [DateTime](xref:System.DateTime)-Objekt zurückgegeben, dessen [Year](xref:System.DateTime.Year)-, [Month](xref:System.DateTime.Month)- und [Day](xref:System.DateTime.Day)-Eigenschaften auf die entsprechenden Werte der Eigenschaft [Today](xref:System.DateTime.Today) festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="8494f-116">If the string representation specifies only a time, parsing returns a [DateTime](xref:System.DateTime) object with its [Year](xref:System.DateTime.Year), [Month](xref:System.DateTime.Month), and [Day](xref:System.DateTime.Day) properties set to the corresponding values of the [Today](xref:System.DateTime.Today) property.</span></span> <span data-ttu-id="8494f-117">Wenn jedoch die [DateTimeStyles.NoCurrentDateDefault](xref:System.Globalization.DateTimeStyles.NoCurrentDateDefault)-Konstante in der Analysemethode angegeben wird, werden die year-, month- und day-Eigenschaften auf den Wert 1 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8494f-117">However, if the [DateTimeStyles.NoCurrentDateDefault](xref:System.Globalization.DateTimeStyles.NoCurrentDateDefault) constant is specified in the parsing method, the resulting year, month, and day properties are set to the value 1.</span></span>

<span data-ttu-id="8494f-118">Zusätzlich zu einer Datums- und Zeitkomponente kann die Zeichenfolgendarstellung einer Datums- und Uhrzeitangabe einen Zeitraum enthalten, der angibt, um wie viel die Zeit von der koordinierten Weltzeit (UTC) abweicht.</span><span class="sxs-lookup"><span data-stu-id="8494f-118">In addition to a date and a time component, the string representation of a date and time can include an offset that indicates how much the time differs from Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="8494f-119">Beispielsweise definiert die Zeichenfolge „2/14/2007 5:32:00 -7:00“ eine Uhrzeit, die sieben Stunden vor UTC liegt.</span><span class="sxs-lookup"><span data-stu-id="8494f-119">For example, the string "2/14/2007 5:32:00 -7:00" defines a time that is seven hours earlier than UTC.</span></span> <span data-ttu-id="8494f-120">Wenn die Abweichung in der Zeichenfolgendarstellung einer Uhrzeit fehlt, gibt die Analyse ein [DateTime](xref:System.DateTime)-Objekt zurück, dessen [Kind](xref:System.DateTime.Kind)-Eigenschaft auf [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="8494f-120">If an offset is omitted from the string representation of a time, parsing returns a [DateTime](xref:System.DateTime) object with its [Kind](xref:System.DateTime.Kind) property set to [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified).</span></span> <span data-ttu-id="8494f-121">Wird eine Abweichung angegeben, gibt die Analyse ein [DateTime](xref:System.DateTime)-Objekt zurück, dessen [Kind](xref:System.DateTime.Kind)-Eigenschaft auf [Local](xref:System.DateTimeKind.Local) festgelegt ist und dessen Wert an die lokale Zeitzone des Computers angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="8494f-121">If an offset is specified, parsing returns a [DateTime](xref:System.DateTime) object with its [Kind](xref:System.DateTime.Kind) property set to [Local](xref:System.DateTimeKind.Local) and its value adjusted to the local time zone of your machine.</span></span> <span data-ttu-id="8494f-122">Sie können dieses Verhalten ändern, indem Sie eine [DateTimeStyles](xref:System.Globalization.DateTimeStyles)-Konstante mit der Analysemethode verwenden.</span><span class="sxs-lookup"><span data-stu-id="8494f-122">You can modify this behavior by using a [DateTimeStyles](xref:System.Globalization.DateTimeStyles) constant with the parsing method.</span></span>

<span data-ttu-id="8494f-123">Der Formatanbieter wird auch zum Interpretieren mehrdeutiger numerischer Datumsangaben verwendet.</span><span class="sxs-lookup"><span data-stu-id="8494f-123">The format provider is also used to interpret an ambiguous numeric date.</span></span> <span data-ttu-id="8494f-124">Beispielsweise ist nicht eindeutig zu erkennen, welche Komponenten des in der Zeichenfolge „02/03/04“ dargestellten Datums für den Monat, den Tag und das Jahr stehen.</span><span class="sxs-lookup"><span data-stu-id="8494f-124">For example, it is not clear which components of the date represented by the string "02/03/04" are the month, day, and year.</span></span> <span data-ttu-id="8494f-125">In diesem Fall werden die Komponenten entsprechend der Reihenfolge ähnlicher Datumsformate im Formatanbieter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="8494f-125">In this case, the components are interpreted according to the order of similar date formats in the format provider.</span></span> 

## <a name="parse"></a><span data-ttu-id="8494f-126">Parse</span><span class="sxs-lookup"><span data-stu-id="8494f-126">Parse</span></span>

<span data-ttu-id="8494f-127">Das folgende Codebeispiel veranschaulicht die Verwendung der `Parse`-Methode zum Konvertieren einer Zeichenfolge in einen `DateTime`-Wert.</span><span class="sxs-lookup"><span data-stu-id="8494f-127">The following code example illustrates the use of the `Parse` method to convert a string into a `DateTime`.</span></span> <span data-ttu-id="8494f-128">In diesem Beispiel wird die dem aktuellen Thread zugeordnete Kultur zum Durchführen der Analyse verwendet.</span><span class="sxs-lookup"><span data-stu-id="8494f-128">This example uses the culture associated with the current thread to perform the parse.</span></span> <span data-ttu-id="8494f-129">Wenn die [CultureInfo](xref:System.Globalization.CultureInfo), die der aktuellen Kultur zugeordnet ist, die Eingabezeichenfolge nicht analysieren kann, wird eine [FormatException](xref:System.FormatException) ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="8494f-129">If the [CultureInfo](xref:System.Globalization.CultureInfo) associated with the current culture cannot parse the input string, a [FormatException](xref:System.FormatException) is thrown.</span></span>

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

<span data-ttu-id="8494f-130">Sie können auch eine `CultureInfo` angeben, die auf eine der durch dieses Objekt definierten Kulturen festgelegt ist, oder Sie können eines der [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Standardobjekte angeben, das von der [CultureInfo.DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat)-Eigenschaft zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8494f-130">You can also specify a `CultureInfo` set to one of the cultures defined by that object, or you can specify one of the standard [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) objects returned by the [CultureInfo.DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat) property.</span></span> <span data-ttu-id="8494f-131">Im folgenden Codebeispiel wird ein Formatanbieter verwendet, um eine deutsche Zeichenfolge in einen `DateTime`-Wert zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="8494f-131">The following code example uses a format provider to parse a German string into a `DateTime`.</span></span> <span data-ttu-id="8494f-132">Eine `CultureInfo`, die für die Kultur „de-DE“ steht, wird definiert und mit der zu analysierenden Zeichenfolge übergeben, um eine erfolgreiche Analyse dieser Zeichenfolge sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="8494f-132">A `CultureInfo` representing the de-DE culture is defined and passed with the string being parsed to ensure successful parsing of this particular string.</span></span> <span data-ttu-id="8494f-133">Hierdurch wird jegliche Einstellung in der `CurrentCulture` von `CurrentThread` ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="8494f-133">This precludes whatever setting is in the `CurrentCulture` of the `CurrentThread`.</span></span>

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

<span data-ttu-id="8494f-134">Auch wenn Sie Überladungen der [Parse](xref:System.DateTime.Parse(System.String))-Methode zur Angabe benutzerdefinierter Formatanbieter verwenden können, werden nicht dem Standard entsprechende Formatanbieter nicht von der Methode unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8494f-134">However, although you can use overloads of the [Parse](xref:System.DateTime.Parse(System.String)) method to specify custom format providers, the method does not support the use of non-standard format providers.</span></span> <span data-ttu-id="8494f-135">Um ein Datum und eine Uhrzeit in einem nicht dem Standard entsprechenden Format zu analysieren, verwenden Sie stattdessen die [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider))-Methode.</span><span class="sxs-lookup"><span data-stu-id="8494f-135">To parse a date and time expressed in a non-standard format, use the [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) method instead.</span></span>

<span data-ttu-id="8494f-136">Im folgenden Codebeispiel wird anhand der [DateTimeStyles](xref:System.Globalization.DateTimeStyles)-Enumeration angegeben, dass die aktuellen Datums- und Uhrzeitinformationen dem `DateTime`-Wert nicht hinzugefügt werden sollen für Felder, die nicht durch die Zeichenfolge definiert werden.</span><span class="sxs-lookup"><span data-stu-id="8494f-136">The following code example uses the [DateTimeStyles](xref:System.Globalization.DateTimeStyles) enumeration to specify that the current date and time information should not be added to the `DateTime` for fields that the string does not define.</span></span>

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

## <a name="parseexact"></a><span data-ttu-id="8494f-137">ParseExact</span><span class="sxs-lookup"><span data-stu-id="8494f-137">ParseExact</span></span>

<span data-ttu-id="8494f-138">Die Methode [DateTime.ParseExact]((Xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) konvertiert eine Zeichenfolge, die einem bestimmten Zeichenfolgenmuster für ein `DateTime`-Objekt entspricht.</span><span class="sxs-lookup"><span data-stu-id="8494f-138">The [DateTime.ParseExact]((xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) method converts a string that conforms to a specified string pattern to a `DateTime` object.</span></span> <span data-ttu-id="8494f-139">Wenn eine Zeichenfolge, die nicht der angegebenen Form entspricht, an diese Methode übergeben wird, wird eine [FormatException](xref:System.FormatException) ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="8494f-139">When a string that is not of the form specified is passed to this method, a [FormatException](xref:System.FormatException) is thrown.</span></span> <span data-ttu-id="8494f-140">Sie können einen der Standardformatbezeichner für Datum und Uhrzeit oder eine begrenzte Kombination der benutzerdefinierten Formatbezeichner für Datum und Uhrzeit angeben.</span><span class="sxs-lookup"><span data-stu-id="8494f-140">You can specify one of the standard date and time format specifiers or a limited combination of the custom date and time format specifiers.</span></span> <span data-ttu-id="8494f-141">Mithilfe der benutzerdefinierten Formatbezeichner können Sie eine benutzerdefinierte Erkennungszeichenfolge erstellen.</span><span class="sxs-lookup"><span data-stu-id="8494f-141">Using the custom format specifiers, it is possible for you to construct a custom recognition string.</span></span> <span data-ttu-id="8494f-142">Erläuterungen zu den Bezeichnern finden Sie in den Themen [Standardformatzeichenfolgen für Datum und Uhrzeit](standard-datetime.md) und [Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit](custom-datetime.md).</span><span class="sxs-lookup"><span data-stu-id="8494f-142">For an explanation of the specifiers, see the topics on [standard date and time format strings](standard-datetime.md) and [custom date and time format strings](custom-datetime.md).</span></span> 

<span data-ttu-id="8494f-143">Jede Überladung der [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider))-Methode enthält auch einen [IFormatProvider](xref:System.IFormatProvider)-Parameter, der normalerweise kulturspezifische Informationen zur Formatierung der Zeichenfolge enthält.</span><span class="sxs-lookup"><span data-stu-id="8494f-143">Each overload of the [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) method also has an [IFormatProvider](xref:System.IFormatProvider) parameter that typically provides culture-specific information about the formatting of the string.</span></span> <span data-ttu-id="8494f-144">In der Regel handelt es sich bei diesem [IFormatProvider](xref:System.IFormatProvider)-Objekt um ein [CultureInfo](xref:System.Globalization.CultureInfo)-Objekt, das eine Standardkultur darstellt, bzw. um ein [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekt, das von der [CultureInfo.DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat)-Eigenschaft zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8494f-144">Typically, this [IFormatProvider](xref:System.IFormatProvider) object is a [CultureInfo](xref:System.Globalization.CultureInfo) object that represents a standard culture or a [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object that is returned by the [CultureInfo.DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat) property.</span></span> <span data-ttu-id="8494f-145">Im Gegensatz zu anderen Funktionen zur Datums- und Uhrzeitanalyse unterstützt diese Methode jedoch auch einen [IFormatProvider](xref:System.IFormatProvider), der ein nicht dem Standard entsprechendes Datums- und Zeitformat definiert.</span><span class="sxs-lookup"><span data-stu-id="8494f-145">However, unlike the other date and time parsing functions, this method also supports an [IFormatProvider](xref:System.IFormatProvider) that defines a non-standard date and time format.</span></span> 

<span data-ttu-id="8494f-146">Im folgenden Codebeispiel wird die `ParseExact`-Methode an ein zu analysierendes Zeichenfolgenobjekt übergeben, gefolgt von einem Formatbezeichner, gefolgt von einem `CultureInfo`-Objekt.</span><span class="sxs-lookup"><span data-stu-id="8494f-146">In the following code example, the `ParseExact` method is passed a string object to parse, followed by a format specifier, followed by a `CultureInfo` object.</span></span> <span data-ttu-id="8494f-147">Diese `ParseExact`-Methode kann nur Zeichenfolgen analysieren, die in der en-US-Kultur das lange Datumsmuster aufweisen.</span><span class="sxs-lookup"><span data-stu-id="8494f-147">This `ParseExact` method can only parse strings that exhibit the long date pattern in the en-US culture.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="8494f-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8494f-148">See Also</span></span>

[<span data-ttu-id="8494f-149">Analysieren von Zeichenfolgen in .NET</span><span class="sxs-lookup"><span data-stu-id="8494f-149">Parsing strings in .NET</span></span>](parsing-strings.md)

[<span data-ttu-id="8494f-150">Formatieren von Typen in .NET</span><span class="sxs-lookup"><span data-stu-id="8494f-150">Formatting types in .NET</span></span>](formatting-types.md)

[<span data-ttu-id="8494f-151">Typkonvertierung in .NET</span><span class="sxs-lookup"><span data-stu-id="8494f-151">Type conversion in .NET</span></span>](type-conversion.md)


