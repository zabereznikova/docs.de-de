---
title: Instanziieren eines DateTimeOffset-Objekts
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- instantiating time zone objects
- time zone objects [.NET Framework], instantiation
- DateTimeOffset structure, converting to DateTime
- DateTimeOffset structure, instantiating
ms.assetid: 9648375f-d368-4373-a976-3332ece00c0a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a48ea87bb5eb1e302ae6a1169c22ea30bd4bc7ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33577279"
---
# <a name="instantiating-a-datetimeoffset-object"></a>Instanziieren eines "DateTimeOffset"-Objekts

Die <xref:System.DateTimeOffset> Struktur bietet eine Reihe von Möglichkeiten zum Erstellen neuer <xref:System.DateTimeOffset> Werte. Viele davon entsprechen direkt die Methoden zum Instanziieren neuer <xref:System.DateTime> Werte mit Erweiterungen, mit denen Sie angeben, der Wert für Datum und Uhrzeit offset von Coordinated Universal Time (UTC). Sie können insbesondere Instanziieren einer <xref:System.DateTimeOffset> Wert auf folgende Weise:

* Mit einer Datums- und Uhrzeitangabe literal.

* Durch Aufrufen einer <xref:System.DateTimeOffset> Konstruktor.

* Durch Implizites Konvertieren einen Wert zu <xref:System.DateTimeOffset> Wert.

* Durch Analysieren der Zeichenfolgendarstellung eines Datums- und Uhrzeitwerts.

Dieses Thema bietet mehr Details und Codebeispiele, die diese Methoden Instanziieren neuer veranschaulichen <xref:System.DateTimeOffset> Werte.

## <a name="date-and-time-literals"></a>Datums- und Zeitliterale

Für Sprachen, die diese zu, eine der am häufigsten verwendeten Methoden zum Instanziieren unterstützen einer <xref:System.DateTime> Wert ist das Datum und die Uhrzeit als hartcodierten Literalwert angeben. Die folgenden Visual Basic-Code erstellt z. B. ein <xref:System.DateTime> Objekt, dessen Wert dem 1. Januar 2008 um 10:00 Uhr.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#1)]

<xref:System.DateTimeOffset> Werte können auch mit Datums- und Zeitliterale, wenn Sprachen unterstützen initialisiert werden <xref:System.DateTime> Literale. Die folgenden Visual Basic-Code erstellt z. B. ein <xref:System.DateTimeOffset> Objekt.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#2)]

Wie die Konsolenausgabe zeigt, die <xref:System.DateTimeOffset> Wert erstellt, die auf diese Weise wird den Offset der lokalen Zeitzone zugewiesen. Dies bedeutet, dass ein <xref:System.DateTimeOffset> Wert zugewiesen, mit einem Zeichenliteral keinen einzigen Zeitpunkt identifiziert, wenn der Code auf verschiedenen Computern ausgeführt wird.

## <a name="datetimeoffset-constructors"></a>"DateTimeOffset"-Konstruktoren

Die <xref:System.DateTimeOffset> sechs Konstruktoren definiert. Vier von ihnen entsprechen direkt <xref:System.DateTime> Konstruktoren, einen zusätzlichen Parameter vom Typ <xref:System.TimeSpan> , definiert das Datum und Uhrzeit den offset von UTC. Damit können Sie definieren eine <xref:System.DateTimeOffset> Wert basierend auf den Wert seiner einzelnen Datums- und Zeitkomponenten. Der folgende Code verwendet beispielsweise diese vier Konstruktoren zum Instanziieren <xref:System.DateTimeOffset> Objekte mit identischen Werten 7/1/2008 12:05 Uhr + 01:00.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#3)]

Beachten Sie, dass bei den Wert des der <xref:System.DateTimeOffset> Objekt mit instanziiert einen <xref:System.Globalization.PersianCalendar> Objekt als eines der Argumente an ihren Konstruktor in der Konsole angezeigt wird, wird es als ein Datum im gregorianischen Kalender, anstatt den persischen Kalender ausgedrückt. Ein Datum unter Verwendung des persischen Kalenders Ausgabe finden Sie im Beispiel in der <xref:System.Globalization.PersianCalendar> Thema.

Die anderen beiden Konstruktoren erstellen ein <xref:System.DateTimeOffset> -Objekt aus einem <xref:System.DateTime> Wert. Das erste Parameter hat einen einzelnen Parameter, die <xref:System.DateTime> Wert konvertieren in eine <xref:System.DateTimeOffset> Wert. Der Offset des resultierenden <xref:System.DateTimeOffset> Wert hängt von der <xref:System.DateTime.Kind%2A> -Eigenschaft der einzelnen Parameter des Konstruktors. Wenn der Wert <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, der Offset ist gleich festgelegt <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. Andernfalls wird die Abweichung entsprechend der lokalen Zeitzone eingestellt. Das folgende Beispiel veranschaulicht die Verwendung dieses Konstruktors zum Instanziieren <xref:System.DateTimeOffset> Objekten, die UTC-Zeit und die lokale Zeitzone darstellen:

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#4)]

> [!NOTE]
> Aufrufen der Überladung des der <xref:System.DateTimeOffset> Konstruktor, der ein einzelnes <xref:System.DateTime> Parameter entspricht einer impliziten Konvertierung von einer <xref:System.DateTime> -Wert an ein <xref:System.DateTimeOffset> Wert.

Der zweite Konstruktor, der erstellt eine <xref:System.DateTimeOffset> -Objekt aus einer <xref:System.DateTime> Wert verfügt über zwei Parameter: den <xref:System.DateTime> zu konvertierenden Wert und eine <xref:System.TimeSpan> offset von UTC Wert, der das Datum und die Uhrzeit darstellt. Dieser Offset-Wert entsprechen muss die <xref:System.DateTime.Kind%2A> -Eigenschaft des ersten Parameters der Konstruktor oder eine <xref:System.ArgumentException> ausgelöst wird. Wenn die <xref:System.DateTime.Kind%2A> Eigenschaft des ersten Parameters ist <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, muss der Wert des zweiten Parameters <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. Wenn die <xref:System.DateTime.Kind%2A> Eigenschaft des ersten Parameters ist <xref:System.DateTimeKind.Local?displayProperty=nameWithType>, der Wert des zweiten Parameters muss den Offset der Zeitzone des lokalen Systems sein. Wenn die <xref:System.DateTime.Kind%2A> Eigenschaft des ersten Parameters ist <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, der Offset kann jeder gültige Wert. Der folgende Code veranschaulicht Aufrufe an diesen Konstruktor zum Konvertieren von <xref:System.DateTime> zu <xref:System.DateTimeOffset> Werte.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#5)]

## <a name="implicit-type-conversion"></a>Implizite Typumwandlung

Die <xref:System.DateTimeOffset> Typ unterstützt eine implizite Typumwandlung: aus einer <xref:System.DateTime> -Wert an ein <xref:System.DateTimeOffset> Wert. (Eine implizite Typkonvertierung ist eine Konvertierung von einem Typ in einen anderen, für die keine explizite Umwandlung (in C#) oder Konvertierung (in Visual Basic) erforderlich ist und bei der keine Informationen verloren gehen. Dies ermöglicht beispielsweise folgenden Code:

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#6)]

Der Offset des resultierenden <xref:System.DateTimeOffset> Wert hängt von der <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> Eigenschaftswert. Wenn der Wert <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, der Offset ist gleich festgelegt <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. Wenn der Wert entweder <xref:System.DateTimeKind.Local?displayProperty=nameWithType> oder <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, der Offset der lokalen Zeitzone festgelegt.

## <a name="parsing-the-string-representation-of-a-date-and-time"></a>Die angegebene Zeichenfolgendarstellung einer Datums- und Uhrzeitangabe analysieren

Die <xref:System.DateTimeOffset> Typ unterstützt vier Methoden, mit denen Sie konvertiert die Zeichenfolgendarstellung eines Datums und die Uhrzeit in einer <xref:System.DateTimeOffset> Wert:

* <xref:System.DateTimeOffset.Parse%2A>, der versucht, konvertiert die Zeichenfolgendarstellung einer Datums- und Uhrzeitangabe in einem <xref:System.DateTimeOffset> -Wert und löst eine Ausnahme aus, wenn die Konvertierung fehlschlägt.

* <xref:System.DateTimeOffset.TryParse%2A>, der versucht, konvertiert die Zeichenfolgendarstellung einer Datums- und Uhrzeitangabe in einem <xref:System.DateTimeOffset> Wert und gibt `false` , wenn die Konvertierung schlägt fehl.

* <xref:System.DateTimeOffset.ParseExact%2A>, der versucht, die angegebene Zeichenfolgendarstellung einer Datums- und Uhrzeitangabe in einem angegebenen Format zu konvertieren einer <xref:System.DateTimeOffset> Wert. Die Methode löst eine Ausnahme aus, wenn bei der Konvertierung ein Fehler auftritt.

* <xref:System.DateTimeOffset.TryParseExact%2A>, der versucht, die angegebene Zeichenfolgendarstellung einer Datums- und Uhrzeitangabe in einem angegebenen Format zu konvertieren einer <xref:System.DateTimeOffset> Wert. Die Methode gibt `false` zurück, wenn bei der Konvertierung ein Fehler auftritt.

Das folgende Beispiel veranschaulicht Aufrufe dieser vier Konvertierungsmethoden zum Instanziieren einer <xref:System.DateTimeOffset> Wert.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#7)]

## <a name="see-also"></a>Siehe auch

[Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
