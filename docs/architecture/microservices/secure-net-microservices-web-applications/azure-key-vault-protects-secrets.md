---
title: Verwenden von Azure Key Vault zum Schutz von Geheimnissen zur Produktionszeit
description: Sicherheit in .NET-Microservices und Webanwendungen – Azure Key Vault ist eine hervorragende Möglichkeit, Anwendungsgeheimnisse zu behandeln, die vollständig von Administratoren gesteuert werden. Administratoren können sogar Entwicklungswerte zuweisen und widerrufen, ohne dass Entwickler sie behandeln müssen.
author: mjrousos
ms.author: wiwagn
ms.date: 10/19/2018
ms.openlocfilehash: 4d121f584188c5d5fa9ddf0d91bea5e107eff0cb
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899659"
---
# <a name="use-azure-key-vault-to-protect-secrets-at-production-time"></a>Verwenden von Azure Key Vault zum Schutz von Geheimnissen zur Produktionszeit

Geheimnisse, die als Umgebungsvariablen oder vom Secret Manager-Tool gespeichert werden, werden weiterhin lokal und unverschlüsselt auf dem Computer gespeichert. [Azure Key Vault](https://azure.microsoft.com/services/key-vault/) ist eine sicherere Option zum Speichern von Geheimnissen, die einen sicheren und zentralen Speicherort für Schlüssel und Geheimnisse bietet.

Das Paket **Microsoft.Extensions.Configuration.AzureKeyVault** erlaubt einer ASP.NET Core-Anwendung, die Konfigurationsinformationen von Azure Key Vault auszulesen. Führen Sie die folgenden Schritte aus, um mit der Verwendung von Geheimnissen aus Azure Key Vault zu beginnen:

1. Registrieren Sie Ihre Anwendung als eine Azure AD-Anwendung. (Der Zugriff auf Schlüsseltresore wird von Azure AD verwaltet.) Dies kann über das Azure-Verwaltungsportal erfolgen.

   Wenn Sie hingegen möchten, dass Ihre Anwendung nicht mit einem Kennwort oder einem Clientgeheimnis authentifiziert wird, sondern mit einem Zertifikat, können Sie das PowerShell-Cmdlet [New-AzADApplication](/powershell/module/az.resources/new-azadapplication) verwenden. Das Zertifikat, das Sie mit Azure Key Vault registrieren, benötigt nur Ihren öffentlichen Schlüssel. Ihre Anwendung verwendet den privaten Schlüssel.

2. Gewähren Sie der registrierten Anwendung Zugriff auf den Schlüsseltresor, indem Sie einen neuen Dienstprinzipal erstellen. Verwenden Sie hierzu die folgenden PowerShell-Befehle:

   ```powershell
   $sp = New-AzADServicePrincipal -ApplicationId "<Application ID guid>"
   Set-AzKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
   ```

3. Schließen Sie den Schlüsseltresor als Konfigurationsquelle in Ihre Anwendung ein, indem Sie die Erweiterungsmethode <xref:Microsoft.Extensions.Configuration.AzureKeyVaultConfigurationExtensions.AddAzureKeyVault%2A?displayProperty=nameWithType> aufrufen, wenn Sie eine <xref:Microsoft.Extensions.Configuration.IConfigurationRoot>-Instanz erstellen. Beachten Sie, dass das Aufrufen von `AddAzureKeyVault` die Anwendungs-ID erfordert, die in den vorherigen Schritten registriert wurde und den Zugriff auf den Schlüsseltresor erhalten hat.

   Sie können auch eine Überladung von `AddAzureKeyVault` verwenden, die ein Zertifikat anstelle des Clientgeheimisses akzeptiert, indem einfach ein Verweis auf das [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory)-Paket einbezogen wird.

> [!IMPORTANT]
> Sie sollten Azure Key Vault als letzten Konfigurationsanbieter registrieren, damit Konfigurationswerte vorheriger Anbieter überschrieben werden können.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Verwenden von Azure Key Vault zum Schutz von Anwendungsgeheimnissen** \
  [https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault](/azure/guidance/guidance-multitenant-identity-keyvault)

- **Sicheres Speichern von App-Geheimnissen während der Entwicklung** \
  [https://docs.microsoft.com/aspnet/core/security/app-secrets](/aspnet/core/security/app-secrets)

- **Konfigurieren des Schutzes von Daten** \
  [https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview](/aspnet/core/security/data-protection/configuration/overview)

- **(Data Protection key management and lifetime in ASP.NET Core) Gültigkeitsdauer und Verwaltung von Schlüsseln für den Schutz von Daten in ASP.NET Core** \
  [https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings](/aspnet/core/security/data-protection/configuration/default-settings)

- GitHub-Repository **Microsoft.Extensions.Configuration.KeyPerFile** \
  <https://github.com/dotnet/extensions/tree/master/src/Configuration/Config.KeyPerFile>

>[!div class="step-by-step"]
>[Zurück](developer-app-secrets-storage.md)
>[Weiter](../key-takeaways.md)
