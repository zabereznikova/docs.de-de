---
title: 'Vorgehensweise: Roundtrip-Datums- und -Uhrzeitwerte'
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: 3aa615dc7d7d1d49dce4897f8508b5210b364fc0
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635136"
---
# <a name="how-to-round-trip-date-and-time-values"></a>Vorgehensweise: Roundtrip-Datums- und -Uhrzeitwerte

In vielen Anwendungen soll ein Datums- und Uhrzeitwert einen bestimmten Zeitpunkt eindeutig identifizieren. In diesem Artikel wird gezeigt, wie ein <xref:System.DateTime>-Wert, ein <xref:System.DateTimeOffset>-Wert sowie ein Datums- und Uhrzeitwert mit Zeitzoneninformationen so gespeichert und wiederhergestellt werden, dass der wiederhergestellte Wert denselben Zeitpunkt bezeichnet wie der gespeicherte Wert.

## <a name="round-trip-a-datetime-value"></a>Durchführen eines Roundtrips für einen DateTime-Wert

1. Konvertieren Sie den <xref:System.DateTime>-Wert in seine Zeichenfolgendarstellung, indem Sie die <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType>-Methode mit dem Formatbezeichner „o“ aufrufen.

2. Speichern Sie die Zeichenfolgendarstellung des <xref:System.DateTime>-Werts in einer Datei, oder übergeben Sie sie über einen Prozess, eine Anwendungsdomäne oder eine Computergrenze.

3. Rufen Sie die Zeichenfolge ab, die den <xref:System.DateTime>-Wert darstellt.

4. Rufen Sie die <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType>-Methode auf, und übergeben Sie <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> als Wert für den `styles`-Parameter.

Das folgende Beispiel veranschaulicht, wie ein Roundtrip für einen <xref:System.DateTime>-Wert ausgeführt wird.

[!code-csharp[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#1)]
[!code-vb[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#1)]

Beim Ausführen von Roundtrips für einen <xref:System.DateTime>-Wert wird durch diese Methode erfolgreich die Uhrzeit für alle Orts- und Weltzeiten beibehalten. Wenn beispielsweise ein lokaler <xref:System.DateTime>-Wert auf einem System in der US-Zeitzone Pacific Standard Time gespeichert und auf einem System in der US-Zeitzone Central Standard Time wiederhergestellt wird, liegen das wiederhergestellte Datum und die Uhrzeit zwei Stunden hinter der ursprünglichen Zeit, was dem Zeitunterschied zwischen den beiden Zeitzonen entspricht. Dieses Verfahren ist für nicht spezifizierte Zeiten jedoch nicht notwendigerweise genau. Alle <xref:System.DateTime>-Werte, deren <xref:System.DateTime.Kind%2A>-Eigenschaft auf <xref:System.DateTimeKind.Unspecified> festgelegt ist, werden als Ortszeiten behandelt. Wenn es sich nicht um die lokale Zeit handelt, kann der richtige Zeitpunkt durch <xref:System.DateTime> nicht erfolgreich identifiziert werden. Die Umgehung für diese Einschränkung besteht darin, einen Datums- und Zeitwert für den Speicher- und Wiederherstellungsvorgang eng an die entsprechende Zeitzone zu koppeln.

## <a name="round-trip-a-datetimeoffset-value"></a>Durchführen eines Roundtrips für einen DateTimeOffset-Wert

1. Konvertieren Sie den <xref:System.DateTimeOffset>-Wert in seine Zeichenfolgendarstellung, indem Sie die <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType>-Methode mit dem Formatbezeichner „o“ aufrufen.

2. Speichern Sie die Zeichenfolgendarstellung des <xref:System.DateTimeOffset>-Werts in einer Datei, oder übergeben Sie sie über einen Prozess, eine Anwendungsdomäne oder eine Computergrenze.

3. Rufen Sie die Zeichenfolge ab, die den <xref:System.DateTimeOffset>-Wert darstellt.

4. Rufen Sie die <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType>-Methode auf, und übergeben Sie <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> als Wert für den `styles`-Parameter.

Das folgende Beispiel veranschaulicht, wie ein Roundtrip für einen <xref:System.DateTimeOffset>-Wert ausgeführt wird.

[!code-csharp[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#2)]
[!code-vb[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#2)]

Durch diese Methode wird ein <xref:System.DateTimeOffset>-Wert immer eindeutig als ein einziger Zeitpunkt identifiziert. Der Wert kann dann durch Aufrufen der <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType>-Methode in die koordinierte Weltzeit (UTC) oder durch Aufrufen der <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=nameWithType>- oder <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType>-Methode in die Zeit einer bestimmten Zeitzone konvertiert werden. Die wesentliche Einschränkung dieser Methode liegt darin, dass die Datums- und Uhrzeitarithmetik möglicherweise keine genauen Ergebnisse für die jeweilige Zeitzone liefert, wenn sie bei einem <xref:System.DateTimeOffset>-Wert durchgeführt wird, der die Zeit in einer bestimmten Zeitzone darstellt. Grund hierfür ist, dass die Zuordnung eines <xref:System.DateTimeOffset>-Werts zu seiner Zeitzone bei seiner Instanziierung aufgehoben wird. Daher können die Anpassungsregeln für diese Zeitzone bei Datums- und Uhrzeitberechnungen nicht mehr angewendet werden. Sie können dieses Problem umgehen, indem Sie einen benutzerdefinierten Typ definieren, der sowohl einen Datums- und Uhrzeitwert als auch die dazugehörige Zeitzone enthält.

## <a name="round-trip-a-date-and-time-value-with-its-time-zone"></a>Durchführen eines Roundtrips für einen Datums- und Uhrzeitwert mit der jeweiligen Zeitzone

1. Definieren Sie eine Klasse oder Struktur mit zwei Feldern. Beim ersten Feld handelt es sich entweder um ein <xref:System.DateTime>- oder ein <xref:System.DateTimeOffset>-Objekt und beim zweiten um ein <xref:System.TimeZoneInfo>-Objekt. Im folgenden Beispiel wird eine einfache Version eines solchen Typs gezeigt.

    [!code-csharp[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#3)]
    [!code-vb[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#3)]

2. Markieren Sie die Klasse mit dem Attribut <xref:System.SerializableAttribute>.

3. Serialisieren Sie das Objekt mit der Methode <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>.

4. Stellen Sie das Objekt mit der Methode <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A> wieder her.

5. Wandeln Sie (in C#) das deserialisierte Objekt in ein Objekt des entsprechenden Typs um, oder konvertieren Sie es (in Visual Basic) in diesen Typ.

Im folgenden Beispiel wird veranschaulicht, wie ein Roundtrip für ein Objekt durchgeführt wird, das sowohl Zeitzonen- als auch Datums- und Uhrzeitinformationen speichert.

[!code-csharp[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#4)]
[!code-vb[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#4)]

Diese Methode sollte stets eindeutig den richtigen Zeitpunkt darstellen, bevor und nachdem dieser gespeichert und wiederhergestellt wurde, vorausgesetzt, dass die Implementierung des kombinierten Objekts aus Datum und Uhrzeit sowie Zeitzone sicherstellt, dass der Datumswert mit dem Zeitzonenwert synchron ist.

## <a name="compile-the-code"></a>Kompilieren des Codes

Diese Beispiele erfordern Folgendes:

- Importieren der folgenden Namespaces mithilfe von `using`-Direktiven (C#) oder `Imports`-Anweisungen (Visual Basic):

  - <xref:System> (nur C#)

  - <xref:System.Globalization?displayProperty=nameWithType>

  - <xref:System.IO?displayProperty=nameWithType>

  - <xref:System.Runtime.Serialization?displayProperty=nameWithType>

  - <xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=nameWithType>

- Jedes Codebeispiel, ausgenommen der `DateInTimeZone`-Klasse, muss in eine Klasse oder ein Visual Basic-Modul eingefügt, in Methoden umschlossen und über die `Main`-Methode aufgerufen werden.

## <a name="see-also"></a>Siehe auch

- [Auswählen zwischen „DateTime“, „DateTimeOffset“, „TimeSpan“ und „TimeZoneInfo“](../../../docs/standard/datetime/choosing-between-datetime.md)
- [Standard-Formatzeichenfolgen für Datum und Uhrzeit](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)
