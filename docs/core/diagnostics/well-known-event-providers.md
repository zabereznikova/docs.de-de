---
title: Bekannte Ereignisanbieter in .NET
description: Sehen Sie sich die von der .NET-Runtime und den .NET-Bibliotheken veröffentlichten Anbieter und Ereignisse an.
ms.topic: reference
ms.date: 12/21/2020
ms.openlocfilehash: 03d505f33e300b094958676bb768fb542d828aeb
ms.sourcegitcommit: c3093e9d106d8ca87cc86eef1f2ae4ecfb392118
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2020
ms.locfileid: "97738187"
---
# <a name="well-known-event-providers-in-net"></a>Bekannte Ereignisanbieter in .NET

Die .NET-Runtime und .NET-Bibliotheken schreiben Diagnoseereignisse über verschiedene Ereignisanbieter. Sie können die entsprechenden Anbieter zur Aktivierung je nach Diagnoseanforderungen auswählen. In diesem Artikel werden einige der in der .NET-Runtime und in den .NET-Bibliotheken am häufigsten verwendeten Ereignisanbieter beschrieben.

## <a name="coreclr"></a>CoreCLR

### <a name="microsoft-windows-dotnetruntime-provider"></a>"Microsoft-Windows-DotNETRuntime" provider

Dieser Anbieter gibt verschiedene Ereignisse von der .NET-Runtime aus, wie GC-, Ladeprogramm-, JIT-, Ausnahme- und andere Ereignisse. Weitere Informationen zu den einzelnen Ereignissen von diesem Anbieter finden Sie in der [Liste der Runtime-Anbieterereignisse](../../fundamentals/diagnostics/runtime-events.md).

### <a name="microsoft-dotnetcore-sampleprofiler-provider"></a>"Microsoft-DotNETCore-SampleProfiler" provider

Bei diesem Anbieter handelt es sich um einen .NET-Runtime-Ereignisanbieter, der beim CPU-Sampling für verwaltete Aufruflisten verwendet wird. Wenn er aktiviert ist, zeichnet er alle 10 Millisekunden eine Momentaufnahme der verwalteten Aufrufliste der einzelnen Threads auf. Um diese Erfassung zu aktivieren, müssen Sie für <xref:System.Diagnostics.Tracing.EventLevel> mindestens `Informational` angeben.

## <a name="framework-libraries"></a>Frameworkbibliotheken

### <a name="microsoft-extensions-dependencyinjection-provider"></a>Microsoft-Extensions-DependencyInjection (Anbieter)

Dieser Anbieter protokolliert Informationen von DependencyInjection. In der folgenden Tabelle sind die vom Anbieter `Microsoft-Extensions-DependencyInjection` protokollierten Ereignisse aufgeführt:

|Ereignisname|Ebene|BESCHREIBUNG|
|----------|-----|-----------|
|`CallSiteBuilt`|Ausführlich (5)|Es wurde eine Aufrufsite erstellt.|
|`ServiceResolved`|Ausführlich (5)|Es wurde ein Dienst aufgelöst.|
|`ExpressionTreeGenerated`|Ausführlich (5)|Es wurde eine Ausdrucksbaumstruktur generiert.|
|`DynamicMethodBuilt`|Ausführlich (5)|Es wurde eine <xref:System.Reflection.Emit.DynamicMethod> erstellt.|

### <a name="systembuffersarraypooleventsource-provider"></a>"System.Buffers.ArrayPoolEventSource" provider

Dieser Anbieter protokolliert Informationen vom ArrayPool. In der folgenden Tabelle sind die von `ArrayPoolEventSource` protokollierten Ereignisse aufgeführt:

|Ereignisname|Ebene|BESCHREIBUNG|
|----------|-----|-----------|
|`BufferRented`|Ausführlich (5)|Ein Puffer wurde erfolgreich geliehen.|
|`BufferAllocated`|Information (4)|Ein Puffer wird vom Pool zugeordnet.|
|`BufferReturned`|Ausführlich (5)|Ein Puffer wird an den Pool zurückgegeben.|
|`BufferTrimmed`|Information (4)|Weil nicht genügend Arbeitsspeicher verfügbar ist oder aufgrund von Inaktivität wurde versucht, einen Puffer freizugeben.|
|`BufferTrimPoll`|Information (4)|Es wird geprüft, ob Puffer verkleinert werden können.|

### <a name="systemnethttp-provider"></a>System.Net.Http (Anbieter)

Dieser Anbieter protokolliert Informationen vom HTTP-Stapel. In der folgenden Tabelle sind die von Anbieter `System.Net.Http` protokollierten Ereignisse aufgeführt:

|Ereignisname|Ebene|BESCHREIBUNG|
|----------|-----|-----------|
|RequestStart|Information (4)|Es wurde eine HTTP-Anforderung gestartet.|
|RequestStop|Information (4)|Es wurde eine HTTP-Anforderung beendet.|
|RequestFailed|Fehler (2)|Bei einer HTTP-Anforderung ist ein Fehler aufgetreten.|
|ConnectionEstablished|Information (4)|Es wurde eine HTTP-Verbindung hergestellt.|
|ConnectionClosed|Information (4)|Es wurde eine HTTP-Verbindung getrennt.|
|RequestLeftQueue|Information (4)|Eine HTTP-Anforderung hat die Anforderungswarteschlange verlassen.|
|RequestHeadersStart|Information (4)|Es wurde eine HTTP-Anforderung für den Header gestartet.|
|RequestHeaderStop|Information (4)|Es wurde eine HTTP-Anforderung für den Header beendet.|
|RequestContentStart|Information (4)|Es wurde eine HTTP-Anforderung für den Inhalt gestartet.|
|RequestContentStop|Information (4)|Es wurde eine HTTP-Anforderung für den Inhalt beendet.|
|ResponseHeadersStart|Information (4)|Es wurde eine HTTP-Antwort für den Header gestartet.|
|ResponseHeaderStop|Information (4)|Es wurde eine HTTP-Antwort für den Header beendet.|
|ResponseContentStart|Information (4)|Es wurde eine HTTP-Antwort für den Inhalt gestartet.|
|ResponseContentStop|Information (4)|Es wurde eine HTTP-Antwort für den Inhalt beendet.|

### <a name="systemnetnameresolution-provider"></a>System.Net.NameResolution (Anbieter)

Dieser Anbieter protokolliert Informationen im Zusammenhang mit der Auflösung von Domänennamen. In der folgenden Tabelle sind die von `System.Net.NameResolution` protokollierten Ereignisse aufgeführt:

|Ereignisname|Ebene|BESCHREIBUNG|
|----------|-----|-----------|
|`ResolutionStart`|Information (4)|Es wurde eine Auflösung von Domänennamen gestartet.|
|`ResolutionStop`|Information (4)|Es wurde eine Auflösung von Domänennamen beendet.|
|`ResolutionFailed`|Information (4)|Bei der Auflösung von Domänennamen ist ein Fehler aufgetreten.|

### <a name="systemnetsockets-provider"></a>System.Net.Sockets (Anbieter)

Dieser Anbieter protokolliert Informationen von <xref:System.Net.Sockets.Socket>. In der folgenden Tabelle sind die von Anbieter `System.Net.Sockets` protokollierten Ereignisse aufgeführt:

|Ereignisname|Ebene|BESCHREIBUNG|
|----------|-----|-----------|
|`ConnectStart`|Information (4)|Der Versuch, eine Socketverbindung zu starten, wurde gestartet.|
|`ConnectStop`|Information (4)|Der Versuch, eine Socketverbindung zu starten, wurde beendet.|
|`ConnectFailed`|Information (4)|Beim Versuch, eine Socketverbindung zu starten, ist ein Fehler aufgetreten.|
|`AcceptStart`|Information (4)|Der Versuch, eine Socketverbindung anzunehmen, wurde gestartet.|
|`AcceptStop`|Information (4)|Der Versuch, eine Socketverbindung anzunehmen, wurde beendet.|
|`AcceptFailed`|Information (4)|Beim Versuch, eine Socketverbindung anzunehmen, ist ein Fehler aufgetreten.|

### <a name="systemthreadingtaskstpleventsource-provider"></a>"System.Threading.Tasks.TplEventSource" provider

Dieser Anbieter protokolliert Informationen zur [Task Parallel Library](../../standard/parallel-programming/task-parallel-library-tpl.md) wie etwa Taskplanerereignisse. In der folgenden Tabelle sind die von `TplEventSource` protokollierten Ereignisse aufgeführt:

|Ereignisname|Stichwort|Ebene|BESCHREIBUNG|
|----------|-------|-----|-----------|
|`TaskScheduled`|`TaskTransfer`(`0x1`)<br /><br />`Tasks`(`0x2`)|Information (4)|<xref:System.Threading.Tasks.Task> wurde in die Warteschlange des Taskplaners aufgenommen.|
|`TaskStarted`|`Tasks`(`0x2`)|Information (4)|<xref:System.Threading.Tasks.Task> hat die Ausführung gestartet.|
|`TaskCompleted`|`TaskStops`(`0x40`)|Information (4)|<xref:System.Threading.Tasks.Task> hat die Ausführung beendet.|
|`TaskWaitBegin`|`TaskTransfer`(`0x1`)<br /><br />`TaskWait`(`0x2`)|Information (4)|Wird ausgelöst, wenn ein impliziter oder expliziter Wartevorgang für den Abschluss von <xref:System.Threading.Tasks.Task> gestartet wurde.|
|`TaskWaitEnd`|`Tasks`(`0x2`)|Ausführlich (5)|Wird ausgelöst, wenn der Wartevorgang für den Abschluss von <xref:System.Threading.Tasks.Task> zurückgegeben wird.|
|`TaskWaitContinuationStarted`|`Tasks`(`0x2`)|Ausführlich (5)|Wird ausgelöst, wenn die mit `TaskWaitEnd` verknüpfte Aufgabe (Methode) gestartet wird.|
|`TaskWaitContinuationCompleted`|`TaskStops`(`0x40`)|Ausführlich (5)|Wird ausgelöst, wenn die mit `TaskWaitEnd` verknüpfte Aufgabe (Methode) abgeschlossen wird.|
|`AwaitTaskContinuationScheduled`|`TaskTransfer`(`0x1`)<br /><br />`Tasks`(`0x2`)|Information (4)|Wird ausgelöst, wenn die asynchrone Fortsetzung für <xref:System.Threading.Tasks.Task> geplant wird.|

## <a name="aspnet-core"></a>ASP.NET Core

ASP.NET Core stellt darüber hinaus auch verschiedene Ereignisse zur Unterstützung bei der Diagnose von Problemen im ASP.NET Core-Stapel bereit.

Weitere Informationen zu den Ereignissen in ASP.NET Core und zu deren Verwendung finden Sie unter [Protokollieren in .NET Core und ASP.NET Core](/aspnet/core/fundamentals/logging/).
