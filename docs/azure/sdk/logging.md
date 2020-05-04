---
title: Protokollieren mit dem Azure SDK für .NET
description: In diesem Artikel erfahren Sie, wie Sie die Protokollierung mit dem Azure SDK für .NET-Clientbibliotheken einrichten.
ms.date: 03/20/2020
ms.custom: azure-sdk-dotnet
ms.author: casoper
author: camsoper
ms.openlocfilehash: b277045a60ef5cc065d77dad84878872dedc963e
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "81433223"
---
# <a name="logging-with-the-azure-sdk-for-net"></a>Protokollieren mit dem Azure SDK für .NET

Mit dem [Azure SDK-](https://azure.microsoft.com/downloads/) für .NET-Clientbibliotheken können Sie die Vorgänge in Clientbibliotheken protokollieren. Dies ermöglicht es Ihnen, E/A-Anforderungen und -Antworten zu überwachen, die Clientbibliotheken an Azure-Dienste senden. In der Regel werden die Protokolle verwendet, um Kommunikationsprobleme zu debuggen oder zu diagnostizieren. In diesem Artikel werden drei Ansätze beschrieben, mit denen sich die Protokollierung mit dem Azure SDK für .NET konfigurieren lässt:

- Protokollieren im Konsolenfenster
- Protokollieren in .NET- Diagnoseablaufverfolgungen
- Konfigurieren einer benutzerdefinierten Protokollierung

> [!IMPORTANT]
> Dieser Artikel bezieht sich auf die Clientbibliotheken, die die neuesten Versionen des Azure SDK für .NET verwenden. Informationen dazu, ob eine Bibliothek unterstützt wird, finden Sie in der Liste mit den [neuesten Azure SDK-Releases](https://azure.github.io/azure-sdk/releases/latest/index.html). Wenn Ihre Anwendung eine ältere Version der Azure SDK-Clientbibliotheken verwendet, finden Sie entsprechende Anweisungen in der jeweiligen Dienstdokumentation.

## <a name="log-information"></a>Protokollieren von Informationen

Das SDK protokolliert die folgenden Informationen und bereinigt die Abfrage- und Headerwerte der Parameter, um personenbezogene Daten zu entfernen.

Protokolleintrag der HTTP-Anforderung:

- Eindeutige ID
- HTTP-Methode
- URI
- Ausgehende Anforderungsheader

Protokolleintrag der HTTP-Antwort:

- Dauer des E/A-Vorgangs (verstrichene Zeit)
- Anfrage-ID
- HTTP-Statuscode
- HTTP-Ursachentext
- Antwortheader
- Fehlerinformationen, falls verfügbar

Bezüglich des Anforderung- und Antwortinhalts:

- Ob im Inhaltsdatenstrom Text oder Byte übertragen werden, ist abhängig vom Header „Content-Type“.
     > [!HINWEIS] Die Inhaltsprotokollierung ist standardmäßig deaktiviert. Legen Sie `Diagnostics.IsLoggingContentEnabled` in `ClientOptions` auf `true` fest, um diese zu aktivieren.

Ereignisprotokolle werden in der Regel auf einer der folgenden drei Ebenen ausgegeben:

- Informationell, für Anforderungs- und Antwortereignisse
- Warnungen, für Fehler
- Ausführlich, für detaillierte Meldungen und die Inhaltsprotokollierung

## <a name="enable-logging-with-built-in-methods"></a>Aktivieren der Protokollierung mit integrierten Methoden

Das Azure SDK für .NET-Clientbibliotheken protokolliert Ereignisse in der Ereignisablaufverfolgung für Windows über die [Klasse `EventSource`](/dotnet/api/system.diagnostics.tracing.eventsource), die typisch für .NET ist. Mit Ereignisquellen können Sie die strukturierte Protokollierung in Ihrem Anwendungscode mit minimalem Leistungsmehraufwand verwenden. Sie müssen nur die Ereignislistener registrieren, um Zugriff auf diese Ereignisprotokolle zu erhalten.

Das SDK enthält die Klasse `Azure.Core.Diagnostics.AzureEventSourceListener` (definiert im NuGet-Paket „Azure.Core“), die zwei statische Methoden enthält, die die umfassende Protokollierung für Ihre .NET-Anwendung vereinfachen: `CreateConsoleLogger` und `CreateTraceLogger`. Diese Methoden nehmen einen optionalen Parameter, der eine Protokollebene angibt.

### <a name="log-to-the-console-window"></a>Protokollieren im Konsolenfenster

Eine der Hauptfunktionen des Azure SDK für .NET-Clientbibliotheken besteht darin, die Anzeige von umfassenden Protokollen in Echtzeit zu vereinfachen. Mit der Methode `CreateConsoleLogger` können Sie Protokolle mit einer einzelnen Codezeile an das Konsolenfenster senden:

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateConsoleLogger();
```

### <a name="log-to-diagnostic-traces"></a>Protokollieren in Diagnoseablaufverfolgungen

Wenn Sie Ablaufverfolgungslistener implementieren, können Sie mit der Methode `CreateTraceLogger` in der standardmäßigen .NET-Ereignisablaufverfolgung ([`System.Diagnostics.Tracing`](https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing)) protokollieren. Weitere Informationen zur Ereignisablaufverfolgung in .NET finden Sie unter [Ablaufverfolgungslistener](https://docs.microsoft.com/dotnet/framework/debug-trace-profile/trace-listeners). In diesem Beispiel wird die Protokollebene „Ausführlich“ dargestellt:

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateTraceLogger(EventLevel.Verbose);
```

## <a name="configure-custom-logging"></a>Konfigurieren der benutzerdefinierten Protokollierung

Wie bereits erwähnt, müssen Sie Ereignislistener registrieren, um vom Azure SDK für .NET Protokollmeldungen zu empfangen. Wenn Sie die umfassende Protokollierung nicht mithilfe der oben genannten vereinfachten Methoden implementieren möchten, können Sie eine Instanz der Klasse `AzureEventSourceListener` erstellen und ihr eine Rückruffunktion übergeben, die Sie schreiben. Diese Methode empfängt Protokollmeldungen, die Sie nach Bedarf verarbeiten lassen können. Wenn Sie die Instanz erstellen, können Sie außerdem die zu berücksichtigenden Protokollebenen angeben.

Im folgenden Beispiel wird ein Ereignislistener erstellt, der mit einer benutzerdefinierten Meldung in der Konsole protokolliert und nach wichtigen Azure-Ereignissen der Ebene „Ausführlich“ gefiltert wird.

```csharp
using AzureEventSourceListener listener = new AzureEventSourceListener((e, message) =>
    {
        // Only log messages from Azure-Core event source
        if (e.EventSource.Name == "Azure-Core")
        {
            Console.WriteLine($"{DateTime.Now} {message}");
        }
    },
    level: EventLevel.Verbose);
```

## <a name="next-steps"></a>Nächste Schritte

- [Aktivieren der Diagnoseprotokollierung für Apps in Azure App Service](https://docs.microsoft.com/azure/app-service/troubleshoot-diagnostic-logs)
- Sehen Sie sich die Optionen unter [Azure-Sicherheitsprotokollierung und -Überwachung](https://docs.microsoft.com/azure/security/fundamentals/log-audit) an.
- Machen Sie sich mit dem Umgang mit den [Protokollen der Azure-Plattform](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview) vertraut.
- Lesen Sie auch den Artikel [Protokollierung und Ablaufverfolgung mit .NET Core](https://docs.microsoft.com/dotnet/core/diagnostics/logging-tracing).
