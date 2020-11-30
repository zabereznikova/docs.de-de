---
title: Interoperabilität mit anderen asynchronen Mustern und Typen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- asynchronous design patterns, .NET
- TAP, .NET support for
- Task-based Asynchronous Pattern, .NET support for
- .NET, asynchronous design patterns
ms.assetid: f120a5d9-933b-4d1d-acb6-f034a57c3749
ms.openlocfilehash: 2ae1c514185152dd709fe06018df513fb54b874b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726716"
---
# <a name="interop-with-other-asynchronous-patterns-and-types"></a>Interoperabilität mit anderen asynchronen Mustern und Typen

Eine kurze Geschichte der asynchronen Muster in .NET:

- Mit .NET Framework 1.0 wurde das Muster <xref:System.IAsyncResult> eingeführt, das auch [asynchrones Programmiermodell (APM)](asynchronous-programming-model-apm.md) oder `Begin/End`-Muster genannt wird.
- Mit .NET Framework 2.0 wurde das [ereignisbasierte asynchrone Muster (Event-based Asynchronous Pattern, EAP)](event-based-asynchronous-pattern-eap.md) hinzugefügt.
- Mit .NET Framework 4 wurde das [taskbasierte asynchrone Muster (Task-based Asynchronous Pattern, TAP)](task-based-asynchronous-pattern-tap.md) eingeführt, das sowohl das APM als auch das EAP ablöst und die Möglichkeit bietet, leicht Migrationsroutinen aus früheren Mustern zu erstellen.
  
## <a name="tasks-and-the-asynchronous-programming-model-apm"></a>Aufgaben und das asynchrone Programmiermodell (Asynchronous Programming Model, APM)

### <a name="from-apm-to-tap"></a>von APM zu TAP  

 Da das Muster [Asynchrones Programmiermodell](asynchronous-programming-model-apm.md) strukturiert ist, lässt sich ganz einfach ein Wrapper für eine APM-Implementierung erstellen, um sie als TAP-Implementierung verfügbar zu machen. .NET Framework 4 und höher enthält für diese Umwandlung Hilfsroutinen in Form von <xref:System.Threading.Tasks.TaskFactory.FromAsync%2A>-Methodenüberladungen.  
  
 Betrachten Sie die <xref:System.IO.Stream> -Klasse und ihre Methoden <xref:System.IO.Stream.BeginRead%2A> / <xref:System.IO.Stream.EndRead%2A> , die die APM-Entsprechung zur synchronen <xref:System.IO.Stream.Read%2A> -Methode darstellen:  
  
 [!code-csharp[Conceptual.AsyncInterop#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Stream1.cs#1)]
 [!code-vb[Conceptual.AsyncInterop#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/stream1.vb#1)]  
[!code-csharp[Conceptual.AsyncInterop#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Stream1.cs#2)]
[!code-vb[Conceptual.AsyncInterop#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/stream1.vb#2)]  
[!code-csharp[Conceptual.AsyncInterop#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Stream1.cs#3)]
[!code-vb[Conceptual.AsyncInterop#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/stream1.vb#3)]  
  
 Sie können die <xref:System.Threading.Tasks.TaskFactory%601.FromAsync%2A?displayProperty=nameWithType> -Methode verwenden, um wie folgt einen TAP-Wrapper für diese Operation zu implementieren:  
  
 [!code-csharp[Conceptual.AsyncInterop#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wrap1.cs#4)]
 [!code-vb[Conceptual.AsyncInterop#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wrap1.vb#4)]  
  
 Diese Implementierung entspricht dem Folgenden:  
  
 [!code-csharp[Conceptual.AsyncInterop#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wrap2.cs#5)]
 [!code-vb[Conceptual.AsyncInterop#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wrap2.vb#5)]  
  
### <a name="from-tap-to-apm"></a>von TAP zu APM  

 Wenn die vorhandene Infrastruktur das APM-Muster erwartet, sollten Sie auch eine TAP-Implementierung erstellen und diese verwenden, wo eine APM-Implementierung erwartet wird.  Da Aufgaben kombiniert werden können und die <xref:System.Threading.Tasks.Task> -Klasse <xref:System.IAsyncResult>implementiert, können Sie hierfür eine einfache Hilfsfunktion verwenden. Der folgende Code verwendet eine Erweiterung der <xref:System.Threading.Tasks.Task%601> -Klasse, aber Sie können eine fast identische Funktion für nicht generische Aufgaben verwenden.  
  
 [!code-csharp[Conceptual.AsyncInterop#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM1.cs#6)]
 [!code-vb[Conceptual.AsyncInterop#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM1.vb#6)]  
  
 Betrachten Sie nun einen Fall, bei dem Sie die folgende TAP-Implementierung haben:  
  
 [!code-csharp[Conceptual.AsyncInterop#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#7)]
 [!code-vb[Conceptual.AsyncInterop#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#7)]  
  
 und Sie möchten diese APM-Implementierung bereitstellen:  
  
 [!code-csharp[Conceptual.AsyncInterop#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#8)]
 [!code-vb[Conceptual.AsyncInterop#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#8)]  
[!code-csharp[Conceptual.AsyncInterop#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#9)]
[!code-vb[Conceptual.AsyncInterop#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#9)]  
  
 Im folgenden Beispiel wird eine Migration zu APM veranschaulicht:  
  
 [!code-csharp[Conceptual.AsyncInterop#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#10)]
 [!code-vb[Conceptual.AsyncInterop#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#10)]  
  
## <a name="tasks-and-the-event-based-asynchronous-pattern-eap"></a>Aufgaben und das ereignisbasierte asynchrone Muster (Event-based Asynchronous Pattern, EAP)  

 Das Umschließen einer [Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md) -Implementierung ist komplizierter als das Umschließen eines APM-Musters, da das EAP-Muster selbst mehr Varianten als das APM-Muster aufweist und geringer strukturiert ist.  Zur Veranschaulichung umschließt der folgende Code die `DownloadStringAsync` -Methode.  `DownloadStringAsync` akzeptiert einen URI, löst während des Herunterladens das `DownloadProgressChanged` -Ereignis aus, um mehrere Fortschrittswerte zu berichten, und löst zum Abschluss das `DownloadStringCompleted` -Ereignis aus.  Das Endergebnis ist eine Zeichenfolge, die den Inhalt der Seite am angegebenen URI enthält.  
  
 [!code-csharp[Conceptual.AsyncInterop#11](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/EAP1.cs#11)]
 [!code-vb[Conceptual.AsyncInterop#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/EAP1.vb#11)]  
  
## <a name="tasks-and-wait-handles"></a>Aufgaben und Wait-Handles  
  
### <a name="from-wait-handles-to-tap"></a>von den Wait-Handles zu TAP  

 Obwohl Wait-Handles kein asynchrones Muster implementieren, können erfahrene Entwickler die <xref:System.Threading.WaitHandle> -Klasse und die <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> -Methode für asynchrone Benachrichtigungen verwenden, wenn ein Wait-Handle festgelegt ist.  Sie können die <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A> -Methode umschließen, um eine aufgabenbasierte Alternative zu jedem synchronen Wartevorgang in einem Wait-Handle zu ermöglichen:  
  
 [!code-csharp[Conceptual.AsyncInterop#12](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wait1.cs#12)]
 [!code-vb[Conceptual.AsyncInterop#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wait1.vb#12)]  
  
 Mit dieser Methode können Sie vorhandene <xref:System.Threading.WaitHandle> -Implementierungen in asynchronen Methoden verwenden.  Wenn Sie beispielsweise die Anzahl von asynchronen Operationen beschränken möchten, die zu einem bestimmten Zeitpunkt ausgeführt werden, können Sie ein Semaphor ( <xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType> -Objekt) verwenden.  Indem Sie den Zähler des Semaphors mit *N* initialisieren, vor jeder Ausführung eines Vorgangs auf das Semaphor warten und das Semaphor freigeben, wenn ein Vorgang abgeschlossen ist, können Sie die Anzahl von gleichzeitig ausgeführten Vorgängen auf *N* drosseln:  
  
 [!code-csharp[Conceptual.AsyncInterop#13](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Semaphore1.cs#13)]
 [!code-vb[Conceptual.AsyncInterop#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Semaphore1.vb#13)]  
  
 Sie können auch ein asynchrones Semaphor erstellen, das nicht auf Wait-Handles beruht und stattdessen vollständig mit Aufgaben funktioniert. Um dies zu erreichen, können Sie Techniken wie die diejenige verwenden, die unter [Verwenden des aufgabenbasierten asynchronen Musters](consuming-the-task-based-asynchronous-pattern.md) zum Erstellen von Datenstrukturen auf <xref:System.Threading.Tasks.Task>hinzugefügt wurde.  
  
### <a name="from-tap-to-wait-handles"></a>von TAP zu Wait-Handles  

 Wie bereits erwähnt, implementiert die <xref:System.Threading.Tasks.Task> -Klasse <xref:System.IAsyncResult>, und diese Implementierung macht die <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle%2A> -Eigenschaft verfügbar, die ein Wait-Handle zurückgibt, das festgelegt wird, wenn der <xref:System.Threading.Tasks.Task> abgeschlossen wurde.  Sie können ein <xref:System.Threading.WaitHandle> für <xref:System.Threading.Tasks.Task> abrufen, wie folgt:  
  
 [!code-csharp[Conceptual.AsyncInterop#14](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wait1.cs#14)]
 [!code-vb[Conceptual.AsyncInterop#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wait1.vb#14)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Aufgabenbasiertes asynchrones Muster (TAP, Task-based Asynchronous Pattern)](task-based-asynchronous-pattern-tap.md)
- [Implementieren des aufgabenbasierten asynchronen Entwurfsmusters](implementing-the-task-based-asynchronous-pattern.md)
- [Nutzen des aufgabenbasierten asynchronen Musters](consuming-the-task-based-asynchronous-pattern.md)
