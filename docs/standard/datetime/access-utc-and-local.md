---
title: 'Gewusst wie: Zugreifen auf die vordefinierte UTC und lokale Zeitzonenobjekte'
description: 'Gewusst wie: Zugreifen auf die vordefinierte UTC und lokale Zeitzonenobjekte'
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/11/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 13454d47-d957-421b-9ecd-940058b8835e
translationtype: Human Translation
ms.sourcegitcommit: c40c28da09e8a122b542463c197196c82c81dd19
ms.openlocfilehash: ab419cf365b61399ea41e99c15e276584ad0db31

---

# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a>Gewusst wie: Zugreifen auf die vordefinierte UTC und lokale Zeitzonenobjekte

Die Klasse [System.TimeZoneInfo](xref:System.TimeZoneInfo) verfügt über zwei Eigenschaften – `Utc` und `Local` – die Ihrem Code den Zugriff auf vordefinierte Zeitzonenobjekte ermöglichen. In diesem Thema wird der Zugriff auf die `TimeZoneInfo`-Objekte erläutert, die von diesen Eigenschaften zurückgegeben werden.

## <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a>So greifen Sie auf das TimeZoneInfo-Objekt für die koordinierte Weltzeit (UTC) zu

1. Verwenden Sie die **static**-Eigenschaft (**Shared** in Visual Basic) [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) für den Zugriff auf die koordinierte Weltzeit.

2. Anstatt das von der Eigenschaft zurückgegebene [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekt einer Objektvariablen zuzuweisen, fahren Sie fort, indem Sie mit der Eigenschaft [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) auf die koordinierte Weltzeit zugreifen.


## <a name="to-access-the-local-time-zone"></a>So greifen Sie auf die lokale Zeitzone zu

1. Verwenden Sie die **static**-Eigenschaft (**Shared** in Visual Basic) [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) für den Zugriff auf die lokale Systemzeitzone.

2. Anstatt das von der Eigenschaft zurückgegebene [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekt einer Objektvariablen zuzuweisen, fahren Sie fort, indem Sie mit der Eigenschaft [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) auf die lokale Zeitzone zugreifen.

## <a name="example"></a>Beispiel

Im folgenden Code werden die Eigenschaften [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) und [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) verwendet,um eine Uhrzeit aus der US-amerikanischen und kanadischen Eastern Normalzeit zu konvertieren, sowie den Namen der Zeitzone auf der Konsole anzuzeigen.

```csharp
// Create Eastern Standard Time value and TimeZoneInfo object      
DateTime estTime = new DateTime(2007, 1, 1, 00, 00, 00);
string timeZoneName = "Eastern Standard Time";
try
{
   TimeZoneInfo est = TimeZoneInfo.FindSystemTimeZoneById(timeZoneName);

   // Convert EST to local time
   DateTime localTime = TimeZoneInfo.ConvertTime(estTime, est, TimeZoneInfo.Local);
   Console.WriteLine("At {0} {1}, the local time is {2} {3}.", 
           estTime, 
           est, 
           localTime, 
           TimeZoneInfo.Local.IsDaylightSavingTime(localTime) ?
                     TimeZoneInfo.Local.DaylightName : 
                     TimeZoneInfo.Local.StandardName);

   // Convert EST to UTC
   DateTime utcTime = TimeZoneInfo.ConvertTime(estTime, est, TimeZoneInfo.Utc);
   Console.WriteLine("At {0} {1}, the time is {2} {3}.", 
           estTime, 
           est, 
           utcTime, 
           TimeZoneInfo.Utc.StandardName);
}
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("The {0} zone cannot be found in the registry.", 
                     timeZoneName);
}
catch (InvalidTimeZoneException)
{
   Console.WriteLine("The registry contains invalid data for the {0} zone.", 
                     timeZoneName);
}
```

```vb
' Create Eastern Standard Time value and TimeZoneInfo object      
Dim estTime As Date = #01/01/2007 00:00:00#
Dim timeZoneName As String = "Eastern Standard Time"
Try
   Dim est As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById(timeZoneName)

   ' Convert EST to local time
   Dim localTime As Date = TimeZoneInfo.ConvertTime(estTime, est, TimeZoneInfo.Local)
   Console.WriteLine("At {0} {1}, the local time is {2} {3}.", _
           estTime, _
           est, _
           localTime, _
           IIf(TimeZoneInfo.Local.IsDaylightSavingTime(localTime), _
               TimeZoneInfo.Local.DaylightName, _
               TimeZoneInfo.Local.StandardName))

   ' Convert EST to UTC
   Dim utcTime As Date = TimeZoneInfo.ConvertTime(estTime, est, TimeZoneInfo.Utc)
   Console.WriteLine("At {0} {1}, the time is {2} {3}.", _
           estTime, _
           est, _
           utcTime, _
           TimeZoneInfo.Utc.StandardName)
Catch e As TimeZoneNotFoundException
   Console.WriteLine("The {0} zone cannot be found in the registry.", _
                     timeZoneName)
Catch e As InvalidTimeZoneException
   Console.WriteLine("The registry contains invalid data for the {0} zone.", _
                     timeZoneName)
End Try
```

Sie sollten stets mit der Eigenschaft [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) auf die lokale Zeitzone zugreifen, anstatt die lokale Zeitzone einer [TimeZoneInfo](xref:System.TimeZoneInfo)-Objektvariablen zuzuweisen. Ebenso sollten Sie stets mit der Eigenschaft [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) auf die koordinierte Weltzeit zugreifen, anstatt die UTC-Zone einer [TimeZoneInfo](xref:System.TimeZoneInfo)-Objektvariablen zuzuweisen. Dies verhindert, dass die [TimeZoneInfo](xref:System.TimeZoneInfo)-Objektvariable durch eine externe Methode ungültig gemacht wird.


## <a name="see-also"></a>Siehe auch

[Datumsangaben, Uhrzeiten und Zeitzonen](index.md)

[Suchen der in einem lokalen System definierten Zeitzonen](finding-the-time-zones-on-local-system.md)



<!--HONumber=Nov16_HO3-->


