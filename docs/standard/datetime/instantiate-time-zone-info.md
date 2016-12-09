---
title: 'Gewusst wie: Instanziieren eines TimeZoneInfo-Objekts'
description: Instanziieren eines TimeZoneInfo-Objekts
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: bff137e5-d550-44c3-b460-b3f2dabd4035
translationtype: Human Translation
ms.sourcegitcommit: c40c28da09e8a122b542463c197196c82c81dd19
ms.openlocfilehash: 1c619cf6bd150e009367b43d1d83fa1713ec2690

---

# <a name="how-to-instantiate-a-timezoneinfo-object"></a>Gewusst wie: Instanziieren eines TimeZoneInfo-Objekts

Die gängigste Methode zum Instanziieren eines [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekts ist es, Informationen darüber vom Betriebssystem abzurufen. In diesem Thema wird erläutert, wie ein [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekt vom lokalen System aus instanziiert wird.

## <a name="to-instantiate-a-timezoneinfo-object"></a>So instanziieren Sie ein TimeZoneInfo-Objekt

1. Deklarieren Sie ein [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekt.

2. Rufen Sie die `static` (`Shared` in Visual Basic) [TimeZoneInfo.FindSystemTimeZoneById](xref:System.TimeZoneInfo.FindSystemTimeZoneById(System.String))-Methode auf.

3. Verarbeiten Sie alle von der Methode ausgelösten Ausnahmen.

## <a name="example"></a>Beispiel

Der folgende Code ruft ein [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekt ab, das die Zeitzone „Eastern Standard Time“ darstellt und die der Ortszeit entsprechende „Eastern Standard Time“ anzeigt.

```csharp
DateTime timeNow = DateTime.Now;
try
{
   TimeZoneInfo easternZone = TimeZoneInfo.FindSystemTimeZoneById("Eastern Standard Time");
   DateTime easternTimeNow = TimeZoneInfo.ConvertTime(timeNow, TimeZoneInfo.Local, 
                                                   easternZone);
   Console.WriteLine("{0} {1} corresponds to {2} {3}.",
                     timeNow, 
                     TimeZoneInfo.Local.IsDaylightSavingTime(timeNow) ?
                               TimeZoneInfo.Local.DaylightName : 
                               TimeZoneInfo.Local.StandardName,
                     easternTimeNow, 
                     easternZone.IsDaylightSavingTime(easternTimeNow) ?
                                 easternZone.DaylightName : 
                                 easternZone.StandardName);
}
// Handle exception
//
// As an alternative to simply displaying an error message, an alternate Eastern
// Standard Time TimeZoneInfo object could be instantiated here either by restoring
// it from a serialized string or by providing the necessary data to the
// CreateCustomTimeZone method.
catch (InvalidTimeZoneException)
{
   Console.WriteLine("The Eastern Standard Time Zone contains invalid or missing data.");
}
catch (SecurityException)
{
   Console.WriteLine("The application lacks permission to read time zone information from the registry.");
}
catch (OutOfMemoryException)
{
   Console.WriteLine("Not enough memory is available to load information on the Eastern Standard Time zone.");
}
// If we weren't passing FindSystemTimeZoneById a literal string, we also 
// would handle an ArgumentNullException.
```

```vb
Dim timeNow As Date = Date.Now
Try
   Dim easternZone As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById("Eastern Standard Time")
   Dim easternTimeNow As Date = TimeZoneInfo.ConvertTime(timeNow, TimeZoneInfo.Local, easternZone)
   Console.WriteLine("{0} {1} corresponds to {2} {3}.", _
                     timeNow, _
                     IIf(TimeZoneInfo.Local.IsDaylightSavingTime(timeNow), _
                         TimeZoneInfo.Local.DaylightName, TimeZoneInfo.Local.StandardName), _
                     easternTimeNow, _
                     IIf(easternZone.IsDaylightSavingTime(easternTimeNow), _
                         easternZone.DaylightName, easternZone.StandardName))
' Handle exception
'
' As an alternative to simply displaying an error message, an alternate Eastern
' Standard Time TimeZoneInfo object could be instantiated here either by restoring
' it from a serialized string or by providing the necessary data to the
' CreateCustomTimeZone method.
Catch e As InvalidTimeZoneException
   Console.WriteLine("The Eastern Standard Time Zone contains invalid or missing data.")   
Catch e As SecurityException
   Console.WriteLine("The application lacks permission to read time zone information from the registry.")
Catch e As OutOfMemoryException
   Console.WriteLine("Not enough memory is available to load information on the Eastern Standard Time zone.")
' If we weren't passing FindSystemTimeZoneById a literal string, we also 
' would handle an ArgumentNullException.
End
``` 

Der einzige Parameter der Methode, [TimeZoneInfo.FindSystemTimeZoneById](xref:System.TimeZoneInfo.FindSystemTimeZoneById(System.String)), ist der Bezeichner der Zeitzone, die abgerufen werden soll; er entspricht der [TimeZoneInfo.Id](xref:System.TimeZoneInfo.Id)-Eigenschaft des Objekts. Der Zeitzonenbezeichner ist ein Schlüsselfeld, das die Zeitzone eindeutig identifiziert. Während die meisten Schlüssel relativ kurz sind, ist der Zeitzonenbezeichner vergleichsweise lang. In den meisten Fällen entspricht der dazugehörige Wert der [StandardName](xref:System.TimeZoneInfo.StandardName)-Eigenschaft eines [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekts, das zum Bereitstellen des Namens der Standardzeit für die Zeitzone verwendet wird. Es gibt jedoch auch Ausnahmen. Die beste Möglichkeit, um sicherzustellen, dass Sie einen gültigen Bezeichner angeben, besteht darin, die auf Ihrem System verfügbaren Zeitzonen aufzulisten und die Bezeichner der darin enthaltenen Zeitzonen zur Kenntnis zu nehmen. Eine Abbildung finden Sie unter [Gewusst wie: Auflisten der auf einem Computer vorhandenen Zeitzonen](enumerate-time-zones.md). Das Thema [Suchen der auf einem lokalen System definierten Zeitzonen](finding-the-time-zones-on-local-system.md) enthält auch eine Liste ausgewählter Zeitzonenbezeichner.

Wenn die Zeitzone gefunden wird, gibt die Methode das zugehörige [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekt zurück. Wenn die Zeitzone gefunden wird, aber die zugehörigen Daten beschädigt oder unvollständig sind, löst die Methode eine [InvalidTimeZoneException](xref:System.InvalidTimeZoneException) aus. 

## <a name="see-also"></a>Siehe auch

[Datumsangaben, Uhrzeiten und Zeitzonen](index.md)

[Suchen der in einem lokalen System definierten Zeitzonen](finding-the-time-zones-on-local-system.md)


<!--HONumber=Nov16_HO3-->


