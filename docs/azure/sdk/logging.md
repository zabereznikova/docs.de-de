---
title: Protokollierung mit dem Azure SDK für .NET
description: Erfahren Sie, wie Sie die Protokollierung mit dem Azure SDK für .NET-Clientbibliotheken aktivieren
ms.date: 03/20/2020
ms.custom: azure-sdk-dotnet
ms.author: casoper
author: camsoper
ms.openlocfilehash: b277045a60ef5cc065d77dad84878872dedc963e
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "81433223"
---
# <a name="logging-with-the-azure-sdk-for-net"></a>Protokollierung mit dem Azure SDK für .NET

Das [Azure SDK](https://azure.microsoft.com/downloads/) für .NET-Clientbibliotheken bietet die Möglichkeit, Clientbibliotheksvorgänge zu protokollieren. Auf diese Weise können Sie E/A-Anforderungen und Antworten überwachen, die Clientbibliotheken an Azure-Dienste erstellen. In der Regel werden die Protokolle zum Debuggen oder Diagnostizieren von Kommunikationsproblemen verwendet. In diesem Artikel werden drei Ansätze beschrieben, um die Protokollierung mit dem Azure SDK für .NET zu aktivieren:

- Protokollieren am Konsolenfenster
- Protokollieren bei .NET-Diagnoseablaufverfolgungen
- Konfigurieren der benutzerdefinierten Protokollierung

> [!IMPORTANT]
> Dieser Artikel gilt für Clientbibliotheken, die die neuesten Versionen des Azure SDK für .NET verwenden. Informationen dazu, ob eine Bibliothek unterstützt wird, finden Sie in der Liste der [neuesten Azure SDK-Versionen](https://azure.github.io/azure-sdk/releases/latest/index.html). Wenn Ihre Anwendung eine ältere Version der Azure SDK-Clientbibliotheken verwendet, lesen Sie bestimmte Anweisungen in der entsprechenden Dienstdokumentation.

## <a name="log-information"></a>Protokollieren von Informationen

Das SDK protokolliert die folgenden Informationen, sanitisierende Parameterabfrage und Headerwerte, um persönliche Daten zu entfernen.

HTTP-Anforderungsprotokolleintrag:

- Eindeutige Kennung
- HTTP-Methode
- URI
- Ausgehende Anforderungsheader

HTTP-Antwortprotokolleintrag:

- Dauer des E/A-Vorgangs (verstrichene Zeit)
- Anfrage-ID
- HTTP-Statuscode
- HTTP-Ursachenphrase
- Antwortheader
- Fehlerinformationen, falls zutreffend

Für Anforderungs- und Antwortinhalte:

- Content Stream als Text oder Bytes, abhängig vom Content-Type-Header.
     > [! HINWEIS: Die Inhaltsprotokollierung ist standardmäßig deaktiviert. Um sie zu `Diagnostics.IsLoggingContentEnabled` `true` aktivieren, setzen Sie auf in `ClientOptions`.

Ereignisprotokolle werden in der Regel auf einer der folgenden drei Ebenen ausgegeben:

- Information für Anforderungs- und Antwortereignisse
- Warnung vor Fehlern
- Ausführlich für detaillierte Nachrichten und Inhaltsprotokollierung

## <a name="enable-logging-with-built-in-methods"></a>Aktivieren der Protokollierung mit integrierten Methoden

Das Azure SDK für .NET-Clientbibliotheken protokolliert Ereignisse in Event [ `EventSource` ](/dotnet/api/system.diagnostics.tracing.eventsource)Tracing for Windows (ETW) über die Klasse , die typisch für .NET ist. Ereignisquellen ermöglichen die Verwendung strukturierter Protokollierung in Ihrem Anwendungscode mit minimalem Leistungsaufwand. Um Zugriff auf diese Ereignisprotokolle zu erhalten, müssen Sie Ereignislistener registrieren.

Das SDK `Azure.Core.Diagnostics.AzureEventSourceListener` enthält die Klasse (definiert im Azure.Core NuGet-Paket), die zwei statische `CreateConsoleLogger` Methoden `CreateTraceLogger`enthält, die die umfassende Protokollierung für Ihre .NET-Anwendung vereinfachen: und . Diese Methoden verwenden einen optionalen Parameter, der eine Protokollebene angibt.

### <a name="log-to-the-console-window"></a>Protokollieren am Konsolenfenster

Ein Kerngrundsatz des Azure SDK für .NET-Clientbibliotheken besteht darin, die Möglichkeit zu vereinfachen, umfassende Protokolle in Echtzeit anzuzeigen. Mit `CreateConsoleLogger` der Methode können Sie Protokolle mit einer einzigen Codezeile an das Konsolenfenster senden:

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateConsoleLogger();
```

### <a name="log-to-diagnostic-traces"></a>Protokollieren zu Diagnoseablaufverfolgungen

Wenn Sie Ablaufverfolgungslistener `CreateTraceLogger` implementieren, können Sie die Methode verwenden,[`System.Diagnostics.Tracing`](https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing)um sich am standardmäßigen .NET-Ereignisablaufverfolgungsmechanismus ( ) zu protokollieren. Weitere Informationen zur Ereignisablaufverfolgung in .NET finden Sie unter Ablaufzeichnen von [Listenern](https://docs.microsoft.com/dotnet/framework/debug-trace-profile/trace-listeners). In diesem Beispiel wird eine Protokollebene von ausführlich angegeben:

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateTraceLogger(EventLevel.Verbose);
```

## <a name="configure-custom-logging"></a>Konfigurieren der benutzerdefinierten Protokollierung

Wie oben erwähnt, müssen Sie Ereignislistener registrieren, um Protokollnachrichten vom Azure SDK für .NET zu empfangen. Wenn Sie keine umfassende Protokollierung mit einer der oben genannten vereinfachten `AzureEventSourceListener` Methoden implementieren möchten, können Sie eine Instanz der Klasse erstellen und eine Rückruffunktion übergeben, die Sie schreiben. Diese Methode empfängt Protokollnachrichten, die Sie nach Bedarf verarbeiten können. Darüber hinaus können Sie beim Erstellen der Instanz die einzuschließenden Protokollebenen angeben.

Im folgenden Beispiel wird ein Ereignislistener erstellt, der sich mit einer benutzerdefinierten Nachricht an der Konsole anmeldet und zu Azure-Kernereignissen der Ebene exbose gefiltert wird.

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
- Überprüfen der [Azure-Sicherheitsprotokollierungs- und Überwachungsoptionen](https://docs.microsoft.com/azure/security/fundamentals/log-audit)
- Erfahren Sie, wie Sie mit [Azure-Plattformprotokollen](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview) arbeiten
- Weitere Informationen [zu .NET Core-Protokollierung und -Ablaufverfolgung](https://docs.microsoft.com/dotnet/core/diagnostics/logging-tracing)
