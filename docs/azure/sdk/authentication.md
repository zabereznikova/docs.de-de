---
title: Authentifizieren bei den Azure-Bibliotheken für .NET
description: Authentifizieren bei den Azure-Bibliotheken für .NET
ms.date: 08/22/2018
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: f6af813cd1423be8784b769b272756b2c8258392
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2020
ms.locfileid: "81607870"
---
# <a name="authenticate-with-the-azure-libraries-for-net"></a><span data-ttu-id="01a1a-103">Authentifizieren bei den Azure-Bibliotheken für .NET</span><span class="sxs-lookup"><span data-stu-id="01a1a-103">Authenticate with the Azure Libraries for .NET</span></span>

## <a name="connect-to-services-with-connection-strings"></a><span data-ttu-id="01a1a-104">Herstellen einer Verbindung mit Diensten mit Verbindungszeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="01a1a-104">Connect to services with connection strings</span></span>

<span data-ttu-id="01a1a-105">Die meisten Azure-Dienstbibliotheken fordern für die Authentifizierung eine Verbindungszeichenfolge oder einen Schlüssel an.</span><span class="sxs-lookup"><span data-stu-id="01a1a-105">Most Azure service libraries require a connection string or keys for authentication.</span></span> <span data-ttu-id="01a1a-106">SQL-Datenbank verwendet beispielsweise eine standardmäßige SQL-Verbindungszeichenfolge:</span><span class="sxs-lookup"><span data-stu-id="01a1a-106">For example, SQL Database uses a standard SQL connection string:</span></span>

```csharp
var builder = new SqlConnectionStringBuilder();
builder.DataSource = "example.database.windows.net";
builder.InitialCatalog = "MyDatabase";
builder.UserID = "sampleuser@example"; // Format user ID as "user@server"
builder.Password = password;
builder.Encrypt = true;
builder.TrustServerCertificate = true;

using (var conn = new SqlConnection(builder.ConnectionString))
{
    conn.Open();
    // Do things with the connection...
    // ...
}
```

<span data-ttu-id="01a1a-107">Azure Storage verlangt einen Speicherschlüssel:</span><span class="sxs-lookup"><span data-stu-id="01a1a-107">Azure Storage uses a storage key:</span></span>

```csharp
string storageConnectionString = "DefaultEndpointsProtocol=https;"
        + "AccountName=" + storageName
        + ";AccountKey=" + storageKey
        + ";EndpointSuffix=core.windows.net";

var account = CloudStorageAccount.Parse(storageConnectionString);
// Do things with the account here...
```

<span data-ttu-id="01a1a-108">Dienstverbindungszeichenfolgen werden in anderen Azure-Diensten wie [Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/), [Azure Cache for Redis](https://docs.microsoft.com/azure/azure-cache-for-redis/cache-dotnet-how-to-use-azure-redis-cache) und [Service Bus](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-get-started-with-queues) verwendet.</span><span class="sxs-lookup"><span data-stu-id="01a1a-108">Service connection strings are used in other Azure services like [CosmosDB](https://docs.microsoft.com/azure/cosmos-db/), [Azure Cache for Redis](https://docs.microsoft.com/azure/azure-cache-for-redis/cache-dotnet-how-to-use-azure-redis-cache), and [Service Bus](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-get-started-with-queues).</span></span> <span data-ttu-id="01a1a-109">Diese Zeichenfolgen können Sie über das Azure-Portal, mit der CLI oder mit PowerShell abrufen.</span><span class="sxs-lookup"><span data-stu-id="01a1a-109">You can get those strings using the Azure portal, CLI, or PowerShell.</span></span> <span data-ttu-id="01a1a-110">Sie können auch die Azure-Verwaltungsbibliotheken für .NET zum Abfragen von Ressourcen verwenden, um Verbindungszeichenfolgen in Ihrem Code zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="01a1a-110">You can also use the Azure management libraries for .NET to query resources to build connection strings in your code.</span></span>

<span data-ttu-id="01a1a-111">Dieser Codeausschnitt verwendet beispielsweise die Verwaltungsbibliotheken, um eine Verbindungszeichenfolge für ein Speicherkonto zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="01a1a-111">This snippet uses the management libraries to create a storage account connection string:</span></span>

```csharp
// Get a storage account
var storage = azure.StorageAccounts.GetByResourceGroup("myResourceGroup", "myStorageAccount");

// Extract the keys
var storageKeys = storage.GetKeys();

// Build the connection string
string storageConnectionString = "DefaultEndpointsProtocol=https;"
        + "AccountName=" + storage.Name
        + ";AccountKey=" + storageKeys[0].Value
        + ";EndpointSuffix=core.windows.net";

// Connect
var account = CloudStorageAccount.Parse(storageConnectionString);

// Do things with the account here...
```

<span data-ttu-id="01a1a-112">Bei anderen Bibliotheken muss Ihre Anwendung mit einem [Dienstprinzipal](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) ausgeführt werden, der die Ausführung der Anwendung mit erteilten Anmeldeinformationen autorisiert.</span><span class="sxs-lookup"><span data-stu-id="01a1a-112">Other libraries require your application to run with a [service principal](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) authorizing the application to run with granted credentials.</span></span> <span data-ttu-id="01a1a-113">Diese Konfiguration ist vergleichbar mit den objektbasierten Authentifizierungsschritten für die unten aufgeführte Verwaltungsbibliothek.</span><span class="sxs-lookup"><span data-stu-id="01a1a-113">This configuration is similar to the object-based authentication steps for the management library listed below.</span></span>

## <a name="azure-management-libraries-for-net-authentication"></a><a name="mgmt-auth"></a><span data-ttu-id="01a1a-114">Azure-Verwaltungsbibliotheken für die .NET-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="01a1a-114">Azure management libraries for .NET authentication</span></span>

[!include[Create service principal](../includes/create-sp.md)]

<span data-ttu-id="01a1a-115">Nachdem der Dienstprinzipal erstellt wurde, stehen zwei Optionen für die Authentifizierung beim Dienstprinzipal zur Verfügung, um Ressourcen zu erstellen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="01a1a-115">Now that the service principal is created, two options are available to authenticate to the service principal to create and manage resources.</span></span>

<span data-ttu-id="01a1a-116">Bei beiden Optionen müssen Sie dem Projekt die folgenden NuGet-Pakete hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="01a1a-116">For both options you will need to add the following NuGet packages to your project.</span></span>

```powershell
Install-Package Microsoft.Azure.Management.Fluent
Install-Package Microsoft.Azure.Management.ResourceManager.Fluent
```

### <a name="authenticate-with-token-credentials"></a><span data-ttu-id="01a1a-117">Authentifizieren mit Zugriffstoken-Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="01a1a-117">Authenticate with token credentials</span></span>

<span data-ttu-id="01a1a-118">Die erste Methode sieht das Erstellen des tokenbasierten Anmeldeinformationsobjekts im Code vor.</span><span class="sxs-lookup"><span data-stu-id="01a1a-118">The first method is to build the token credential object in code.</span></span> <span data-ttu-id="01a1a-119">Sie müssen die Anmeldeinformationen in einer Konfigurationsdatei, der Registrierung oder Azure Key Vault sicher speichern.</span><span class="sxs-lookup"><span data-stu-id="01a1a-119">You should store the credentials securely in a configuration file, the registry, or Azure KeyVault.</span></span>

```csharp
var credentials = SdkContext.AzureCredentialsFactory
    .FromServicePrincipal(clientId,
    clientSecret,
    tenantId,
    AzureEnvironment.AzureGlobalCloud);
```

<span data-ttu-id="01a1a-120">Verwenden Sie die Werte *clientId*, *clientSecret* und *tenantId* aus der JSON-Ausgabe, die Sie beim Erstellen des Dienstprinzipals erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="01a1a-120">Use the *clientId*, *clientSecret*, and *tenantId* values from the JSON output when you created the service principal.</span></span>

<span data-ttu-id="01a1a-121">Erstellen Sie dann das Einstiegspunktobjekt `Azure`, um mit der Verwendung der API zu beginnen:</span><span class="sxs-lookup"><span data-stu-id="01a1a-121">Then create the entry point `Azure` object to start working with the API:</span></span>

```csharp
var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```

### <a name="file-based-authentication"></a><a name="mgmt-file"></a><span data-ttu-id="01a1a-122">Dateibasierte Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="01a1a-122">File-based authentication</span></span>

<span data-ttu-id="01a1a-123">Die dateibasierte Authentifizierung ermöglicht Ihnen das Ablegen der Anmeldeinformationen für den Dienstprinzipal in einer einfachen Textdatei, die Sie im Dateisystem schützen.</span><span class="sxs-lookup"><span data-stu-id="01a1a-123">File-based authentication allows you to put the service principal credentials in a plain text file and secure it within the file system.</span></span>

[!include[File-based authentication](../includes/file-based-auth.md)]

<span data-ttu-id="01a1a-124">Lesen Sie den Inhalt der Datei, und erstellen Sie das Einstiegspunktobjekt `Azure`, um mit der Verwendung der API zu beginnen:</span><span class="sxs-lookup"><span data-stu-id="01a1a-124">Read the contents of the file and create the entry point `Azure` object to start working with the API:</span></span>

```csharp
// pull in the location of the authentication properties file from the environment
var credentials = SdkContext.AzureCredentialsFactory
    .FromFile(Environment.GetEnvironmentVariable("AZURE_AUTH_LOCATION"));

var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```
