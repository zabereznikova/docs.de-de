---
title: Konvertieren zwischen DateTime und DateTimeOffset
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb91ed8edd0c5cd3cb1d051157596f311718195d
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2019
ms.locfileid: "70107065"
---
# <a name="converting-between-datetime-and-datetimeoffset"></a>Konvertieren zwischen DateTime und DateTimeOffset

Obwohl die <xref:System.DateTimeOffset> -Struktur ein höheres Maß an Zeit Zonen Bewusstsein bietet als <xref:System.DateTime> die- <xref:System.DateTime> Struktur, werden Parameter häufiger in Methoden aufrufen verwendet. Aus diesem Grund ist die Möglichkeit, Werte <xref:System.DateTimeOffset> in Werte <xref:System.DateTime> zu konvertieren und umgekehrt, besonders wichtig. In diesem Thema wird gezeigt, wie diese Konvertierungen auf eine Weise durchgeführt werden, bei der so viele Zeitzoneninformationen wie möglich beibehalten werden.

> [!NOTE]
> Sowohl der <xref:System.DateTime> -Typ <xref:System.DateTimeOffset> als auch der-Typ weisen einige Einschränkungen auf, wenn Zeiten in Zeitzonen dargestellt werden. Mit der <xref:System.DateTime.Kind%2A> - <xref:System.DateTime> Eigenschaft kann nur koordinierte Weltzeit (UTC) und die lokale Zeitzone des Systems widerspiegeln. <xref:System.DateTimeOffset>Gibt den Offset einer Uhrzeit von der UTC wieder, aber nicht die tatsächliche Zeitzone, zu der dieser Offset gehört. Ausführliche Informationen zu Zeitwerten und zur Unterstützung von Zeitzonen finden Sie unter [auswählen zwischen DateTime, DateTimeOffset, TimeSpan und TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md).

## <a name="conversions-from-datetime-to-datetimeoffset"></a>Konvertierungen von DateTime in DateTimeOffset

Die <xref:System.DateTimeOffset> -Struktur bietet zwei äquivalente Möglichkeiten <xref:System.DateTime> , <xref:System.DateTimeOffset> um eine Konvertierung durchzuführen, die für die meisten Konvertierungen geeignet ist:

- Der <xref:System.DateTimeOffset.%23ctor%2A> -Konstruktor, der ein neues <xref:System.DateTimeOffset> -Objekt auf Grundlage <xref:System.DateTime> eines-Werts erstellt.

- Der implizite Konvertierungs Operator, mit dem Sie einem- <xref:System.DateTime> <xref:System.DateTimeOffset> Objekt einen Wert zuweisen können.

Bei UTC-und <xref:System.DateTime> lokalen Werten spiegelt <xref:System.DateTimeOffset.Offset%2A> die-Eigenschaft des <xref:System.DateTimeOffset> resultierenden Werts genau den UTC-oder lokalen Zeit Zonen Offset wider. Der folgende Code konvertiert z. b. eine UTC-Zeit in <xref:System.DateTimeOffset> den entsprechenden-Wert.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#1)]

In diesem Fall beträgt die Abweichung der `utcTime2`-Variablen 00:00. Entsprechend konvertiert der folgende Code eine lokale Zeit in den entsprechenden <xref:System.DateTimeOffset> Wert.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#2)]

Bei Werten, <xref:System.DateTime> deren <xref:System.DateTime.Kind%2A> -Eigenschaft ist <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, wird für diese beiden Konvertierungs <xref:System.DateTimeOffset> Methoden jedoch ein Wert erzeugt, dessen Offset der der lokalen Zeitzone entspricht. Dies wird im folgenden Beispiel gezeigt, das in der Zeitzone „Pacific Standard Time“ (USA) ausgeführt wird.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#3)]

Wenn der <xref:System.DateTime> Wert das Datum und die Uhrzeit in einer anderen als der lokalen Zeitzone oder UTC wieder gibt, können Sie ihn in einen <xref:System.DateTimeOffset> -Wert konvertieren und seine Zeitzoneninformationen beibehalten, indem <xref:System.DateTimeOffset.%23ctor%2A> Sie den überladenen Konstruktor aufrufen. Im folgenden Beispiel wird z. b. ein <xref:System.DateTimeOffset> -Objekt instanziiert, das die Central Standard Time wieder gibt.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#4)]

Der zweite Parameter dieser Konstruktorüberladung, ein <xref:System.TimeSpan> -Objekt, das den Offset der Uhrzeit von UTC darstellt, sollte durch Aufrufen der <xref:System.TimeZoneInfo.GetUtcOffset%28System.DateTime%29?displayProperty=nameWithType> -Methode der entsprechenden Zeitzone der Uhrzeit abgerufen werden. Der einzige Parameter der Methode ist der <xref:System.DateTime> Wert, der das Datum und die Uhrzeit darstellt, die konvertiert werden sollen. Wenn die Zeitzone die Sommerzeit unterstützt, ermöglicht dieser Parameter der Methode, die richtige Abweichung für dieses spezielle Datum und diese spezielle Uhrzeit zu bestimmen.

## <a name="conversions-from-datetimeoffset-to-datetime"></a>Konvertierungen von DateTimeOffset in DateTime

Die <xref:System.DateTimeOffset.DateTime%2A> -Eigenschaft wird am häufigsten <xref:System.DateTimeOffset> für <xref:System.DateTime> die Konvertierung verwendet. Es wird jedoch ein <xref:System.DateTime> Wert zurückgegeben, dessen <xref:System.DateTimeKind.Unspecified> <xref:System.DateTime.Kind%2A> -Eigenschaft ist, wie im folgenden Beispiel veranschaulicht.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#5)]

Dies bedeutet, dass alle Informationen über <xref:System.DateTimeOffset> die Beziehung des Werts zur UTC bei der Konvertierung verloren gehen, <xref:System.DateTimeOffset.DateTime%2A> wenn die-Eigenschaft verwendet wird. Dies wirkt <xref:System.DateTimeOffset> sich auf Werte aus, die der UTC-Zeit oder der lokalen Zeit des <xref:System.DateTimeOffset.DateTime%2A> Systems entsprechen, da die Struktur nur die <xref:System.DateTime.Kind%2A> beiden Zeitzonen in der-Eigenschaft widerspiegelt.

Um so viele Zeitzoneninformationen wie möglich beizubehalten, wenn ein <xref:System.DateTimeOffset> in einen <xref:System.DateTime> -Wert umgerechnet wird, können <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> Sie <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> die-Eigenschaft und die-Eigenschaft verwenden.

### <a name="converting-a-utc-time"></a>Umstellen einer UTC-Zeit

Um anzugeben, dass es <xref:System.DateTimeOffset.DateTime%2A> sich bei einem konvertierten Wert um die UTC-Zeit handelt, <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> können Sie den Wert der-Eigenschaft abrufen. Dies unterscheidet sich <xref:System.DateTimeOffset.DateTime%2A> von der-Eigenschaft auf zwei Arten:

- Es wird ein <xref:System.DateTime> Wert zurück <xref:System.DateTime.Kind%2A> gegeben, <xref:System.DateTimeKind.Utc>dessen-Eigenschaft ist.

- Wenn der <xref:System.DateTimeOffset.Offset%2A> Eigenschafts Wert nicht gleich <xref:System.TimeSpan.Zero?displayProperty=nameWithType>ist, wird die Uhrzeit in die UTC konvertiert.

> [!NOTE]
> Wenn Ihre Anwendung erfordert, dass <xref:System.DateTime> konvertierte Werte eindeutig einen einzigen Zeitpunkt identifizieren, sollten Sie die <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> -Eigenschaft verwenden, um alle <xref:System.DateTimeOffset> Konvertierungen zu <xref:System.DateTime> verarbeiten.

Im folgenden Code wird die <xref:System.DateTimeOffset.UtcDateTime%2A> -Eigenschaft verwendet, <xref:System.DateTimeOffset> um einen-Wert <xref:System.TimeSpan.Zero?displayProperty=nameWithType> zu konvertieren <xref:System.DateTime> , dessen Abweichung einem Wert entspricht.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#6)]

Im folgenden Code wird die <xref:System.DateTimeOffset.UtcDateTime%2A> -Eigenschaft verwendet, um sowohl eine Zeit Zonen Konvertierung als auch eine Typkonvertierung für einen <xref:System.DateTimeOffset> Wert auszuführen.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#12)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#12)]

### <a name="converting-a-local-time"></a>Lokale Zeit wird umgerechnet

Um anzugeben, dass <xref:System.DateTimeOffset> ein Wert die Ortszeit darstellt, können Sie den <xref:System.DateTime> von der <xref:System.DateTimeOffset.DateTime%2A?displayProperty=nameWithType> -Eigenschaft zurückgegebenen Wert an `static` die`Shared` -Methode ( <xref:System.DateTime.SpecifyKind%2A> in Visual Basic) übergeben. Die-Methode gibt das an Sie übergebenen Datum und die Uhrzeit als ersten Parameter zurück, <xref:System.DateTime.Kind%2A> legt aber die-Eigenschaft auf den Wert fest, der durch den zweiten Parameter angegeben wird. Im folgenden Code wird die <xref:System.DateTime.SpecifyKind%2A> -Methode verwendet, <xref:System.DateTimeOffset> wenn ein-Wert, dessen Offset dem Wert der lokalen Zeitzone entspricht, umgerechnet wird.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#7)]

Sie können auch die <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> -Eigenschaft verwenden, um einen <xref:System.DateTimeOffset> -Wert in <xref:System.DateTime> einen lokalen Wert zu konvertieren. Die <xref:System.DateTime.Kind%2A> -Eigenschaft des zurück <xref:System.DateTime> gegebenen Werts <xref:System.DateTimeKind.Local>ist. Im folgenden Code wird die <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> -Eigenschaft verwendet, <xref:System.DateTimeOffset> wenn ein-Wert, dessen Offset dem Wert der lokalen Zeitzone entspricht, umgerechnet wird. 

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#10)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#10)]

Wenn Sie einen <xref:System.DateTime> Wert mithilfe <xref:System.DateTimeOffset.ToLocalTime%2A> der <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> -Eigenschaft abrufen, konvertiert der `get` -Accessor der Eigenschaft <xref:System.DateTimeOffset> zuerst den Wert in UTC und konvertiert ihn dann durch Aufrufen der-Methode in die lokale Zeit. Dies bedeutet, dass Sie einen Wert aus der <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> -Eigenschaft abrufen können, um gleichzeitig eine Zeit Zonen Konvertierung auszuführen, wenn Sie eine Typkonvertierung durchführen. Es bedeutet auch, dass die beim Durchführen der Konvertierung die Anpassungsregeln der lokalen Zeitzone angewendet werden. Der folgende Code veranschaulicht die Verwendung <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> der-Eigenschaft, um sowohl einen Typ als auch eine Zeit Zonen Konvertierung auszuführen.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#11)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#11)]

### <a name="a-general-purpose-conversion-method"></a>Eine allgemeine Konvertierungsmethode

Im folgenden Beispiel wird eine Methode mit `ConvertFromDateTimeOffset` dem Namen <xref:System.DateTimeOffset> definiert, <xref:System.DateTime> die Werte in-Werte konvertiert. Basierend auf dem Offset bestimmt der Wert, ob <xref:System.DateTimeOffset> der Wert eine UTC- <xref:System.DateTime.Kind%2A> Zeit, eine lokale Zeit oder eine andere Zeit ist, und definiert die Eigenschaft des zurückgegebenen Datums-und Uhrzeitwerts entsprechend.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#8)]

Im folgenden Beispiel wird die `ConvertFromDateTimeOffset` -Methode aufgerufen <xref:System.DateTimeOffset> , um Werte zu konvertieren, die eine UTC-Zeit, eine lokale Zeit und eine Uhrzeit in der Central Standard Time-Zeitzone (USA) darstellen.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#9)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#9)]

Beachten Sie, dass bei diesem Code von zwei Annahmen ausgegangen wird, die je nach der Anwendung und der Quelle ihrer Datums- und Uhrzeitwerte, nicht immer zutreffen:

- Dabei wird <xref:System.TimeSpan.Zero?displayProperty=nameWithType> davon ausgegangen, dass ein Datums-und Uhrzeitwert, dessen Offset UTC darstellt. Tatsächlich ist die UTC keine Zeit in einer bestimmten Zeitzone, sondern die Uhrzeit, nach der alle Uhrzeiten in den Zeitzone der Welt standardisiert sind. Zeitzonen können auch einen Offset von <xref:System.TimeSpan.Zero>aufweisen.

- Es wird angenommen, dass ein Datums- und Uhrzeitwert, dessen Abweichung der Abweichung der lokalen Zeitzone entspricht, die lokale Zeitzone darstellt. Dies ist möglicherweise nicht der Fall, weil Datums- und Uhrzeitwerte nicht mehr ihrer ursprünglichen Zeitzone verknüpft sind. Datum und Uhrzeit können aus einer anderen Zeitzone mit der gleichen Abweichung stammen.

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
