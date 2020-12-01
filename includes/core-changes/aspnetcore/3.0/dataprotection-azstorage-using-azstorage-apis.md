---
ms.openlocfilehash: f6e4c3d5c5fd020562e48515554136e0f8b6785c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032496"
---
### <a name="data-protection-dataprotectionblobs-uses-new-azure-storage-apis"></a>Schutz von Daten: DataProtection.Blobs verwendet neue Azure Storage-APIs

`Azure.Extensions.AspNetCore.DataProtection.Blobs` hängt von den [Azure Storage-Bibliotheken](https://github.com/Azure/azure-storage-net) ab. Für diese Bibliotheken wurden die Assemblys, Pakete und Namespaces umbenannt. Ab ASP.NET Core 3.0 verwendet `Azure.Extensions.AspNetCore.DataProtection.Blobs` die neuen APIs und Pakete mit dem Präfix `Azure.Storage.`.

Wenn Sie Fragen zu den Azure Storage-APIs haben, lesen Sie unter <https://github.com/Azure/azure-storage-net> nach. Dieses Problem wird unter [dotnet/aspnetcore#19570](https://github.com/dotnet/aspnetcore/issues/19570) behandelt.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Das Paket verwies auf das NuGet-Paket `WindowsAzure.Storage`.
Das Pakete verweist auf das NuGet-Paket `Microsoft.Azure.Storage.Blob`.

#### <a name="new-behavior"></a>Neues Verhalten

Das Pakete verweist auf das NuGet-Paket `Azure.Storage.Blob`.

#### <a name="reason-for-change"></a>Grund für die Änderung

Diese Änderung ermöglicht `Azure.Extensions.AspNetCore.DataProtection.Blobs` die Migration zu den empfohlenen Azure Storage-Paketen.

#### <a name="recommended-action"></a>Empfohlene Aktion

Wenn Sie weiterhin die älteren Azure Storage-APIs mit ASP.NET Core 3.0 verwenden müssen, fügen Sie eine direkte Abhängigkeit vom Paket [WindowsAzure.Storage](https://www.nuget.org/packages/WindowsAzure.Storage/) oder [Microsoft Azure Storage](https://www.nuget.org/packages/Microsoft.Azure.Storage.Blob/) hinzu. Dieses Paket kann parallel zu den neuen `Azure.Storage`-APIs installiert werden.

In vielen Fällen umfasst das Upgrade nur das Ändern der `using`-Anweisungen, um die neuen Namespaces zu verwenden:

```diff
- using Microsoft.WindowsAzure.Storage;
- using Microsoft.WindowsAzure.Storage.Blob;
- using Microsoft.Azure.Storage;
- using Microsoft.Azure.Storage.Blob;
+ using Azure.Storage;
+ using Azure.Storage.Blobs;
```

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

Keine

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
