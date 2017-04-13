---
title: "Konvertieren zwischen &quot;DateTime&quot; und &quot;DateTimeOffset&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "04/10/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Konvertieren von DateTimeOffset- und DateTime-Werten"
  - "Konvertieren von Zeiten"
  - "Date-Datentyp, Konvertieren"
  - "Datumsangaben [.NET Framework], Konvertieren"
  - "DateTime-Struktur, Konvertieren"
  - "DateTimeOffset-Struktur, Konvertieren"
  - "Konvertierung lokaler Zeiten"
  - "Zeitzonen [.NET Framework], Konvertierungen"
  - "UTC-Zeiten, Konvertieren"
ms.assetid: b605ff97-0c45-4c24-833f-4c6a3e8be64c
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Konvertieren zwischen &quot;DateTime&quot; und &quot;DateTimeOffset&quot;
Die <xref:System.DateTimeOffset>\-Struktur bietet zwar eine umfassendere Unterstützung von Zeitzonen als die <xref:System.DateTime>\-Struktur, <xref:System.DateTime>\-Parameter werden in Methodenaufrufen jedoch häufiger verwendet.  Daher kommt der Möglichkeit, <xref:System.DateTimeOffset>\-Werte in <xref:System.DateTime>\-Werte zu konvertieren und umgekehrt, eine besondere Bedeutung zu.  In diesem Thema wird beschrieben, wie diese Konvertierungen so durchgeführt werden können, dass möglichst viele Zeitzoneninformationen erhalten bleiben.  
  
> [!NOTE]
>  Sowohl der <xref:System.DateTime>\-Typ als auch der <xref:System.DateTimeOffset>\-Typ unterliegen bei der Darstellung von Zeiten in Zeitzonen gewissen Einschränkungen.  Mit seiner <xref:System.DateTime.Kind%2A>\-Eigenschaft kann der <xref:System.DateTime>\-Typ nur die koordinierte Weltzeit \(UTC\) und die lokale Zeitzone des Systems wiedergeben.  <xref:System.DateTimeOffset> hingegen gibt den Offset einer Zeit von der koordinierten Weltzeit wieder, jedoch nicht die eigentliche Zeitzone, zu der dieser Offset gehört.  Ausführliche Informationen zu Zeitwerten und die Unterstützung von Zeitzonen finden Sie unter [Auswählen zwischen "DateTime", "DateTimeOffset", "TimeSpan" und "TimeZoneInfo"](../../../docs/standard/datetime/choosing-between-datetime.md).  
  
## Konvertieren von "DateTime" in "DateTimeOffset"  
 Die <xref:System.DateTimeOffset>\-Struktur bietet zwei gleichwertige Möglichkeiten zum Konvertieren von <xref:System.DateTime>\-Werten in <xref:System.DateTimeOffset>\-Werte, die für die meisten Konvertierungen geeignet sind:  
  
-   Der <xref:System.DateTimeOffset.%23ctor%2A>\-Konstruktor, der ein neues <xref:System.DateTimeOffset>\-Objekt auf Basis eines <xref:System.DateTime>\-Werts erstellt.  
  
-   Der implizite Konvertierungsoperator, der es Ihnen ermöglicht, einem <xref:System.DateTimeOffset>\-Objekt einen <xref:System.DateTime>\-Wert zuzuweisen.  
  
 Für UTC\- und lokale <xref:System.DateTime>\-Werte gibt die <xref:System.DateTimeOffset.Offset%2A>\-Eigenschaft des resultierenden <xref:System.DateTimeOffset>\-Werts den Offset von der koordinierten Weltzeit oder der lokalen Zeitzone genau wieder.  Im folgenden Code wird z. B. eine UTC\-Zeit in den entsprechenden <xref:System.DateTimeOffset>\-Wert konvertiert.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#1)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#1)]  
  
 In diesem Fall beträgt der Offset der `utcTime2`\-Variablen 00:00.  Auf ähnliche Weise wird im folgenden Code eine lokale Zeit in den entsprechenden <xref:System.DateTimeOffset>\-Wert konvertiert.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#2)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#2)]  
  
 Für <xref:System.DateTime>\-Werte, deren <xref:System.DateTime.Kind%2A>\-Eigenschaft <xref:System.DateTimeKind?displayProperty=fullName> lautet, bringen diese beiden Konvertierungsmethoden jedoch einen <xref:System.DateTimeOffset>\-Wert hervor, dessen Offset dem dem lokalen Zeitzone entspricht.  Dies wird im folgenden Beispiel gezeigt, das in der Zeitzone Pacific Normalzeit ausgeführt wird.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#3)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#3)]  
  
 Wenn der <xref:System.DateTime>\-Wert einen Datums\- und Uhrzeitwert wiedergibt, der nicht der lokalen Zeitzone oder der koordinierten Weltzeit entspricht, können Sie ihn in einen <xref:System.DateTimeOffset>\-Wert konvertieren und seine Zeitzoneninformationen beibehalten, indem Sie den überladenen <xref:System.DateTimeOffset.%23ctor%2A>\-Konstruktor aufrufen.  Im folgenden Beispiel wird z. B. ein <xref:System.DateTimeOffset>\-Objekt instanziiert, das die Zeitzone Central Normalzeit wiedergibt.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#4)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#4)]  
  
 Der zweite Parameter für diese Konstruktorüberladung \(ein <xref:System.TimeSpan>\-Objekt, das den Offset von der koordinierten Weltzeit angibt\) sollte durch Aufrufen der <xref:System.TimeZoneInfo.GetUtcOffset%28System.DateTime%29?displayProperty=fullName>\-Methode der entsprechenden Zeitzone abgerufen werden.  Der einzige Parameter dieser Methode ist der <xref:System.DateTime>\-Wert, der den zu konvertierenden Datums\- und Uhrzeitwert darstellt.  Wenn die Zeitzone die Sommerzeit unterstützt, kann die Methode mit diesem Parameter den entsprechenden Offset für den Datums\- und Uhrzeitwert bestimmen.  
  
## Konvertieren von "DateTimeOffset " in "DateTime"  
 Die <xref:System.DateTimeOffset.DateTime%2A>\-Eigenschaft wird für gewöhnlich verwendet, um <xref:System.DateTimeOffset>\-Werte in <xref:System.DateTime>\-Werte zu konvertieren.  Sie gibt jedoch einen <xref:System.DateTime>\-Wert zurück, dessen <xref:System.DateTime.Kind%2A>\-Eigenschaft <xref:System.DateTimeKind> ist, wie im folgenden Beispiel veranschaulicht wird.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#5)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#5)]  
  
 Das bedeutet, dass alle Informationen über die Beziehung des <xref:System.DateTimeOffset>\-Werts mit der koordinierten Weltzeit durch die Konvertierung verloren gehen, wenn die <xref:System.DateTimeOffset.DateTime%2A>\-Eigenschaft verwendet wird.  Dies hat Auswirkungen auf die <xref:System.DateTimeOffset>\-Werte, die der UTC\-Zeit oder der lokalen Systemzeit entsprechen, da die <xref:System.DateTimeOffset.DateTime%2A>\-Struktur in seiner <xref:System.DateTime.Kind%2A>\-Eigenschaft nur zwei Zeitzonen wiedergibt.  
  
 Damit beim Konvertieren eines <xref:System.DateTimeOffset>\-Werts in einen <xref:System.DateTime>\-Wert möglichst viele Zeitzoneninformationen erhalten bleiben, können Sie die <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=fullName>\-Eigenschaft und die <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=fullName>\-Eigenschaft verwenden.  
  
### Konvertieren einer UTC\-Zeit  
 Um anzugeben, dass ein konvertierter <xref:System.DateTimeOffset.DateTime%2A>\-Wert der UTC\-Zeit entspricht, können Sie den Wert der <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=fullName>\-Eigenschaft abrufen.  Diese unterscheidet sich von der <xref:System.DateTimeOffset.DateTime%2A>\-Eigenschaft in zweierlei Hinsicht:  
  
-   Sie gibt einen <xref:System.DateTime>\-Wert zurück, dessen <xref:System.DateTime.Kind%2A>\-Eigenschaft <xref:System.DateTimeKind> ist.  
  
-   Wenn der Wert der <xref:System.DateTimeOffset.Offset%2A>\-Eigenschaft nicht <xref:System.TimeSpan.Zero?displayProperty=fullName> entspricht, konvertiert sie die Zeit in die UTC\-Zeit.  
  
> [!NOTE]
>  Wenn Ihre Anwendung erfordert, dass konvertierte <xref:System.DateTime>\-Werte einen bestimmten Zeitpunkt eindeutig identifizieren, empfiehlt es sich, die <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=fullName>\-Eigenschaft zum Konvertieren sämtlicher <xref:System.DateTimeOffset>\-Werte in <xref:System.DateTime>\-Werte zu verwenden.  
  
 Im folgenden Code wird die <xref:System.DateTimeOffset.UtcDateTime%2A>\-Eigenschaft verwendet, um einen <xref:System.DateTimeOffset>\-Wert, dessen Offset <xref:System.TimeSpan.Zero?displayProperty=fullName> entspricht, in einen <xref:System.DateTime>\-Wert zu konvertieren.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#6)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#6)]  
  
 Im folgenden Code wird die <xref:System.DateTimeOffset.UtcDateTime%2A>\-Eigenschaft verwendet, um für einen <xref:System.DateTimeOffset>\-Wert sowohl eine Zeitzonenkonvertierung als auch eine Typkonvertierung durchzuführen.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#12)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#12)]  
  
### Konvertieren einer lokalen Zeit  
 Um anzugeben, dass ein <xref:System.DateTimeOffset>\-Wert die lokale Zeit darstellt, können Sie den <xref:System.DateTime>\-Wert übergeben, der von der <xref:System.DateTimeOffset.DateTime%2A?displayProperty=fullName>\-Eigenschaft an die `static` \(`Shared` in Visual Basic\) <xref:System.DateTime.SpecifyKind%2A>\-Methode zurückgegeben wird.  Diese Methode gibt den Datums\- und Uhrzeitwert zurück, der ihr als erster Parameter übergeben wurde, aber legt die <xref:System.DateTime.Kind%2A>\-Eigenschaft auf den Wert fest, der durch ihren zweiter Parameter angegeben wurde.  Im folgenden Code wird die <xref:System.DateTime.SpecifyKind%2A>\-Methode verwendet, um einen <xref:System.DateTimeOffset>\-Wert zu konvertieren, dessen Offset dem der lokalen Zeitzone entspricht.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#7)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#7)]  
  
 Sie können auch die <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=fullName>\-Eigenschaft verwenden, um einen <xref:System.DateTimeOffset>\-Wert in einen lokalen <xref:System.DateTime>\-Wert zu konvertieren.  Die <xref:System.DateTime.Kind%2A>\-Eigenschaft des zurückgegebenen <xref:System.DateTime>\-Werts ist <xref:System.DateTimeKind>.  Im folgenden Code wird die <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=fullName>\-Eigenschaft verwendet, um einen <xref:System.DateTimeOffset>\-Wert zu konvertieren, dessen Offset dem der lokalen Zeitzone entspricht.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#10)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#10)]  
  
 Wenn Sie einen <xref:System.DateTime>\-Wert mit der <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=fullName>\-Eigenschaft abrufen, konvertiert der `get`\-Accessor dieser Eigenschaft den <xref:System.DateTimeOffset>\-Wert zunächst in die koordinierte Weltzeit und anschließend in die lokale Zeit, indem die <xref:System.DateTimeOffset.ToLocalTime%2A>\-Methode aufgerufen wird.  Das bedeutet, dass Sie einen Wert von der <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=fullName>\-Eigenschaft abrufen können, um eine Zeitzonenkonvertierung zeitgleich mit einer Typkonvertierung durchzuführen.  Außerdem bedeutet es, dass die Anpassungsregeln der lokalen Zeitzone während der Konvertierung angewendet werden.  Der folgende Code veranschaulicht die Verwendung der <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=fullName>\-Eigenschaft zur Durchführung einer Zeitzonenkonvertierung und einer Typkonvertierung.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#11)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#11)]  
  
### Eine allgemeine Konvertierungsmethode  
 Im folgenden Beispiel wird eine Methode namens `ConvertFromDateTimeOffset` definiert, die <xref:System.DateTimeOffset>\-Werte in <xref:System.DateTime>\-Werte konvertiert.  Auf Basis ihres Offsets bestimmt sie, ob der <xref:System.DateTimeOffset>\-Wert eine koordinierte Weltzeit, eine lokale Zeit oder eine andere Zeit darstellt, und definiert entsprechend die <xref:System.DateTime.Kind%2A>\-Eigenschaft des zurückgegebenen Datums\- und Uhrzeitwerts.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#8)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#8)]  
  
 Im folgenden Beispiel wird die Methode `ConvertFromDateTimeOffset` auf, um <xref:System.DateTimeOffset>\-Werte zu konvertieren, die eine UTC\-Zeit, eine lokale Zeit und eine Zeit in der Zeitzone Central Normalzeit darstellen.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#9)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#9)]  
  
 Beachten Sie, dass in diesem Code von zwei Annahmen ausgegangen wird, die je nach Anwendung und Quelle der Datums\- und Uhrzeitwerte nicht immer gültig sein müssen:  
  
-   Es wird davon ausgegangen, dass ein Datums\- und Uhrzeitwert, dessen Offset <xref:System.TimeSpan.Zero?displayProperty=fullName> ist, die koordinierte Weltzeit darstellt.  Tatsächlich ist die koordinierte Weltzeit aber keine Zeit in einer bestimmten Zeitzone, sondern eine Zeit, in Bezug auf die die Zeiten in den Zeitzonen der Erde standardisiert werden.  Zeitzonen können auch den Offset <xref:System.TimeSpan.Zero> haben.  
  
-   Es wird davon ausgegangen, dass ein Datums\- und Uhrzeitwert, dessen Offset dem der lokalen Zeitzone entspricht, die lokale Zeitzone darstellt.  Da die Zuordnung von Datums\- und Uhrzeitwerten zu ihrer ursprünglichen Zeitzone aufgehoben wird, ist dies möglicherweise jedoch nicht der Fall. Der Datums\- und Uhrzeitwert kann aus einer anderen Zeitzone mit dem gleichen Offset stammen.  
  
## Siehe auch  
 [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)