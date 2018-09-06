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
ms.openlocfilehash: 830e3e6e98be2eaaff2af6c0bdac650732833ab7
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43864420"
---
# <a name="converting-between-datetime-and-datetimeoffset"></a>Konvertieren zwischen DateTime und DateTimeOffset

Obwohl die <xref:System.DateTimeOffset> Struktur bietet einen höheren Grad der Zeitzonen als der <xref:System.DateTime> Struktur <xref:System.DateTime> Parameter werden häufiger in Methodenaufrufen verwendet. Daher die Möglichkeit zum Konvertieren <xref:System.DateTimeOffset> Werte <xref:System.DateTime> -Werte und umgekehrt ist besonders wichtig. In diesem Thema veranschaulicht, wie diese Konvertierungen auf eine Weise vorzunehmen, die so viele Zeitzoneninformationen wie möglich beibehalten.

> [!NOTE]
> Sowohl die <xref:System.DateTime> und <xref:System.DateTimeOffset> Typen weisen einige Einschränkungen auf, wenn Zeiten in Zeitzonen, darstellt. Mit der <xref:System.DateTime.Kind%2A> Eigenschaft <xref:System.DateTime> wird nur die koordinierte Weltzeit (UTC) und die lokale Zeitzone des Systems widerspiegeln. <xref:System.DateTimeOffset> Gibt die Abweichung einer Uhrzeit in UTC, aber er berücksichtigt nicht, dass die tatsächliche Zeitzone, zu der diese Abweichung, gehört. Weitere Informationen zu Uhrzeitwerten und Unterstützung von Zeitzonen finden Sie unter [auswählen zwischen DateTime, DateTimeOffset, TimeSpan und TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md).

## <a name="conversions-from-datetime-to-datetimeoffset"></a>Konvertierungen von DateTime in DateTimeOffset

Die <xref:System.DateTimeOffset> Struktur bietet zwei gleichwertige Möglichkeiten zum <xref:System.DateTime> zu <xref:System.DateTimeOffset> Konvertierung, die für die meisten Konvertierungen eignen:

* Die <xref:System.DateTimeOffset.%23ctor%2A> Konstruktor, der eine neue erstellt <xref:System.DateTimeOffset> Objekt auf Grundlage einer <xref:System.DateTime> Wert.

* Der implizite Konvertierungsoperator, die Sie zuweisen kann eine <xref:System.DateTime> -Werts in einen <xref:System.DateTimeOffset> Objekt.

Für UTC und lokale <xref:System.DateTime> Werte, die <xref:System.DateTimeOffset.Offset%2A> -Eigenschaft des resultierenden <xref:System.DateTimeOffset> Wert entspricht genau die Abweichung der Zeitzone UTC-Zeit oder Ortszeit. Der folgende Code konvertiert z.B. eine UTC-Zeit, in den entsprechenden <xref:System.DateTimeOffset> Wert.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#1)]

In diesem Fall beträgt die Abweichung der `utcTime2`-Variablen 00:00. Auf ähnliche Weise mit der folgende Code eine lokale Zeit konvertiert, in den entsprechenden <xref:System.DateTimeOffset> Wert.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#2)]

Beachten Sie jedoch bei <xref:System.DateTime> Werte, deren <xref:System.DateTime.Kind%2A> Eigenschaft <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, erzeugen diese beiden Konvertierungsmethoden eine <xref:System.DateTimeOffset> Wert, dessen Abweichung der lokalen Zeitzone. Dies wird im folgenden Beispiel gezeigt, das in der Zeitzone „Pacific Standard Time“ (USA) ausgeführt wird.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#3)]

Wenn die <xref:System.DateTime> Wert entspricht, das Datum und Uhrzeit in einer als der Ortszeit oder UTC, können Sie diese zum Konvertieren einer <xref:System.DateTimeOffset> Wert und die Zeitzoneninformationen beibehalten, durch Aufrufen der überladenen <xref:System.DateTimeOffset.%23ctor%2A> Konstruktor. Z. B. das folgende Beispiel instanziiert ein <xref:System.DateTimeOffset> -Objekt, das Central Standard Time wiedergibt.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#4)]

Der zweite Parameter dieser Konstruktorüberladung, ein <xref:System.TimeSpan> -Objekt, das den Offset von der koordinierten Weltzeit darstellt, die durch den Aufruf abgerufen werden soll die <xref:System.TimeZoneInfo.GetUtcOffset%28System.DateTime%29?displayProperty=nameWithType> Methode die entsprechende Zeitzone. Ist der einzige Parameter dieser Methode die <xref:System.DateTime> Wert, der zu konvertierende Datum und Uhrzeit darstellt. Wenn die Zeitzone die Sommerzeit unterstützt, ermöglicht dieser Parameter der Methode, die richtige Abweichung für dieses spezielle Datum und diese spezielle Uhrzeit zu bestimmen.

## <a name="conversions-from-datetimeoffset-to-datetime"></a>Konvertierungen von DateTimeOffset in DateTime

Die <xref:System.DateTimeOffset.DateTime%2A> Eigenschaft wird am häufigsten auszuführenden <xref:System.DateTimeOffset> zu <xref:System.DateTime> Konvertierung. Allerdings gibt es eine <xref:System.DateTime> , deren Wert <xref:System.DateTime.Kind%2A> -Eigenschaft ist <xref:System.DateTimeKind.Unspecified>, wie im folgende Beispiel veranschaulicht.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#5)]

Dies bedeutet, dass alle Informationen zu der <xref:System.DateTimeOffset> Uhrzeitwerts Beziehung zur UTC ist der Konvertierung verloren gehen bei der <xref:System.DateTimeOffset.DateTime%2A> Eigenschaft wird verwendet. Dies wirkt sich auf <xref:System.DateTimeOffset> Werte, die auf UTC-Zeit oder Ortszeit des Systems, da entsprechen den <xref:System.DateTimeOffset.DateTime%2A> Struktur widerspiegelt, nur diese beiden Zeitzonen in seine <xref:System.DateTime.Kind%2A> Eigenschaft.

Um so viele Zeitzoneninformationen wie möglich zu erhalten, bei der Konvertierung ein <xref:System.DateTimeOffset> auf eine <xref:System.DateTime> Wert können Sie die <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> und <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> Eigenschaften.

### <a name="converting-a-utc-time"></a>Konvertieren einer UTC-Zeit

Gibt an, dass eine konvertierte <xref:System.DateTimeOffset.DateTime%2A> Wert die UTC-Zeit ist, können Sie den Wert von Abrufen der <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> Eigenschaft. Es unterscheidet sich von der <xref:System.DateTimeOffset.DateTime%2A> Eigenschaft gibt es zwei Möglichkeiten:

* Gibt eine <xref:System.DateTime> , deren Wert <xref:System.DateTime.Kind%2A> Eigenschaft <xref:System.DateTimeKind.Utc>.

* Wenn die <xref:System.DateTimeOffset.Offset%2A> -Eigenschaftswert ist nicht gleich <xref:System.TimeSpan.Zero?displayProperty=nameWithType>, die Uhrzeit in UTC konvertiert.

> [!NOTE]
> Wenn Ihre Anwendung, dass konvertierte erfordert <xref:System.DateTime> Werte eindeutig einen bestimmten Zeitpunkt identifizieren, sollten Sie verwenden die <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> Eigenschaft zur Behandlung aller <xref:System.DateTimeOffset> zu <xref:System.DateTime> Konvertierungen.

Der folgende code verwendet die <xref:System.DateTimeOffset.UtcDateTime%2A> Eigenschaft konvertieren eine <xref:System.DateTimeOffset> Wert, dessen Abweichung entspricht <xref:System.TimeSpan.Zero?displayProperty=nameWithType> auf eine <xref:System.DateTime> Wert.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#6)]

Der folgende code verwendet die <xref:System.DateTimeOffset.UtcDateTime%2A> Eigenschaft, um sowohl eine zeitzonenkonvertierung als auch eine typkonvertierung auszuführen, auf eine <xref:System.DateTimeOffset> Wert.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#12)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#12)]

### <a name="converting-a-local-time"></a>Eine lokale Zeit konvertieren

Gibt an, dass eine <xref:System.DateTimeOffset> Wert die Ortszeit darstellt, können Sie übergeben die <xref:System.DateTime> von zurückgegebene Wert die <xref:System.DateTimeOffset.DateTime%2A?displayProperty=nameWithType> Eigenschaft, um die `static` (`Shared` in Visual Basic) <xref:System.DateTime.SpecifyKind%2A> Methode. Die Methode gibt das Datum und Uhrzeit, die als erster Parameter übergeben, aber legt die <xref:System.DateTime.Kind%2A> Eigenschaft als zweiten Parameter angegebene Wert. Der folgende code verwendet die <xref:System.DateTime.SpecifyKind%2A> Methode bei der Konvertierung einer <xref:System.DateTimeOffset> Wert, dessen Abweichung der lokalen Zeitzone entspricht.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#7)]

Sie können auch die <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> Eigenschaft konvertieren eine <xref:System.DateTimeOffset> -Wert in einen lokalen <xref:System.DateTime> Wert. Die <xref:System.DateTime.Kind%2A> -Eigenschaft des zurückgegebenen <xref:System.DateTime> Wert <xref:System.DateTimeKind.Local>. Der folgende code verwendet die <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> Eigenschaft bei der Konvertierung einer <xref:System.DateTimeOffset> Wert, dessen Abweichung der lokalen Zeitzone entspricht. 

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#10)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#10)]

Beim Abrufen einer <xref:System.DateTime> -Wert mithilfe der <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> -Eigenschaft, die der Eigenschaft `get` Accessor zuerst konvertiert die <xref:System.DateTimeOffset> Wert in UTC, konvertiert sie dann lokale Zeit durch Aufrufen der <xref:System.DateTimeOffset.ToLocalTime%2A> Methode. Dies bedeutet, dass Sie einen Wert aus abrufen können die <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> Eigenschaft, um eine zeitzonenkonvertierung zur gleichen Zeit führen, dass Sie eine typkonvertierung auszuführen. Es bedeutet auch, dass die beim Durchführen der Konvertierung die Anpassungsregeln der lokalen Zeitzone angewendet werden. Der folgende Code veranschaulicht die Verwendung der <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> Eigenschaft, um sowohl einen Typ als auch eine zeitzonenkonvertierung auszuführen.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#11)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#11)]

### <a name="a-general-purpose-conversion-method"></a>Eine allgemeine Konvertierungsmethode

Das folgende Beispiel definiert eine Methode namens `ConvertFromDateTimeOffset` , konvertiert <xref:System.DateTimeOffset> Werte <xref:System.DateTime> Werte. Basierend auf der Abweichung, die es bestimmt, ob die <xref:System.DateTimeOffset> -Wert eine UTC-Zeit, eine Ortszeit oder eine andere Zeit, und definiert des zurückgegebenen Datums- und Uhrzeitwerts <xref:System.DateTime.Kind%2A> Eigenschaft entsprechend.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#8)]

Das folgende Beispiel ruft die `ConvertFromDateTimeOffset` Methode zum Konvertieren <xref:System.DateTimeOffset> Werte, die eine UTC-Zeit, eine lokale Zeit und eine Uhrzeit in den USA darstellen. Central Standard Time-Zeitzone (USA) darstellen.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#9)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#9)]

Beachten Sie, dass bei diesem Code von zwei Annahmen ausgegangen wird, die je nach der Anwendung und der Quelle ihrer Datums- und Uhrzeitwerte, nicht immer zutreffen:

* Es wird davon ausgegangen, dass Datum und Uhrzeit-Wert, dessen Abweichung ist <xref:System.TimeSpan.Zero?displayProperty=nameWithType> UTC darstellt. Tatsächlich ist die UTC keine Zeit in einer bestimmten Zeitzone, sondern die Uhrzeit, nach der alle Uhrzeiten in den Zeitzone der Welt standardisiert sind. Zeitzonen können auch einen Offset von haben <xref:System.TimeSpan.Zero>.

* Es wird angenommen, dass ein Datums- und Uhrzeitwert, dessen Abweichung der Abweichung der lokalen Zeitzone entspricht, die lokale Zeitzone darstellt. Dies ist möglicherweise nicht der Fall, weil Datums- und Uhrzeitwerte nicht mehr ihrer ursprünglichen Zeitzone verknüpft sind. Datum und Uhrzeit können aus einer anderen Zeitzone mit der gleichen Abweichung stammen.

## <a name="see-also"></a>Siehe auch

* [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
