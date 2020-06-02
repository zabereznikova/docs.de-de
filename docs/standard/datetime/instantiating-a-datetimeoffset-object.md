---
title: Instanziieren eines "DateTimeOffset"-Objekts
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
ms.openlocfilehash: c290af0c9cef619000a6620ba35209489856c5b8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84281595"
---
# <a name="instantiating-a-datetimeoffset-object"></a>Instanziieren eines "DateTimeOffset"-Objekts

Die- <xref:System.DateTimeOffset> Struktur bietet eine Reihe von Möglichkeiten, neue <xref:System.DateTimeOffset> Werte zu erstellen. Viele von Ihnen entsprechen direkt den Methoden zum Instanziieren neuer <xref:System.DateTime> Werte mit Erweiterungen, mit denen Sie die Abweichung des Datums-und Uhrzeitwerts von der koordinierten Weltzeit (UTC) angeben können. Vor allem können Sie einen <xref:System.DateTimeOffset> Wert auf folgende Weise instanziieren:

- Mithilfe eines Datums-und uhrzeitanliterals.

- Durch Aufrufen eines <xref:System.DateTimeOffset> Konstruktors.

- Durch implizites wandeln eines Werts in einen <xref:System.DateTimeOffset> Wert.

- Durch Analysieren der Zeichenfolgendarstellung eines Datums- und Uhrzeitwerts.

Dieses Thema enthält ausführlichere Informationen und Codebeispiele, die diese Methoden zum Instanziieren neuer <xref:System.DateTimeOffset> Werte veranschaulichen.

## <a name="date-and-time-literals"></a>Datums- und Zeitliterale

Für Sprachen, die dies unterstützen, besteht eine der gängigsten Methoden zum Instanziieren eines Werts darin, <xref:System.DateTime> das Datum und die Uhrzeit als hart codierten Literalwert bereitzustellen. Der folgende Visual Basic Code erstellt z. b. ein- <xref:System.DateTime> Objekt, dessen Wert dem 1. Januar 2008 und 10:00 Uhr entspricht.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#1)]

<xref:System.DateTimeOffset>Werte können auch mit Datums-und Uhrzeit Literalen initialisiert werden, wenn Sprachen verwendet werden, die <xref:System.DateTime> Literale unterstützen. Der folgende Visual Basic Code erstellt z. b. ein- <xref:System.DateTimeOffset> Objekt.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#2)]

Wie die Konsolenausgabe zeigt, <xref:System.DateTimeOffset> wird dem auf diese Weise erstellten Wert der Offset der lokalen Zeitzone zugewiesen. Dies bedeutet, dass ein <xref:System.DateTimeOffset> mit einem zeichenliteralwert zugewiesener Wert keinen einzelnen Zeitpunkt identifiziert, wenn der Code auf verschiedenen Computern ausgeführt wird.

## <a name="datetimeoffset-constructors"></a>DateTimeOffset-Konstruktoren

Der- <xref:System.DateTimeOffset> Typ definiert sechs Konstruktoren. Vier von Ihnen entsprechen direkt den <xref:System.DateTime> Konstruktoren mit einem zusätzlichen Parameter vom Typ <xref:System.TimeSpan> , der den Offset von Datum und Uhrzeit von UTC definiert. Diese ermöglichen es Ihnen, <xref:System.DateTimeOffset> basierend auf dem Wert der einzelnen Datums-und Uhrzeit Komponenten einen Wert zu definieren. Im folgenden Code werden z. b. diese vier Konstruktoren verwendet, um <xref:System.DateTimeOffset> Objekte mit identischen Werten von 7/1/2008 12:05 Uhr + 01:00 zu instanziieren.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#3)]

Beachten Sie Folgendes: Wenn der Wert des <xref:System.DateTimeOffset> Objekts, das mithilfe eines- <xref:System.Globalization.PersianCalendar> Objekts als eines der Argumente für den Konstruktor instanziiert wird, in der Konsole angezeigt wird, wird es als Datum im gregorianischen Kalender und nicht im persischen Kalender ausgedrückt. Informationen zum Ausgeben eines Datums mit dem persischen Kalender finden Sie im Beispiel im <xref:System.Globalization.PersianCalendar> Thema.

Die anderen beiden Konstruktoren erstellen ein- <xref:System.DateTimeOffset> Objekt aus einem <xref:System.DateTime> Wert. Der erste verfügt über einen einzelnen Parameter, den Wert, der <xref:System.DateTime> in einen-Wert konvertiert werden soll <xref:System.DateTimeOffset> . Der Offset des resultierenden <xref:System.DateTimeOffset> Werts hängt von der <xref:System.DateTime.Kind%2A> -Eigenschaft des einzelnen Parameters des Konstruktors ab. Wenn der Wert ist <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> , wird der Offset auf festgelegt <xref:System.TimeSpan.Zero?displayProperty=nameWithType> . Andernfalls wird die Abweichung entsprechend der lokalen Zeitzone eingestellt. Im folgenden Beispiel wird veranschaulicht, wie dieser Konstruktor verwendet wird, um Objekte zu instanziieren, <xref:System.DateTimeOffset> die die UTC und die lokale Zeitzone darstellen:

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#4)]

> [!NOTE]
> Das Aufrufen der Überladung des <xref:System.DateTimeOffset> Konstruktors, der über einen einzelnen Parameter verfügt, <xref:System.DateTime> entspricht dem Durchführen einer impliziten Konvertierung eines <xref:System.DateTime> Werts in einen- <xref:System.DateTimeOffset> Wert.

Der zweite Konstruktor, der ein <xref:System.DateTimeOffset> -Objekt aus einem- <xref:System.DateTime> Wert erstellt, verfügt über zwei Parameter: den <xref:System.DateTime> zu konvertierenden Wert und einen <xref:System.TimeSpan> -Wert, der das Datum und die Uhrzeit Abweichung von UTC darstellt. Dieser Offset Wert muss der <xref:System.DateTime.Kind%2A> -Eigenschaft des ersten Parameters des Konstruktors entsprechen, oder es wird eine ausgelöst <xref:System.ArgumentException> . Wenn die- <xref:System.DateTime.Kind%2A> Eigenschaft des ersten Parameters ist <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> , muss der Wert des zweiten Parameters sein <xref:System.TimeSpan.Zero?displayProperty=nameWithType> . Wenn die- <xref:System.DateTime.Kind%2A> Eigenschaft des ersten Parameters ist <xref:System.DateTimeKind.Local?displayProperty=nameWithType> , muss der Wert des zweiten Parameters der Zeit Zonen Abweichung des lokalen Systems sein. Wenn die- <xref:System.DateTime.Kind%2A> Eigenschaft des ersten Parameters ist <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType> , kann der Offset ein beliebiger gültiger Wert sein. Der folgende Code veranschaulicht Aufrufe dieses Konstruktors, um in-Werte zu konvertieren <xref:System.DateTime> <xref:System.DateTimeOffset> .

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#5)]

## <a name="implicit-type-conversion"></a>Implizite Typkonvertierung

Der- <xref:System.DateTimeOffset> Typ unterstützt eine implizite Typkonvertierung: von einem- <xref:System.DateTime> Wert in einen- <xref:System.DateTimeOffset> Wert. (Eine implizite Typkonvertierung ist eine Konvertierung von einem Typ in einen anderen, für die keine explizite Umwandlung (in C#) oder Konvertierung (in Visual Basic) erforderlich ist und bei der keine Informationen verloren gehen. Dies ermöglicht beispielsweise folgenden Code:

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#6)]

Der Offset des resultierenden <xref:System.DateTimeOffset> Werts hängt vom <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> Eigenschafts Wert ab. Wenn der Wert ist <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> , wird der Offset auf festgelegt <xref:System.TimeSpan.Zero?displayProperty=nameWithType> . Wenn der Wert entweder <xref:System.DateTimeKind.Local?displayProperty=nameWithType> oder ist <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType> , wird der Offset auf den Wert der lokalen Zeitzone festgelegt.

## <a name="parsing-the-string-representation-of-a-date-and-time"></a>Die Zeichen folgen Darstellung eines Datums und einer Uhrzeit werden verarbeitet.

Der- <xref:System.DateTimeOffset> Typ unterstützt vier Methoden, die es Ihnen ermöglichen, die Zeichen folgen Darstellung eines Datums und einer Uhrzeit in einen-Wert zu konvertieren <xref:System.DateTimeOffset> :

- <xref:System.DateTimeOffset.Parse%2A>, der versucht, die Zeichen folgen Darstellung eines Datums und einer Uhrzeit in einen <xref:System.DateTimeOffset> -Wert zu konvertieren, und löst eine Ausnahme aus, wenn bei der Konvertierung ein Fehler auftritt.

- <xref:System.DateTimeOffset.TryParse%2A>, der versucht, die Zeichen folgen Darstellung eines Datums und einer Uhrzeit in einen <xref:System.DateTimeOffset> -Wert zu konvertieren, und gibt zurück, `false` Wenn die Konvertierung fehlschlägt.

- <xref:System.DateTimeOffset.ParseExact%2A>, der versucht, die Zeichen folgen Darstellung eines Datums und einer Uhrzeit in einem angegebenen Format in einen-Wert zu konvertieren <xref:System.DateTimeOffset> . Die Methode löst eine Ausnahme aus, wenn bei der Konvertierung ein Fehler auftritt.

- <xref:System.DateTimeOffset.TryParseExact%2A>, der versucht, die Zeichen folgen Darstellung eines Datums und einer Uhrzeit in einem angegebenen Format in einen-Wert zu konvertieren <xref:System.DateTimeOffset> . Die Methode gibt `false` zurück, wenn bei der Konvertierung ein Fehler auftritt.

Das folgende Beispiel veranschaulicht Aufrufe dieser vier Zeichen folgen Konvertierungs Methoden, um einen-Wert zu instanziieren <xref:System.DateTimeOffset> .

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#7)]

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](index.md)
