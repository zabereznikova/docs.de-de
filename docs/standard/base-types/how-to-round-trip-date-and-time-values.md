---
title: 'Gewusst wie: Roundtrip-Datums- und -Uhrzeitwerte'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- round-trip date and time values
- dates [.NET Framework], round-trip values
- time zones [.NET Framework], round-trip date and time values
- time [.NET Framework], round-trip values
- formatting strings [.NET Framework], round-trip values
ms.assetid: b609b277-edc6-4c74-b03e-ea73324ecbdb
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 515a29e279cfa8fc100e0612fc19df7abc6a3b36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-round-trip-date-and-time-values"></a>Gewusst wie: Roundtrip-Datums- und -Uhrzeitwerte
In vielen Anwendungen soll ein Datums- und Uhrzeitwert einen bestimmten Zeitpunkt eindeutig identifizieren. In diesem Thema wird gezeigt, wie zum Speichern und Wiederherstellen einer <xref:System.DateTime> Wert, einen <xref:System.DateTimeOffset> Wert und einen Wert für Datum und Uhrzeit mit Time zone Informationen, damit die wiederhergestellte Wert zur gleiche Zeit wie der gespeicherte Wert identifiziert.  
  
### <a name="to-round-trip-a-datetime-value"></a>So führen Sie einen Roundtrip für einen DateTime-Wert durch  
  
1.  Konvertieren der <xref:System.DateTime> Wert in seine Zeichenfolgendarstellung durch Aufrufen der <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> Methode mit dem Formatbezeichner "o".  
  
2.  Speichern Sie die Zeichenfolgendarstellung der <xref:System.DateTime> Wert in eine Datei, oder es über einen Prozess, Anwendungsdomäne oder Computergrenze übergeben.  
  
3.  Rufen Sie die Zeichenfolge, die stellt die <xref:System.DateTime> Wert.  
  
4.  Rufen Sie die <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> Methode, und übergeben <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> als Wert für die `styles` Parameter.  
  
 Im folgende Beispiel wird veranschaulicht, wie ein Roundtrip eine <xref:System.DateTime> Wert.  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#1)]
 [!code-vb[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#1)]  
  
 Bei der Round-Tripping ein <xref:System.DateTime> Wert dieses Verfahren erfolgreich die Zeit für alle Zeitangaben von lokaler und universeller beibehalten. Angenommen, eine lokale <xref:System.DateTime> Wert wird auf einem System in den USA gespeichert. Pacific Standard Time gespeichert und auf einem System in der US-Zeitzone Central Standard Time wiederhergestellt wird, liegen das wiederhergestellte Datum und die Uhrzeit zwei Stunden hinter der ursprünglichen Zeit, was dem Zeitunterschied zwischen den beiden Zeitzonen entspricht. Dieses Verfahren ist für nicht spezifizierte Zeiten jedoch nicht notwendigerweise genau. Alle <xref:System.DateTime> Werte, deren <xref:System.DateTime.Kind%2A> Eigenschaft <xref:System.DateTimeKind.Unspecified> behandelt, als ob sie lokalen Zeiten sind. Wenn dies nicht der Fall ist die <xref:System.DateTime> wird nicht erfolgreich identifizieren die richtigen Zeitpunkts. Die Umgehung für diese Einschränkung besteht darin, einen Datums- und Zeitwert für den Speicher- und Wiederherstellungsvorgang eng an die entsprechende Zeitzone zu koppeln.  
  
### <a name="to-round-trip-a-datetimeoffset-value"></a>So führen Sie einen Roundtrip für einen DateTimeOffset-Wert durch  
  
1.  Konvertieren der <xref:System.DateTimeOffset> Wert in seine Zeichenfolgendarstellung durch Aufrufen der <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> Methode mit dem Formatbezeichner "o".  
  
2.  Speichern Sie die Zeichenfolgendarstellung der <xref:System.DateTimeOffset> Wert in eine Datei, oder es über einen Prozess, Anwendungsdomäne oder Computergrenze übergeben.  
  
3.  Rufen Sie die Zeichenfolge, die stellt die <xref:System.DateTimeOffset> Wert.  
  
4.  Rufen Sie die <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> Methode, und übergeben <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> als Wert für die `styles` Parameter.  
  
 Im folgende Beispiel wird veranschaulicht, wie ein Roundtrip eine <xref:System.DateTimeOffset> Wert.  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#2)]
 [!code-vb[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#2)]  
  
 Diese Technik ist immer eindeutig identifiziert einen <xref:System.DateTimeOffset> Wert als einen einzigen Zeitpunkt. Der Wert kann dann in die koordinierte Weltzeit (UTC) konvertiert werden, durch Aufrufen der <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType> -Methode, oder er kann in die Zeit in einer bestimmten Zeitzone konvertiert werden, durch Aufrufen der <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=nameWithType> oder <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> Methode. Die wichtigste Einschränkung für diese Technik ist dieses Datum und die Uhrzeit arithmetischen, beim Ausführen auf einer <xref:System.DateTimeOffset> Wert, der die Zeit in einer bestimmten Zeitzone darstellt, möglicherweise nicht präzise Ergebnisse für diese Zeitzone erstellt. Grund hierfür ist, wenn ein <xref:System.DateTimeOffset> Wert instanziiert wird, wird es seiner Zeitzone aufgehoben. Daher können die Anpassungsregeln für diese Zeitzone bei Datums- und Uhrzeitberechnungen nicht mehr angewendet werden. Sie können dieses Problem umgehen, indem Sie einen benutzerdefinierten Typ definieren, der sowohl einen Datums- und Uhrzeitwert als auch die dazugehörige Zeitzone enthält.  
  
### <a name="to-round-trip-a-date-and-time-value-with-its-time-zone"></a>Für den roundtripvorgang einen Wert für Datum und Uhrzeit mit seiner Zeitzone  
  
1.  Definieren Sie eine Klasse oder eine Struktur mit zwei Feldern. Das erste Feld handelt es sich um eine <xref:System.DateTime> oder ein <xref:System.DateTimeOffset> Objekt und das zweite ist ein <xref:System.TimeZoneInfo> Objekt. Im folgende Beispiel wird eine einfache Version eines solchen Typs.  
  
     [!code-csharp[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#3)]
     [!code-vb[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#3)]  
  
2.  Markieren Sie die Klasse mit dem <xref:System.SerializableAttribute> Attribut.  
  
3.  Serialisiert das Objekt mit der <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType> Methode.  
  
4.  Wiederherstellen, das mit der <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A> Methode.  
  
5.  Umgewandelt (in c#) oder konvertieren Sie das deserialisierte Objekt (in Visual Basic) aus, um ein Objekt des entsprechenden Typs.  
  
 Im folgende Beispiel wird veranschaulicht, wie für den roundtripvorgang ein Objekt, das sowohl Datum und Uhrzeit und Zeitzone Informationen speichert.  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#4)]
 [!code-vb[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#4)]  
  
 Diese Technik sollte immer eindeutig richtigen Zeitpunkt Standardzeitintervall sowohl vor und nach dem er gespeichert und wiederhergestellt, die Implementierung des kombinierten Datum und Uhrzeit und Zeitzone Objekts nicht den Date-Wert mit synchron sind zulässig, entsprechen die der Wert der Zeitzone.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Diese Beispiele erfordern Folgendes:  
  
-   Die folgenden Namespaces importiert werden, mit den C#- `using` Anweisungen oder [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] `Imports` Anweisungen:  
  
    -   <xref:System>(Nur c#).  
  
    -   <xref:System.Globalization?displayProperty=nameWithType>.  
  
    -   <xref:System.IO?displayProperty=nameWithType>.  
  
    -   <xref:System.Runtime.Serialization?displayProperty=nameWithType>.  
  
    -   <xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=nameWithType>.  
  
-   Ein Verweis auf "System.Core.dll".  
  
-   Jedes Codebeispiel, außer die `DateInTimeZone` -Klasse, in einer Klasse oder Visual Basic-Modul enthalten, mit Methoden umschlossen und aus aufgerufen werden sollte die `Main` Methode.  
  
## <a name="see-also"></a>Siehe auch  
 [Durchführen von Formatierungsvorgängen](../../../docs/standard/base-types/performing-formatting-operations.md)  
 [Auswählen zwischen „DateTime“, „DateTimeOffset“, „TimeSpan“ und „TimeZoneInfo“](../../../docs/standard/datetime/choosing-between-datetime.md)  
 [Standard Date and Time Format Strings](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)
