---
title: 'Gewusst wie: Anzeigen der Millisekunden in Datums- und Uhrzeitwerten'
description: Anzeigen der Millisekunden in Datums- und Uhrzeitwerten
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 78599e33-1c3f-4335-b320-751e35906338
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 9bcec8a610ed0fd47d168e23fb1454067e2d3fac

---

# <a name="how-to-display-milliseconds-in-date-and-time-values"></a>Gewusst wie: Anzeigen der Millisekunden in Datums- und Uhrzeitwerten

Bei den Standardformatierungsmethoden für Datum und Uhrzeit, wie z.B. [DateTime.ToString()](xref:System.DateTime.ToString), werden die Stunden, Minuten und Sekunden eines Uhrzeitwerts berücksichtigt, deren Millisekundenkomponente jedoch nicht. In diesem Thema wird erläutert, wie die Millisekundenkomponente für Datum und Uhrzeit in eine formatierte Datums- und Uhrzeitzeichenfolge eingefügt wird.

## <a name="to-display-the-millisecond-component-of-a-datetime-value"></a>So zeigen Sie die Millisekundenkomponente eines DateTime-Werts an

1. Wenn Sie mit der Zeichenfolgendarstellung eines Datums arbeiten, konvertieren Sie das Datum in einen [DateTime](xref:System.DateTime)- oder einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert, indem Sie die statischen Methoden [DateTime.Parse(String)](xref:System.DateTime.Parse(System.String)) oder [DateTimeOffset.Parse(String)](xref:System.DateTimeOffset.Parse(System.String)) verwenden.

2. Um die Zeichenfolgendarstellung der Millisekundenkomponente für eine Uhrzeit zu extrahieren, rufen Sie die [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String))-Methode oder die [DateTimeOffset.ToString](xref:System.DateTimeOffset.ToString(System.String))-Methode des Datums- und Uhrzeitwerts auf und übergeben das benutzerdefinierte Formatmuster `fff` oder `FFF` alleine oder zusammen mit anderen benutzerdefinierten Formatbezeichnern als Formatparameter.

## <a name="example"></a>Beispiel

Im Beispiel werden der Konsole die Millisekundenkomponente eines [DateTime](xref:System.DateTime)-Werts und ein [DateTimeOffset](xref:System.DateTimeOffset)-Wert angezeigt, und zwar sowohl alleine als auch als Bestandteil einer längeren Datums- und Uhrzeitzeichenfolge. 

```csharp
using System;
using System.Globalization;
using System.Text.RegularExpressions;

public class MillisecondDisplay
{
   public static void Main()
   {
      string dateString = "7/16/2008 8:32:45.126 AM";

      try
      {
         DateTime dateValue = DateTime.Parse(dateString);
         DateTimeOffset dateOffsetValue = DateTimeOffset.Parse(dateString);

         // Display Millisecond component alone.
         Console.WriteLine("Millisecond component only: {0}", 
                           dateValue.ToString("fff"));
         Console.WriteLine("Millisecond component only: {0}", 
                           dateOffsetValue.ToString("fff"));

         // Display Millisecond component with full date and time.
         Console.WriteLine("Date and Time with Milliseconds: {0}", 
                           dateValue.ToString("MM/dd/yyyy hh:mm:ss.fff tt"));                        
         Console.WriteLine("Date and Time with Milliseconds: {0}", 
                           dateOffsetValue.ToString("MM/dd/yyyy hh:mm:ss.fff tt"));

         // Append millisecond pattern to current culture's full date time pattern
         string fullPattern = DateTimeFormatInfo.CurrentInfo.FullDateTimePattern;
         fullPattern = Regex.Replace(fullPattern, "(:ss|:s)", "$1.fff");

         // Display Millisecond component with modified full date and time pattern.
         Console.WriteLine("Modified full date time pattern: {0}", 
                           dateValue.ToString(fullPattern));
         Console.WriteLine("Modified full date time pattern: {0}",
                           dateOffsetValue.ToString(fullPattern));
      }
      catch (FormatException)
      {
         Console.WriteLine("Unable to convert {0} to a date.", dateString);
      }
   }
}
// The example displays the following output if the current culture is en-US:
//    Millisecond component only: 126
//    Millisecond component only: 126
//    Date and Time with Milliseconds: 07/16/2008 08:32:45.126 AM
//    Date and Time with Milliseconds: 07/16/2008 08:32:45.126 AM
//    Modified full date time pattern: Wednesday, July 16, 2008 8:32:45.126 AM
//    Modified full date time pattern: Wednesday, July 16, 2008 8:32:45.126 AM
```

```vb
Imports System.Globalization
Imports System.Text.REgularExpressions

Module MillisecondDisplay
   Public Sub Main()

      Dim dateString As String = "7/16/2008 8:32:45.126 AM"

      Try
         Dim dateValue As Date = Date.Parse(dateString)
         Dim dateOffsetValue As DateTimeOffset = DateTimeOffset.Parse(dateString)

         ' Display Millisecond component alone.
         Console.WriteLine("Millisecond component only: {0}", _
                           dateValue.ToString("fff"))
         Console.WriteLine("Millisecond component only: {0}", _
                           dateOffsetValue.ToString("fff"))

         ' Display Millisecond component with full date and time.
         Console.WriteLine("Date and Time with Milliseconds: {0}", _
                           dateValue.ToString("MM/dd/yyyy hh:mm:ss.fff tt"))                        
         Console.WriteLine("Date and Time with Milliseconds: {0}", _
                           dateOffsetValue.ToString("MM/dd/yyyy hh:mm:ss.fff tt"))

         ' Append millisecond pattern to current culture's full date time pattern
         Dim fullPattern As String = DateTimeFormatInfo.CurrentInfo.FullDateTimePattern
         fullPattern = Regex.Replace(fullPattern, "(:ss|:s)", "$1.fff")

         ' Display Millisecond component with modified full date and time pattern.
         Console.WriteLine("Modified full date time pattern: {0}", _
                           dateValue.ToString(fullPattern))                        
         Console.WriteLine("Modified full date time pattern: {0}", _
                           dateOffsetValue.ToString(fullPattern))
      Catch e As FormatException
         Console.WriteLine("Unable to convert {0} to a date.", dateString)      
      End Try
   End Sub
End Module
' The example displays the following output if the current culture is en-US:
'    Millisecond component only: 126
'    Millisecond component only: 126
'    Date and Time with Milliseconds: 07/16/2008 08:32:45.126 AM
'    Date and Time with Milliseconds: 07/16/2008 08:32:45.126 AM
'    Modified full date time pattern: Wednesday, July 16, 2008 8:32:45.126 AM
'    Modified full date time pattern: Wednesday, July 16, 2008 8:32:45.126 AM
```

Das `fff`-Formatmuster schließt alle nachfolgenden Nullen (0) in den Millisekundenwert ein. Diese werden vom `FFF`-Formatmuster unterdrückt. Der Unterschied wird im folgenden Beispiel veranschaulicht.

```csharp
DateTime dateValue = new DateTime(2008, 7, 16, 8, 32, 45, 180); 
Console.WriteLine(dateValue.ToString("fff"));    
Console.WriteLine(dateValue.ToString("FFF"));
// The example displays the following output to the console:
//    180
//    18 
```

```vb
Dim dateValue As New Date(2008, 7, 16, 8, 32, 45, 180) 
Console.WriteLIne(dateValue.ToString("fff"))    
Console.WriteLine(dateValue.ToString("FFF"))
' The example displays the following output to the console:
'    180
'    18
```

Ein Problem beim Festlegen eines vollständigen benutzerdefinierten Formatbezeichners, der die Millisekundenkomponente für Datum und Uhrzeit umfasst, besteht darin, dass ein hartcodiertes Format festgelegt wird, das möglicherweise nicht der Anordnung der Uhrzeitelemente in der aktuellen Kultur der Anwendung entspricht. Die bessere Alternative besteht darin, eines der Anzeigemuster für Datum und Uhrzeit abzurufen, die durch das [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekt der aktuellen Kultur definiert sind, und es so zu bearbeiten, dass die Millisekunden berücksichtigt werden. Diese Herangehensweise wird im Beispiel ebenfalls verdeutlicht. Dabei wird das vollständige Datums- und Uhrzeitmuster der aktuellen Kultur aus der [DateTimeFormatInfo.FullDateTimePattern](xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern)-Eigenschaft abgerufen und das benutzerdefinierte Muster `.ffff` nach dem Sekundenmuster eingefügt. Beachten Sie, dass im Beispiel ein regulärer Ausdruck verwendet wird, um diesen Vorgang in einem einzelnen Methodenaufruf auszuführen.

Sie können auch einen benutzerdefinierten Formatbezeichner verwenden, um einen anderen Sekundenbruchteil als Millisekunden anzuzeigen. Durch den benutzerdefinierten Formatbezeichner `f` oder `F` werden beispielsweise Zehntelsekunden, durch den benutzerdefinierten Formatbezeichner `ff` oder `FF` Hundertstelsekunden und durch den benutzerdefinierten Formatbezeichner `ffff` oder `FFFF` Zehntausendstelsekunden angezeigt. Bruchteile einer Millisekunde werden abgeschnitten und nicht in der zurückgegebenen Zeichenfolge gerundet. Diese Formatbezeichner werden im folgenden Beispiel verwendet.

```csharp
DateTime dateValue = new DateTime(2008, 7, 16, 8, 32, 45, 180); 
Console.WriteLine("{0} seconds", dateValue.ToString("s.f"));
Console.WriteLine("{0} seconds", dateValue.ToString("s.ff"));      
Console.WriteLine("{0} seconds", dateValue.ToString("s.ffff"));
// The example displays the following output to the console:
//    45.1 seconds
//    45.18 seconds
//    45.1800 seconds
```

```vb
Dim dateValue As New DateTime(2008, 7, 16, 8, 32, 45, 180) 
Console.WriteLine("{0} seconds", dateValue.ToString("s.f"))
Console.WriteLine("{0} seconds", dateValue.ToString("s.ff"))      
Console.WriteLine("{0} seconds", dateValue.ToString("s.ffff"))
' The example displays the following output to the console:
'    45.1 seconds
'    45.18 seconds
'    45.1800 seconds
```

> [!NOTE]
> Es besteht die Möglichkeit, sehr kleine Sekundenbruchteile wie Zehntausendstelsekunden oder Hunderttausendstelsekunden anzuzeigen. Diese Werte sind jedoch möglicherweise nicht sinnvoll. Die Genauigkeit der Datums- und Uhrzeitwerte hängt von der Auflösung der Systemuhr ab.

## <a name="see-also"></a>Siehe auch

[System.Globalization.DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)

[Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit](custom-datetime.md)




<!--HONumber=Nov16_HO3-->


