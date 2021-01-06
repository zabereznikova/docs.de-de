---
title: Grundlegendes zur Authentifizierung in den Azure-Bibliotheken für .NET
description: Enthält eine Beschreibung der unterschiedlichen Authentifizierungsmöglichkeiten mit dem Azure SDK für .NET.
ms.date: 06/19/2020
ms.custom: devx-track-dotnet
ms.openlocfilehash: 0a508606b40905d5b09b8515910873359efbbf2e
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "97700840"
---
# <a name="authenticate-with-the-azure-sdk-for-net"></a><span data-ttu-id="2901f-103">Authentifizieren mit dem Azure SDK für .NET</span><span class="sxs-lookup"><span data-stu-id="2901f-103">Authenticate with the Azure SDK for .NET</span></span>

## <a name="recommended-azureidentity"></a><span data-ttu-id="2901f-104">Empfohlen: Azure.Identity</span><span class="sxs-lookup"><span data-stu-id="2901f-104">Recommended: Azure.Identity</span></span>

<span data-ttu-id="2901f-105">Für die neuesten Pakete im Azure SDK für .NET wird für die Authentifizierung ein gemeinsames Authentifizierungspaket verwendet: `Azure.Identity`.</span><span class="sxs-lookup"><span data-stu-id="2901f-105">The latest packages in the Azure SDK for .NET use a common authentication package to authenticate, `Azure.Identity`.</span></span> <span data-ttu-id="2901f-106">Wir empfehlen Ihnen, `Azure.Identity` anstelle der anderen Authentifizierungsmechanismen zu nutzen, die weiter unten in diesem Dokument beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="2901f-106">Using `Azure.Identity` is recommended over other authentication mechanisms described later in this document.</span></span> <span data-ttu-id="2901f-107">Pakete, die die von `Azure.Identity` bereitgestellten Anmeldeinformationen unterstützen, bauen auf `Azure.Core` auf und verfügen über Paketbezeichner, die mit *Azure* beginnen.</span><span class="sxs-lookup"><span data-stu-id="2901f-107">Packages supporting the credentials provided by `Azure.Identity` are built on top of `Azure.Core` and have package identifiers starting with *Azure*.</span></span> <span data-ttu-id="2901f-108">Eine Liste der Pakete, die `Azure.Core` verwenden, finden Sie in der [Paketliste](packages.md).</span><span class="sxs-lookup"><span data-stu-id="2901f-108">[See the package list](packages.md) for an inventory of packages that use `Azure.Core`.</span></span>

<span data-ttu-id="2901f-109">Eine vollständige Anleitung zur Nutzung von `Azure.Identity` in Ihrem Projekt finden Sie in der Dokumentation zum [Azure Identity-Client für .NET](/dotnet/api/overview/azure/identity-readme).</span><span class="sxs-lookup"><span data-stu-id="2901f-109">For complete instructions on using `Azure.Identity` in your project, see the documentation for [Azure Identity client for .NET](/dotnet/api/overview/azure/identity-readme).</span></span>

> [!TIP]
> <span data-ttu-id="2901f-110">Beispiele für die Nutzung von Azure Identity zum Verwalten von und Zugreifen auf Azure-Ressourcen finden Sie unter dem [Beispiel für Azure Identity, Ressourcenverwaltung und Speicherung](/samples/dotnet/samples/azure-identity-resource-management-storage/).</span><span class="sxs-lookup"><span data-stu-id="2901f-110">See the [Azure Identity, Resource Management, and Storage sample](/samples/dotnet/samples/azure-identity-resource-management-storage/) for examples of using Azure Identity to manage and access Azure resources.</span></span>

<span data-ttu-id="2901f-111">Informationen zum Authentifizieren bei Bibliotheken, die Azure.Identity nicht unterstützen, finden Sie im restlichen Teil dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="2901f-111">To authenticate with libraries that don't support Azure.Identity, see the rest of this topic.</span></span>

## <a name="access-azure-resources"></a><span data-ttu-id="2901f-112">Zugreifen auf Azure-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="2901f-112">Access Azure resources</span></span>

<span data-ttu-id="2901f-113">Zum Interagieren mit Azure-Ressourcen, z. B. Abrufen eines Geheimnisses aus Key Vault oder Speichern eines Blobs in Storage, benötigen viele Azure-Dienstbibliotheken eine Verbindungszeichenfolge oder Schlüssel für die Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="2901f-113">To interact with Azure resources, such as retrieving a secret from Key Vault or storing a blob in Storage, many Azure service libraries require a connection string or keys for authentication.</span></span> <span data-ttu-id="2901f-114">Für SQL-Datenbank wird beispielsweise eine [standardmäßige SQL-Verbindungszeichenfolge](/azure/azure-sql/database/connect-query-dotnet-core) genutzt.</span><span class="sxs-lookup"><span data-stu-id="2901f-114">For example, SQL Database uses a [standard SQL connection string](/azure/azure-sql/database/connect-query-dotnet-core).</span></span> <span data-ttu-id="2901f-115">Dienstverbindungszeichenfolgen werden in anderen Azure-Diensten wie [Azure Cosmos DB](/azure/cosmos-db/), [Azure Cache for Redis](/azure/azure-cache-for-redis/cache-dotnet-how-to-use-azure-redis-cache) und [Service Bus](/azure/service-bus-messaging/service-bus-dotnet-get-started-with-queues) verwendet.</span><span class="sxs-lookup"><span data-stu-id="2901f-115">Service connection strings are used in other Azure services like [CosmosDB](/azure/cosmos-db/), [Azure Cache for Redis](/azure/azure-cache-for-redis/cache-dotnet-how-to-use-azure-redis-cache), and [Service Bus](/azure/service-bus-messaging/service-bus-dotnet-get-started-with-queues).</span></span> <span data-ttu-id="2901f-116">Diese Zeichenfolgen können Sie über das Azure-Portal, mit der CLI oder mit PowerShell abrufen.</span><span class="sxs-lookup"><span data-stu-id="2901f-116">You can get those strings using the Azure portal, CLI, or PowerShell.</span></span> <span data-ttu-id="2901f-117">Sie können auch die Azure-Verwaltungsbibliotheken für .NET zum Abfragen von Ressourcen verwenden, um Verbindungszeichenfolgen in Ihrem Code zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2901f-117">You can also use the Azure management libraries for .NET to query resources to build connection strings in your code.</span></span>

<span data-ttu-id="2901f-118">Die Methoden für die Verwendung einer Verbindungszeichenfolge variieren je nach Produkt.</span><span class="sxs-lookup"><span data-stu-id="2901f-118">The methods for using a connection string vary by product.</span></span> <span data-ttu-id="2901f-119">[Weitere Informationen finden Sie in der Dokumentation zu Ihrem Azure-Produkt](/azure/?product=featured).</span><span class="sxs-lookup"><span data-stu-id="2901f-119">[Refer to the documentation for your Azure product](/azure/?product=featured).</span></span>

## <a name="manage-azure-resources"></a><span data-ttu-id="2901f-120">Verwalten von Azure-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="2901f-120">Manage Azure resources</span></span>

[!include[Create service principal](includes/create-sp.md)]

<span data-ttu-id="2901f-121">Nachdem der Dienstprinzipal erstellt wurde, stehen zwei Optionen für die Authentifizierung beim Dienstprinzipal zur Verfügung, um Ressourcen zu erstellen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="2901f-121">Now that the service principal is created, two options are available to authenticate to the service principal to create and manage resources.</span></span>

<span data-ttu-id="2901f-122">Bei beiden Optionen müssen Sie dem Projekt die folgenden NuGet-Pakete hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="2901f-122">For both options you will need to add the following NuGet packages to your project.</span></span>

```powershell
Install-Package Microsoft.Azure.Management.Fluent
Install-Package Microsoft.Azure.Management.ResourceManager.Fluent
```

### <a name="authenticate-with-token-credentials"></a><span data-ttu-id="2901f-123">Authentifizieren mit Zugriffstoken-Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="2901f-123">Authenticate with token credentials</span></span>

<span data-ttu-id="2901f-124">Die erste Methode sieht das Erstellen des tokenbasierten Anmeldeinformationsobjekts im Code vor.</span><span class="sxs-lookup"><span data-stu-id="2901f-124">The first method is to build the token credential object in code.</span></span> <span data-ttu-id="2901f-125">Sie müssen die Anmeldeinformationen in einer Konfigurationsdatei, der Registrierung oder Azure Key Vault sicher speichern.</span><span class="sxs-lookup"><span data-stu-id="2901f-125">You should store the credentials securely in a configuration file, the registry, or Azure KeyVault.</span></span>

```csharp
var credentials = SdkContext.AzureCredentialsFactory
    .FromServicePrincipal(clientId,
        clientSecret,
        tenantId,
        AzureEnvironment.AzureGlobalCloud);
```

<span data-ttu-id="2901f-126">Verwenden Sie die Werte *clientId*, *clientSecret* und *tenantId* aus der JSON-Ausgabe, die Sie beim Erstellen des Dienstprinzipals erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="2901f-126">Use the *clientId*, *clientSecret*, and *tenantId* values from the JSON output when you created the service principal.</span></span>

<span data-ttu-id="2901f-127">Erstellen Sie dann das Einstiegspunktobjekt `Azure`, um mit der Verwendung der API zu beginnen:</span><span class="sxs-lookup"><span data-stu-id="2901f-127">Then create the entry point `Azure` object to start working with the API:</span></span>

```csharp
var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```

<span data-ttu-id="2901f-128">Es empfiehlt sich, die *subscriptionId* aus der JSON-Ausgabe explizit für das `Azure`-Objekt bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="2901f-128">It is recommended that you explicitly provide the *subscriptionId* from the JSON output to the `Azure` object:</span></span>

```csharp
var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithSubscription(subscriptionId);
```

### <a name="file-based-authentication"></a><a name="mgmt-file"></a><span data-ttu-id="2901f-129">Dateibasierte Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="2901f-129">File-based authentication</span></span>

<span data-ttu-id="2901f-130">Die dateibasierte Authentifizierung ermöglicht Ihnen das Ablegen der Anmeldeinformationen für den Dienstprinzipal in einer einfachen Textdatei, die Sie im Dateisystem schützen.</span><span class="sxs-lookup"><span data-stu-id="2901f-130">File-based authentication allows you to put the service principal credentials in a plain text file and secure it within the file system.</span></span>

[!include[File-based authentication](includes/file-based-auth.md)]

<span data-ttu-id="2901f-131">Lesen Sie den Inhalt der Datei, und erstellen Sie das Einstiegspunktobjekt `Azure`, um mit der Verwendung der API zu beginnen:</span><span class="sxs-lookup"><span data-stu-id="2901f-131">Read the contents of the file and create the entry point `Azure` object to start working with the API:</span></span>

```csharp
// pull in the location of the authentication properties file from the environment
var credentials = SdkContext.AzureCredentialsFactory
    .FromFile(Environment.GetEnvironmentVariable("AZURE_AUTH_LOCATION"));

var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```
