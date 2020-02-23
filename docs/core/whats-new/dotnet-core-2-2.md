---
title: Neuerungen in .NET Core 2.2
description: Informationen zu den neuen Features in .NET Core 2.2.
dev_langs:
- csharp
- vb
ms.date: 12/04/2018
ms.openlocfilehash: 9495288658fa102df8f0fbd643e2fcdf49d8f3b3
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451979"
---
# <a name="whats-new-in-net-core-22"></a>Neuerungen in .NET Core 2.2

.NET Core 2.2 enthält Verbesserungen für die Anwendungsbereitstellung, für die Ereignisbehandlung für Runtimedienste, für die Authentifizierung bei Azure SQL-Datenbanken, für die JIT-Compilerleistung und bei der Codeeinführung vor dem Einfügen der `Main`-Methode.

## <a name="new-deployment-mode"></a>Neuer Bereitstellungsmodus

Ab .NET Core 2.2 können Sie [frameworkabhängige ausführbare Dateien](../deploying/index.md#publish-runtime-dependent) bereitstellen, die **.exe**-Dateien anstelle von **.dll**-Dateien sind. Frameworkabhängige ausführbare Dateien (FDE) funktionieren ähnlich wie frameworkabhängige Bereitstellungen, benötigen aber zur Ausführung eine freigegebene Version von .NET Core für das gesamte System. Ihre Anwendung enthält nur Code und alle Drittanbieterabhängigkeiten. Im Gegensatz zu frameworkabhängigen Bereitstellungen sind FDEs plattformspezifisch.

Dieser neue Bereitstellungsmodus hat den entscheidenden Vorteil, dass Sie eine ausführbare Datei anstelle einer Bibliothek erstellen, was bedeutet, dass Sie Ihre Anwendung direkt ausführen können, ohne vorher `dotnet` aufzurufen.

## <a name="core"></a>Kernspeicher

**Behandeln von Ereignissen in Runtimediensten**

Möglicherweise möchten Sie die Nutzung von Runtimediensten wie GC, JIT und ThreadPool durch Ihre Anwendung überwachen, um zu verstehen, wie sich diese auf Ihre Anwendung auswirken. Auf Windows-Systemen geschieht dies in der Regel durch die Überwachung der ETW-Ereignisse des aktuellen Prozesses. Obwohl dies weiterhin gut funktioniert, ist es nicht immer möglich, ETW zu verwenden, wenn Sie in einer Umgebung mit niedriger Priorität oder unter Linux oder macOS arbeiten. 

Ab .NET Core 2.2 können CoreCLR-Ereignisse nun über die <xref:System.Diagnostics.Tracing.EventListener?displayProperty=nameWithType>-Klasse genutzt werden. Diese Ereignisse beschreiben das Verhalten der Runtimedienste wie GC, JIT-Kompilierung, ThreadPool und Interop. Dies sind die gleichen Ereignisse wie bei Teilen des CoreCLR ETW-Anbieters.  Dies ermöglicht es Anwendungen, diese Ereignisse zu verarbeiten oder einen Transportmechanismus zu nutzen, um sie an einen Telemetrieaggregationsdienst zu senden. Im folgenden Codebeispiel wird erläutert, wie Sie Ereignisse abonnieren:

```csharp
internal sealed class SimpleEventListener : EventListener
{
    // Called whenever an EventSource is created.
    protected override void OnEventSourceCreated(EventSource eventSource)
    {
        // Watch for the .NET runtime EventSource and enable all of its events.
        if (eventSource.Name.Equals("Microsoft-Windows-DotNETRuntime"))
        {
            EnableEvents(eventSource, EventLevel.Verbose, (EventKeywords)(-1));
        }
    }

    // Called whenever an event is written.
    protected override void OnEventWritten(EventWrittenEventArgs eventData)
    {
        // Write the contents of the event to the console.
        Console.WriteLine($"ThreadID = {eventData.OSThreadId} ID = {eventData.EventId} Name = {eventData.EventName}");
        for (int i = 0; i < eventData.Payload.Count; i++)
        {
            string payloadString = eventData.Payload[i]?.ToString() ?? string.Empty;
            Console.WriteLine($"\tName = \"{eventData.PayloadNames[i]}\" Value = \"{payloadString}\"");
        }
        Console.WriteLine("\n");
    }
}
```

.NET Core 2.2 fügt der <xref:System.Diagnostics.Tracing.EventWrittenEventArgs>-Klasse die folgenden beiden Eigenschaften hinzu, um zusätzliche Informationen über ETW-Ereignisse bereitzustellen:

- <xref:System.Diagnostics.Tracing.EventWrittenEventArgs.OSThreadId?displayProperty=nameWithType>

- <xref:System.Diagnostics.Tracing.EventWrittenEventArgs.TimeStamp?displayProperty=nameWithType>

## <a name="data"></a>Daten

**AAD-Authentifizierung bei Azure SQL-Datenbanken mit der SqlConnection.AccessToken-Eigenschaft**

Ab .NET Core 2.2 kann ein von Azure Active Directory ausgegebenes Zugriffstoken zur Authentifizierung bei einer Azure SQL-Datenbank verwendet werden. Zur Unterstützung von Zugriffstoken wurde die Eigenschaft <xref:System.Data.SqlClient.SqlConnection.AccessToken> zur <xref:System.Data.SqlClient.SqlConnection>-Klasse hinzugefügt. Um die Vorteile der AAD-Authentifizierung zu nutzen, laden Sie die Version 4.6 des NuGet-Pakets „System.Data.SqlClient“ herunter. Um dieses Feature zu nutzen, können Sie den Wert des Zugriffstokens über die [Active Directory-Authentifizierungsbibliothek für .NET](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet) beziehen, die im NuGet-Paket [`Microsoft.IdentityModel.Clients.ActiveDirectory`](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/) enthalten ist.

## <a name="jit-compiler-improvements"></a>Verbesserungen am JIT-Compiler

**Mehrstufige Kompilierung bleibt ein abonnierbares Feature**

Der JIT-Compiler implementierte in .NET Core 2.1 eine neue Compilertechnologie, *mehrstufige Kompilierung*, als abonnierbares Feature. Damit soll eine Leistungssteigerung erzielt werden. Eine der wichtigen Aufgaben, die vom JIT-Compiler ausgeführt werden, ist die Optimierung der Ausführung des Codes. Für wenig genutzte Codepfade muss der Compiler jedoch möglicherweise mehr Zeit zur Optimierung des Codes aufbringen, als die Runtime zur Ausführung nicht optimierten Codes benötigt. Die mehrstufige Kompilierung unterteilt die JIT-Kompilierung in zwei Phasen:

- Eine **erste Stufe**, die so schnell wie möglich Code generiert.

- Eine **zweite Stufe**, die optimiertem Code für Methoden generiert, die häufig ausgeführt werden. Die zweite Stufe der Kompilierung wird parallel zum Verbessern der Leistung ausgeführt.

Informationen zur Leistungssteigerung, die sich aus der mehrstufigen Kompilierung ergeben kann, finden Sie unter [Ankündigung zu .NET Core 2.2 Vorschauversion 2](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-2-preview-2/).

In .NET Core 2.2 Vorschauversion 2 wurde die mehrstufige Kompilierung standardmäßig aktiviert. Allerdings haben wir entschieden, dass wir noch nicht bereit sind, die mehrstufige Kompilierung standardmäßig zu aktivieren. Daher bleibt die mehrstufigen Kompilierung in .NET Core 2.2 weiterhin ein abonnierbares Feature. Informationen zum Abonnieren der mehrstufigen Kompilierung finden Sie unter [Verbesserungen am Jit-Compiler](dotnet-core-2-1.md#jit-compiler-improvements) in [Neuerungen in .NET Core 2.1](dotnet-core-2-1.md).

## <a name="runtime"></a>Laufzeit

**Einfügen von Code vor der Ausführung der Main-Methode**

Ab .NET Core 2.2 können Sie einen Startuphook verwenden, um Code vor der Ausführung der Main-Methode einer Anwendung einzufügen. Startuphooks ermöglichen es einem Host, das Verhalten von Anwendungen nach dem Bereitstellung anzupassen, ohne die Anwendung neu kompilieren oder ändern zu müssen.

Wir erwarten von Hostinganbietern, dass sie benutzerdefinierte Konfigurationen und Richtlinien definieren, einschließlich Einstellungen, die das Ladeverhalten des Haupteinstiegspunktes potenziell beeinflussen, wie beispielsweise das Verhalten  <xref:System.Runtime.Loader.AssemblyLoadContext?displayProperty=nameWithType> . Der Hook kann verwendet werden, um die Ablaufverfolgung oder Telemetrieinjektion einzurichten, Rückrufe zur Handhabung einzurichten oder um ein anderes umgebungsabhängiges Verhalten zu definieren. Der Hook ist vom Einstiegspunkt getrennt, sodass der Benutzercode nicht geändert werden muss.

Weitere Informationen finden Sie unter [Hoststartuphook](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/host-startup-hook.md).

## <a name="see-also"></a>Siehe auch

- [Neuigkeiten in .NET Core](index.md)
- [Neuerungen in ASP.NET Core 2.2](/aspnet/core/release-notes/aspnetcore-2.2)
- [Neue Features in EF Core 2.2](/ef/core/what-is-new/ef-core-2.2)
