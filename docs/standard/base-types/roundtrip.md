---
title: 'Gewusst wie: Roundtrip-Datums- und -Uhrzeitwerte'
description: Roundtrip-Datums- und -Uhrzeitwerte
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 15690f18-1bb9-4bb8-bc11-0b737e2f0859
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: b4bf747faff171e4a90a897e5f7ef442012e7699

---

# <a name="how-to-roundtrip-date-and-time-values"></a>Gewusst wie: Roundtrip-Datums- und -Uhrzeitwerte

In vielen Anwendungen soll ein Datums- und Uhrzeitwert einen bestimmten Zeitpunkt eindeutig identifizieren. In diesem Thema wird gezeigt, wie ein [DateTime](xref:System.DateTime)-Wert und ein [DateTimeOffset](xref:System.DateTimeOffset)-Wert so gespeichert und wiederhergestellt werden, dass der wiederhergestellte Wert denselben Zeitpunkt bezeichnet wie der gespeicherte Wert.

## <a name="to-roundtrip-a-datetime-value"></a>So führen Sie einen Roundtrip für einen DateTime-Wert durch

1. Konvertieren Sie den [DateTime](xref:System.DateTime)-Wert in seine Zeichenfolgendarstellung, indem Sie die [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String))-Methode mit dem Formatbezeichner „o“ aufrufen.

2. Speichern Sie die Zeichenfolgendarstellung des [DateTime](xref:System.DateTime)-Werts in einer Datei, oder übergeben Sie sie über einen Prozess, eine Anwendungsdomäne oder eine Computergrenze.

3. Rufen Sie die Zeichenfolge ab, die den [DateTime](xref:System.DateTime)-Wert darstellt.

4. Rufen Sie die Methode [DateTime.Parse(String, IFormatProvider, DateTimeStyles)](xref:System.DateTime.Parse(System.String,System.IFormatProvider,System.Globalization.DateTimeStyles)) auf, und übergeben Sie [DateTimeStyles.RoundtripKind](xref:System.Globalization.DateTimeStyles.RoundtripKind) als Wert für den *DateTimeStyles*-Parameter.

Das folgende Beispiel veranschaulicht, wie ein Roundtrip für einen [DateTime](xref:System.DateTime)-Wert durchgeführt wird.

```csharp
const string fileName = @".\DateFile.txt";

StreamWriter outFile = new StreamWriter(fileName);

// Save DateTime value.
DateTime dateToSave = DateTime.SpecifyKind(new DateTime(2008, 6, 12, 18, 45, 15), 
                                           DateTimeKind.Local);
string dateString = dateToSave.ToString("o");      
Console.WriteLine("Converted {0} ({1}) to {2}.", 
                  dateToSave.ToString(), 
                  dateToSave.Kind.ToString(), 
                  dateString);      
outFile.WriteLine(dateString);
Console.WriteLine("Wrote {0} to {1}.", dateString, fileName);
outFile.Close();

// Restore DateTime value.
DateTime restoredDate;

StreamReader inFile = new StreamReader(fileName);
dateString = inFile.ReadLine();
inFile.Close();
restoredDate = DateTime.Parse(dateString, null, DateTimeStyles.RoundtripKind);
Console.WriteLine("Read {0} ({2}) from {1}.", restoredDate.ToString(), 
                                              fileName, 
                                              restoredDate.Kind.ToString());
// The example displays the following output:
//    Converted 6/12/2008 6:45:15 PM (Local) to 2008-06-12T18:45:15.0000000-05:00.
//    Wrote 2008-06-12T18:45:15.0000000-05:00 to .\DateFile.txt.
//    Read 6/12/2008 6:45:15 PM (Local) from .\DateFile.txt.
```

```vb
Const fileName As String = ".\DateFile.txt"

Dim outFile As New StreamWriter(fileName)

' Save DateTime value.
Dim dateToSave As Date = DateTime.SpecifyKind(#06/12/2008 6:45:15 PM#, _
                                              DateTimeKind.Local)
Dim dateString As String = dateToSave.ToString("o")      
Console.WriteLine("Converted {0} ({1}) to {2}.", dateToSave.ToString(), _
                  dateToSave.Kind.ToString(), dateString)      
outFile.WriteLine(dateString)
Console.WriteLine("Wrote {0} to {1}.", dateString, fileName)
outFile.Close()   

' Restore DateTime value.
Dim restoredDate As Date

Dim inFile As New StreamReader(fileName)
dateString = inFile.ReadLine()
inFile.Close()
restoredDate = DateTime.Parse(dateString, Nothing, DateTimeStyles.RoundTripKind)
Console.WriteLine("Read {0} ({2}) from {1}.", restoredDate.ToString(), _
                  fileName, restoredDAte.Kind.ToString())
' The example displays the following output:
'    Converted 6/12/2008 6:45:15 PM (Local) to 2008-06-12T18:45:15.0000000-05:00.
'    Wrote 2008-06-12T18:45:15.0000000-05:00 to .\DateFile.txt.
'    Read 6/12/2008 6:45:15 PM (Local) from .\DateFile.txt.
```

Beim Roundtrip eines [DateTime](xref:System.DateTime)-Werts wird durch diese Technik erfolgreich die Uhrzeit für alle Orts- und Weltzeiten beibehalten. Wenn beispielsweise ein lokaler [DateTime](xref:System.DateTime)-Wert auf einem System in der US-Zeitzone Pacific Standard Time gespeichert und auf einem System in der US-Zeitzone Central Standard Time wiederhergestellt wird, liegen das wiederhergestellte Datum und die Uhrzeit zwei Stunden hinter der ursprünglichen Zeit, was dem Zeitunterschied zwischen den beiden Zeitzonen entspricht. Dieses Verfahren ist für nicht spezifizierte Zeiten jedoch nicht notwendigerweise genau. Alle [DateTime](xref:System.DateTime)-Werte, deren [Kind](xref:System.DateTime.Kind)-Eigenschaft [Unspecified](xref:System.DateTimeKind.Unspecified) lautet, werden als lokale Zeiten behandelt. Wenn dies nicht korrekt ist, kann der richtige Zeitpunkt durch [DateTime](xref:System.DateTime) nicht erfolgreich identifiziert werden. Die Umgehung für diese Einschränkung besteht darin, einen Datums- und Zeitwert für den Speicher- und Wiederherstellungsvorgang eng an die entsprechende Zeitzone zu koppeln.

## <a name="to-roundtrip-a-datetimeoffset-value"></a>So führen Sie einen Roundtrip für einen DateTimeOffset-Wert durch

Konvertieren Sie den [DateTimeOffset](xref:System.DateTimeOffset)-Wert in seine Zeichenfolgendarstellung, indem Sie die [DateTimeOffset.ToString(String)](xref:System.DateTimeOffset.ToString(System.String))-Methode mit dem Formatbezeichner „o“ aufrufen.

2. Speichern Sie die Zeichenfolgendarstellung des [DateTimeOffset](xref:System.DateTimeOffset)-Werts in einer Datei, oder übergeben Sie sie über einen Prozess, eine Anwendungsdomäne oder eine Computergrenze.

3. Rufen Sie die Zeichenfolge ab, die den [DateTimeOffset](xref:System.DateTimeOffset)-Wert darstellt.

4. Rufen Sie die Methode [DateTimeOffset.Parse(String, IFormatProvider, DateTimeStyles)](xref:System.DateTimeOffset.Parse(System.String,System.IFormatProvider,System.Globalization.DateTimeStyles)) auf, und übergeben Sie [DateTimeStyles.RoundtripKind](xref:System.Globalization.DateTimeStyles.RoundtripKind) als Wert für den *styles*-Parameter.

Das folgende Beispiel veranschaulicht, wie ein Roundtrip für einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert durchgeführt wird.

```csharp
const string fileName = @".\DateOff.txt";

StreamWriter outFile = new StreamWriter(fileName);

// Save DateTime value.
DateTimeOffset dateToSave = new DateTimeOffset(2008, 6, 12, 18, 45, 15, 
                                               new TimeSpan(7, 0, 0));
string dateString = dateToSave.ToString("o");      
Console.WriteLine("Converted {0} to {1}.", dateToSave.ToString(), 
                  dateString);      
outFile.WriteLine(dateString);
Console.WriteLine("Wrote {0} to {1}.", dateString, fileName);
outFile.Close();

// Restore DateTime value.
DateTimeOffset restoredDateOff;

StreamReader inFile = new StreamReader(fileName);
dateString = inFile.ReadLine();
inFile.Close();
restoredDateOff = DateTimeOffset.Parse(dateString, null, 
                                       DateTimeStyles.RoundtripKind);
Console.WriteLine("Read {0} from {1}.", restoredDateOff.ToString(), 
                  fileName);
// The example displays the following output:
//    Converted 6/12/2008 6:45:15 PM +07:00 to 2008-06-12T18:45:15.0000000+07:00.
//    Wrote 2008-06-12T18:45:15.0000000+07:00 to .\DateOff.txt.
//    Read 6/12/2008 6:45:15 PM +07:00 from .\DateOff.txt.
```

```vb
Const fileName As String = ".\DateOff.txt"

Dim outFile As New StreamWriter(fileName)

' Save DateTime value.
Dim dateToSave As New DateTimeOffset(2008, 6, 12, 18, 45, 15, _
                                     New TimeSpan(7, 0, 0))
Dim dateString As String = dateToSave.ToString("o")      
Console.WriteLine("Converted {0} to {1}.", dateToSave.ToString(), dateString)      
outFile.WriteLine(dateString)
Console.WriteLine("Wrote {0} to {1}.", dateString, fileName)
outFile.Close()   

' Restore DateTime value.
Dim restoredDateOff As DateTimeOffset

Dim inFile As New StreamReader(fileName)
dateString = inFile.ReadLine()
inFile.Close()
restoredDateOff = DateTimeOffset.Parse(dateString, Nothing, DateTimeStyles.RoundTripKind)
Console.WriteLine("Read {0} from {1}.", restoredDateOff.ToString(), fileName)
' The example displays the following output:
'    Converted 6/12/2008 6:45:15 PM +07:00 to 2008-06-12T18:45:15.0000000+07:00.
'    Wrote 2008-06-12T18:45:15.0000000+07:00 to .\DateOff.txt.
'    Read 6/12/2008 6:45:15 PM +07:00 from .\DateOff.txt.
```

Durch diese Technik wird ein [DateTimeOffset](xref:System.DateTimeOffset)-Wert immer eindeutig als ein einziger Zeitpunkt identifiziert. Der Wert kann dann durch Aufrufen der [DateTimeOffset.ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime)-Methode in die koordinierte Weltzeit (UTC) konvertiert werden, oder er kann durch Aufrufen der Methode [DateTimeOffset.ToOffset](xref:System.DateTimeOffset.ToOffset(System.TimeSpan)) oder der Methode „[TimeZoneInfo.ConvertTime(DateTimeOffset TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)“ in die Uhrzeit einer bestimmten Zeitzone konvertiert werden. Die wesentliche Einschränkung dieser Technik liegt darin, dass die Datums- und Uhrzeitarithmetik möglicherweise keine genauen Ergebnisse für die jeweilige Zeitzone liefert, wenn sie an einem [DateTimeOffset](xref:System.DateTimeOffset)-Wert durchgeführt wird, der die Zeit in einer bestimmten Zeitzone darstellt. Der Grund hierfür ist, dass ein [DateTimeOffset](xref:System.DateTimeOffset)-Wert bei seiner Instanziierung von seiner Zeitzone losgelöst wird. Daher können die Anpassungsregeln für diese Zeitzone bei Datums- und Uhrzeitberechnungen nicht mehr angewendet werden. Sie können dieses Problem umgehen, indem Sie einen benutzerdefinierten Typ definieren, der sowohl einen Datums- und Uhrzeitwert als auch die dazugehörige Zeitzone enthält.

## <a name="see-also"></a>Siehe auch

[Durchführen von Formatierungsvorgängen](performing-formatting-operations.md)

[Standardformatzeichenfolgen für Datum und Uhrzeit](standard-datetime.md)




<!--HONumber=Nov16_HO3-->


