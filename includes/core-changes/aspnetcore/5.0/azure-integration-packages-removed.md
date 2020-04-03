---
ms.openlocfilehash: d8506893f5b3eefa6f46dc9f773e43b125ee5210
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291635"
---
### <a name="azure-microsoft-prefixed-azure-integration-packages-removed"></a>Azure: Azure-Integrationspakete mit Präfix „Microsoft“ entfernt

Die folgenden `Microsoft.*`-Pakete zur Integration von ASP.NET Core und Azure SDKs sind in ASP.NET Core 5.0 nicht enthalten:

* [Microsoft.Extensions.Configuration.AzureKeyVault](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.AzureKeyVault/) für die Integration von [Azure Key Vault](/azure/key-vault/) in das [Konfigurationssystem](/aspnet/core/fundamentals/configuration/).
* [Microsoft.AspNetCore.DataProtection.AzureKeyVault](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureKeyVault/) zur Integration von Azure Key Vault in das [ASP.NET Core Data Protection-System](/aspnet/core/security/data-protection/introduction).
* [Microsoft.AspNetCore.DataProtection.AzureStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureStorage/) zur Integration von [Azure Blob Storage](/azure/storage/blobs/) in das ASP.NET Core-Datenschutzsystem.

Dieses Problem wird unter [dotnet/aspnetcore#19570](https://github.com/dotnet/aspnetcore/issues/19570) behandelt.

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 1

#### <a name="old-behavior"></a>Altes Verhalten

Die `Microsoft.*`-Pakete integrierten Azure-Dienste in die APIs für Konfiguration und Datenschutz.

#### <a name="new-behavior"></a>Neues Verhalten

Neue `Azure.*`-Pakete integrierten Azure-Dienste in die APIs für Konfiguration und Datenschutz.

#### <a name="reason-for-change"></a>Grund für die Änderung

Die Änderungen wurden aufgrund der folgenden Eigenschaften der `Microsoft.*`-Pakete vorgenommen:

* Es wurden veraltete Versionen des Azure SDK verwendet. Einfache Updates waren nicht möglich, weil die neuen Azure SDK-Versionen Änderungen mit Auswirkung auf die Lauffähigkeit umfassten.
* Sie waren an den .NET Core-Releasezeitplan gebunden. Eine Übertragung des Paketbesitzes an das Azure SDK-Team ermöglicht Paketupdates im Rahmen von Azure SDK-Aktualisierungen.

#### <a name="recommended-action"></a>Empfohlene Aktion

Ersetzen Sie in Projekten mit ASP.NET Core 2.1 oder höher die alten `Microsoft.*`- durch die neuen `Azure.*`-Pakete.

| Alt | Neu |
|--|--|
| `Microsoft.AspNetCore.DataProtection.AzureKeyVault` | [Azure.AspNetCore.DataProtection.Keys](https://www.nuget.org/packages/Azure.AspNetCore.DataProtection.Keys) |
| `Microsoft.AspNetCore.DataProtection.AzureStorage` | [Azure.AspNetCore.DataProtection.Blobs](https://www.nuget.org/packages/Azure.AspNetCore.DataProtection.Blobs) |
| `Microsoft.Extensions.Configuration.AzureKeyVault` | [Azure.Extensions.Configuration.Secrets](https://www.nuget.org/packages/Azure.Extensions.Configuration.Secrets) |

Die neuen Pakete verwenden eine neue Azure SDK-Version, die Breaking Changes umfasst. Die allgemeinen Nutzungsmuster haben sich nicht verändert. Einige Überladungen und Optionen können abweichen, um sich an Änderungen in den zugrunde liegenden Azure SDK-APIs anzupassen.

Für die alten Pakete gilt:

* Sie werden für die gesamte Lebensdauer von .NET Core 2.1 und 3.1 vom ASP.NET Core-Team unterstützt.
* Die Pakete sind nicht in .NET 5 enthalten.

Stellen Sie beim Upgrade Ihres Projekts auf .NET 5 auf die `Azure.*`-Pakete um, um eine weitere Unterstützung zu gewährleisten.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:Microsoft.Extensions.Configuration.AzureKeyVaultConfigurationExtensions.AddAzureKeyVault%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.ProtectKeysWithAzureKeyVault%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.PersistKeysToAzureBlobStorage%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:Microsoft.Extensions.Configuration.AzureKeyVaultConfigurationExtensions.AddAzureKeyVault`
- `Overload:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.ProtectKeysWithAzureKeyVault`
- `Overload:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.PersistKeysToAzureBlobStorage`

-->
