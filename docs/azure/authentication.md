---
title: Grundlegendes zur Authentifizierung in den Azure-Bibliotheken für .NET
description: Enthält eine Beschreibung der unterschiedlichen Authentifizierungsmöglichkeiten mit dem Azure SDK für .NET.
ms.date: 06/19/2020
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: 5ed29d5485dc7f59bcc757c8903116edf6bd5d7d
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174844"
---
# <a name="authenticate-with-the-azure-sdk-for-net"></a>Authentifizieren mit dem Azure SDK für .NET

## <a name="recommended-azureidentity"></a>Empfohlen: Azure.Identity

Für die neuesten Pakete im Azure SDK für .NET wird für die Authentifizierung ein gemeinsames Authentifizierungspaket verwendet: `Azure.Identity`. Wir empfehlen Ihnen, `Azure.Identity` anstelle der anderen Authentifizierungsmechanismen zu nutzen, die weiter unten in diesem Dokument beschrieben sind. Pakete, die die von `Azure.Identity` bereitgestellten Anmeldeinformationen unterstützen, verfügen über Paketbezeichner, die mit *Azure.* beginnen. [Weitere Informationen finden Sie unter den neuesten Releases im Azure SDK für .NET](https://azure.github.io/azure-sdk/releases/latest/index.html#net).

Eine vollständige Anleitung zur Nutzung von `Azure.Identity` in Ihrem Projekt finden Sie in der Dokumentation zum [Azure Identity-Client für .NET](/dotnet/api/overview/azure/identity-readme).

> [!TIP]
> Beispiele für die Nutzung von Azure Identity zum Verwalten von und Zugreifen auf Azure-Ressourcen finden Sie unter dem [Beispiel für Azure Identity, Ressourcenverwaltung und Speicherung](/samples/dotnet/samples/azure-identity-resource-management-storage/).

Informationen zum Authentifizieren bei Bibliotheken, die Azure.Identity nicht unterstützen, finden Sie im restlichen Teil dieses Themas.

## <a name="access-azure-resources"></a>Zugreifen auf Azure-Ressourcen

Zum Interagieren mit Azure-Ressourcen, z. B. Abrufen eines Geheimnisses aus Key Vault oder Speichern eines Blobs in Storage, benötigen viele Azure-Dienstbibliotheken eine Verbindungszeichenfolge oder Schlüssel für die Authentifizierung. Für SQL-Datenbank wird beispielsweise eine [standardmäßige SQL-Verbindungszeichenfolge](https://docs.microsoft.com/azure/azure-sql/database/connect-query-dotnet-core) genutzt. Dienstverbindungszeichenfolgen werden in anderen Azure-Diensten wie [Azure Cosmos DB](/azure/cosmos-db/), [Azure Cache for Redis](/azure/azure-cache-for-redis/cache-dotnet-how-to-use-azure-redis-cache) und [Service Bus](/azure/service-bus-messaging/service-bus-dotnet-get-started-with-queues) verwendet. Diese Zeichenfolgen können Sie über das Azure-Portal, mit der CLI oder mit PowerShell abrufen. Sie können auch die Azure-Verwaltungsbibliotheken für .NET zum Abfragen von Ressourcen verwenden, um Verbindungszeichenfolgen in Ihrem Code zu erstellen.

Die Methoden für die Verwendung einer Verbindungszeichenfolge variieren je nach Produkt. [Weitere Informationen finden Sie in der Dokumentation zu Ihrem Azure-Produkt](/azure/?product=featured).

## <a name="manage-azure-resources"></a>Verwalten von Azure-Ressourcen

[!include[Create service principal](includes/create-sp.md)]

Nachdem der Dienstprinzipal erstellt wurde, stehen zwei Optionen für die Authentifizierung beim Dienstprinzipal zur Verfügung, um Ressourcen zu erstellen und zu verwalten.

Bei beiden Optionen müssen Sie dem Projekt die folgenden NuGet-Pakete hinzufügen.

```powershell
Install-Package Microsoft.Azure.Management.Fluent
Install-Package Microsoft.Azure.Management.ResourceManager.Fluent
```

### <a name="authenticate-with-token-credentials"></a>Authentifizieren mit Zugriffstoken-Anmeldeinformationen

Die erste Methode sieht das Erstellen des tokenbasierten Anmeldeinformationsobjekts im Code vor. Sie müssen die Anmeldeinformationen in einer Konfigurationsdatei, der Registrierung oder Azure Key Vault sicher speichern.

```csharp
var credentials = SdkContext.AzureCredentialsFactory
    .FromServicePrincipal(clientId,
        clientSecret,
        tenantId,
        AzureEnvironment.AzureGlobalCloud);
```

Verwenden Sie die Werte *clientId*, *clientSecret* und *tenantId* aus der JSON-Ausgabe, die Sie beim Erstellen des Dienstprinzipals erhalten haben.

Erstellen Sie dann das Einstiegspunktobjekt `Azure`, um mit der Verwendung der API zu beginnen:

```csharp
var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```

### <a name="file-based-authentication"></a><a name="mgmt-file"></a>Dateibasierte Authentifizierung

Die dateibasierte Authentifizierung ermöglicht Ihnen das Ablegen der Anmeldeinformationen für den Dienstprinzipal in einer einfachen Textdatei, die Sie im Dateisystem schützen.

[!include[File-based authentication](includes/file-based-auth.md)]

Lesen Sie den Inhalt der Datei, und erstellen Sie das Einstiegspunktobjekt `Azure`, um mit der Verwendung der API zu beginnen:

```csharp
// pull in the location of the authentication properties file from the environment
var credentials = SdkContext.AzureCredentialsFactory
    .FromFile(Environment.GetEnvironmentVariable("AZURE_AUTH_LOCATION"));

var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```
