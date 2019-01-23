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
ms.openlocfilehash: 11f62b8fe8a28d6fe6401d53dac4b9bc1c45b21d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554599"
---
# <a name="instantiating-a-datetimeoffset-object"></a>Instanziieren eines "DateTimeOffset"-Objekts

Die <xref:System.DateTimeOffset> Struktur bietet eine Reihe von Methoden zum Erstellen neuer <xref:System.DateTimeOffset> Werte. Viele von ihnen entsprechen direkt an die Methoden zum Instanziieren neuer <xref:System.DateTime> Werte mit Erweiterungen, mit denen Sie angeben, der Wert für Datum und Uhrzeit den offset von Coordinated Universal Time (UTC). Sie können insbesondere Instanziieren einer <xref:System.DateTimeOffset> Wert auf folgende Weise:

* Verwenden Sie ein Datum und Uhrzeit-literal.

* Durch Aufrufen einer <xref:System.DateTimeOffset> Konstruktor.

* Durch Implizites Konvertieren eines Werts zu <xref:System.DateTimeOffset> Wert.

* Durch Analysieren der Zeichenfolgendarstellung eines Datums- und Uhrzeitwerts.

Dieses Thema enthält mehr Details und Codebeispiele, die dieser Methoden zum Instanziieren neuer veranschaulichen <xref:System.DateTimeOffset> Werte.

## <a name="date-and-time-literals"></a>Datum und Uhrzeit – Literale

Für Sprachen, die dies eine der am häufigsten verwendeten Methoden zum Instanziieren unterstützen eine <xref:System.DateTime> Wert ist, um das Datum und die Uhrzeit als hartcodierten Literalwert bereitzustellen. Die folgende Visual Basic-Code erstellt z.B. eine <xref:System.DateTime> Objekt, dessen Wert 1. Januar 2008, um 10:00 Uhr.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#1)]

<xref:System.DateTimeOffset> Werte können auch mithilfe von Datums- und Uhrzeitliterale, wenn Sprachen unterstützen initialisiert werden <xref:System.DateTime> Literale. Die folgende Visual Basic-Code erstellt z.B. eine <xref:System.DateTimeOffset> Objekt.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#2)]

Wie die Konsolenausgabe zeigt, die <xref:System.DateTimeOffset> Wert erstellt, die auf diese Weise den Offset der lokalen Zeitzone zugewiesen ist. Dies bedeutet, dass eine <xref:System.DateTimeOffset> Wert zugewiesen wird, über ein Zeichenliteral keinen einzigen Zeitpunkt identifiziert, wenn der Code auf verschiedenen Computern ausgeführt wird.

## <a name="datetimeoffset-constructors"></a>DateTimeOffset-Konstruktoren

Die <xref:System.DateTimeOffset> Typ definiert sechs Konstruktoren. Vier von ihnen entsprechen direkt den <xref:System.DateTime> Konstruktoren, mit einem zusätzlichen Parameter vom Typ <xref:System.TimeSpan> , definiert das Datum und uhrzeitabweichung von UTC. Diese können Sie definieren eine <xref:System.DateTimeOffset> Wert basierend auf dem Wert der einzelnen Datums- und Uhrzeitkomponenten. Der folgende Code verwendet beispielsweise diese vier Konstruktoren instanziieren <xref:System.DateTimeOffset> Objekte mit identischen Werten von 7/1/2008 12:05 AM + 01:00.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#3)]

Beachten Sie, dass bei den Wert des der <xref:System.DateTimeOffset> Objekt instanziiert, mit einer <xref:System.Globalization.PersianCalendar> -Objekt als eines der Argumente an den Konstruktor in der Konsole angezeigt wird, wird es als ein Datum im gregorianischen Kalender statt dem persischen Kalender ausgedrückt. Um ein Datum unter Verwendung des persischen Kalenders auszugeben, siehe das Beispiel in der <xref:System.Globalization.PersianCalendar> Thema.

Die anderen beiden Konstruktoren erstellen ein <xref:System.DateTimeOffset> -Objekt aus einem <xref:System.DateTime> Wert. Die erste Parameter hat einen einzelnen Parameter, die <xref:System.DateTime> konvertiert werden soll eine <xref:System.DateTimeOffset> Wert. Die Abweichung des resultierenden <xref:System.DateTimeOffset> Wert hängt von der <xref:System.DateTime.Kind%2A> Eigenschaft der einzelnen Parameter des Konstruktors. Wenn der Wert <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, gleich der Offset festgelegt <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. Andernfalls wird die Abweichung entsprechend der lokalen Zeitzone eingestellt. Das folgende Beispiel veranschaulicht die Verwendung dieses Konstruktors instanziieren <xref:System.DateTimeOffset> Objekte, die UTC-Zeit und die lokale Zeitzone darstellen:

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#4)]

> [!NOTE]
> Aufrufen der Überladung des der <xref:System.DateTimeOffset> Konstruktor mit einem einzelnen <xref:System.DateTime> Parameter entspricht dem impliziten Konvertieren von einem <xref:System.DateTime> Wert eine <xref:System.DateTimeOffset> Wert.

Der zweite Konstruktor, der erstellt eine <xref:System.DateTimeOffset> -Objekt aus einer <xref:System.DateTime> Wert verfügt über zwei Parameter: die <xref:System.DateTime> zu konvertierenden Wert und einem <xref:System.TimeSpan> Wert, der das Datum und Uhrzeit darstellt uhrzeitabweichung von UTC. Dieser Abweichungswert muss entsprechen, die die <xref:System.DateTime.Kind%2A> -Eigenschaft des ersten Parameters des Konstruktors oder einer <xref:System.ArgumentException> ausgelöst. Wenn die <xref:System.DateTime.Kind%2A> -Eigenschaft des ersten Parameters ist <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, der Wert des zweiten Parameters muss <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. Wenn die <xref:System.DateTime.Kind%2A> -Eigenschaft des ersten Parameters ist <xref:System.DateTimeKind.Local?displayProperty=nameWithType>, der Wert des zweiten Parameters muss der Offset der Zeitzone des lokalen Systems sein. Wenn die <xref:System.DateTime.Kind%2A> -Eigenschaft des ersten Parameters ist <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, der Offset kann ein beliebiger gültiger Wert sein. Der folgende Code zeigt Aufrufe dieses Konstruktors zum Konvertieren <xref:System.DateTime> zu <xref:System.DateTimeOffset> Werte.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#5)]

## <a name="implicit-type-conversion"></a>Implizite typkonvertierung

Die <xref:System.DateTimeOffset> unterstützt eine implizite typkonvertierung: von einer <xref:System.DateTime> Wert eine <xref:System.DateTimeOffset> Wert. (Eine implizite Typkonvertierung ist eine Konvertierung von einem Typ in einen anderen, für die keine explizite Umwandlung (in C#) oder Konvertierung (in Visual Basic) erforderlich ist und bei der keine Informationen verloren gehen. Dies ermöglicht beispielsweise folgenden Code:

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#6)]

Die Abweichung des resultierenden <xref:System.DateTimeOffset> Wert hängt von der <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> -Eigenschaftswert. Wenn der Wert <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, gleich der Offset festgelegt <xref:System.TimeSpan.Zero?displayProperty=nameWithType>. Wenn der Wert entweder <xref:System.DateTimeKind.Local?displayProperty=nameWithType> oder <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, der Offset der lokalen Zeitzone festgelegt.

## <a name="parsing-the-string-representation-of-a-date-and-time"></a>Die Zeichenfolgendarstellung einer Datums- und Uhrzeitangabe analysieren

Die <xref:System.DateTimeOffset> -Typ unterstützt vier Methoden, mit denen Sie konvertiert die Zeichenfolgendarstellung eines Datums und einer Uhrzeit in einer <xref:System.DateTimeOffset> Wert:

* <xref:System.DateTimeOffset.Parse%2A>, der versucht, konvertiert die Zeichenfolgendarstellung einer Datums- und Uhrzeitangabe in einen <xref:System.DateTimeOffset> Wert ein, und löst eine Ausnahme aus, wenn die Konvertierung schlägt fehl.

* <xref:System.DateTimeOffset.TryParse%2A>, der versucht, konvertiert die Zeichenfolgendarstellung einer Datums- und Uhrzeitangabe in einen <xref:System.DateTimeOffset> Wert und gibt `false` , wenn die Konvertierung schlägt fehl.

* <xref:System.DateTimeOffset.ParseExact%2A>, konvertiert die Zeichenfolgendarstellung einer Datums- und Uhrzeitangabe in einem angegebenen Format, versucht ein <xref:System.DateTimeOffset> Wert. Die Methode löst eine Ausnahme aus, wenn bei der Konvertierung ein Fehler auftritt.

* <xref:System.DateTimeOffset.TryParseExact%2A>, konvertiert die Zeichenfolgendarstellung einer Datums- und Uhrzeitangabe in einem angegebenen Format, versucht ein <xref:System.DateTimeOffset> Wert. Die Methode gibt `false` zurück, wenn bei der Konvertierung ein Fehler auftritt.

Das folgende Beispiel veranschaulicht Aufrufe dieser vier Konvertierungsmethoden zum Instanziieren einer <xref:System.DateTimeOffset> Wert.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#7)]

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
