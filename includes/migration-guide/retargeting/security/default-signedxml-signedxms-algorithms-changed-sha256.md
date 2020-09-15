---
ms.openlocfilehash: e2ae329d027d605e6331afe422e550990fab1042
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614540"
---
### <a name="default-signedxml-and-signedxms-algorithms-changed-to-sha256"></a><span data-ttu-id="b5f89-101">Die Standardalgorithmen SignedXML und SignedXMS wurden in SHA-256 geändert</span><span class="sxs-lookup"><span data-stu-id="b5f89-101">Default SignedXML and SignedXMS algorithms changed to SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="b5f89-102">Details</span><span class="sxs-lookup"><span data-stu-id="b5f89-102">Details</span></span>

<span data-ttu-id="b5f89-103">In .NET Framework 4.7 und früheren Versionen verwenden SignedXML und SignedCMS für einige Vorgänge standardmäßig SHA-1. Ab .NET Framework 4.7.1 ist SHA-256 für diese Vorgänge standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b5f89-103">In the .NET Framework 4.7 and earlier, SignedXML and SignedCMS default to SHA1 for some operations.Starting with the .NET Framework 4.7.1, SHA256 is enabled by default for these operations.</span></span> <span data-ttu-id="b5f89-104">Diese Änderung ist erforderlich, da SHA-1 nicht mehr sicher ist.</span><span class="sxs-lookup"><span data-stu-id="b5f89-104">This change is necessary because SHA1 is no longer considered to be secure.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b5f89-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="b5f89-105">Suggestion</span></span>

<span data-ttu-id="b5f89-106">Es gibt zwei neue Kontextwechselwerte, mit denen festgelegt wird, ob SHA-1 (unsicher) oder SHA-256 standardmäßig verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="b5f89-106">There are two new context switch values to control whether SHA1 (insecure) or SHA256 is used by default:</span></span>

- <span data-ttu-id="b5f89-107">Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms</span><span class="sxs-lookup"><span data-stu-id="b5f89-107">Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms</span></span>
- <span data-ttu-id="b5f89-108">Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithmsBei Apps mit der Zielplattform .NET Framework 4.7.1 und höheren Versionen kann die Verwendung von SHA-1 als Standardoption wiederhergestellt werden, wenn die Verwendung von SHA-256 nicht erwünscht ist, indem die folgende Konfigurationsoption dem Abschnitt [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) Ihrer Anwendungskonfigurationsdatei hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="b5f89-108">Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms For applications that target the .NET Framework 4.7.1 and later versions, if the use of SHA256 is undesirable, you can restore the default to SHA1 by adding the following configuration switch to the [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms=true;Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms=true" />
```

<span data-ttu-id="b5f89-109">Bei Apps mit der Zielplattform .NET Framework 4.7 und früheren Versionen können Sie sich für diese Änderung entscheiden, indem Sie die folgende Konfigurationsoption dem Abschnitt [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) Ihrer Anwendungskonfigurationsdatei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="b5f89-109">For applications that target the .NET Framework 4.7 and earlier versions, you can opt into this change by adding the following configuration switch to the [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms=false;Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms=false" />
```

| <span data-ttu-id="b5f89-110">name</span><span class="sxs-lookup"><span data-stu-id="b5f89-110">Name</span></span>    | <span data-ttu-id="b5f89-111">Wert</span><span class="sxs-lookup"><span data-stu-id="b5f89-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b5f89-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="b5f89-112">Scope</span></span>   | <span data-ttu-id="b5f89-113">Gering</span><span class="sxs-lookup"><span data-stu-id="b5f89-113">Minor</span></span>       |
| <span data-ttu-id="b5f89-114">Version</span><span class="sxs-lookup"><span data-stu-id="b5f89-114">Version</span></span> | <span data-ttu-id="b5f89-115">4.7.1</span><span class="sxs-lookup"><span data-stu-id="b5f89-115">4.7.1</span></span>       |
| <span data-ttu-id="b5f89-116">Typ</span><span class="sxs-lookup"><span data-stu-id="b5f89-116">Type</span></span>    | <span data-ttu-id="b5f89-117">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="b5f89-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="b5f89-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="b5f89-118">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Pkcs.CmsSigner?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.Reference?displayProperty=nameWithType>
