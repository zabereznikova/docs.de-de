---
title: Konvertieren zwischen DateTime und DateTimeOffset
description: Konvertieren zwischen DateTimeOffset-Werten und DateTime-Werten in .net. Die DateTimeOffset-Struktur bietet mehr Zeit Zonen Bewusstsein als die DateTime-Struktur.
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DateTime structure, converting
- time zones [.NET Framework], conversions
- UTC times, converting
- DateTimeOffset structure, converting
- converting DateTimeOffset and DateTime values
- dates [.NET Framework], converting
- converting times
- Date data type, converting
- local time conversions
ms.assetid: b605ff97-0c45-4c24-833f-4c6a3e8be64c
ms.openlocfilehash: cf55db7c22ad2495bdbeb3202fcefb89bae42d69
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768676"
---
# <a name="converting-between-datetime-and-datetimeoffset"></a>Konvertieren zwischen DateTime und DateTimeOffset

Obwohl die- <xref:System.DateTimeOffset> Struktur ein höheres Maß an Zeit Zonen Bewusstsein bietet als die- <xref:System.DateTime> Struktur, <xref:System.DateTime> werden Parameter häufiger in Methoden aufrufen verwendet. Aus diesem Grund ist die Möglichkeit, <xref:System.DateTimeOffset> Werte in Werte zu konvertieren <xref:System.DateTime> und umgekehrt, besonders wichtig. In diesem Thema wird gezeigt, wie diese Konvertierungen auf eine Weise durchgeführt werden, bei der so viele Zeitzoneninformationen wie möglich beibehalten werden.

> [!NOTE]
> Sowohl der <xref:System.DateTime> -Typ als auch der- <xref:System.DateTimeOffset> Typ weisen einige Einschränkungen auf, wenn Zeiten in Zeitzonen dargestellt werden. Mit der- <xref:System.DateTime.Kind%2A> Eigenschaft <xref:System.DateTime> kann nur koordinierte Weltzeit (UTC) und die lokale Zeitzone des Systems widerspiegeln. <xref:System.DateTimeOffset>Gibt den Offset einer Uhrzeit von der UTC wieder, aber nicht die tatsächliche Zeitzone, zu der dieser Offset gehört. Ausführliche Informationen zu Zeitwerten und zur Unterstützung von Zeitzonen finden Sie unter [auswählen zwischen DateTime, DateTimeOffset, TimeSpan und TimeZoneInfo](choosing-between-datetime.md).

## <a name="conversions-from-datetime-to-datetimeoffset"></a>Konvertierungen von DateTime in DateTimeOffset

Die- <xref:System.DateTimeOffset> Struktur bietet zwei äquivalente Möglichkeiten, um eine Konvertierung durchzuführen <xref:System.DateTime> <xref:System.DateTimeOffset> , die für die meisten Konvertierungen geeignet ist:

- Der- <xref:System.DateTimeOffset.%23ctor%2A> Konstruktor, der ein neues- <xref:System.DateTimeOffset> Objekt auf Grundlage eines-Werts erstellt <xref:System.DateTime> .

- Der implizite Konvertierungs Operator, mit dem Sie einem- <xref:System.DateTime> Objekt einen Wert zuweisen können <xref:System.DateTimeOffset> .

Bei UTC-und lokalen <xref:System.DateTime> Werten spiegelt die- <xref:System.DateTimeOffset.Offset%2A> Eigenschaft des resultierenden <xref:System.DateTimeOffset> Werts genau den UTC-oder lokalen Zeit Zonen Offset wider. Der folgende Code konvertiert z. b. eine UTC-Zeit in den entsprechenden- <xref:System.DateTimeOffset> Wert.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#1)]

In diesem Fall beträgt die Abweichung der `utcTime2`-Variablen 00:00. Entsprechend konvertiert der folgende Code eine lokale Zeit in den entsprechenden <xref:System.DateTimeOffset> Wert.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#2)]

Bei <xref:System.DateTime> Werten, deren- <xref:System.DateTime.Kind%2A> Eigenschaft ist <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType> , wird für diese beiden Konvertierungs Methoden jedoch ein Wert erzeugt, <xref:System.DateTimeOffset> dessen Offset der der lokalen Zeitzone entspricht. Dies wird im folgenden Beispiel gezeigt, das in der US Pacific Standard Time-Zone ausgeführt wird.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#3)]

Wenn der <xref:System.DateTime> Wert das Datum und die Uhrzeit in einer anderen als der lokalen Zeitzone oder UTC wieder gibt, können Sie ihn in einen <xref:System.DateTimeOffset> -Wert konvertieren und seine Zeitzoneninformationen beibehalten, indem Sie den überladenen <xref:System.DateTimeOffset.%23ctor%2A> Konstruktor aufrufen. Im folgenden Beispiel wird z. b. ein-Objekt instanziiert <xref:System.DateTimeOffset> , das die Central Standard Time wieder gibt.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#4)]

Der zweite Parameter dieser Konstruktorüberladung, ein <xref:System.TimeSpan> -Objekt, das den Offset der Uhrzeit von UTC darstellt, sollte durch Aufrufen der <xref:System.TimeZoneInfo.GetUtcOffset%28System.DateTime%29?displayProperty=nameWithType> -Methode der entsprechenden Zeitzone der Uhrzeit abgerufen werden. Der einzige Parameter der Methode ist der <xref:System.DateTime> Wert, der das Datum und die Uhrzeit darstellt, die konvertiert werden sollen. Wenn die Zeitzone die Sommerzeit unterstützt, ermöglicht dieser Parameter der Methode, die richtige Abweichung für dieses spezielle Datum und diese spezielle Uhrzeit zu bestimmen.

## <a name="conversions-from-datetimeoffset-to-datetime"></a>Konvertierungen von DateTimeOffset in DateTime

Die- <xref:System.DateTimeOffset.DateTime%2A> Eigenschaft wird am häufigsten für die <xref:System.DateTimeOffset> <xref:System.DateTime> Konvertierung verwendet. Es wird jedoch ein Wert zurückgegeben <xref:System.DateTime> , dessen- <xref:System.DateTime.Kind%2A> Eigenschaft ist <xref:System.DateTimeKind.Unspecified> , wie im folgenden Beispiel veranschaulicht.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#5)]

Dies bedeutet, dass alle Informationen über die <xref:System.DateTimeOffset> Beziehung des Werts zur UTC bei der Konvertierung verloren gehen, wenn die- <xref:System.DateTimeOffset.DateTime%2A> Eigenschaft verwendet wird. Dies wirkt sich <xref:System.DateTimeOffset> auf Werte aus, die der UTC-Zeit oder der lokalen Zeit des Systems entsprechen, da die <xref:System.DateTimeOffset.DateTime%2A> Struktur nur die beiden Zeitzonen in der-Eigenschaft widerspiegelt <xref:System.DateTime.Kind%2A> .

Um so viele Zeitzoneninformationen wie möglich beizubehalten, wenn ein <xref:System.DateTimeOffset> in einen <xref:System.DateTime> -Wert umgerechnet wird, können Sie die-Eigenschaft und die-Eigenschaft verwenden <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> .

### <a name="converting-a-utc-time"></a>Umstellen einer UTC-Zeit

Um anzugeben, dass es sich bei einem konvertierten <xref:System.DateTimeOffset.DateTime%2A> Wert um die UTC-Zeit handelt, können Sie den Wert der- <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> Eigenschaft abrufen. Dies unterscheidet sich von der- <xref:System.DateTimeOffset.DateTime%2A> Eigenschaft auf zwei Arten:

- Es wird ein Wert zurückgegeben, <xref:System.DateTime> dessen- <xref:System.DateTime.Kind%2A> Eigenschaft ist <xref:System.DateTimeKind.Utc> .

- Wenn der <xref:System.DateTimeOffset.Offset%2A> Eigenschafts Wert nicht gleich <xref:System.TimeSpan.Zero?displayProperty=nameWithType> ist, wird die Uhrzeit in die UTC konvertiert.

> [!NOTE]
> Wenn Ihre Anwendung erfordert, dass konvertierte <xref:System.DateTime> Werte eindeutig einen einzigen Zeitpunkt identifizieren, sollten Sie die- <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> Eigenschaft verwenden, um alle <xref:System.DateTimeOffset> <xref:System.DateTime> Konvertierungen zu verarbeiten.

Im folgenden Code wird die- <xref:System.DateTimeOffset.UtcDateTime%2A> Eigenschaft verwendet, um einen-Wert zu konvertieren, <xref:System.DateTimeOffset> dessen Abweichung <xref:System.TimeSpan.Zero?displayProperty=nameWithType> einem Wert entspricht <xref:System.DateTime> .

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#6)]

Im folgenden Code wird die <xref:System.DateTimeOffset.UtcDateTime%2A> -Eigenschaft verwendet, um sowohl eine Zeit Zonen Konvertierung als auch eine Typkonvertierung für einen <xref:System.DateTimeOffset> Wert auszuführen.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#12)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#12)]

### <a name="converting-a-local-time"></a>Lokale Zeit wird umgerechnet

Um anzugeben, dass ein <xref:System.DateTimeOffset> Wert die Ortszeit darstellt, können Sie den <xref:System.DateTime> von der-Eigenschaft zurückgegebenen Wert <xref:System.DateTimeOffset.DateTime%2A?displayProperty=nameWithType> an die- `static` `Shared` Methode (in Visual Basic) übergeben <xref:System.DateTime.SpecifyKind%2A> . Die-Methode gibt das an Sie übergebenen Datum und die Uhrzeit als ersten Parameter zurück, legt aber die- <xref:System.DateTime.Kind%2A> Eigenschaft auf den Wert fest, der durch den zweiten Parameter angegeben wird. Im folgenden Code wird die- <xref:System.DateTime.SpecifyKind%2A> Methode verwendet, wenn ein- <xref:System.DateTimeOffset> Wert, dessen Offset dem Wert der lokalen Zeitzone entspricht, umgerechnet wird.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#7)]

Sie können auch die- <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> Eigenschaft verwenden, um einen- <xref:System.DateTimeOffset> Wert in einen lokalen Wert zu konvertieren <xref:System.DateTime> . Die- <xref:System.DateTime.Kind%2A> Eigenschaft des zurückgegebenen <xref:System.DateTime> Werts ist <xref:System.DateTimeKind.Local> . Im folgenden Code wird die- <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> Eigenschaft verwendet, wenn ein- <xref:System.DateTimeOffset> Wert, dessen Offset dem Wert der lokalen Zeitzone entspricht, umgerechnet wird.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#10)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#10)]

Wenn Sie einen <xref:System.DateTime> Wert mithilfe der <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> -Eigenschaft abrufen, konvertiert der- `get` Accessor der Eigenschaft zuerst den <xref:System.DateTimeOffset> Wert in UTC und konvertiert ihn dann durch Aufrufen der-Methode in die lokale Zeit <xref:System.DateTimeOffset.ToLocalTime%2A> . Dies bedeutet, dass Sie einen Wert aus der- <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> Eigenschaft abrufen können, um gleichzeitig eine Zeit Zonen Konvertierung auszuführen, wenn Sie eine Typkonvertierung durchführen. Es bedeutet auch, dass die beim Durchführen der Konvertierung die Anpassungsregeln der lokalen Zeitzone angewendet werden. Der folgende Code veranschaulicht die Verwendung der <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> -Eigenschaft, um sowohl einen Typ als auch eine Zeit Zonen Konvertierung auszuführen.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#11)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#11)]

### <a name="a-general-purpose-conversion-method"></a>Eine allgemeine Konvertierungsmethode

Im folgenden Beispiel wird eine Methode mit dem Namen definiert `ConvertFromDateTimeOffset` , die <xref:System.DateTimeOffset> Werte in- <xref:System.DateTime> Werte konvertiert. Basierend auf dem Offset bestimmt der Wert, ob der <xref:System.DateTimeOffset> Wert eine UTC-Zeit, eine lokale Zeit oder eine andere Zeit ist, und definiert die Eigenschaft des zurückgegebenen Datums-und Uhrzeitwerts <xref:System.DateTime.Kind%2A> entsprechend.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#8)]

Im folgenden Beispiel wird die `ConvertFromDateTimeOffset` -Methode aufgerufen, um Werte zu konvertieren, <xref:System.DateTimeOffset> die eine UTC-Zeit, eine lokale Zeit und eine Uhrzeit in der US-zentral Standard Zeitzone darstellen.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#9)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#9)]

Beachten Sie, dass bei diesem Code von zwei Annahmen ausgegangen wird, die je nach der Anwendung und der Quelle ihrer Datums- und Uhrzeitwerte, nicht immer zutreffen:

- Dabei wird davon ausgegangen, dass ein Datums-und Uhrzeitwert, dessen Offset <xref:System.TimeSpan.Zero?displayProperty=nameWithType> UTC darstellt. Tatsächlich ist die UTC keine Zeit in einer bestimmten Zeitzone, sondern die Uhrzeit, nach der alle Uhrzeiten in den Zeitzone der Welt standardisiert sind. Zeitzonen können auch einen Offset von aufweisen <xref:System.TimeSpan.Zero> .

- Es wird angenommen, dass ein Datums- und Uhrzeitwert, dessen Abweichung der Abweichung der lokalen Zeitzone entspricht, die lokale Zeitzone darstellt. Dies ist möglicherweise nicht der Fall, weil Datums- und Uhrzeitwerte nicht mehr ihrer ursprünglichen Zeitzone verknüpft sind. Datum und Uhrzeit können aus einer anderen Zeitzone mit der gleichen Abweichung stammen.

## <a name="see-also"></a>Weitere Informationen

- [Datumsangaben, Uhrzeiten und Zeitzonen](index.md)
