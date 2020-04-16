---
title: Authentifizieren bei den Azure-Bibliotheken für .NET
description: Authentifizieren bei den Azure-Bibliotheken für .NET
ms.date: 08/22/2018
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: e562b60da0a2d34f716e80d3d5d0d0b5e55b0cdb
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2020
ms.locfileid: "81433145"
---
# <a name="authenticate-with-the-azure-libraries-for-net"></a><span data-ttu-id="1c7ef-103">Authentifizieren bei den Azure-Bibliotheken für .NET</span><span class="sxs-lookup"><span data-stu-id="1c7ef-103">Authenticate with the Azure Libraries for .NET</span></span>

## <a name="connect-to-services-with-connection-strings"></a><span data-ttu-id="1c7ef-104">Herstellen einer Verbindung mit Diensten mit Verbindungszeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="1c7ef-104">Connect to services with connection strings</span></span>

<span data-ttu-id="1c7ef-105">Die meisten Azure-Dienstbibliotheken fordern für die Authentifizierung eine Verbindungszeichenfolge oder einen Schlüssel an.</span><span class="sxs-lookup"><span data-stu-id="1c7ef-105">Most Azure service libraries require a connection string or keys for authentication.</span></span> <span data-ttu-id="1c7ef-106">SQL-Datenbank verwendet beispielsweise eine standardmäßige SQL-Verbindungszeichenfolge:</span><span class="sxs-lookup"><span data-stu-id="1c7ef-106">For example, SQL Database uses a standard SQL connection string:</span></span>

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

<span data-ttu-id="1c7ef-107">Azure Storage verlangt einen Speicherschlüssel:</span><span class="sxs-lookup"><span data-stu-id="1c7ef-107">Azure Storage uses a storage key:</span></span>

```csharp
string storageConnectionString = "DefaultEndpointsProtocol=https;"
        + "AccountName=" + storageName
        + ";AccountKey=" + storageKey
        + ";EndpointSuffix=core.windows.net";

var account = CloudStorageAccount.Parse(storageConnectionString);
// Do things with the account here...
```

<span data-ttu-id="1c7ef-108">Dienstverbindungszeichenfolgen werden in anderen Azure-Diensten wie [CosmosDB](/azure/documentdb/documentdb-dotnet-application#a-nametoc395637769astep-5-wiring-up-azure-cosmos-db), [Azure Cache für Redis](/azure/azure-cache-for-redis/cache-dotnet-how-to-use-azure-redis-cache)und [Service Bus](/azure/service-bus-messaging/service-bus-dotnet-get-started-with-queues) verwendet, und Sie können diese Zeichenfolgen über das Azure-Portal, die CLI oder PowerShell abrufen.</span><span class="sxs-lookup"><span data-stu-id="1c7ef-108">Service connection strings are used in other Azure services like [CosmosDB](/azure/documentdb/documentdb-dotnet-application#a-nametoc395637769astep-5-wiring-up-azure-cosmos-db), [Azure Cache for Redis](/azure/azure-cache-for-redis/cache-dotnet-how-to-use-azure-redis-cache), and [Service Bus](/azure/service-bus-messaging/service-bus-dotnet-get-started-with-queues) and you can get those strings using the Azure portal, CLI, or PowerShell.</span></span> <span data-ttu-id="1c7ef-109">Sie können auch die Azure-Verwaltungsbibliotheken für .NET zum Abfragen von Ressourcen verwenden, um Verbindungszeichenfolgen in Ihrem Code zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1c7ef-109">You can also use the Azure management libraries for .NET to query resources to build connection strings in your code.</span></span>

<span data-ttu-id="1c7ef-110">Dieser Codeausschnitt verwendet beispielsweise die Verwaltungsbibliotheken, um eine Verbindungszeichenfolge für ein Speicherkonto zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="1c7ef-110">This snippet uses the management libraries to create a storage account connection string:</span></span>

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

<span data-ttu-id="1c7ef-111">Bei anderen Bibliotheken muss Ihre Anwendung mit einem [Dienstprinzipal](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) ausgeführt werden, der die Ausführung der Anwendung mit erteilten Anmeldeinformationen autorisiert.</span><span class="sxs-lookup"><span data-stu-id="1c7ef-111">Other libraries require your application to run with a [service principal](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) authorizing the application to run with granted credentials.</span></span> <span data-ttu-id="1c7ef-112">Diese Konfiguration ist vergleichbar mit den objektbasierten Authentifizierungsschritten für die unten aufgeführte Verwaltungsbibliothek.</span><span class="sxs-lookup"><span data-stu-id="1c7ef-112">This configuration is similar to the object-based authentication steps for the management library listed below.</span></span>

## <a name="azure-management-libraries-for-net-authentication"></a><a name="mgmt-auth"></a><span data-ttu-id="1c7ef-113">Azure-Verwaltungsbibliotheken für die .NET-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="1c7ef-113">Azure management libraries for .NET authentication</span></span>

[!include[Create service principal](../includes/create-sp.md)]

<span data-ttu-id="1c7ef-114">Nachdem der Dienstprinzipal erstellt wurde, stehen zwei Optionen für die Authentifizierung beim Dienstprinzipal zur Verfügung, um Ressourcen zu erstellen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="1c7ef-114">Now that the service principal is created, two options are available to authenticate to the service principal to create and manage resources.</span></span>

<span data-ttu-id="1c7ef-115">Für beide Optionen müssen Sie ihrem Projekt die folgenden NuGet-Pakete hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1c7ef-115">For both options you will need to add the following NuGet packages to your project.</span></span>

```powershell
Install-Package Microsoft.Azure.Management.Fluent
Install-Package Microsoft.Azure.Management.ResourceManager.Fluent
```

### <a name="authenticate-with-token-credentials"></a><span data-ttu-id="1c7ef-116">Authentifizieren mit Zugriffstoken-Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="1c7ef-116">Authenticate with token credentials</span></span>

<span data-ttu-id="1c7ef-117">Die erste Methode sieht das Erstellen des tokenbasierten Anmeldeinformationsobjekts im Code vor.</span><span class="sxs-lookup"><span data-stu-id="1c7ef-117">The first method is to build the token credential object in code.</span></span> <span data-ttu-id="1c7ef-118">Sie müssen die Anmeldeinformationen in einer Konfigurationsdatei, der Registrierung oder Azure Key Vault sicher speichern.</span><span class="sxs-lookup"><span data-stu-id="1c7ef-118">You should store the credentials securely in a configuration file, the registry, or Azure KeyVault.</span></span>

```csharp
var credentials = SdkContext.AzureCredentialsFactory
    .FromServicePrincipal(clientId,
    clientSecret,
    tenantId,
    AzureEnvironment.AzureGlobalCloud);
```

<span data-ttu-id="1c7ef-119">Verwenden Sie die Werte *clientId*, *clientSecret* und *tenantId* aus der JSON-Ausgabe, die Sie beim Erstellen des Dienstprinzipals erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="1c7ef-119">Use the *clientId*, *clientSecret*, and *tenantId* values from the JSON output when you created the service principal.</span></span>

<span data-ttu-id="1c7ef-120">Erstellen Sie dann das Einstiegspunktobjekt `Azure`, um mit der Verwendung der API zu beginnen:</span><span class="sxs-lookup"><span data-stu-id="1c7ef-120">Then create the entry point `Azure` object to start working with the API:</span></span>

```csharp
var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```

### <a name="file-based-authentication"></a><a name="mgmt-file"></a><span data-ttu-id="1c7ef-121">Dateibasierte Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="1c7ef-121">File-based authentication</span></span>

<span data-ttu-id="1c7ef-122">Die dateibasierte Authentifizierung ermöglicht Ihnen das Ablegen der Anmeldeinformationen für den Dienstprinzipal in einer einfachen Textdatei, die Sie im Dateisystem schützen.</span><span class="sxs-lookup"><span data-stu-id="1c7ef-122">File-based authentication allows you to put the service principal credentials in a plain text file and secure it within the file system.</span></span>

[!include[File-based authentication](../includes/file-based-auth.md)]

<span data-ttu-id="1c7ef-123">Lesen Sie den Inhalt der Datei, und erstellen Sie das Einstiegspunktobjekt `Azure`, um mit der Verwendung der API zu beginnen:</span><span class="sxs-lookup"><span data-stu-id="1c7ef-123">Read the contents of the file and create the entry point `Azure` object to start working with the API:</span></span>

```csharp
// pull in the location of the authentication properties file from the environment
var credentials = SdkContext.AzureCredentialsFactory
    .FromFile(Environment.GetEnvironmentVariable("AZURE_AUTH_LOCATION"));

var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```
