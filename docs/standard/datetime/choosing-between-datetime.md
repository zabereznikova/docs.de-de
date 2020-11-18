---
title: Vergleichen von DateTime, DateTimeOffset, TimeSpan und TimeZoneInfo
description: Erfahren Sie mehr über die Unterschiede zwischen den Typen DateTime, DateTimeOffset, TimeSpan und TimeZoneInfo zur Darstellung von Datums-und Uhrzeit Informationen in .net.
ms.date: 04/10/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DateTimeOffset structure
- TimeZoneInfo class
- time zones [.NET], common uses
- date and time classes [.NET]
- time zones [.NET], type options
- DateTime structure
ms.assetid: 07f17aad-3571-4014-9ef3-b695a86f3800
ms.openlocfilehash: 23c846dfd634e476b60ffd867519a60a0ae6b6cf
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94818094"
---
# <a name="choose-between-datetime-datetimeoffset-timespan-and-timezoneinfo"></a>Auswählen zwischen "DateTime", "DateTimeOffset", "TimeSpan" und "TimeZoneInfo"

.NET-Anwendungen können Datums-und Uhrzeit Informationen auf verschiedene Weise verwenden. Zu den gängigsten Verwendungsmöglichkeiten von Datums-und Uhrzeit Informationen gehören:

- Darstellen eines reinen Datums, damit Zeitinformationen unberücksichtigt bleiben.

- Darstellen einer reinen Uhrzeit, damit Datumsinformationen unberücksichtigt bleiben.

- Darstellen eines abstrakten Datums mit Uhrzeit, die an keine bestimmte Zeit und keinen bestimmten Ort gebunden sind (z. B. öffnen die meisten Geschäfte einer internationalen Kette an Wochentagen um 9:00 Uhr).

- Zum Abrufen von Datums-und Uhrzeit Informationen aus Quellen außerhalb von .net, in der Regel, wo Datums-und Uhrzeit Informationen in einem einfachen Datentyp gespeichert sind.

- Eindeutiges und unzweideutiges Identifizieren eines einzigen Zeitpunkts. Für einige Anwendungen ist es erforderlich, dass ein Datum und eine Uhrzeit nur auf dem Host System eindeutig sind. Bei anderen apps ist es erforderlich, dass Sie über Systeme hinweg eindeutig sind (d. h., ein auf einem System serialisiertes Datum kann auf der ganzen Welt auf einem anderen System sinnvoll deserialisiert und verwendet werden).

- Erhalten mehrerer verwandter Zeiten (z. B. die lokale Zeit des Anforderers und die Empfangszeit des Servers für eine Webanforderung).

- Durchführen von Datums- und Uhrzeitberechnungen, möglicherweise mit einem Ergebnis, das einen einzigen Zeitpunkt eindeutig identifiziert.

.NET enthält die <xref:System.DateTime> <xref:System.DateTimeOffset> Typen,, <xref:System.TimeSpan> und <xref:System.TimeZoneInfo> , die alle zum Erstellen von Anwendungen verwendet werden können, die mit Datums-und Uhrzeitangaben arbeiten.

> [!NOTE]
> In diesem Thema wird nicht erläutert, <xref:System.TimeZone> weil seine Funktionalität fast vollständig in die-Klasse integriert ist <xref:System.TimeZoneInfo> . Verwenden Sie nach Möglichkeit die- <xref:System.TimeZoneInfo> Klasse anstelle der- <xref:System.TimeZone> Klasse.

## <a name="the-datetimeoffset-structure"></a>Die DateTimeOffset-Struktur

Die <xref:System.DateTimeOffset> -Struktur stellt einen Datums- und Uhrzeitwert zusammen mit einem Offset dar, der angibt, um wie viel dieser Wert von UTC abweicht. Somit identifiziert der Wert immer eindeutig einen einzigen Zeitpunkt.

Der <xref:System.DateTimeOffset> -Typ bietet die gesamte Funktionalität des <xref:System.DateTime> -Typs plus Unterstützung von Zeitzonen. Dies eignet sich für Anwendungen, für die Folgendes möglich ist:

- Eindeutiges und unzweideutiges Identifizieren eines einzigen Zeitpunkts. Der <xref:System.DateTimeOffset> -Typ kann zur eindeutigen Definition der Bedeutung von "jetzt" verwendet werden, um Transaktionszeiten zu protokollieren, die Zeiten von System- oder Anwendungsereignissen zu protokollieren und um die Zeiten der Erstellung und Änderung von Dateien aufzuzeichnen.

- Ausführen von allgemeinen Datums- und Uhrzeitberechnungen

- Erhalten mehrerer verwandter Uhrzeiten, solange diese Zeiten als zwei gesonderte Werte oder als zwei Member einer Struktur gespeichert werden.

> [!NOTE]
> Diese Verwendungsarten für <xref:System.DateTimeOffset> -Werte sind sehr viel häufiger als die für <xref:System.DateTime> -Werte. Als Ergebnis sollten Sie <xref:System.DateTimeOffset> als Standardtyp für Datum und Uhrzeit für die Anwendungsentwicklung in Erwägung gezogen werden.

Ein <xref:System.DateTimeOffset> Wert ist nicht an eine bestimmte Zeitzone gebunden, kann aber aus einer Vielzahl von Zeitzonen stammen. Das folgende Beispiel listet die Zeitzonen auf, zu denen eine Reihe von <xref:System.DateTimeOffset> Werten (einschließlich einer lokalen Pacific Standard Time) gehören können.

[!code-csharp[System.DateTimeOffset.Conceptual#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual1.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual1.vb#1)]

Die Ausgabe zeigt, dass jeder Datums- und Uhrzeitwert in diesem Beispiel zu mindestens drei verschiedenen Zeitzonen gehören kann. Der <xref:System.DateTimeOffset> Wert 6/10/2007 zeigt, dass, wenn ein Datums-und Uhrzeitwert eine Sommerzeit darstellt, der Offset von UTC nicht gleich dem Basis-UTC-Offset der Ursprungs Zeitzone oder dem Offset von UTC im anzeigen Amen entspricht. Da ein einzelner <xref:System.DateTimeOffset> Wert nicht eng mit seiner Zeitzone verknüpft ist, kann er nicht den Übergang einer Zeitzone zur und von der Sommerzeit widerspiegeln. Dies kann problematisch sein, wenn die Datums-und Uhrzeit Arithmetik zum Bearbeiten eines Werts verwendet wird <xref:System.DateTimeOffset> . Eine Erläuterung der Durchführung von Datums- und Uhrzeitberechnungen auf eine Weise, die die Anpassungsregeln einer Zeitzone berücksichtigt, finden Sie unter [Durchführen arithmetischer Datums- und Uhrzeitoperationen](performing-arithmetic-operations.md).

## <a name="the-datetime-structure"></a>Die DateTime-Struktur

Ein <xref:System.DateTime> -Wert definiert ein bestimmtes Datum und eine Uhrzeit. Sie enthält eine- <xref:System.DateTime.Kind%2A> Eigenschaft, die eingeschränkte Informationen über die Zeitzone bereitstellt, zu der dieses Datum und die Uhrzeit gehören. Der von der <xref:System.DateTimeKind> -Eigenschaft zurückgegebene <xref:System.DateTime.Kind%2A> Wert zeigt an, ob der <xref:System.DateTime> -Wert eine lokale Uhrzeit darstellt (<xref:System.DateTimeKind.Local?displayProperty=nameWithType>), eine Zeit im UTC-Format (Coordinated Universal Time) (<xref:System.DateTimeKind.Utc?displayProperty=nameWithType>) oder eine unspezifische Uhrzeit (<xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>).

Die <xref:System.DateTime> Struktur eignet sich für Anwendungen mit einer oder mehreren der folgenden Eigenschaften:

- Nur mit Daten arbeiten.

- Nur mit Uhrzeiten arbeiten.

- Mit abstrakten Datums- und Uhrzeitwerten arbeiten.

- Mit Datums- und Uhrzeitwerten arbeiten, für die Zeitzoneninformationen fehlen.

- Nur mit UTC-Datums- und Uhrzeitwerten arbeiten.

- Abrufen von Datums-und Uhrzeit Informationen aus Quellen außerhalb von .net (z. b. SQL-Datenbanken). In der Regel speichern diese Quellen Datums- und Uhrzeitinformationen in einem einfachen Format, das mit der <xref:System.DateTime> -Struktur kompatibel ist.

- Arithmetische Operationen mit Datums- und Uhrzeitwerten durchführen, wobei aber allgemeine Ergebnisse von Belang sind. Beispielsweise ist es bei einer Additionsoperation, bei der einem bestimmten Datum und einer Uhrzeit sechs Monate hinzuaddiert werden, oft nicht wichtig, ob das Ergebnis hinsichtlich der Sommerzeit angepasst wird.

Wenn nicht ein bestimmter <xref:System.DateTime> -Wert UTC darstellt, ist dieser Datums- und Uhrzeitwert häufig mehrdeutig oder in seiner Portierbarkeit eingeschränkt. Wenn z. B. ein <xref:System.DateTime> -Wert die lokale Uhrzeit darstellt, ist er innerhalb dieser lokalen Zeitzone portierbar (d. h., wenn der Wert auf einem anderen System in derselben Zeitzone deserialisiert wird, identifiziert dieser Wert immer noch eindeutig einen einzigen Zeitpunkt). Außerhalb der lokalen Zeitzone kann dieser <xref:System.DateTime> -Wert über mehrere Interpretationen verfügen. Wenn die <xref:System.DateTime.Kind%2A> -Eigenschaft des Werts <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>ist, ist er sogar noch weniger portierbar: Er ist jetzt innerhalb derselben Zeitzone mehrdeutig und möglicherweise sogar auf dem selben System, auf dem er erstmalig serialisiert wurde. Nur wenn ein <xref:System.DateTime> -Wert eine UTC-Zeit darstellt, identifiziert dieser Wert eindeutig einen einzigen Zeitpunkt, unabhängig vom System oder der Zeitzone, in der der Wert verwendet wird.

> [!IMPORTANT]
> Beim Speichern oder Freigeben von <xref:System.DateTime> -Daten sollte UTC verwendet werden, und die <xref:System.DateTime> - <xref:System.DateTime.Kind%2A> -Eigenschaft des Werts sollte auf <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>festgelegt werden.

## <a name="the-timespan-structure"></a>Die TimeSpan-Struktur

Die <xref:System.TimeSpan> -Struktur stellt ein Zeitintervall dar. Sein zwei typischen Anwendungsmöglichkeiten sind:

- Darstellen des Zeitintervalls zwischen zwei Datums- und Uhrzeitwerten. Beispielsweise gibt die Subtraktion eines <xref:System.DateTime> -Werts von einem anderen einen <xref:System.TimeSpan> -Wert zurück.

- Messen der verstrichenen Zeit. Beispielsweise gibt die- <xref:System.Diagnostics.Stopwatch.Elapsed%2A?displayProperty=nameWithType> Eigenschaft einen <xref:System.TimeSpan> Wert zurück, der das Zeitintervall angibt, das seit dem Aufruf einer der <xref:System.Diagnostics.Stopwatch> Methoden, die die verstrichene Zeit zu messen beginnen, verstrichen ist.

Ein- <xref:System.TimeSpan> Wert kann auch als Ersatz für einen-Wert verwendet werden <xref:System.DateTime> , wenn dieser Wert eine Uhrzeit ohne Verweis auf einen bestimmten Tag widerspiegelt. Diese Verwendung ähnelt der-Eigenschaft <xref:System.DateTime.TimeOfDay%2A?displayProperty=nameWithType> und der-Eigenschaft <xref:System.DateTimeOffset.TimeOfDay%2A?displayProperty=nameWithType> , die einen Wert zurückgeben, <xref:System.TimeSpan> der die Uhrzeit ohne Verweis auf ein Datum darstellt. Beispielsweise kann die <xref:System.TimeSpan> -Struktur verwendet werden, um die täglichen Öffnungszeiten eines Geschäfts darzustellen oder um die Uhrzeit darzustellen, zu der alle regulären Ereignisse auftreten.

Das folgende Beispiel definiert eine `StoreInfo` -Struktur, die <xref:System.TimeSpan> -Objekte für Öffnungszeiten von Geschäften enthält sowie ein <xref:System.TimeZoneInfo> -Objekt, das die Zeitzone des Geschäfts darstellt. Die Struktur enthält außerdem zwei Methoden, `IsOpenNow` und `IsOpenAt`, die angeben, ob das Geschäft zu einem vom Benutzer angegebenen Zeitpunkt geöffnet ist, wobei angenommen wird, dass er sich in der lokalen Zeitzone aufhält.

[!code-csharp[Conceptual.ChoosingDates#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.choosingdates/cs/datetimereplacement1.cs#1)]
[!code-vb[Conceptual.ChoosingDates#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.choosingdates/vb/datetimereplacement1.vb#1)]

Die `StoreInfo` -Struktur kann dann von Clientcode wie folgt verwendet werden.

[!code-csharp[Conceptual.ChoosingDates#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.choosingdates/cs/datetimereplacement1.cs#2)]
[!code-vb[Conceptual.ChoosingDates#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.choosingdates/vb/datetimereplacement1.vb#2)]

## <a name="the-timezoneinfo-class"></a>Die TimeZoneInfo-Klasse

Die <xref:System.TimeZoneInfo> class represents any of the Earth's time zones, and enables the conversion of any date and time in one time zone to its equivalent in another time zone. Die <xref:System.TimeZoneInfo> -Klasse ermöglicht das Arbeiten mit Datums- und Zeitwerten, sodass jeder Datums- und Uhrzeitwert eindeutig einen einzigen Zeitpunkt identifiziert. Die <xref:System.TimeZoneInfo> -Klasse ist außerdem erweiterbar. Obwohl sie von den für Windows-Systeme bereitgestellten und in der Registrierung definierten Zeitzoneninformationen abhängt, unterstützt sie die Erstellung benutzerdefinierter Zeitzonen. Sie unterstützt außerdem die Serialisierung und Deserialisierung von Zeitzoneninformationen.

In einigen Fällen kann noch weitere Entwicklungsarbeit erforderlich sein, um die <xref:System.TimeZoneInfo> -Klasse optimal zu nutzen. Wenn die Datums-und Uhrzeitwerte nicht eng mit den Zeitzonen gekoppelt sind, zu denen Sie gehören, sind weitere Schritte erforderlich. Wenn Ihre Anwendung keinen Mechanismus zum Verknüpfen eines Datums und einer Uhrzeit mit der zugehörigen Zeitzone bereitstellt, ist es einfach, dass ein bestimmter Datums-und Uhrzeitwert von der Zeitzone getrennt wird. Eine Methode zum Verknüpfen dieser Informationen besteht darin, eine Klasse oder Struktur zu definieren, die sowohl den Datums- und Zeitwert als auch sein zugeordnetes Zeitzonenobjekt enthält.

Um die Zeit Zonen Unterstützung in .net zu nutzen, müssen Sie die Zeitzone kennen, zu der ein Datums-und Uhrzeitwert gehört, wenn das Datums-und Uhrzeit Objekt instanziiert wird. Die Zeitzone ist oft nicht bekannt, insbesondere in Web-oder Netzwerk-apps.

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](index.md)
