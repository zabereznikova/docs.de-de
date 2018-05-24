---
title: Verwenden von Azure Key Vault zum Schutz von Geheimnissen zur Produktionszeit
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Verwenden von Azure Key Vault zum Schutz von Geheimnissen zur Produktionszeit
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 5ad5686909c29eba5916cbcc4b7115a16108a004
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="using-azure-key-vault-to-protect-secrets-at-production-time"></a><span data-ttu-id="74d87-103">Verwenden von Azure Key Vault zum Schutz von Geheimnissen zur Produktionszeit</span><span class="sxs-lookup"><span data-stu-id="74d87-103">Using Azure Key Vault to protect secrets at production time</span></span>

<span data-ttu-id="74d87-104">Geheimnisse, die als Umgebungsvariablen oder vom Secret Manager-Tool gespeichert werden, werden weiterhin lokal und unverschlüsselt auf dem Computer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="74d87-104">Secrets stored as environment variables or stored by the Secret Manager tool are still stored locally and unencrypted on the machine.</span></span> <span data-ttu-id="74d87-105">[Azure Key Vault](https://azure.microsoft.com/services/key-vault/) ist eine sicherere Option zum Speichern von Geheimnissen, die einen sicheren und zentralen Speicherort für Schlüssel und Geheimnisse bietet.</span><span class="sxs-lookup"><span data-stu-id="74d87-105">A more secure option for storing secrets is [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), which provides a secure, central location for storing keys and secrets.</span></span>

<span data-ttu-id="74d87-106">Das Paket Microsoft.Extensions.Configuration.AzureKeyVault erlaubt einer ASP.NET Core-Anwendung, die Konfigurationsinformationen von Azure Key Vault auszulesen.</span><span class="sxs-lookup"><span data-stu-id="74d87-106">The Microsoft.Extensions.Configuration.AzureKeyVault package allows an ASP.NET Core application to read configuration information from Azure Key Vault.</span></span> <span data-ttu-id="74d87-107">Führen Sie die folgenden Schritte aus, um mit der Verwendung von Geheimnissen aus Azure Key Vault zu beginnen:</span><span class="sxs-lookup"><span data-stu-id="74d87-107">To start using secrets from an Azure Key Vault, you follow these steps:</span></span>

<span data-ttu-id="74d87-108">Registrieren Sie zunächst Ihre Anwendung als eine Azure AD-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="74d87-108">First, register your application as an Azure AD application.</span></span> <span data-ttu-id="74d87-109">(Der Zugriff auf Schlüsseltresore wird von Azure AD verwaltet.) Dies kann über das Azure-Verwaltungsportal erfolgen.</span><span class="sxs-lookup"><span data-stu-id="74d87-109">(Access to key vaults is managed by Azure AD.) This can be done through the Azure management portal.</span></span>

<span data-ttu-id="74d87-110">Wenn Sie hingegen möchten, dass Ihre Anwendung nicht mit einem Kennwort oder einem Clientgeheimnis authentifiziert wird, sondern mit einem Zertifikat, können Sie das PowerShell-Cmdlet [New-AzureRmADApplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication) verwenden.</span><span class="sxs-lookup"><span data-stu-id="74d87-110">Alternatively, if you want your application to authenticate using a certificate instead of a password or client secret, you can use the [New-AzureRmADApplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication) PowerShell cmdlet.</span></span> <span data-ttu-id="74d87-111">Das Zertifikat, das Sie mit Azure Key Vault registrieren, benötigt nur Ihren öffentlichen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="74d87-111">The certificate that you register with Azure Key Vault needs only your public key.</span></span> <span data-ttu-id="74d87-112">(Ihre Anwendung verwendet den privaten Schlüssel.)</span><span class="sxs-lookup"><span data-stu-id="74d87-112">(Your application will use the private key.)</span></span>

<span data-ttu-id="74d87-113">Gewähren Sie zudem der registrierten Anwendung Zugriff auf den Schlüsseltresor, indem Sie einen neuen Dienstprinzipal erstellen.</span><span class="sxs-lookup"><span data-stu-id="74d87-113">Second, give the registered application access to the key vault by creating a new service principal.</span></span> <span data-ttu-id="74d87-114">Verwenden Sie hierzu die folgenden PowerShell-Befehle:</span><span class="sxs-lookup"><span data-stu-id="74d87-114">You can do this using the following PowerShell commands:</span></span>

```powershell
$sp = New-AzureRmADServicePrincipal -ApplicationId "<Application ID guid>"
Set-AzureRmKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
```

<span data-ttu-id="74d87-115">Schließen Sie dann den Schlüsseltresor als Konfigurationsquelle in Ihre Anwendung ein, indem Sie die Erweiterungsmethode „IConfigurationBuilder.AddAzureKeyVault“ aufrufen, wenn Sie eine IConfigurationRoot-Instanz erstellen.</span><span class="sxs-lookup"><span data-stu-id="74d87-115">Third, include the key vault as a configuration source in your application by calling the IConfigurationBuilder.AddAzureKeyVault extension method when you create an IConfigurationRoot instance.</span></span> <span data-ttu-id="74d87-116">Beachten Sie, dass das Aufrufen von „AddAzureKeyVault“ die Anwendungs-ID benötigt, die in den vorherigen Schritten registriert wurde und den Zugriff auf den Schlüsseltresor erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="74d87-116">Note that calling AddAzureKeyVault will require the application ID that was registered and given access to the key vault in the previous steps.</span></span>

  <span data-ttu-id="74d87-117">Derzeit unterstützen .NET Standard und .NET Core das Abrufen der Konfigurationsinformationen aus Azure Key Vault mithilfe einer Client-ID und dem geheimen Clientschlüssel.</span><span class="sxs-lookup"><span data-stu-id="74d87-117">Currently, .NET Standard and .NET Core support getting configuration information from an Azure Key Vault using a client ID and client secret.</span></span> <span data-ttu-id="74d87-118">.NET Framework-Anwendungen können eine Überladung von „IConfigurationBuilder.AddAzureKeyVault“ verwenden, die ein Zertifikat anstelle des geheimen Clientschlüssels verwendet.</span><span class="sxs-lookup"><span data-stu-id="74d87-118">.NET Framework applications can use an overload of IConfigurationBuilder.AddAzureKeyVault that takes a certificate in place of the client secret.</span></span> <span data-ttu-id="74d87-119">Während dieses Dokument verfasst wird, [wird daran gearbeitet](https://github.com/aspnet/Configuration/issues/605), diese Überladung für .NET Standard und .NET Core verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="74d87-119">As of this writing, work is [in progress](https://github.com/aspnet/Configuration/issues/605) to make that overload available in .NET Standard and .NET Core.</span></span> <span data-ttu-id="74d87-120">Bis die AddAzureKeyVault-Überladung verfügbar ist, die ein Zertifikat akzeptiert, können ASP.NET Core-Anwendungen auf Azure Key Vault mit zertifikatbasierter Authentifizierung zugreifen, indem wie in folgendem Beispiel gezeigt wird ein KeyVaultClient-Objekt explizit erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="74d87-120">Until the AddAzureKeyVault overload that accepts a certificate is available, ASP.NET Core applications can access an Azure Key Vault with certificate-based authentication by explicitly creating a KeyVaultClient object, as shown in the following example:</span></span>

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

<span data-ttu-id="74d87-121">In diesem Beispiel erfolgt der Aufruf von „AddAzureKeyVault“ am Ende der Registrierung des Konfigurationsanbieters.</span><span class="sxs-lookup"><span data-stu-id="74d87-121">In this example, the call to AddAzureKeyVault comes at the end of configuration provider registration.</span></span> <span data-ttu-id="74d87-122">Es ist eine bewährte Methode, Azure Key Vault als letzten Konfigurationsanbieter zu registrieren, damit eine Gelegenheit zum Überschreiben von Konfigurationswerten der vorherigen Anbieter besteht und keine Konfigurationswerte von anderen Quellen die des Schlüsseltresors überschreiben.</span><span class="sxs-lookup"><span data-stu-id="74d87-122">It is a best practice to register Azure Key Vault as the last configuration provider so that it has an opportunity to override configuration values from previous providers, and so that no configuration values from other sources override those from the key vault.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="74d87-123">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="74d87-123">Additional resources</span></span>

-   <span data-ttu-id="74d87-124">**Using Azure Key Vault to protect application secrets (Verwenden von Azure Key Vault zum Schutz von Anwendungsgeheimnissen)**
    [*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)</span><span class="sxs-lookup"><span data-stu-id="74d87-124">**Using Azure Key Vault to protect application secrets**
[*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)</span></span>

-   <span data-ttu-id="74d87-125">**Safe storage of app secrets during development (Sicheres Speichern geheimer App-Schlüssel während der Entwicklung)**
    [*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)</span><span class="sxs-lookup"><span data-stu-id="74d87-125">**Safe storage of app secrets during development**
[*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)</span></span>

-   <span data-ttu-id="74d87-126">**Configuring data protection (Konfigurieren des Schutzes von Daten)**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)</span><span class="sxs-lookup"><span data-stu-id="74d87-126">**Configuring data protection**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)</span></span>

-   <span data-ttu-id="74d87-127">**Key management and lifetime (Schlüsselverwaltung und Lebensdauer)**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#data-protection-default-settings*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)</span><span class="sxs-lookup"><span data-stu-id="74d87-127">**Key management and lifetime**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#data-protection-default-settings*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)</span></span>

-   <span data-ttu-id="74d87-128">**Microsoft.Extensions.Configuration.DockerSecrets.**</span><span class="sxs-lookup"><span data-stu-id="74d87-128">**Microsoft.Extensions.Configuration.DockerSecrets.**</span></span> <span data-ttu-id="74d87-129">GitHub repo (Scrutor. GitHub-Reporitory).</span><span class="sxs-lookup"><span data-stu-id="74d87-129">GitHub repo.</span></span>
    [*https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets*](https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets)

>[!div class="step-by-step"]
<span data-ttu-id="74d87-130">[Zurück](developer-app-secrets-storage.md) [Weiter] (../key-takeaways.md)</span><span class="sxs-lookup"><span data-stu-id="74d87-130">[Previous] (developer-app-secrets-storage.md) [Next] (../key-takeaways.md)</span></span>
