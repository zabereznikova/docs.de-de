---
title: Verwenden von Azure Key Vault zum Schutz von Geheimnissen zur Produktionszeit
description: Sicherheit in .NET-Microservices und Webanwendungen – Azure Key Vault ist eine hervorragende Möglichkeit, Anwendungsgeheimnisse zu behandeln, die vollständig von Administratoren gesteuert werden. Administratoren können sogar Entwicklungswerte zuweisen und widerrufen, ohne dass Entwickler sie behandeln müssen.
author: mjrousos
ms.date: 01/30/2020
ms.openlocfilehash: d2d3690c0c8787ace6bcdfacbdb612f9ef957b98
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94916241"
---
# <a name="use-azure-key-vault-to-protect-secrets-at-production-time"></a><span data-ttu-id="6ef03-104">Verwenden von Azure Key Vault zum Schutz von Geheimnissen zur Produktionszeit</span><span class="sxs-lookup"><span data-stu-id="6ef03-104">Use Azure Key Vault to protect secrets at production time</span></span>

<span data-ttu-id="6ef03-105">Geheimnisse, die als Umgebungsvariablen oder vom Secret Manager-Tool gespeichert werden, werden weiterhin lokal und unverschlüsselt auf dem Computer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="6ef03-105">Secrets stored as environment variables or stored by the Secret Manager tool are still stored locally and unencrypted on the machine.</span></span> <span data-ttu-id="6ef03-106">[Azure Key Vault](https://azure.microsoft.com/services/key-vault/) ist eine sicherere Option zum Speichern von Geheimnissen, die einen sicheren und zentralen Speicherort für Schlüssel und Geheimnisse bietet.</span><span class="sxs-lookup"><span data-stu-id="6ef03-106">A more secure option for storing secrets is [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), which provides a secure, central location for storing keys and secrets.</span></span>

<span data-ttu-id="6ef03-107">Das Paket **Azure.Extensions.AspNetCore.Configuration.Secrets** ermöglicht einer ASP.NET Core-Anwendung das Lesen von Konfigurationsinformationen aus Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="6ef03-107">The **Azure.Extensions.AspNetCore.Configuration.Secrets** package allows an ASP.NET Core application to read configuration information from Azure Key Vault.</span></span> <span data-ttu-id="6ef03-108">Führen Sie die folgenden Schritte aus, um mit der Verwendung von Geheimnissen aus Azure Key Vault zu beginnen:</span><span class="sxs-lookup"><span data-stu-id="6ef03-108">To start using secrets from an Azure Key Vault, you follow these steps:</span></span>

1. <span data-ttu-id="6ef03-109">Registrieren Sie Ihre Anwendung als eine Azure AD-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="6ef03-109">Register your application as an Azure AD application.</span></span> <span data-ttu-id="6ef03-110">(Der Zugriff auf Schlüsseltresore wird von Azure AD verwaltet.) Dies kann über das Azure-Verwaltungsportal erfolgen.</span><span class="sxs-lookup"><span data-stu-id="6ef03-110">(Access to key vaults is managed by Azure AD.) This can be done through the Azure management portal.\</span></span>

   <span data-ttu-id="6ef03-111">Wenn Sie hingegen möchten, dass Ihre Anwendung nicht mit einem Kennwort oder einem Clientgeheimnis authentifiziert wird, sondern mit einem Zertifikat, können Sie das PowerShell-Cmdlet [New-AzADApplication](/powershell/module/az.resources/new-azadapplication) verwenden.</span><span class="sxs-lookup"><span data-stu-id="6ef03-111">Alternatively, if you want your application to authenticate using a certificate instead of a password or client secret, you can use the [New-AzADApplication](/powershell/module/az.resources/new-azadapplication) PowerShell cmdlet.</span></span> <span data-ttu-id="6ef03-112">Das Zertifikat, das Sie mit Azure Key Vault registrieren, benötigt nur Ihren öffentlichen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="6ef03-112">The certificate that you register with Azure Key Vault needs only your public key.</span></span> <span data-ttu-id="6ef03-113">Ihre Anwendung verwendet den privaten Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="6ef03-113">Your application will use the private key.</span></span>

2. <span data-ttu-id="6ef03-114">Gewähren Sie der registrierten Anwendung Zugriff auf den Schlüsseltresor, indem Sie einen neuen Dienstprinzipal erstellen.</span><span class="sxs-lookup"><span data-stu-id="6ef03-114">Give the registered application access to the key vault by creating a new service principal.</span></span> <span data-ttu-id="6ef03-115">Verwenden Sie hierzu die folgenden PowerShell-Befehle:</span><span class="sxs-lookup"><span data-stu-id="6ef03-115">You can do this using the following PowerShell commands:</span></span>

   ```powershell
   $sp = New-AzADServicePrincipal -ApplicationId "<Application ID guid>"
   Set-AzKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
   ```

3. <span data-ttu-id="6ef03-116">Fügen Sie den Schlüsseltresor als Konfigurationsquelle in Ihrer Anwendung hinzu, indem Sie die Erweiterungsmethode „AzureKeyVaultConfigurationExtensions.AddAzureKeyVault“ aufrufen, wenn Sie eine <xref:Microsoft.Extensions.Configuration.IConfigurationRoot>-Instanz erstellen.</span><span class="sxs-lookup"><span data-stu-id="6ef03-116">Include the key vault as a configuration source in your application by calling the AzureKeyVaultConfigurationExtensions.AddAzureKeyVault extension method when you create an <xref:Microsoft.Extensions.Configuration.IConfigurationRoot> instance.</span></span>

<span data-ttu-id="6ef03-117">Beachten Sie, dass das Aufrufen von `AddAzureKeyVault` die Anwendungs-ID erfordert, die in den vorherigen Schritten registriert wurde und den Zugriff auf den Schlüsseltresor erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="6ef03-117">Note that calling `AddAzureKeyVault` requires the application ID that was registered and given access to the key vault in the previous steps.</span></span> <span data-ttu-id="6ef03-118">Alternativ können Sie zuerst den Azure CLI-Befehl `az login` ausführen und dann eine Überladung von `AddAzureKeyVault` verwenden, die eine DefaultAzureCredential-Klasse anstelle des Clients akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="6ef03-118">Or you can firstly running the Azure CLI command: `az login`, then using an overload of `AddAzureKeyVault` that takes a DefaultAzureCredential in place of the client.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6ef03-119">Sie sollten Azure Key Vault als letzten Konfigurationsanbieter registrieren, damit Konfigurationswerte vorheriger Anbieter überschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="6ef03-119">We recommend that you register Azure Key Vault as the last configuration provider, so it can override configuration values from previous providers.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6ef03-120">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="6ef03-120">Additional resources</span></span>

- <span data-ttu-id="6ef03-121">**Verwenden von Azure Key Vault zum Schutz von Anwendungsgeheimnissen** </span><span class="sxs-lookup"><span data-stu-id="6ef03-121">**Using Azure Key Vault to protect application secrets** </span></span>\
  [https://docs.microsoft.com/azure/architecture/multitenant-identity](/azure/architecture/multitenant-identity-keyvault)

- <span data-ttu-id="6ef03-122">**Sicheres Speichern von App-Geheimnissen während der Entwicklung** </span><span class="sxs-lookup"><span data-stu-id="6ef03-122">**Safe storage of app secrets during development** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/app-secrets](/aspnet/core/security/app-secrets)

- <span data-ttu-id="6ef03-123">**Konfigurieren des Schutzes von Daten** </span><span class="sxs-lookup"><span data-stu-id="6ef03-123">**Configuring data protection** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview](/aspnet/core/security/data-protection/configuration/overview)

- <span data-ttu-id="6ef03-124">**(Data Protection key management and lifetime in ASP.NET Core) Gültigkeitsdauer und Verwaltung von Schlüsseln für den Schutz von Daten in ASP.NET Core** </span><span class="sxs-lookup"><span data-stu-id="6ef03-124">**Data Protection key management and lifetime in ASP.NET Core** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings](/aspnet/core/security/data-protection/configuration/default-settings)

- <span data-ttu-id="6ef03-125">GitHub-Repository **Microsoft.Extensions.Configuration**.</span><span class="sxs-lookup"><span data-stu-id="6ef03-125">**Microsoft.Extensions.Configuration** GitHub repository.</span></span> \
  <https://github.com/dotnet/extensions/tree/master/src/Configuration>

>[!div class="step-by-step"]
><span data-ttu-id="6ef03-126">[Zurück](developer-app-secrets-storage.md)
>[Weiter](../key-takeaways.md)</span><span class="sxs-lookup"><span data-stu-id="6ef03-126">[Previous](developer-app-secrets-storage.md)
[Next](../key-takeaways.md)</span></span>
