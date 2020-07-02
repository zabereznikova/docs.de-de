---
ms.openlocfilehash: 23e278d38d6904d8afe927e6b54c388d443e41f5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616062"
---
### <a name="signedxmlgetpublickey-returns-rsacng-on-net462-or-lightup-without-retargeting-change"></a><span data-ttu-id="60e10-101">SignedXml.GetPublicKey gibt unter .NET Framework 4.6.2 RSACng (oder CngLightup) zurück, ohne Änderungen neu zuzuweisen</span><span class="sxs-lookup"><span data-stu-id="60e10-101">SignedXml.GetPublicKey returns RSACng on net462 (or lightup) without retargeting change</span></span>

#### <a name="details"></a><span data-ttu-id="60e10-102">Details</span><span class="sxs-lookup"><span data-stu-id="60e10-102">Details</span></span>

<span data-ttu-id="60e10-103">Ab .NET Framework 4.6.2 wird für den konkreten Typ des Objekts, das von der <xref:System.Security.Cryptography.Xml.SignedXml.GetPublicKey%2A?displayProperty=nameWithType>-Methode zurückgegeben wird, nicht mehr die CryptoServiceProvider-Implementierung, sondern eine Cng-Implementierung verwendet. Probleme sind durch diese Änderung nicht aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="60e10-103">Starting with the .NET Framework 4.6.2, the concrete type of the object returned by the <xref:System.Security.Cryptography.Xml.SignedXml.GetPublicKey%2A?displayProperty=nameWithType> method changed (without a quirk) from a CryptoServiceProvider implementation to a Cng implementation.</span></span> <span data-ttu-id="60e10-104">Der Grund für die Änderung ist, dass für die Implementierung anstelle von `certificate.PublicKey.Key` nun die interne Methode `certificate.GetAnyPublicKey` verwendet wird, die eine Weiterleitung zu <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey%2A?displayProperty=nameWithType> vornimmt.</span><span class="sxs-lookup"><span data-stu-id="60e10-104">This is because the implementation changed from using `certificate.PublicKey.Key` to using the internal `certificate.GetAnyPublicKey` which forwards to <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey%2A?displayProperty=nameWithType>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="60e10-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="60e10-105">Suggestion</span></span>

<span data-ttu-id="60e10-106">Für Apps, die unter .NET Framework 4.7.1 oder einer neueren Version ausgeführt werden, können Sie die standardmäßig von .NET Framework 4.6.1 und früheren Versionen verwendete CryptoServiceProvider-Implementierung verwenden, indem Sie dem Abschnitt [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) Ihrer Anwendungskonfigurationsdatei die folgende Konfigurationsoption hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="60e10-106">Starting with apps running on the .NET Framework 4.7.1, you can use the CryptoServiceProvider implementation used by default in the .NET Framework 4.6.1 and earlier versions by adding the following configuration switch to the [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.Xml.SignedXmlUseLegacyCertificatePrivateKey=true" />
```

| <span data-ttu-id="60e10-107">Name</span><span class="sxs-lookup"><span data-stu-id="60e10-107">Name</span></span>    | <span data-ttu-id="60e10-108">Wert</span><span class="sxs-lookup"><span data-stu-id="60e10-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="60e10-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="60e10-109">Scope</span></span>   | <span data-ttu-id="60e10-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="60e10-110">Edge</span></span>        |
| <span data-ttu-id="60e10-111">Version</span><span class="sxs-lookup"><span data-stu-id="60e10-111">Version</span></span> | <span data-ttu-id="60e10-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="60e10-112">4.6.2</span></span>       |
| <span data-ttu-id="60e10-113">Typ</span><span class="sxs-lookup"><span data-stu-id="60e10-113">Type</span></span>    | <span data-ttu-id="60e10-114">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="60e10-114">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="60e10-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="60e10-115">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignatureReturningKey(System.Security.Cryptography.AsymmetricAlgorithm@)?displayProperty=nameWithType>
