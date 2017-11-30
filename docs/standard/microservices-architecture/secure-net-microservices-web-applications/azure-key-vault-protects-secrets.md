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
# <a name="using-azure-key-vault-to-protect-secrets-at-production-time"></a>Verwendung von Azure Key Vault zum Schützen von geheimen Schlüsseln zum Zeitpunkt der Produktion

Geheime Schlüssel als Umgebungsvariablen gespeichert oder vom Tool geheimen Manager sind weiterhin lokal gespeichert und unverschlüsselt auf dem Computer. Ist eine sicherere Option zum Speichern von geheimen Schlüsseln [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), stellt einen sicheren, zentralen Speicherort zum Speichern von Schlüsseln und geheimen Schlüsseln.

Das Paket Microsoft.Extensions.Configuration.AzureKeyVault kann es sich um eine ASP.NET Core-Anwendung zum Lesen von Konfigurationsinformationen aus Azure Key Vault. Um mithilfe von geheimen Daten aus einem Azure-Schlüsseltresor zu starten, gehen Sie folgendermaßen vor:

Registrieren Sie zuerst die Anwendung als eine Azure AD-Anwendung. (Zugriff auf wichtige Tresore wird von Azure Active Directory verwaltet.) Dies kann über das Azure-Verwaltungsportal erfolgen.

Auch wenn Sie Ihre Anwendung zur Authentifizierung ein Zertifikat und ein Kennwort oder Client-Geheimnis verwenden möchten, können Sie die [neu AzureRmADApplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication) PowerShell-Cmdlet. Das Zertifikat, das Sie mit Azure Key Vault registrieren benötigt nur mit Ihrem öffentlichen Schlüssel. (Die Anwendung wird den privaten Schlüssel verwenden.)

Zweitens gewähren Sie dem registrierten Anwendung-Zugriff auf den schlüsseltresor, indem Sie einen neuen Dienstprinzipal zu erstellen. Hierzu können Sie mit den folgenden PowerShell-Befehlen:

```powershell
$sp = New-AzureRmADServicePrincipal -ApplicationId "<Application ID guid>"
Set-AzureRmKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
```

Schließen Sie im dritten schlüsseltresor als eine Konfigurationsquelle in Ihrer Anwendung, durch Aufrufen der Erweiterungsmethode IConfigurationBuilder.AddAzureKeyVault, bei der Erstellung einer IConfigurationRoot-Instanz. Beachten Sie, dass bei AddAzureKeyVault Aufrufen die Anwendungs-ID, die registriert und den Zugriff auf den schlüsseltresor in den vorherigen Schritten angegeben wurde.

  Derzeit unterstützen .NET Standard und .NET Core beim Abrufen von Konfigurationsinformationen aus Azure Key Vault mithilfe einer Client-ID und den geheimen Clientschlüssel. .NET Framework-Anwendungen können eine Überladung der IConfigurationBuilder.AddAzureKeyVault verwenden, die ein Zertifikat anstelle der geheime Clientschlüssel akzeptiert. Verfassung dieses Dokuments arbeiten ist [läuft](https://github.com/aspnet/Configuration/issues/605) auf diese Überladung in standardmäßigen .NET und .NET Core verfügbar zu machen. Bis die AddAzureKeyVault-Überladung, die akzeptiert, dass ein Zertifikat verfügbar ist, können ASP.NET Core Anwendungen Azure Key Vault mit Clientzertifikaten basierende Authentifizierung zugreifen explizit Erstellen eines KeyVaultClient-Objekts, wie im folgenden Beispiel gezeigt:

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

In diesem Beispiel stammen der Aufruf von AddAzureKeyVault am Ende der konfigurationsanbieterregistrierung. Es ist eine bewährte Methode Azure Key Vault als der letzte Konfigurationsanbieter registrieren, damit er eine Gelegenheit Konfigurationswerte aus vorherigen Anbieter überschrieben hat, und keine Konfigurationswerte aus anderen Quellen, die aus dem schlüsseltresor überschreiben.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Mit Azure Key Vault Anwendung geheime Schlüssel schützen**
    [*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)

-   **Sichere Speicherung von app-Kennwörter während der Entwicklung**
    [*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)

-   **Konfigurieren von Data Protection**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)

-   **Wichtige Management und Lebensdauer**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#Data-Schutz-Standardeinstellungen*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)

-   **Microsoft.Extensions.Configuration.DockerSecrets.** GitHub-Repository.
    [*https://github.com/ASPNET/Configuration/Tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets*](https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets)

>[!div class="step-by-step"]
[Vorherigen] (Developer-app-Kennwörter-storage.md) [weiter] (.. / Schlüssel-takeaways.md)
