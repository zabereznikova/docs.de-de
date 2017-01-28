---
title: "Gewusst wie: Auflösen von mehrdeutigen Zeiten"
description: "Auflösen von mehrdeutigen Zeiten"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/16/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: e86050c6-d16d-405e-8bba-7205945c9a81
translationtype: Human Translation
ms.sourcegitcommit: c40c28da09e8a122b542463c197196c82c81dd19
ms.openlocfilehash: b31ea18cd7a7e32863f384cb279dc715fd62b3df

---

# <a name="how-to-resolve-ambiguous-times"></a>Gewusst wie: Auflösen von mehrdeutigen Zeiten

Eine mehrdeutige Zeit ist eine Zeit, die mehreren koordinierten Weltzeiten (UTC) zugeordnet werden kann. Dies ist der Fall, wenn die Uhrzeit umgestellt wird, beispielsweise während des Übergangs von der Sommerzeit einer Zeitzone auf die Standardzeit. Bei der Verarbeitung einer mehrdeutigen Zeit haben Sie eine der folgenden Möglichkeiten:

* Treffen Sie eine Annahme darüber, wie die Zeit UTC zuzuordnen ist. Beispielsweise können Sie davon ausgehen, dass eine mehrdeutige Zeit immer in der Standardzeit der Zeitzone ausgedrückt wird.

* Wenn die mehrdeutige Zeit ein vom Benutzer eingegebenes Datenelement ist, können Sie es dem Benutzer überlassen, die Mehrdeutigkeit aufzulösen.

Dieser Artikel zeigt, wie eine mehrdeutige Zeit durch die Annahme aufgelöst werden kann, dass es sich um die Standardzeit der Zeitzone handelt.

## <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a>So ordnen Sie eine mehrdeutige Zeit der Standardzeit einer Zeitzone zu

1. Rufen Sie die Methode [System.TimeZoneInfo.IsAmbiguousTime(DateTime)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTime)) oder die Methode [System.TimeZoneInfo.IsAmbiguousTime(DateTimeOffset)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTimeOffset)) auf, um zu ermitteln, ob die Zeit mehrdeutig ist.

2. Wenn die Zeit mehrdeutig ist, subtrahieren Sie die Zeit von dem [TimeSpan](xref:System.TimeSpan)-Objekt, das von der [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset)-Eigenschaft der Zeitzone zurückgegeben wird.

3. Rufen Sie die `static`-Methode (`Shared` in Visual Basic) [SpecifyKind](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) auf, um die [Kind](xref:System.DateTime.Kind)-Eigenschaft des UTC-Datums- und Uhrzeitwerts auf [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) festzulegen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht die Konvertierung eines mehrdeutigen [DateTime](xref:System.DateTime)-Werts in UTC, indem angenommen wird, dass er die Standardzeit der lokalen Zeitzone darstellt. 

```csharp
private DateTime ResolveAmbiguousTime(DateTime ambiguousTime)
{
   // Time is not ambiguous
   if (! TimeZoneInfo.Local.IsAmbiguousTime(ambiguousTime))
   { 
      return ambiguousTime; 
   }
   // Time is ambiguous
   else
   {
      DateTime utcTime = DateTime.SpecifyKind(ambiguousTime - TimeZoneInfo.Local.BaseUtcOffset, 
                                              DateTimeKind.Utc);      
      Console.WriteLine("{0} local time corresponds to {1} {2}.", 
                        ambiguousTime, utcTime, utcTime.Kind.ToString());
      return utcTime;            
   }   
}
```

```vb
Private Function ResolveAmbiguousTime(ambiguousTime As Date) As Date
   ' Time is not ambiguous
   If Not TimeZoneInfo.Local.IsAmbiguousTime(ambiguousTime) Then 
      Return TimeZoneInfo.ConvertTimeToUtc(ambiguousTime) 
   ' Time is ambiguous
   Else
      Dim utcTime As Date = DateTime.SpecifyKind(ambiguousTime - TimeZoneInfo.Local.BaseUtcOffset, DateTimeKind.Utc)      
      Console.WriteLine("{0} local time corresponds to {1} {2}.", ambiguousTime, utcTime, utcTime.Kind.ToString())
      Return utcTime            
   End If   
End Function
```

Das Beispiel besteht aus einer Methode namens `ResolveAmbiguousTime`, die ermittelt, ob der ihr übergebene [DateTime](xref:System.DateTime)-Wert mehrdeutig ist. Wenn der Wert mehrdeutig ist, gibt die Methode einem [DateTime](xref:System.DateTime)-Wert zurück, der die entsprechende UTC-Zeit darstellt. Die Methode führt diese Konvertierung durch, indem sie den Wert der [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset)-Eigenschaft der lokalen Zeitzone von der Ortszeit subtrahiert. 

Normalerweise wird eine mehrdeutige Zeit durch Aufrufen der [GetAmbiguousTimeOffsets](xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets(System.DateTime))-Methode verarbeitet, um ein Array von [TimeSpan](xref:System.TimeSpan)-Objekten abzurufen, die die möglichen UTC-Abweichungen der mehrdeutigen Zeit enthalten. In diesem Beispiel wird jedoch die willkürliche Annahme getroffen, dass eine mehrdeutige Zeit immer der Standardzeit der Zeitzone zugeordnet werden soll. Die [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset)-Eigenschaft gibt die Abweichung zwischen UTC und der Standardzeit einer Zeitzone zurück.

## <a name="see-also"></a>Siehe auch

[Datumsangaben, Uhrzeiten und Zeitzonen](index.md)

[Gewusst wie: Auflösen mehrdeutiger Zeiten durch den Benutzer](let-users-resolve-ambiguous-times.md)




<!--HONumber=Nov16_HO3-->


