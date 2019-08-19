---
title: Azure Functions Server Lose apps
description: Azure Functions bietet Server lose Funktionen in mehreren Sprachen (C#JavaScript, Java) und Plattformen, um ereignisgesteuerten Code für die sofortige Skalierung bereitzustellen.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 4febcc01eebf3efce3fc1eb42e19c2ec6c0baa52
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577603"
---
# <a name="azure-functions"></a>Überprüfung auf

Azure Functions bietet eine Server lose computeerfahrung. Eine Funktion wird von einem *Trigger* aufgerufen (z. b. Zugriff auf einen HTTP-Endpunkt oder einen Timer) und führt einen Codeblock oder eine Geschäftslogik aus. Funktionen unterstützen außerdem spezialisierte *Bindungen* , die eine Verbindung mit Ressourcen wie Speicher und Warteschlangen herstellen.

![Azure Functions-Logo](./media/azure-functions-logo.png)

Es gibt zwei Versionen des Azure Functions-Frameworks. Die Legacy Version unterstützt die vollständige .NET Framework und die neue Laufzeit unterstützt plattformübergreifende .net Core-Anwendungen. Neben C# JavaScript, F#und Java werden weitere Sprachen unterstützt. Funktionen, die im Portal erstellt werden, bieten eine umfangreiche Skript Syntax. Funktionen, die als eigenständige Projekte erstellt werden, können mit vollständiger Platt Form Unterstützung bereitgestellt werden.

Weitere Informationen finden Sie unter [Azure Functions-Dokumentation](https://docs.microsoft.com/azure/azure-functions).

## <a name="functions-v1-vs-v2"></a>Functions v1 und v2

Es gibt zwei Versionen der Azure Functions Laufzeit: 1. x und 2. x. Version 1. x ist allgemein verfügbar (GA). Es unterstützt die .net-Entwicklung im Portal oder auf Windows-Computern und verwendet die .NET Framework. 1. x unter C#stützt, JavaScript und F#und bietet experimentelle Unterstützung für python, PHP, typescript, Batch, bash und PowerShell.

[Version 2. x ist jetzt auch allgemein verfügbar](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/). Es nutzt .net Core und unterstützt die plattformübergreifende Entwicklung auf Windows-, macOS-und Linux-Computern. 2. x bietet erstklassige Unterstützung für Java, bietet aber noch keine direkte Unterstützung für die experimentellen Sprachen. Version 2. x verwendet ein neues Modell für die Bindungs Erweiterbarkeit, das Erweiterungen von Drittanbietern für die Plattform, unabhängige Versionsverwaltung von Bindungen und eine optimierte Ausführungsumgebung ermöglicht.

> **In 1. x ist ein bekanntes Problem mit der [Unterstützung für die Bindungs Umleitung](https://github.com/Azure/azure-functions-host/issues/992)aufgetreten.** Das Problem ist spezifisch für die .net-Entwicklung. Projekte mit Abhängigkeiten von Bibliotheken, die eine andere Version als die Bibliotheken enthalten, die in der Laufzeit enthalten sind, sind betroffen. Das Functions-Team hat sich verpflichtet, konkrete Statusinformationen zu dem Problem zu treffen. Das Team adressiert Bindungs Umleitungen in 2. x, bevor es in die allgemeine Verfügbarkeit übergeht. Die offizielle Team Anweisung mit den empfohlenen Korrekturen und Problem Umgehungen finden Sie hier: Assemblyauflösung [in Azure Functions](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).

Weitere Informationen finden Sie unter [Vergleichen von 1. x und 2. x](https://docs.microsoft.com/azure/azure-functions/functions-versions).

## <a name="programming-language-support"></a>Unterstützung für Programmiersprachen

Die folgenden Sprachen werden entweder in allgemeiner Verfügbarkeit (GA), Vorschau oder experimentell unterstützt.

|Sprache      |1. x         |2.x      |
|--------------|------------|---------|
|**C#**        |GAS          |Vorschau  |
|**JavaScript**|GAS          |Vorschau  |
|**F#**        |GAS          |         |
|**Java**      |            |Vorschau  |
|**Python**    |Experimentell|         |
|**PHP**       |Experimentell|         |
|**TypeScript**|Experimentell|         |
|**Batch**     |Experimentell|         |
|**Verschlüsselt**      |Experimentell|         |
|**PowerShell**|Experimentell|         |

Weitere Informationen finden Sie unter [Sprach- und Regionsunterstützung für die Textanalyse-API](https://docs.microsoft.com/azure/azure-functions/supported-languages).

## <a name="app-service-plans"></a>App Service-Pläne

Funktionen werden durch einen *App Service-Plan*unterstützt. Der Plan definiert die Ressourcen, die von der Functions-App verwendet werden. Sie können einem Bereich Pläne zuweisen, die Größe und Anzahl der zu verwendenden virtuellen Computer ermitteln und einen Tarif auswählen. Für einen echten Server losen Ansatz können Funktions-apps den **Verbrauchs** Plan verwenden. Der Verbrauchs Plan skaliert das Back-End automatisch basierend auf der Auslastung.

Weitere Informationen finden Sie unter [App Service-Pläne](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).

## <a name="create-your-first-function"></a>Erstellen Ihrer ersten Funktion

Es gibt drei gängige Methoden, um Funktions-apps zu erstellen.

* Skriptfunktionen im Portal.
* Erstellen Sie die erforderlichen Ressourcen mithilfe der Azure-Befehlszeilenschnittstelle (CLI).
* Erstellen Sie Funktionen lokal mithilfe Ihrer bevorzugten IDE, und veröffentlichen Sie Sie in Azure.

Weitere Informationen zum Erstellen einer Skriptfunktion im Portal finden [Sie unter Erstellen Ihrer ersten Funktion in der Azure-Portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).

Informationen zum Erstellen aus der Azure CLI finden Sie unter [Erstellen Ihrer ersten Funktion mit der Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).

Informationen zum Erstellen einer Funktion aus Visual Studio finden Sie unter [Erstellen Ihrer ersten Funktion mit Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).

## <a name="understand-triggers-and-bindings"></a>Grundlegendes zu Triggern und Bindungen

Funktionen werden von einem- Aufruf aufgerufen und können über genau einen verfügen. Zusätzlich zum Aufrufen der Funktion dienen bestimmte Trigger auch als Bindungen. Zusätzlich zum-Vorgang können auch mehrere Bindungen definiert werden. *Bindungen* bieten eine deklarative Möglichkeit, um Daten mit Ihrem Code zu verbinden. Sie können an (Eingabe) oder empfangende Daten (Ausgabe) übermittelt werden. Trigger und Bindungen erleichtern das Arbeiten mit Funktionen. Bindungen entfernen den Aufwand für das manuelle Erstellen von Datenbank-oder Dateisystem Verbindungen. Alle Informationen, die für die Bindungen benötigt werden, sind in einer speziellen Datei " *Functions. JSON* " für Skripts enthalten oder mit Attributen im Code deklariert.

Einige gängige Trigger sind:

* BLOB Storage: Rufen Sie Ihre Funktion auf, wenn eine Datei oder ein Ordner im Speicher hochgeladen oder geändert wird.
* HTTP: Rufen Sie Ihre Funktion wie eine Rest-API auf.
* Queue: Rufen Sie die Funktion auf, wenn Elemente in einer Warteschlange vorhanden sind.
* Timer: Rufen Sie Ihre Funktion in einem regulären Rhythmus auf.

Beispiele für Bindungen sind:

* Cosmosdb: Stellen Sie problemlos eine Verbindung mit der Datenbank her, um Dateien zu laden oder zu speichern.
* Table Storage: Arbeiten Sie mit dem Schlüssel-Wert-Speicher von ihrer Funktionen-app.
* Queue Storage: problemlos Elemente aus einer Warteschlange abrufen oder neue Elemente in der Warteschlange platzieren.

Die folgende Beispieldatei " *Functions. JSON* " definiert einen-und eine-Bindung:

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

In diesem Beispiel wird die Funktion durch eine Änderung des BLOB-Speichers im `images` Container ausgelöst. Die Informationen für die Datei werden an die Datei übertragen, sodass der-Triggerwert auch als Bindung fungiert. Eine weitere Bindung besteht darin, Informationen in eine Warte `images`Schlange mit dem Namen einzufügen.

Hier ist das C# Skript für die-Funktion:

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

Das Beispiel ist eine einfache Funktion, die den Namen der Datei annimmt, die geändert oder in den BLOB-Speicher hochgeladen wurde, und Sie zur späteren Verarbeitung in eine Warteschlange platziert.

Eine vollständige Liste der Trigger und Bindungen finden Sie unter [Azure Functions Trigger und Bindungen Konzepte](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).

## <a name="proxies"></a>Proxys

Proxys stellen Umleitungs Funktionen für Ihre Anwendung bereit. Proxys machen einen Endpunkt verfügbar und ordnen diesen Endpunkt einer anderen Ressource zu. Mit Proxys können Sie folgende Aktionen ausführen:

* Leitet eine eingehende Anforderung an einen anderen Endpunkt um.
* Ändern Sie die eingehende Anforderung, bevor Sie weitergeleitet wird.
* Ändern oder Bereitstellen einer Antwort.

Proxys werden für folgende Szenarien verwendet:

* Vereinfachen, verkürzen oder Ändern der URL.
* Bereitstellen eines konsistenten API-Präfixes für mehrere Back-End-Dienste.
* Simulieren einer Antwort auf einen Endpunkt, der entwickelt wird.
* Bereitstellen einer statischen Antwort auf einen bekannten Endpunkt
* Halten Sie einen API-Endpunkt konsistent, während das Back-End verschoben oder migriert wird.

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

Der `Domain Redirect` Proxy nimmt eine verkürzte Route an und ordnet Sie der längeren Funktions Ressource zu. Die Transformation sieht wie folgt aus:

`https://--shorturl--/123` -> `https://--longurl--.azurewebsites.net/api/UrlRedirect/123`

Der `Root` Proxy übernimmt alle Elemente, die an die Stamm`https://--shorturl--/`-URL () gesendet werden, und leitet Sie an die Dokumentations Website um.

Ein Beispiel für die Verwendung von Proxys finden [Sie im Video Azure: Bringen Sie Ihre APP mit Server losem Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102)in die Cloud. In Echtzeit wird eine ASP.net Core Anwendung, die auf dem lokalen SQL Server ausgeführt wird, in die Azure-Cloud migriert. Proxys dienen zum Umgestalten eines herkömmlichen Web-API-Projekts für die Verwendung von Funktionen.

Weitere Informationen zu Proxys finden Sie unter [Arbeiten mit Azure-Funktionsproxys](https://docs.microsoft.com/azure/azure-functions/functions-proxies).

>[!div class="step-by-step"]
>[Zurück](azure-serverless-platform.md)
>[Weiter](application-insights.md)
