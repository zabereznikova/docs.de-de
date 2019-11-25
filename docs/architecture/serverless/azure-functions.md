---
title: 'Azure Functions: Serverlose Apps'
description: Azure Functions bietet serverlose Funktionen für mehrere Sprachen (C#, JavaScript, Java) und Plattformen, um ereignisgesteuerten Code für die sofortige Skalierung bereitzustellen.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 5e8187b3752a0f0d0bcf8e15f2ce440dc5a64e45
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2019
ms.locfileid: "72522866"
---
# <a name="azure-functions"></a>Überprüfung auf

Azure Functions bietet eine serverlose Computeerfahrung. Eine Funktion wird durch einen *Trigger* aufgerufen (z.B. den Zugriff auf einen HTTP-Endpunkt oder einen Timer) und führt einen Codeblock oder Geschäftslogik aus. Funktionen unterstützen auch spezialisierte *Bindungen*, die eine Verbindung mit Ressourcen wie Speicher und Warteschlangen herstellen.

![Azure Functions-Logo](./media/azure-functions-logo.png)

Es gibt zwei Versionen des Azure Functions-Frameworks. Die Legacyversion unterstützt die vollständige Version von .NET Framework, und die neue Runtime unterstützt plattformübergreifende .NET Core-Anwendungen. Neben C# werden weitere Sprachen wie JavaScript, F# und Java unterstützt. Funktionen, die im Portal erstellt werden, bieten eine umfangreiche Skriptsyntax. Funktionen, die als eigenständige Projekte erstellt werden, können mit vollständiger Plattformunterstützung bereitgestellt werden.

Weitere Informationen finden Sie in der [Azure Functions-Dokumentation](https://docs.microsoft.com/azure/azure-functions).

## <a name="functions-v1-vs-v2"></a>Functions v1 im Vergleich zu v2

Es gibt zwei Versionen der Azure Functions-Runtime: 1.x und 2.x. Version 1.x ist allgemein verfügbar (GA). Sie unterstützt die .NET-Entwicklung im Portal oder auf Windows-Computern und verwendet .NET Framework. 1.x unterstützt C#, JavaScript und F# und bietet experimentelle Unterstützung für Python, PHP, TypeScript, Batch, Bash und PowerShell.

[Version 2.x ist jetzt ebenfalls allgemein verfügbar](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/). Sie nutzt .NET Core und unterstützt plattformübergreifende Entwicklung auf Windows-, macOS- und Linux-Computern. 2.x bietet erstklassige Unterstützung für Java, aber noch keine direkte Unterstützung für die experimentellen Sprachen. Version 2.x verwendet ein neues Modell für die Bindungserweiterbarkeit, das Erweiterungen von Drittanbietern für die Plattform, unabhängige Versionsverwaltung von Bindungen und eine optimierte Ausführungsumgebung ermöglicht.

> **In 1.x gibt es ein bekanntes Problem mit [Bindungsumleitungsunterstützung](https://github.com/Azure/azure-functions-host/issues/992).** Das Problem ist spezifisch für die .NET-Entwicklung. Projekte mit Abhängigkeiten von Bibliotheken, die eine andere Version als die Bibliotheken aufweisen, die in der Runtime enthalten sind, sind betroffen. Das Functions-Team hat sich zum Ziel gesetzt, konkrete Fortschritte bei der Lösung des Problems zu erzielen. Das Team wird sich mit Bindungsumleitungen in Version 2.x befassen, bevor die allgemeine Verfügbarkeit bekanntgegeben wird. Die offizielle Teamaussage mit den empfohlenen Korrekturen und Problemumgehungen finden Sie hier: [Assemblyauflösung in Azure Functions](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).

Weitere Informationen finden Sie unter [Vergleich von 1.x und 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions).

## <a name="programming-language-support"></a>Unterstützung für Programmiersprachen

Die folgenden Sprachen werden in Versionen mit allgemeiner Verfügbarkeit (GA), als Vorschau oder als experimentelles Feature unterstützt.

|Sprache      |1.x         |2.x      |
|--------------|------------|---------|
|**C#**        |Allgemein verfügbar          |Vorschau  |
|**JavaScript**|Allgemein verfügbar          |Vorschau  |
|**F#**        |Allgemein verfügbar          |         |
|**Java**      |            |Vorschau  |
|**Python**    |Experimentell|         |
|**PHP**       |Experimentell|         |
|**TypeScript**|Experimentell|         |
|**Batch**     |Experimentell|         |
|**Bash**      |Experimentell|         |
|**PowerShell**|Experimentell|         |

Weitere Informationen finden Sie unter [Unterstützte Sprachen](https://docs.microsoft.com/azure/azure-functions/supported-languages).

## <a name="app-service-plans"></a>App Service-Pläne

Funktionen werden durch einen *App Service-Plan* unterstützt. Der Plan definiert die Ressourcen, die von der Funktions-App verwendet werden. Sie können einer Region Pläne zuweisen, die Größe und Anzahl der zu verwendenden virtuellen Computer bestimmen und einen Tarif auswählen. Für einen echten serverlosen Ansatz können Funktions-Apps den **Verbrauchstarif** verwenden. Der Verbrauchstarif skaliert das Back-End automatisch basierend auf der Auslastung.

Weitere Informationen finden Sie unter [App Service-Pläne](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).

## <a name="create-your-first-function"></a>Erstellen Ihrer ersten Funktion

Es gibt drei gängige Methoden, um Funktions-Apps zu erstellen.

- Skriptfunktionen im Portal.
- Erstellen der erforderlichen Ressourcen mithilfe der Azure-Befehlszeilenschnittstelle (CLI).
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

## <a name="proxies"></a>Proxys

Proxys bieten Umleitungsfunktionen für Ihre Anwendung. Proxies stellen einen Endpunkt bereit und ordnen diesen Endpunkt einer anderen Ressource zu. Mit Proxys haben Sie die folgenden Möglichkeiten:

- Umleiten einer eingehenden Anforderung an einen anderen Endpunkt.
- Ändern der eingehenden Anforderung, bevor sie übergeben wird.
- Ändern oder Bereitstellen einer Antwort.

Proxys werden beispielsweise für die folgenden Szenarien verwendet:

- Vereinfachen, Kürzen oder Ändern der URL.
- Bereitstellen eines konsistenten API-Präfix für mehrere Back-End-Dienste.
- Simulieren einer Antwort an einen Endpunkt, der entwickelt wird.
- Bereitstellen einer statischen Antwort für einen bekannten Endpunkt.
- Aufrechterhalten der Konsistenz eines API-Endpunkts, während das Back-End verschoben oder migriert wird.

Proxys werden als JSON-Definitionen gespeichert. Im Folgenden ein Beispiel:

```json
{
  "$schema": "http://json.schemastore.org/proxies",
  "proxies": {
    "Domain Redirect": {
      "matchCondition": {
        "route": "/{shortUrl}"
      },
      "backendUri": "http://%WEBSITE_HOSTNAME%/api/UrlRedirect/{shortUrl}"
    },
    "Root": {
      "matchCondition": {
        "route": "/"
      },
      "responseOverrides": {
        "response.statusCode": "301",
        "response.statusReason": "Moved Permanently",
        "response.headers.location": "https://docs.microsoft.com/"
      }
    }
  }
}
```

Der `Domain Redirect`-Proxy verwendet eine gekürzte Route und ordnet sie der längeren Funktionsressource zu. Die Transformation sieht wie folgt aus:

`https://--shorturl--/123` -> `https://--longurl--.azurewebsites.net/api/UrlRedirect/123`

Der `Root`-Proxy verwendet alles, was an die Stamm-URL (`https://--shorturl--/`) gesendet wird, und leitet es an die Dokumentationswebsite weiter.

Ein Beispiel für die Verwendung von Proxys sehen Sie im Video [Azure: Bring your app to the cloud with serverless Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102) (Migrieren einer App zur Cloud mit serverlosen Azure Functions). In Echtzeit wird eine ASP.NET Core-Anwendung, die auf einem lokalen SQL-Server ausgeführt wird, zur Azure-Cloud migriert. Proxys werden verwendet, um das Refactoring eines traditionellen Web-API-Projekts zur Verwendung von Funktionen zu unterstützen.

Weitere Informationen zu Proxys finden Sie unter [Arbeiten mit Azure Functions-Proxys](https://docs.microsoft.com/azure/azure-functions/functions-proxies).

>[!div class="step-by-step"]
>[Zurück](azure-serverless-platform.md)
>[Weiter](application-insights.md)
