---
ms.openlocfilehash: 36a9db601f7637185bf48dfcbe2233b4489fcdcf
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614442"
---
### <a name="aescryptoserviceprovider-decryptor-provides-a-reusable-transform"></a><span data-ttu-id="76f36-101">Die AesCryptoServiceProvider-Entschlüsselungsmethode stellt eine wiederverwendbare Transformation bereit</span><span class="sxs-lookup"><span data-stu-id="76f36-101">AesCryptoServiceProvider decryptor provides a reusable transform</span></span>

#### <a name="details"></a><span data-ttu-id="76f36-102">Details</span><span class="sxs-lookup"><span data-stu-id="76f36-102">Details</span></span>

<span data-ttu-id="76f36-103">Für Apps mit der Zielplattform .NET Framework 4.6.2 und höher stellt die <xref:System.Security.Cryptography.AesCryptoServiceProvider>-Entschlüsselungsmethode eine wiederverwendbare Transformation bereit.</span><span class="sxs-lookup"><span data-stu-id="76f36-103">Starting with apps that target the .NET Framework 4.6.2, the <xref:System.Security.Cryptography.AesCryptoServiceProvider> decryptor provides a reusable transform.</span></span> <span data-ttu-id="76f36-104">Nach einem Aufruf von <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName> wird die Transformation erneut initialisiert und kann wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="76f36-104">After a call to <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>, the transform is reinitialized and can be reused.</span></span> <span data-ttu-id="76f36-105">Bei Apps mit früheren Versionen von .NET Framework als Zielplattform wird bei dem Versuch, die Entschlüsselungsmethode durch Aufrufen von <xref:System.Security.Cryptography.CryptoAPITransform.TransformBlock(System.Byte[],System.Int32,System.Int32,System.Byte[],System.Int32)?displayProperty=fullName> nach einem Aufruf von <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName> wiederzuverwenden, eine <xref:System.Security.Cryptography.CryptographicException> ausgelöst, oder es werden fehlerhafte Daten erstellt.</span><span class="sxs-lookup"><span data-stu-id="76f36-105">For apps that target earlier versions of the .NET Framework, attempting to reuse the decryptor by calling <xref:System.Security.Cryptography.CryptoAPITransform.TransformBlock(System.Byte[],System.Int32,System.Int32,System.Byte[],System.Int32)?displayProperty=fullName> after a call to <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName> throws a <xref:System.Security.Cryptography.CryptographicException> or produces corrupted data.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="76f36-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="76f36-106">Suggestion</span></span>

<span data-ttu-id="76f36-107">Der Einfluss dieser Änderung sollte klein sein, da dies das erwartete Verhalten ist. Für Anwendungen, die vom bisherigen Verhalten abhängen, muss dieses Verhalten nicht übernommen werden, wenn Sie dem Abschnitt `<runtime>` der Anwendungskonfigurationsdatei die folgende Konfigurationseinstellung hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="76f36-107">The impact of this change should be minimal, since this is the expected behavior.Applications that depend on the previous behavior can opt out of it using it by adding the following configuration setting to the `<runtime>` section of the application's configuration file:</span></span>

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=true"/>
</runtime>
```

<span data-ttu-id="76f36-108">Für Anwendungen, die für frühere Versionen von .NET Framework vorgesehen sind, aber unter .NET Framework 4.6.2 oder einer höheren Version ausgeführt werden, kann dieses Verhalten übernommen werden, indem dem `<runtime>`-Abschnitt der Anwendungskonfigurationsdatei die folgende Konfigurationseinstellung hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="76f36-108">In addition, applications that target a previous version of the .NET Framework but are running under a version of the .NET Framework starting with .NET Framework 4.6.2 can opt in to it by adding the following configuration setting to the `<runtime>` section of the application's configuration file:</span></span>

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=false"/>
</runtime>
```

| <span data-ttu-id="76f36-109">name</span><span class="sxs-lookup"><span data-stu-id="76f36-109">Name</span></span>    | <span data-ttu-id="76f36-110">Wert</span><span class="sxs-lookup"><span data-stu-id="76f36-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="76f36-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="76f36-111">Scope</span></span>   | <span data-ttu-id="76f36-112">Gering</span><span class="sxs-lookup"><span data-stu-id="76f36-112">Minor</span></span>       |
| <span data-ttu-id="76f36-113">Version</span><span class="sxs-lookup"><span data-stu-id="76f36-113">Version</span></span> | <span data-ttu-id="76f36-114">4.6.2</span><span class="sxs-lookup"><span data-stu-id="76f36-114">4.6.2</span></span>       |
| <span data-ttu-id="76f36-115">Typ</span><span class="sxs-lookup"><span data-stu-id="76f36-115">Type</span></span>    | <span data-ttu-id="76f36-116">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="76f36-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="76f36-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="76f36-117">Affected APIs</span></span>

- <xref:System.Security.Cryptography.AesCryptoServiceProvider.CreateDecryptor?displayProperty=nameWithType>
