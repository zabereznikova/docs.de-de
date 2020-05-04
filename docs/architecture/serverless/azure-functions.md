---
title: 'Azure Functions: Serverlose Apps'
description: Azure Functions bietet serverlose Funktionen für mehrere Sprachen (C#, JavaScript, Java) und Plattformen, um ereignisgesteuerten Code für die sofortige Skalierung bereitzustellen.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 04/06/2020
ms.openlocfilehash: 2dee60e3635be94a55ee26a7f04942bc59cb8dec
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135723"
---
# <a name="azure-functions"></a>Überprüfung auf

Azure Functions bietet eine serverlose Computeerfahrung. Eine Funktion wird durch einen *Trigger* aufgerufen (z.B. den Zugriff auf einen HTTP-Endpunkt oder einen Timer) und führt einen Codeblock oder Geschäftslogik aus. Funktionen unterstützen auch spezialisierte *Bindungen*, die eine Verbindung mit Ressourcen wie Speicher und Warteschlangen herstellen.

![Azure Functions-Logo](./media/azure-functions-logo.png)

Die aktuelle Laufzeitversion 3.0 unterstützt plattformübergreifende .NET Core 3.1-Anwendungen. Neben C# werden weitere Sprachen wie JavaScript, F# und Java unterstützt. Funktionen, die im Portal erstellt werden, bieten eine umfangreiche Skriptsyntax. Funktionen, die als eigenständige Projekte erstellt werden, können mit vollständiger Plattformunterstützung bereitgestellt werden.

Weitere Informationen finden Sie in der [Azure Functions-Dokumentation](https://docs.microsoft.com/azure/azure-functions).

## <a name="programming-language-support"></a>Unterstützung für Programmiersprachen

Die folgenden Sprachen werden alle in der allgemeinen Verfügbarkeit (General Availability, GA) unterstützt.

|Sprache      |Unterstützte Runtimes|
|--------------|------------------|
|**C#**        |.NET Core 3.1     |
|**JavaScript**|Node 10 & 12      |
|**F#**        |.NET Core 3.1     |
|**Java**      |Java 8            |
|**Python**    |Python 3.6, 3.7, & 3.8|
|**TypeScript**|Node 10 & 12 (über JavaScript)|
|**PowerShell**|PowerShell Core 6|

Weitere Informationen finden Sie unter [Unterstützte Sprachen](https://docs.microsoft.com/azure/azure-functions/supported-languages).

## <a name="app-service-plans"></a>App Service-Pläne

Funktionen werden durch einen *App Service-Plan* unterstützt. Der Plan definiert die Ressourcen, die von der Funktions-App verwendet werden. Sie können einer Region Pläne zuweisen, die Größe und Anzahl der zu verwendenden virtuellen Computer bestimmen und einen Tarif auswählen. Für einen echten serverlosen Ansatz können Funktions-Apps den **Verbrauchstarif** verwenden. Der Verbrauchstarif skaliert das Back-End automatisch basierend auf der Auslastung.

Eine weitere Hostingoption für Funktions-Apps ist der [Premium-Plan](https://docs.microsoft.com/azure/azure-functions/functions-premium-plan). Dieser Plan bietet eine „Always On“-Instanz zur Vermeidung von Kaltstarts, unterstützt erweiterte Features wie VNet-Konnektivität und wird auf Premiumhardware ausgeführt.

Weitere Informationen finden Sie unter [App Service-Pläne](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).

## <a name="create-your-first-function"></a>Erstellen Ihrer ersten Funktion

Es gibt drei gängige Methoden, um Funktions-Apps zu erstellen.

- Skriptfunktionen im Portal.
- Erstellen der erforderlichen Ressourcen mithilfe der Azure CLI.
- Lokales Erstellen von Funktionen mithilfe Ihrer bevorzugten IDE und Veröffentlichen der Funktionen in Azure.

Weitere Informationen zum Erstellen einer Skriptfunktion im Portal finden Sie unter [Erstellen Ihrer ersten Funktion im Azure-Portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).

Wenn Sie den Buildvorgang mit der Azure CLI ausführen möchten, finden Sie weitere Informationen unter [Erstellen Ihrer ersten Funktion mit der Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).

Informationen zum Erstellen einer Funktion aus Visual Studio finden Sie unter [Erstellen Ihrer ersten Funktion mit Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).

## <a name="understand-triggers-and-bindings"></a>Informationen zu Triggern und Bindungen

Funktionen werden von einem *Trigger* aufgerufen und können über genau einen Trigger verfügen. Zusätzlich zum Aufrufen der Funktion dienen bestimmte Trigger auch als Bindungen. Zusätzlich zum Trigger können Sie auch mehrere Bindungen definieren. *Bindungen* stellen eine deklarative Möglichkeit zum Verbinden von Daten mit Ihrem Code bereit. Sie können übergeben werden (Eingabe) oder Daten empfangen (Ausgabe). Trigger und Bindungen erleichtern das Arbeiten mit Funktionen. Durch Bindungen entfällt der Mehraufwand für das manuelle Erstellen von Datenbank- oder Dateisystemverbindungen. Alle für die Bindungen benötigten Informationen sind in einer speziellen Datei *functions.json* für Skripts enthalten oder werden mit Attributen im Code deklariert.

Einige gängige Trigger sind:

- Blob Storage: Rufen Sie Ihre Funktion auf, wenn eine Datei oder ein Ordner in den Speicher hochgeladen oder dort geändert wird.
- HTTP: Rufen Sie Ihre Funktion wie eine REST-API auf.
- Queue: Rufen Sie die Funktion auf, wenn Elemente in einer Warteschlange vorhanden sind.
- Timer: Rufen Sie Ihre Funktion in einem regulären Intervall auf.

Beispiele für Bindungen sind:

- CosmosDB: Stellen Sie problemlos eine Verbindung mit der Datenbank her, um Dateien zu laden oder zu speichern.
- Table Storage: Arbeiten Sie mit dem Schlüssel-Wert-Speicher aus Ihrer Funktions-App.
- Queue Storage: Rufen Sie problemlos Elemente aus einer Warteschlange ab, oder speichern Sie neue Elemente in der Warteschlange.

In der folgenden Beispieldatei *functions.json* wird ein Trigger und eine Bindung definiert:

```json
{
  "bindings": [
    {
      "name": "myBlob",
      "type": "blobTrigger",
      "direction": "in",
      "path": "images/{name}",
      "connection": "AzureWebJobsStorage"
    },
    {
      "name": "$return",
      "type": "queue",
      "direction": "out",
      "queueName": "images",
      "connection": "AzureWebJobsStorage"
    }
  ],
  "disabled": false
}
```

In diesem Beispiel wird die Funktion durch eine Änderung am Blobspeicher im `images`-Container ausgelöst. Die Informationen für die Datei werden übergeben, sodass der Trigger auch als Bindung fungiert. Eine weitere Bindung ist vorhanden, um Informationen in eine Warteschlange namens `images`einzufügen.

Dies ist das C#-Skript für die Funktion:

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

Das Beispiel ist eine einfache Funktion, die den Namen der Datei annimmt, die geändert oder in den Blobspeicher hochgeladen wurde, und sie zur späteren Verarbeitung in einer Warteschlange platziert.

Eine vollständige Liste der Trigger und Bindungen finden Sie unter [Konzepte für Azure Functions-Trigger und -Bindungen](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).

>[!div class="step-by-step"]
>[Zurück](azure-serverless-platform.md)
>[Weiter](application-insights.md)
