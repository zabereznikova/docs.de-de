---
title: Verwenden von Azure Key Vault zum Schutz von Geheimnissen zur Produktionszeit
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Verwenden von Azure Key Vault zum Schutz von Geheimnissen zur Produktionszeit
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 84e016e4620b73444f800b02076489012ea5e844
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2018
ms.locfileid: "43001439"
---
# <a name="using-azure-key-vault-to-protect-secrets-at-production-time"></a>Verwenden von Azure Key Vault zum Schutz von Geheimnissen zur Produktionszeit

Geheimnisse, die als Umgebungsvariablen oder vom Secret Manager-Tool gespeichert werden, werden weiterhin lokal und unverschlüsselt auf dem Computer gespeichert. [Azure Key Vault](https://azure.microsoft.com/services/key-vault/) ist eine sicherere Option zum Speichern von Geheimnissen, die einen sicheren und zentralen Speicherort für Schlüssel und Geheimnisse bietet.

Das Paket Microsoft.Extensions.Configuration.AzureKeyVault erlaubt einer ASP.NET Core-Anwendung, die Konfigurationsinformationen von Azure Key Vault auszulesen. Führen Sie die folgenden Schritte aus, um mit der Verwendung von Geheimnissen aus Azure Key Vault zu beginnen:

Registrieren Sie zunächst Ihre Anwendung als eine Azure AD-Anwendung. (Der Zugriff auf Schlüsseltresore wird von Azure AD verwaltet.) Dies kann über das Azure-Verwaltungsportal erfolgen.

Wenn Sie hingegen möchten, dass Ihre Anwendung nicht mit einem Kennwort oder einem Clientgeheimnis authentifiziert wird, sondern mit einem Zertifikat, können Sie das PowerShell-Cmdlet [New-AzureRmADApplication](https://docs.microsoft.com/powershell/module/azurerm.resources/new-azurermadapplication) verwenden. Das Zertifikat, das Sie mit Azure Key Vault registrieren, benötigt nur Ihren öffentlichen Schlüssel. (Ihre Anwendung verwendet den privaten Schlüssel.)

Gewähren Sie zudem der registrierten Anwendung Zugriff auf den Schlüsseltresor, indem Sie einen neuen Dienstprinzipal erstellen. Verwenden Sie hierzu die folgenden PowerShell-Befehle:

```powershell
$sp = New-AzureRmADServicePrincipal -ApplicationId "<Application ID guid>"
Set-AzureRmKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
```

Schließen Sie dann den Schlüsseltresor als Konfigurationsquelle in Ihre Anwendung ein, indem Sie die Erweiterungsmethode „IConfigurationBuilder.AddAzureKeyVault“ aufrufen, wenn Sie eine IConfigurationRoot-Instanz erstellen. Beachten Sie, dass das Aufrufen von „AddAzureKeyVault“ die Anwendungs-ID benötigt, die in den vorherigen Schritten registriert wurde und den Zugriff auf den Schlüsseltresor erhalten hat.

  Derzeit unterstützen .NET Standard und .NET Core das Abrufen der Konfigurationsinformationen aus Azure Key Vault mithilfe einer Client-ID und dem geheimen Clientschlüssel. .NET Framework-Anwendungen können eine Überladung von „IConfigurationBuilder.AddAzureKeyVault“ verwenden, die ein Zertifikat anstelle des geheimen Clientschlüssels verwendet. Während dieses Dokument verfasst wird, [wird daran gearbeitet](https://github.com/aspnet/Configuration/issues/605), diese Überladung für .NET Standard und .NET Core verfügbar zu machen. Bis die AddAzureKeyVault-Überladung verfügbar ist, die ein Zertifikat akzeptiert, können ASP.NET Core-Anwendungen auf Azure Key Vault mit zertifikatbasierter Authentifizierung zugreifen, indem wie in folgendem Beispiel gezeigt wird ein KeyVaultClient-Objekt explizit erstellt wird:

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

In diesem Beispiel erfolgt der Aufruf von „AddAzureKeyVault“ am Ende der Registrierung des Konfigurationsanbieters. Es ist eine bewährte Methode, Azure Key Vault als letzten Konfigurationsanbieter zu registrieren, damit eine Gelegenheit zum Überschreiben von Konfigurationswerten der vorherigen Anbieter besteht und keine Konfigurationswerte von anderen Quellen die des Schlüsseltresors überschreiben.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Using Azure Key Vault to protect application secrets (Verwenden von Azure Key Vault zum Schutz von Anwendungsgeheimnissen)**
    [*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)

-   **Safe storage of app secrets during development (Sicheres Speichern geheimer App-Schlüssel während der Entwicklung)**
    [*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)

-   **Configuring data protection (Konfigurieren des Schutzes von Daten)**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)

-   **Key management and lifetime (Schlüsselverwaltung und Lebensdauer)**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#data-protection-default-settings*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)

-   **Microsoft.Extensions.Configuration.DockerSecrets.** GitHub repo (Scrutor. GitHub-Reporitory).
    [*https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets*](https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets)

>[!div class="step-by-step"]
[Zurück](developer-app-secrets-storage.md)
[Weiter](../key-takeaways.md)
