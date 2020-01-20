---
ms.openlocfilehash: db70596552ffd699156e1b7a55cb1e944596f077
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901897"
---
### <a name="data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis"></a>Schutz von Daten: DataProtection.AzureStorage verwendet neue Azure Storage-APIs.

<xref:Microsoft.AspNetCore.DataProtection.AzureStorage?displayProperty=fullName> hängt von den [Azure Storage-Bibliotheken](https://github.com/Azure/azure-storage-net) ab. Für diese Bibliotheken wurden die Assemblys, Pakete und Namespaces umbenannt. Ab ASP.NET Core 3.0 verwendet `Microsoft.AspNetCore.DataProtection.AzureStorage` die neuen APIs und Pakete mit dem Präfix `Microsoft.Azure.Storage.`.

Wenn Sie Fragen zu den Azure Storage-APIs haben, lesen Sie unter <https://github.com/Azure/azure-storage-net> nach. Dieses Problem wird unter [dotnet/aspnetcore#8472](https://github.com/dotnet/aspnetcore/issues/8472) behandelt.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Das Paket verwies auf das NuGet-Paket `WindowsAzure.Storage`.

#### <a name="new-behavior"></a>Neues Verhalten

Das Pakete verweist auf das NuGet-Paket `Microsoft.Azure.Storage.Blob`.

#### <a name="reason-for-change"></a>Grund für die Änderung

Diese Änderung ermöglicht `Microsoft.AspNetCore.DataProtection.AzureStorage` die Migration zu den empfohlenen Azure Storage-Paketen.

#### <a name="recommended-action"></a>Empfohlene Aktion

Wenn Sie weiterhin die älteren Azure Storage-APIs mit ASP.NET Core 3.0 verwenden müssen, fügen Sie eine direkte Abhängigkeit vom Paket [WindowsAzure.Storage](https://www.nuget.org/packages/WindowsAzure.Storage/) hinzu. Dieses Paket kann parallel zu den neuen `Microsoft.Azure.Storage`-APIs installiert werden.

In vielen Fällen umfasst das Upgrade nur das Ändern der `using`-Anweisungen, um die neuen Namespaces zu verwenden:

```diff
- using Microsoft.WindowsAzure.Storage;
- using Microsoft.WindowsAzure.Storage.Blob;
+ using Microsoft.Azure.Storage;
+ using Microsoft.Azure.Storage.Blob;
```

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

Keine

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
