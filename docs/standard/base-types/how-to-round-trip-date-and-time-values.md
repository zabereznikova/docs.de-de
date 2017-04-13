---
title: "Gewusst wie: Roundtrip-Datums- und -Uhrzeitwerte | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Roundtrip-Datums- und -Uhrzeitwerte"
  - "Datumsangaben [.NET Framework], Roundtripwerte"
  - "Zeitzonen [.NET Framework], Roundtrip-Datums- und -Uhrzeitwerte"
  - "Zeit [.NET Framework], Roundtripwerte"
  - "Formatzeichenfolgen [.NET Framework], Roundtripwerte"
ms.assetid: b609b277-edc6-4c74-b03e-ea73324ecbdb
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Roundtrip-Datums- und -Uhrzeitwerte
In vielen Anwendungen soll durch einen Datums\- und Uhrzeitwert ein bestimmter Zeitpunkt eindeutig identifiziert werden.  In diesem Thema wird dargestellt, wie ein <xref:System.DateTime>\-Wert, ein <xref:System.DateTimeOffset>\-Wert und ein Datums\- und Uhrzeitwert mit Zeitzoneninformationen so gespeichert und wiederhergestellt werden, dass der wiederhergestellte Wert dieselbe Zeit wie der gespeicherte Wert identifiziert.  
  
### Herstellen eines Roundtrips für einen DateTime\-Wert  
  
1.  Konvertieren Sie den <xref:System.DateTime>\-Wert in seine Zeichenfolgedarstellung, indem Sie die <xref:System.DateTime.ToString%28System.String%29?displayProperty=fullName>\-Methode mit dem "o"\-Formatbezeichner aufrufen.  
  
2.  Speichern Sie die Zeichenfolgedarstellung des <xref:System.DateTime>\-Werts in eine Datei, oder übergeben Sie sie an einen Prozess, eine Anwendungsdomäne oder einen Computer.  
  
3.  Rufen Sie die Zeichenfolge ab, die den <xref:System.DateTime>\-Wert darstellt.  
  
4.  Rufen Sie die <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=fullName>\-Methode auf, und übergeben Sie <xref:System.Globalization.DateTimeStyles?displayProperty=fullName> als Wert des `styles`\-Parameters.  
  
 Das folgende Beispiel zeigt, wie ein Roundtrip für einen <xref:System.DateTime>\-Wert erstellt wird.  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#1)]
 [!code-vb[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#1)]  
  
 Beim Erstellen eines Roundtrips für einen <xref:System.DateTime>\-Wert kann mit dieser Technik erfolgreich die Uhrzeit für alle lokalen und Weltzeitangaben beibehalten werden.  Wenn beispielsweise ein lokaler <xref:System.DateTime>\-Wert in einem System in der Zeitzone Pacific Normalzeit gespeichert wird und in einem System in der Zeitzone Central Normalzeit wiederhergestellt wird, reagiert das wiederhergestellte Datum und Uhrzeit zwei Stunden später als die ursprüngliche Zeit, was den Zeitunterschied zwischen diesen beiden Zeitzonen widerspiegelt.  Diese Technik ist jedoch nicht notwendigerweise genau für nicht spezifizierte Zeiten.  Alle <xref:System.DateTime>\-Werte, deren <xref:System.DateTime.Kind%2A>\-Eigenschaft <xref:System.DateTimeKind> ist, werden als Ortszeiten behandelt.  Wenn dies nicht der Fall ist, gibt <xref:System.DateTime>nicht erfolgreich den richtigen Zeitpunkt wieder.  Diese Einschränkung kann umgangen werden, indem ein Datums\- und Zeitwert für den Speicherungs\- und Wiederherstellungsvorgang eng mit seiner Zeitzone verknüpft wird.  
  
### Herstellen eines Roundtrips für einen DateTimeOffset\-Wert  
  
1.  Konvertieren Sie den <xref:System.DateTimeOffset>\-Wert in seine Zeichenfolgedarstellung, indem Sie die <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=fullName>\-Methode mit dem "o"\-Formatbezeichner aufrufen.  
  
2.  Speichern Sie die Zeichenfolgedarstellung des <xref:System.DateTimeOffset>\-Werts in eine Datei, oder übergeben Sie sie an einen Prozess, eine Anwendungsdomäne oder einen Computer.  
  
3.  Rufen Sie die Zeichenfolge ab, die den <xref:System.DateTimeOffset>\-Wert darstellt.  
  
4.  Rufen Sie die <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=fullName>\-Methode auf, und übergeben Sie <xref:System.Globalization.DateTimeStyles?displayProperty=fullName> als Wert des `styles`\-Parameters.  
  
 Das folgende Beispiel zeigt, wie ein Roundtrip für einen <xref:System.DateTimeOffset>\-Wert erstellt wird.  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#2)]
 [!code-vb[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#2)]  
  
 Mit dieser Technik wird ein <xref:System.DateTimeOffset>\-Wert stets eindeutig als ein bestimmter Zeitpunkt identifiziert.  Der Wert kann dann in die koordinierte Weltzeit \(Coordinated Universal Time, UTC\) konvertiert werden, indem die <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=fullName>\-Methode aufgerufen wird, oder er kann in die Uhrzeit einer bestimmten Zeitzone konvertiert werden, indem die <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=fullName>\-Methode oder die <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=fullName>\-Methode aufgerufen wird.  Diese Technik wird im Wesentlichen nur dadurch eingeschränkt, dass die durch die Arithmetik von Datum und Uhrzeit, wenn sie für einen <xref:System.DateTimeOffset>\-Wert ausgeführt wird, der die Uhrzeit in einer bestimmten Zeitzone darstellt, möglicherweise keine präzisen Ergebnisse für diese Zeitzone erstellt.  Das liegt daran, dass beim Instantiieren eines <xref:System.DateTimeOffset>\-Werts die Zuordnung dieses Werts zu seiner Zeitzone aufgehoben wird.  Daher können die Anpassungsregeln dieser Zeitzone nicht mehr angewendet werden, wenn Sie Datums\- und Uhrzeitberechnungen durchführen.  Sie können dieses Problem umgehen, indem Sie einen benutzerdefinierten Typ definieren, der einen Datums\- und einen Uhrzeitwert sowie die dazugehörige Zeitzone umfasst.  
  
### So erstellen Sie einen Roundtrip für einen Datums\- und Uhrzeitwert mit seiner Zeitzone  
  
1.  Definieren Sie eine Klasse oder eine Struktur mit zwei Feldern.  Das erste Feld ist entweder ein <xref:System.DateTime>\-Objekt oder ein <xref:System.DateTimeOffset>\-Objekt, und das zweite Feld ist ein <xref:System.TimeZoneInfo>\-Objekt.  Das folgende Beispiel ist die einfache Version eines solchen Typs.  
  
     [!code-csharp[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#3)]
     [!code-vb[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#3)]  
  
2.  Markieren Sie die Klasse mit dem <xref:System.SerializableAttribute>\-Attribut.  
  
3.  Serialisieren Sie das Objekt mit der <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=fullName>\-Methode.  
  
4.  Stellen Sie das Objekt mit der <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A>\-Methode wieder her.  
  
5.  Wandeln Sie das deserialisierte Objekt in ein Objekt des richtigen Typs um \(in C\#\) oder konvertieren Sie es \(in Visual Basic\).  
  
 Das folgenden Beispiel veranschaulicht einen Roundtrip für ein Objekt, das Datums\- und Uhrzeitinformationen und Zeitzoneninformationen speichert.  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#4)]
 [!code-vb[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#4)]  
  
 Diese Technik sollte immer eindeutig den richtigen Zeitpunkt vor und nach dem Speichern und Wiederherstellen widerspiegeln, unter der Voraussetzung, dass die Implementierung des kombinierten Datums\-, Uhrzeit\- und Zeitzonen\-Objekts es nicht zulässt, dass der Datumswert nicht mehr mit dem Zeitzonenwert synchron ist.  
  
## Kompilieren des Codes  
 Für diese Beispiele gelten folgende Voraussetzungen:  
  
-   Dass die folgenden Namespaces mit C\#\-`using`\-Anweisungen oder [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]`Imports`\-Anweisungen importiert werden:  
  
    -   <xref:System> \(nur C\#\).  
  
    -   <xref:System.Globalization?displayProperty=fullName>.  
  
    -   <xref:System.IO?displayProperty=fullName>.  
  
    -   <xref:System.Runtime.Serialization?displayProperty=fullName>.  
  
    -   <xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=fullName>.  
  
-   Ein Projektverweis auf System.Core.dll.  
  
-   Jedes Codebeispiel, mit Ausnahme der `DateInTimeZone`\-Klasse, sollte in eine Klasse oder ein Visual Basic\-Modul eingeschlossen werden, mit Methoden umschlossen werden und von der `Main`\-Methode aufgerufen werden.  
  
## Siehe auch  
 [Durchführen von Formatierungsvorgängen](../../../docs/standard/base-types/performing-formatting-operations.md)   
 [Auswählen zwischen "DateTime", "DateTimeOffset", "TimeSpan" und "TimeZoneInfo"](../../../docs/standard/datetime/choosing-between-datetime.md)   
 [Standard\-Formatzeichenfolgen für Datum und Uhrzeit](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)