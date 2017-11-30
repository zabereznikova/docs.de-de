---
title: "Verwendung von Azure Key Vault zum Schützen von geheimen Schlüsseln zum Zeitpunkt der Produktion"
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Verwendung von Azure Key Vault zum Schützen von geheimen Schlüsseln zum Zeitpunkt der Produktion"
keywords: Docker, Microservices, ASP.NET, Container
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 7f922997e8d0c63e206cd68f4efda14985c86b72
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="using-azure-key-vault-to-protect-secrets-at-production-time"></a><span data-ttu-id="34dbb-104">Verwendung von Azure Key Vault zum Schützen von geheimen Schlüsseln zum Zeitpunkt der Produktion</span><span class="sxs-lookup"><span data-stu-id="34dbb-104">Using Azure Key Vault to protect secrets at production time</span></span>

<span data-ttu-id="34dbb-105">Geheime Schlüssel als Umgebungsvariablen gespeichert oder vom Tool geheimen Manager sind weiterhin lokal gespeichert und unverschlüsselt auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="34dbb-105">Secrets stored as environment variables or stored by the Secret Manager tool are still stored locally and unencrypted on the machine.</span></span> <span data-ttu-id="34dbb-106">Ist eine sicherere Option zum Speichern von geheimen Schlüsseln [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), stellt einen sicheren, zentralen Speicherort zum Speichern von Schlüsseln und geheimen Schlüsseln.</span><span class="sxs-lookup"><span data-stu-id="34dbb-106">A more secure option for storing secrets is [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), which provides a secure, central location for storing keys and secrets.</span></span>

<span data-ttu-id="34dbb-107">Das Paket Microsoft.Extensions.Configuration.AzureKeyVault kann es sich um eine ASP.NET Core-Anwendung zum Lesen von Konfigurationsinformationen aus Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="34dbb-107">The Microsoft.Extensions.Configuration.AzureKeyVault package allows an ASP.NET Core application to read configuration information from Azure Key Vault.</span></span> <span data-ttu-id="34dbb-108">Um mithilfe von geheimen Daten aus einem Azure-Schlüsseltresor zu starten, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="34dbb-108">To start using secrets from an Azure Key Vault, you follow these steps:</span></span>

<span data-ttu-id="34dbb-109">Registrieren Sie zuerst die Anwendung als eine Azure AD-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="34dbb-109">First, register your application as an Azure AD application.</span></span> <span data-ttu-id="34dbb-110">(Zugriff auf wichtige Tresore wird von Azure Active Directory verwaltet.) Dies kann über das Azure-Verwaltungsportal erfolgen.</span><span class="sxs-lookup"><span data-stu-id="34dbb-110">(Access to key vaults is managed by Azure AD.) This can be done through the Azure management portal.</span></span>

<span data-ttu-id="34dbb-111">Auch wenn Sie Ihre Anwendung zur Authentifizierung ein Zertifikat und ein Kennwort oder Client-Geheimnis verwenden möchten, können Sie die [neu AzureRmADApplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication) PowerShell-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="34dbb-111">Alternatively, if you want your application to authenticate using a certificate instead of a password or client secret, you can use the [New-AzureRmADApplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication) PowerShell cmdlet.</span></span> <span data-ttu-id="34dbb-112">Das Zertifikat, das Sie mit Azure Key Vault registrieren benötigt nur mit Ihrem öffentlichen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="34dbb-112">The certificate that you register with Azure Key Vault needs only your public key.</span></span> <span data-ttu-id="34dbb-113">(Die Anwendung wird den privaten Schlüssel verwenden.)</span><span class="sxs-lookup"><span data-stu-id="34dbb-113">(Your application will use the private key.)</span></span>

<span data-ttu-id="34dbb-114">Zweitens gewähren Sie dem registrierten Anwendung-Zugriff auf den schlüsseltresor, indem Sie einen neuen Dienstprinzipal zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="34dbb-114">Second, give the registered application access to the key vault by creating a new service principal.</span></span> <span data-ttu-id="34dbb-115">Hierzu können Sie mit den folgenden PowerShell-Befehlen:</span><span class="sxs-lookup"><span data-stu-id="34dbb-115">You can do this using the following PowerShell commands:</span></span>

```powershell
$sp = New-AzureRmADServicePrincipal -ApplicationId "<Application ID guid>"
Set-AzureRmKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
```

<span data-ttu-id="34dbb-116">Schließen Sie im dritten schlüsseltresor als eine Konfigurationsquelle in Ihrer Anwendung, durch Aufrufen der Erweiterungsmethode IConfigurationBuilder.AddAzureKeyVault, bei der Erstellung einer IConfigurationRoot-Instanz.</span><span class="sxs-lookup"><span data-stu-id="34dbb-116">Third, include the key vault as a configuration source in your application by calling the IConfigurationBuilder.AddAzureKeyVault extension method when you create an IConfigurationRoot instance.</span></span> <span data-ttu-id="34dbb-117">Beachten Sie, dass bei AddAzureKeyVault Aufrufen die Anwendungs-ID, die registriert und den Zugriff auf den schlüsseltresor in den vorherigen Schritten angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="34dbb-117">Note that calling AddAzureKeyVault will require the application ID that was registered and given access to the key vault in the previous steps.</span></span>

  <span data-ttu-id="34dbb-118">Derzeit unterstützen .NET Standard und .NET Core beim Abrufen von Konfigurationsinformationen aus Azure Key Vault mithilfe einer Client-ID und den geheimen Clientschlüssel.</span><span class="sxs-lookup"><span data-stu-id="34dbb-118">Currently, .NET Standard and .NET Core support getting configuration information from an Azure Key Vault using a client ID and client secret.</span></span> <span data-ttu-id="34dbb-119">.NET Framework-Anwendungen können eine Überladung der IConfigurationBuilder.AddAzureKeyVault verwenden, die ein Zertifikat anstelle der geheime Clientschlüssel akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="34dbb-119">.NET Framework applications can use an overload of IConfigurationBuilder.AddAzureKeyVault that takes a certificate in place of the client secret.</span></span> <span data-ttu-id="34dbb-120">Verfassung dieses Dokuments arbeiten ist [läuft](https://github.com/aspnet/Configuration/issues/605) auf diese Überladung in standardmäßigen .NET und .NET Core verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="34dbb-120">As of this writing, work is [in progress](https://github.com/aspnet/Configuration/issues/605) to make that overload available in .NET Standard and .NET Core.</span></span> <span data-ttu-id="34dbb-121">Bis die AddAzureKeyVault-Überladung, die akzeptiert, dass ein Zertifikat verfügbar ist, können ASP.NET Core Anwendungen Azure Key Vault mit Clientzertifikaten basierende Authentifizierung zugreifen explizit Erstellen eines KeyVaultClient-Objekts, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="34dbb-121">Until the AddAzureKeyVault overload that accepts a certificate is available, ASP.NET Core applications can access an Azure Key Vault with certificate-based authentication by explicitly creating a KeyVaultClient object, as shown in the following example:</span></span>

```csharp
// Configure Key Vault client
var kvClient = new KeyVaultClient(new KeyVaultClient.AuthenticationCallback(async
    (authority, resource, scope) =>
    {
        var cert = // Get certificate from local store/file/key vault etc. as needed
        // From the Microsoft.IdentityModel.Clients.ActiveDirectory pacakge
        var authContext = new AuthenticationContext(authority,
            TokenCache.DefaultShared);
        var result = await authContext.AcquireTokenAsync(resource,
            // From the Microsoft.Rest.ClientRuntime.Azure.Authentication pacakge
            new ClientAssertionCertificate("{Application ID}", cert));
        return result.AccessToken;
    }));

    // Get configuration values from Key Vault
    var builder = new ConfigurationBuilder()
        .SetBasePath(env.ContentRootPath)
        // Other configuration providers go here.
        .AddAzureKeyVault("{KeyValueUri}", kvClient,
        new DefaultKeyVaultSecretManager());
```

<span data-ttu-id="34dbb-122">In diesem Beispiel stammen der Aufruf von AddAzureKeyVault am Ende der konfigurationsanbieterregistrierung.</span><span class="sxs-lookup"><span data-stu-id="34dbb-122">In this example, the call to AddAzureKeyVault comes at the end of configuration provider registration.</span></span> <span data-ttu-id="34dbb-123">Es ist eine bewährte Methode Azure Key Vault als der letzte Konfigurationsanbieter registrieren, damit er eine Gelegenheit Konfigurationswerte aus vorherigen Anbieter überschrieben hat, und keine Konfigurationswerte aus anderen Quellen, die aus dem schlüsseltresor überschreiben.</span><span class="sxs-lookup"><span data-stu-id="34dbb-123">It is a best practice to register Azure Key Vault as the last configuration provider so that it has an opportunity to override configuration values from previous providers, and so that no configuration values from other sources override those from the key vault.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="34dbb-124">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="34dbb-124">Additional resources</span></span>

-   <span data-ttu-id="34dbb-125">**Mit Azure Key Vault Anwendung geheime Schlüssel schützen**
    [*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)</span><span class="sxs-lookup"><span data-stu-id="34dbb-125">**Using Azure Key Vault to protect application secrets**
[*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)</span></span>

-   <span data-ttu-id="34dbb-126">**Sichere Speicherung von app-Kennwörter während der Entwicklung**
    [*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)</span><span class="sxs-lookup"><span data-stu-id="34dbb-126">**Safe storage of app secrets during development**
[*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)</span></span>

-   <span data-ttu-id="34dbb-127">**Konfigurieren von Data Protection**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)</span><span class="sxs-lookup"><span data-stu-id="34dbb-127">**Configuring data protection**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)</span></span>

-   <span data-ttu-id="34dbb-128">**Wichtige Management und Lebensdauer**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#Data-Schutz-Standardeinstellungen*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)</span><span class="sxs-lookup"><span data-stu-id="34dbb-128">**Key management and lifetime**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#data-protection-default-settings*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)</span></span>

-   <span data-ttu-id="34dbb-129">**Microsoft.Extensions.Configuration.DockerSecrets.**</span><span class="sxs-lookup"><span data-stu-id="34dbb-129">**Microsoft.Extensions.Configuration.DockerSecrets.**</span></span> <span data-ttu-id="34dbb-130">GitHub-Repository.</span><span class="sxs-lookup"><span data-stu-id="34dbb-130">GitHub repo.</span></span>
    [<span data-ttu-id="34dbb-131">*https://github.com/ASPNET/Configuration/Tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets*</span><span class="sxs-lookup"><span data-stu-id="34dbb-131">*https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets*</span></span>](https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets)

>[!div class="step-by-step"]
<span data-ttu-id="34dbb-132">[Vorherigen] (Developer-app-Kennwörter-storage.md) [weiter] (.. / Schlüssel-takeaways.md)</span><span class="sxs-lookup"><span data-stu-id="34dbb-132">[Previous] (developer-app-secrets-storage.md) [Next] (../key-takeaways.md)</span></span>
