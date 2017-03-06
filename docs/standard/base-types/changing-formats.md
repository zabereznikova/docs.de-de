---
title: "Beispiel für reguläre Ausdrücke: Ändern von Datumsformaten"
description: "Beispiel für reguläre Ausdrücke: Ändern von Datumsformaten"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 3e196697-981c-4c1d-93dd-c3b236ef36dd
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: f801e8761ad2dfe80915cc4425c359cfae99949e
ms.lasthandoff: 03/02/2017

---

# <a name="regular-expression-example-changing-date-formats"></a>Beispiel für reguläre Ausdrücke: Ändern von Datumsformaten

Im folgenden Codebeispiel wird die [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String))-Methode verwendet, um Datumsangaben in der Form *mm/tt/jj* durch Datumsangaben in der Form *tt-mm-jj* zu ersetzen.

## <a name="example"></a>Beispiel

```csharp
static string MDYToDMY(string input) 
{
   try {
      return Regex.Replace(input, 
            "\\b(?<month>\\d{1,2})/(?<day>\\d{1,2})/(?<year>\\d{2,4})\\b",
            "${day}-${month}-${year}", RegexOptions.None,
            TimeSpan.FromMilliseconds(150));
   }         
   catch (RegexMatchTimeoutException) {
      return input;
   }
}
```

```vb
Function MDYToDMY(input As String) As String
   Try
      Return Regex.Replace(input, _
             "\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b", _
             "${day}-${month}-${year}", RegexOptions.None,
             TimeSpan.FromMilliseconds(150))
    Catch e As RegexMatchTimeoutException
       Return input
    End Try         
End Function
```

Der folgende Code zeigt, wie die `MDYToDMY`-Methode in einer Anwendung aufgerufen werden kann. 

```csharp
using System;
using System.Globalization;
using System.Text.RegularExpressions;

public class Class1
{
   public static void Main()
   {
      string dateString = DateTime.Today.ToString("d", 
                                        DateTimeFormatInfo.InvariantInfo);
      string resultString = MDYToDMY(dateString);
      Console.WriteLine("Converted {0} to {1}.", dateString, resultString);
   }

   static string MDYToDMY(string input) 
   {
      try {
         return Regex.Replace(input, 
               "\\b(?<month>\\d{1,2})/(?<day>\\d{1,2})/(?<year>\\d{2,4})\\b",
               "${day}-${month}-${year}", RegexOptions.None,
               TimeSpan.FromMilliseconds(150));
      }         
      catch (RegexMatchTimeoutException) {
         return input;
      }
   }

}
// The example displays the following output to the console if run on 8/21/2007:
//      Converted 08/21/2007 to 21-08-2007.
```

```vb
Imports System.Globalization
Imports System.Text.RegularExpressions

Module DateFormatReplacement
   Public Sub Main()
      Dim dateString As String = Date.Today.ToString("d", _
                                           DateTimeFormatInfo.InvariantInfo)
      Dim resultString As String = MDYToDMY(dateString)
      Console.WriteLine("Converted {0} to {1}.", dateString, resultString)
   End Sub

    Function MDYToDMY(input As String) As String
       Try
          Return Regex.Replace(input, _
                 "\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b", _
                 "${day}-${month}-${year}", RegexOptions.None,
                 TimeSpan.FromMilliseconds(150))
        Catch e As RegexMatchTimeoutException
           Return input
        End Try         
    End Function
End Module
' The example displays the following output to the console if run on 8/21/2007:
'      Converted 08/21/2007 to 21-08-2007.
```

## <a name="comments"></a>Kommentare

Das Muster für reguläre Ausdrücke `\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b` wird entsprechend der folgenden Tabelle interpretiert:

Muster | Beschreibung
------- | ----------- 
`\b` | Der Vergleich beginnt an einer Wortgrenze.
`(?<month>\d{1,2})` | Entsprechung für eine oder zwei Dezimalstellen finden. Dies ist die erfasste Gruppe `month`.
`/` | Entsprechung für den Schrägstrich finden.
`(?<day>\d{1,2})` | Entsprechung für eine oder zwei Dezimalstellen finden. Dies ist die erfasste Gruppe `day`.
`/` | Entsprechung für den Schrägstrich finden.
`(?<year>\d{2,4})` | Entsprechung für zwei bis vier Dezimalstellen finden. Dies ist die erfasste Gruppe `year`.
`\b` | Der Vergleich endet an einer Wortgrenze.
 
Das Muster `${day}-${month}-${year}` definiert die Ersetzungszeichenfolge wie in der folgenden Tabelle gezeigt.

Muster | Beschreibung
------- | ----------- 
`$(day)` | Zeichenfolge hinzufügen, die von der Erfassungsgruppe `day` erfasst wurde.
`-` | Bindestrich hinzufügen.
`$(month)` | Zeichenfolge hinzufügen, die von der Erfassungsgruppe `month` erfasst wurde.
`-` | Bindestrich hinzufügen.
`$(year)` | Zeichenfolge hinzufügen, die von der Erfassungsgruppe `year` erfasst wurde.
 
## <a name="see-also"></a>Siehe auch

[Reguläre Ausdrücke in .NET](regular-expressions.md)

[Beispiele für reguläre Ausdrücke](regex-examples.md)

