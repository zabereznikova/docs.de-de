---
title: Azure Functions – serverlose apps
description: Azure Functions bietet serverlose Funktionen in mehreren Sprachen (c#, JavaScript, Java) und Plattformen ereignisgesteuerte sofortige Skalierung Code.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 4febcc01eebf3efce3fc1eb42e19c2ec6c0baa52
ms.sourcegitcommit: 89fcad7e816c12eb1299128481183f01c73f2c07
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "63807893"
---
# <a name="azure-functions"></a>Überprüfung auf

Azure Functions bietet eine serverlosen computeoberfläche. Eine Funktion wird aufgerufen, indem eine *Trigger* (z. B. Zugriff auf einen HTTP-Endpunkt oder einen Timer) und führt einen Anweisungsblock Code oder die Geschäftslogik aus. Unterstützt auch spezielle Funktionen *Bindungen* , die Verbindung mit Ressourcen wie Speichersystemen und Warteschlangen.

![Azure Functions-logo](./media/azure-functions-logo.png)

Es gibt zwei Versionen von Azure Functions-Framework. Die ältere Version unterstützt das vollständige .NET Framework und die neue Runtime unterstützt die plattformübergreifende .NET Core-Anwendungen. Weitere Sprachen neben C# wie z.B. JavaScript F#, und Java werden unterstützt. Im Portal erstellte Funktionen bieten eine umfangreiche Syntax für die Skripterstellung. Funktionen, die als eigenständige Projekte erstellt werden, können mit vollständiger Unterstützung und Funktionen bereitgestellt werden.

Weitere Informationen finden Sie unter [Dokumentation zu Azure Functions](https://docs.microsoft.com/azure/azure-functions).

## <a name="functions-v1-vs-v2"></a>Funktionen von v1 und v2

Es gibt zwei Versionen von Azure Functions-Laufzeit: 1.x und 2.x. Version 1.x ist allgemein verfügbar (GA). Es unterstützt die Entwicklung von .NET über das Portal oder die Windows-Computer und verwendet die .NET Framework. 1.x unterstützt C#, JavaScript und F#, experimentelle Unterstützung für Python, PHP, TypeScript, Batch, Bash und PowerShell.

[Version 2.x ist nun ebenfalls allgemein verfügbar](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/). Es nutzt die .NET Core und unterstützt die plattformübergreifende Entwicklung unter Windows, MacOS und Linux-Computer. 2.x bietet erstklassige Unterstützung für Java, aber noch direkt unterstützt keine experimentellen Sprachen. Version 2.x verwendet ein neues Erweiterbarkeitsmodell von Bindung, die Erweiterungen von Drittanbietern für die Plattform, Bindungen, voneinander unabhängige Versionen ermöglicht und eine optimierte ausführungsumgebung.

> **Es gibt ein bekanntes Problem in 1.x mit [Umleitung bindungsunterstützung](https://github.com/Azure/azure-functions-host/issues/992).** Das Problem ist spezifisch für die Entwicklung von .NET. Projekte mit Abhängigkeiten von Bibliotheken, die eine andere Version der Bibliotheken, die in der Laufzeit enthalten sind, sind betroffen. Die Functions-Team für die konkrete Fortschritte auf dem Problem zugesichert wurde. Das Team werden bindungsumleitungen in 2.x behandelt, bevor er in der allgemeinen Verfügbarkeit geht. Die offizielle Team-Anweisung mit empfohlenen Problembehebungen und problemumgehungen ist hier verfügbar: [Assembly-Auflösung in Azure Functions](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).

Weitere Informationen finden Sie unter [Vergleichen von 1.x und 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions).

## <a name="programming-language-support"></a>Unterstützung für Programmiersprachen

Die folgenden Sprachen unterstützt werden entweder im allgemeinen Verfügbarkeit (GA), in der Vorschau anzuzeigen oder experimentell.

|Sprache      |1.x         |2.x      |
|--------------|------------|---------|
|**C#**        |GA          |Vorschau  |
|**JavaScript**|GA          |Vorschau  |
|**F#**        |GA          |         |
|**Java**      |            |Vorschau  |
|**Python**    |Experimentell|         |
|**PHP**       |Experimentell|         |
|**TypeScript**|Experimentell|         |
|**Batch**     |Experimentell|         |
|**Bash**      |Experimentell|         |
|**PowerShell**|Experimentell|         |

Weitere Informationen finden Sie unter [unterstützte Sprachen](https://docs.microsoft.com/azure/azure-functions/supported-languages).

## <a name="app-service-plans"></a>App Service-Pläne

Funktionen verfügen über eine *app Service-Plan*. Der Plan definiert die von der Functions-app verwendeten Ressourcen. Sie können Pläne in einer Region zuweisen, bestimmen die Größe und Anzahl von virtuellen Computern, die verwendet werden, und wählen Sie einen Tarif. Für einen Ansatz mit "true" serverlosen Funktionen-apps verwenden die **Verbrauch** Plan. Das Back-End automatisch je nach Auslastung kann der verbrauchsbasierten Verbrauchsplan skaliert werden.

Weitere Informationen finden Sie unter [App Service-Pläne](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).

## <a name="create-your-first-function"></a>Erstellen Sie Ihrer ersten Funktion

Es gibt drei Möglichkeiten, die Sie die Funktions-apps erstellen können.

* ScriptEngine-Funktionen im Portal.
* Erstellen Sie die erforderlichen Ressourcen mithilfe der Azure-Befehlszeilenschnittstelle (CLI).
* Erstellen Sie Funktionen lokal mit Ihrer bevorzugten IDE, und veröffentlichen Sie sie in Azure.

Weitere Informationen zum Erstellen einer skriptgesteuerten Funktion im Portal finden Sie unter [Erstellen Ihrer ersten Funktion im Azure-Portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).

Um über das Azure-Befehlszeilenschnittstelle zu erstellen, finden Sie unter [Erstellen Ihrer ersten Funktion mit der Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).

Um eine Funktion von Visual Studio zu erstellen, finden Sie unter [Erstellen Ihrer ersten Funktion mit Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).

## <a name="understand-triggers-and-bindings"></a>Verstehen von Triggern und Bindungen

Funktionen aufgerufen werden, indem eine *Trigger* sind genau möglich. Bestimmte Trigger stellen zusätzlich zum Aufrufen der Funktion können auch Bindungen. Sie können auch mehrere Bindungen zusätzlich zu den Trigger definieren. *Bindungen* bieten eine deklarative Möglichkeit, Daten zu Ihrem Code zu verbinden. Sie können im (Eingabe) übergeben werden oder Empfangen von Daten (Ausgabe). Trigger und Bindungen stellen Funktionen einfach zu können. Entfernen Sie Bindungen systemverbindungen Datenbank oder Datei manuell erstellt. Alle Informationen, die erforderlich sind, für die Bindungen befindet sich in einem speziellen *"Functions.JSON"* -Datei für Skripts oder mit Attributen im Code deklariert.

Einige gängigen Trigger enthalten:

* BLOB-Speicher: Rufen Sie Ihre Funktion auf, wenn eine Datei oder einen Ordner hochgeladen oder im Speicher geändert wird.
* HTTP: Rufen Sie die Funktion wie eine REST-API.
* Warteschlange: Aufrufen der Funktion aus, wenn Elemente in einer Warteschlange vorhanden sind.
* Timer: Rufen Sie Ihre Funktion in regelmäßigen Abständen.

Beispiele für Bindungen sind:

* COSMOS DB: problemlos Herstellen einer Verbindung mit der Datenbank zu laden oder Speichern von Dateien.
* Tabellenspeicher: Arbeiten Sie mit Schlüssel/Wert-Speicher aus Ihrer Funktionen-app.
* Warteschlangenspeicher: problemlos Abrufen von Elementen aus einer Warteschlange, oder platzieren Sie neue Elemente in der Warteschlange.

Im folgenden Beispiel *"Functions.JSON"* -Datei definiert wird, einen Trigger und eine Bindung:

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

In diesem Beispiel wird die Funktion ausgelöst, durch eine Änderung in den blobspeicher in die `images` Container. Die Informationen für die Datei ist, übergeben, damit der Trigger außerdem als Bindung fungiert. Eine andere Bindung vorhanden ist, um die Informationen in eine Warteschlange mit dem Namen `images`.

Hier ist der C#-Skript für die Funktion:

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

Das Beispiel ist eine einfache Funktion, die dem Namen der Datei, die akzeptiert wurde geändert oder BLOB-Speicher hochgeladen, und platziert es in eine Warteschlange für die spätere Verarbeitung.

Eine vollständige Liste von Triggern und Bindungen, finden Sie unter [Konzepte Azure Functions-Trigger und-Bindungen](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).

## <a name="proxies"></a>Proxys

Proxys geben den umleitungs-Funktionalität für Ihre Anwendung. Proxys einen Endpunkt verfügbar machen, und ordnen Sie diesen Endpunkt zu einer anderen Ressource. Mit Proxys möglich ist können Sie folgende Aktionen ausführen:

* Eine eingehende Anforderung an einen anderen Endpunkt umgeleitet wird.
* Ändern Sie die eingehende Anforderung aus, bevor sie weitergegeben wird.
* Ändern Sie, oder geben Sie eine Antwort.

Proxys werden z. B. für Szenarien verwendet:

* Vereinfachen, verkürzen, oder Ändern der URL.
* Bereitstellen einer API-präfixkonsistenz an mehrere Back-End-Dienste.
* Simulieren eine Antwort an einen Endpunkt, entwickelt.
* Bereitstellen von statischen Antwort auf einen bekannten Endpunkt.
* API-Endpunkt Sicherstellen der Konsistenz und während das Back-End migriert oder verschoben wird.

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

Die `Domain Redirect` Proxy akzeptiert eine verkürzte Route und ordnet es zu längeren Funktion Ressource. Die Transformation sieht wie folgt aus:

`https://--shorturl--/123` -> `https://--longurl--.azurewebsites.net/api/UrlRedirect/123`

Die `Root` Proxy wird alles gesendet, um die Stamm-URL (`https://--shorturl--/`) und leitet ihn an der Dokumentationswebsite.

Ein Beispiel der Verwendung von Proxys im Video [Azure: Bringen Sie Ihre app in die Cloud mit serverlosen Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102). In Echtzeit wird eine ASP.NET Core-Anwendung, die auf lokalen SQL Server ausgeführt wird mit der Azure Cloud migriert. Proxys werden verwendet, um zu ein herkömmlichen Web-API-Projekt zum Verwenden der Funktionen Umgestalten.

Weitere Informationen zu Proxys finden Sie unter [arbeiten mit Azure Functions-Proxys](https://docs.microsoft.com/azure/azure-functions/functions-proxies).

>[!div class="step-by-step"]
>[Zurück](azure-serverless-platform.md)
>[Weiter](application-insights.md)
