---
ms.openlocfilehash: c996dafcf65b1fd428be908be346de603ead6e0b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615679"
---
### <a name="certificate-eku-oid-validation"></a><span data-ttu-id="f0c5b-101">EKU-OID-Zertifikatüberprüfung</span><span class="sxs-lookup"><span data-stu-id="f0c5b-101">Certificate EKU OID validation</span></span>

#### <a name="details"></a><span data-ttu-id="f0c5b-102">Details</span><span class="sxs-lookup"><span data-stu-id="f0c5b-102">Details</span></span>

<span data-ttu-id="f0c5b-103">Ab .NET Framework 4.6 führt die Klasse <xref:System.Net.Security.SslStream> oder <xref:System.Net.ServicePointManager> eine Überprüfung mithilfe der erweiterten Schlüsselverwendung (EKU) und unter Berücksichtigung von Objektbezeichnern (OIDs) durch.</span><span class="sxs-lookup"><span data-stu-id="f0c5b-103">Starting with .NET Framework 4.6, the <xref:System.Net.Security.SslStream> or <xref:System.Net.ServicePointManager> classes perform enhanced key use (EKU) object identifier (OID) validation.</span></span> <span data-ttu-id="f0c5b-104">Eine EKU-Erweiterung ist eine Sammlung von OIDs, die Anwendungen kennzeichnen, die den Schlüssel verwenden.</span><span class="sxs-lookup"><span data-stu-id="f0c5b-104">An enhanced key usage (EKU) extension is a collection of object identifiers (OIDs) that indicate the applications that use the key.</span></span> <span data-ttu-id="f0c5b-105">Bei der EKU-OID-Überprüfung werden Remotezertifikatrückrufe verwendet, um sicherzustellen, dass das Remotezertifikat über die richtigen OIDs für den entsprechenden Zweck verfügt.</span><span class="sxs-lookup"><span data-stu-id="f0c5b-105">EKU OID validation uses remote certificate callbacks to ensure that the remote certificate has the correct OIDs for the intended purpose.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f0c5b-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="f0c5b-106">Suggestion</span></span>

<span data-ttu-id="f0c5b-107">Wenn diese Änderung nicht erwünscht ist, können Sie die EKU-OID-Zertifikatüberprüfung deaktivieren, indem Sie die folgende Option [\<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) im [\`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md)-Element Ihrer Anwendungskonfigurationsdatei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="f0c5b-107">If this change is undesirable, you can disable certificate EKU OID validation by adding the following switch to the [\<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) in the [\`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) of your app configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Net.DontCheckCertificateEKUs=true" />
</runtime>
```

> [!IMPORTANT]
> <span data-ttu-id="f0c5b-108">Diese Einstellung wird lediglich aus Gründen der Abwärtskompatibilität bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f0c5b-108">This setting is provided for backward compatibility only.</span></span> <span data-ttu-id="f0c5b-109">Abgesehen davon wird die Verwendung nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="f0c5b-109">Its use is otherwise not recommended.</span></span>

| <span data-ttu-id="f0c5b-110">name</span><span class="sxs-lookup"><span data-stu-id="f0c5b-110">Name</span></span>    | <span data-ttu-id="f0c5b-111">Wert</span><span class="sxs-lookup"><span data-stu-id="f0c5b-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f0c5b-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="f0c5b-112">Scope</span></span>   | <span data-ttu-id="f0c5b-113">Gering</span><span class="sxs-lookup"><span data-stu-id="f0c5b-113">Minor</span></span>       |
| <span data-ttu-id="f0c5b-114">Version</span><span class="sxs-lookup"><span data-stu-id="f0c5b-114">Version</span></span> | <span data-ttu-id="f0c5b-115">4.6</span><span class="sxs-lookup"><span data-stu-id="f0c5b-115">4.6</span></span>         |
| <span data-ttu-id="f0c5b-116">Typ</span><span class="sxs-lookup"><span data-stu-id="f0c5b-116">Type</span></span>    | <span data-ttu-id="f0c5b-117">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="f0c5b-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="f0c5b-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="f0c5b-118">Affected APIs</span></span>

- <xref:System.Net.Security.SslStream?displayProperty=nameWithType>
- <xref:System.Net.ServicePointManager?displayProperty=nameWithType>
- <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.FtpWebRequest?displayProperty=nameWithType>
