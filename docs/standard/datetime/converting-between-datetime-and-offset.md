---
title: Konvertieren zwischen DateTime und DateTimeOffset
ms.custom: 
ms.date: 04/10/2017
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
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 35923fb89d6ca2edb3453db61386f0cd23047278
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="converting-between-datetime-and-datetimeoffset"></a>Konvertieren zwischen DateTime und DateTimeOffset

Obwohl die <xref:System.DateTimeOffset> Struktur bietet eine genauere speichersteuerung Zeitzonen als die <xref:System.DateTime> Struktur <xref:System.DateTime> Parameter werden häufig in Methodenaufrufen verwendet. Daher die Möglichkeit zum Konvertieren <xref:System.DateTimeOffset> Werte <xref:System.DateTime> Werte und umgekehrt ist besonders wichtig. In diesem Thema wird gezeigt, wie für diese auf eine Weise Konvertierungen, die so viele Informationen zur Zeitzone wie möglich beibehalten wird.

> [!NOTE]
> Sowohl die <xref:System.DateTime> und <xref:System.DateTimeOffset> Typen weisen einige Einschränkungen beim Zeiten in Zeitzonen darstellen. Mit der <xref:System.DateTime.Kind%2A> Eigenschaft <xref:System.DateTime> kann nur Coordinated Universal Time (UTC) und das System lokalen Zeitzone entsprechen. <xref:System.DateTimeOffset>Gibt den offset von UTC einer Zeit, aber nicht reflektiert, dass die eigentliche Zeitzone, zu der dieser Offset, gehört. Ausführliche Informationen zu Time-Werten und Unterstützung von Zeitzonen finden Sie unter [Choosing Between DateTime, DateTimeOffset TimeSpan und "TimeZoneInfo"](../../../docs/standard/datetime/choosing-between-datetime.md).

## <a name="conversions-from-datetime-to-datetimeoffset"></a>Konvertierungen von DateTime in DateTimeOffset

Die <xref:System.DateTimeOffset> Struktur bietet zwei Möglichkeiten für die entsprechende auszuführenden <xref:System.DateTime> auf <xref:System.DateTimeOffset> Konvertierung, die für die meisten Konvertierungen geeignet sind:

* Die <xref:System.DateTimeOffset.%23ctor%2A> Konstruktor, der eine neue erstellt <xref:System.DateTimeOffset> -Objekt auf Grundlage einer <xref:System.DateTime> Wert.

* Der implizite Konvertierungsoperator, dadurch können Sie zum Zuweisen einer <xref:System.DateTime> -Wert an eine <xref:System.DateTimeOffset> Objekt.

Für UTC und lokale <xref:System.DateTime> Werte, die <xref:System.DateTimeOffset.Offset%2A> -Eigenschaft des resultierenden <xref:System.DateTimeOffset> Wert genau widerspiegelt Zeitzonenoffset der UTC-Zeit oder Ortszeit. Der folgende Code konvertiert z. B. eine UTC-Zeit in die entsprechende <xref:System.DateTimeOffset> Wert.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#1)]

In diesem Fall beträgt die Abweichung der `utcTime2`-Variablen 00:00. Analog konvertiert der folgende Code eine Ortszeit in die entsprechende <xref:System.DateTimeOffset> Wert.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#2)]

Beachten Sie jedoch bei <xref:System.DateTime> Werte, deren <xref:System.DateTime.Kind%2A> Eigenschaft ist <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, diese beiden Konvertierungsmethoden erzeugen eine <xref:System.DateTimeOffset> -Wert, dessen Offset der lokalen Zeitzone. Dies wird im folgenden Beispiel gezeigt, das in der Zeitzone „Pacific Standard Time“ (USA) ausgeführt wird.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#3)]

Wenn die <xref:System.DateTime> Wert wiedergibt, Datum und Uhrzeit in ein Element als der Ortszeit oder UTC, konvertieren Sie sie in einem <xref:System.DateTimeOffset> Wert und die Zeitzoneninformationen beibehalten, durch Aufrufen der überladenen <xref:System.DateTimeOffset.%23ctor%2A> Konstruktor. Z. B. das folgende Beispiel instanziiert einen <xref:System.DateTimeOffset> -Objekt, das Central Normalzeit wiedergibt.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#4)]

Der zweite Parameter für diese Konstruktorüberladung eine <xref:System.TimeSpan> -Objekt, das die Zeit Offset von UTC darstellt, abgerufen werden sollen, durch Aufrufen der <xref:System.TimeZoneInfo.GetUtcOffset%28System.DateTime%29?displayProperty=nameWithType> -Methode der entsprechenden Zeitzone. Ist der einzige Parameter der Methode der <xref:System.DateTime> Wert, der die zu konvertierende Datums- und Zeitangabe darstellt. Wenn die Zeitzone die Sommerzeit unterstützt, ermöglicht dieser Parameter der Methode, die richtige Abweichung für dieses spezielle Datum und diese spezielle Uhrzeit zu bestimmen.

## <a name="conversions-from-datetimeoffset-to-datetime"></a>Konvertierungen von DateTimeOffset in DateTime

Die <xref:System.DateTimeOffset.DateTime%2A> Eigenschaft wird am häufigsten auszuführenden <xref:System.DateTimeOffset> auf <xref:System.DateTime> Konvertierung. Allerdings gibt es eine <xref:System.DateTime> , dessen Wert <xref:System.DateTime.Kind%2A> Eigenschaft <xref:System.DateTimeKind.Unspecified>, wie das folgende Beispiel veranschaulicht.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#5)]

Dies bedeutet, dass alle Informationen über die <xref:System.DateTimeOffset> Zeitwerts Beziehung in UTC-Zeit ist von der Konvertierung verloren gegangen bei der <xref:System.DateTimeOffset.DateTime%2A> Eigenschaft wird verwendet. Dies wirkt sich auf <xref:System.DateTimeOffset> Werte, die in UTC-Zeit oder Ortszeit für das System, da entsprechen den <xref:System.DateTimeOffset.DateTime%2A> Struktur widerspiegelt, nur die zwei Zeitzonen in seiner <xref:System.DateTime.Kind%2A> Eigenschaft.

So viele Informationen zur Zeitzone wie möglich beibehalten, bei der Konvertierung einer <xref:System.DateTimeOffset> auf eine <xref:System.DateTime> Wert können Sie die <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> und <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> Eigenschaften.

### <a name="converting-a-utc-time"></a>Konvertieren eine UTC-Zeit

Gibt an, dass eine konvertierte <xref:System.DateTimeOffset.DateTime%2A> Wert die UTC-Zeit ist, können Sie den Wert der Abrufen der <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> Eigenschaft. Sie unterscheidet sich von der <xref:System.DateTimeOffset.DateTime%2A> Eigenschaft auf zwei Arten:

* Es gibt eine <xref:System.DateTime> , dessen Wert <xref:System.DateTime.Kind%2A> Eigenschaft ist <xref:System.DateTimeKind.Utc>.

* Wenn die <xref:System.DateTimeOffset.Offset%2A> Eigenschaftswert ist nicht gleich <xref:System.TimeSpan.Zero?displayProperty=nameWithType>, die Zeit in UTC konvertiert.

> [!NOTE]
> Wenn Ihre Anwendung, dass konvertierte erfordert <xref:System.DateTime> Werte eindeutig einen einzigen Zeitpunkt Zeitpunkt identifizieren, sollten Sie mit der <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> Eigenschaft zur Behandlung aller <xref:System.DateTimeOffset> auf <xref:System.DateTime> Konvertierungen.

Der folgende code verwendet die <xref:System.DateTimeOffset.UtcDateTime%2A> Eigenschaft konvertiert eine <xref:System.DateTimeOffset> Wert, dessen Offset entspricht <xref:System.TimeSpan.Zero?displayProperty=nameWithType> auf eine <xref:System.DateTime> Wert.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#6)]

Der folgende code verwendet die <xref:System.DateTimeOffset.UtcDateTime%2A> Eigenschaft für eine zeitzonenkonvertierung und eine Konvertierung vom Typ Ausführen einer <xref:System.DateTimeOffset> Wert.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#12)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#12)]

### <a name="converting-a-local-time"></a>Lokale Zeit konvertieren

Gibt an, dass eine <xref:System.DateTimeOffset> Wert die Ortszeit darstellt, können Sie übergeben die <xref:System.DateTime> zurückgegebene Wert den <xref:System.DateTimeOffset.DateTime%2A?displayProperty=nameWithType> Eigenschaft, um die `static` (`Shared` in Visual Basic) <xref:System.DateTime.SpecifyKind%2A> Methode. Die Methode gibt das Datum und die Uhrzeit, die als erster Parameter übergeben, sondern legt die <xref:System.DateTime.Kind%2A> Eigenschaft auf den Wert, der von seinem zweiten Parameter angegeben. Der folgende code verwendet die <xref:System.DateTime.SpecifyKind%2A> Methode beim Konvertieren einer <xref:System.DateTimeOffset> Wert, dessen Offset, die von der lokalen Zeitzone entspricht.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#7)]

Sie können auch die <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> Eigenschaft konvertiert eine <xref:System.DateTimeOffset> Wert mit einer lokalen <xref:System.DateTime> Wert. Die <xref:System.DateTime.Kind%2A> -Eigenschaft des zurückgegebenen <xref:System.DateTime> Wert <xref:System.DateTimeKind.Local>. Der folgende code verwendet die <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> Eigenschaft beim Konvertieren einer <xref:System.DateTimeOffset> Wert, dessen Offset, die von der lokalen Zeitzone entspricht. 

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#10)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#10)]

Beim Abrufen einer <xref:System.DateTime> mithilfe der <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> -Eigenschaft, der Eigenschaft `get` Accessor zuerst konvertiert die <xref:System.DateTimeOffset> Wert in UTC, dann konvertiert es in die Ortszeit durch Aufrufen der <xref:System.DateTimeOffset.ToLocalTime%2A> Methode. Dies bedeutet, dass ein Wert abgerufen werden kann die <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> Eigenschaft, um eine zeitzonenkonvertierung zur gleichen Zeit ausführen, dass Sie eine Konvertierung vom Typ durchführen. Es bedeutet auch, dass die beim Durchführen der Konvertierung die Anpassungsregeln der lokalen Zeitzone angewendet werden. Der folgende Code veranschaulicht die Verwendung der <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> Eigenschaft um einen Typ und eine zeitzonenkonvertierung auszuführen.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#11)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#11)]

### <a name="a-general-purpose-conversion-method"></a>Eine allgemeine Konvertierungsmethode

Das folgende Beispiel definiert eine Methode namens `ConvertFromDateTimeOffset` , konvertiert <xref:System.DateTimeOffset> Werte <xref:System.DateTime> Werte. Basierend auf dem Offset, bestimmt, ob die <xref:System.DateTimeOffset> Wert eine UTC-Zeit, eine Ortszeit oder eine andere Zeit, und das zurückgegebene Datum und die Time-Werten definiert <xref:System.DateTime.Kind%2A> Eigenschaft entsprechend.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#8)]

Im folgenden Beispiel wird die `ConvertFromDateTimeOffset` -Methode zum Konvertieren <xref:System.DateTimeOffset> Werte, die eine UTC-Zeit, eine lokale Zeit und eine Zeit in den USA darstellen. Central Standard Time-Zeitzone (USA) darstellen.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#9)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#9)]

Beachten Sie, dass bei diesem Code von zwei Annahmen ausgegangen wird, die je nach der Anwendung und der Quelle ihrer Datums- und Uhrzeitwerte, nicht immer zutreffen:

* Es wird davon ausgegangen, dass Datum und Uhrzeit-Wert, dessen Offset ist <xref:System.TimeSpan.Zero?displayProperty=nameWithType> (UTC) darstellt. Tatsächlich ist die UTC keine Zeit in einer bestimmten Zeitzone, sondern die Uhrzeit, nach der alle Uhrzeiten in den Zeitzone der Welt standardisiert sind. Zeitzonen können auch einen Offset von <xref:System.TimeSpan.Zero>.

* Es wird angenommen, dass ein Datums- und Uhrzeitwert, dessen Abweichung der Abweichung der lokalen Zeitzone entspricht, die lokale Zeitzone darstellt. Dies ist möglicherweise nicht der Fall, weil Datums- und Uhrzeitwerte nicht mehr ihrer ursprünglichen Zeitzone verknüpft sind. Datum und Uhrzeit können aus einer anderen Zeitzone mit der gleichen Abweichung stammen.

## <a name="see-also"></a>Siehe auch

[Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
