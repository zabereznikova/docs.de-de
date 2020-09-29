---
ms.openlocfilehash: 9f5f238e3d4222af1da3a1713e1b3e65de6e6f49
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "91024985"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a><span data-ttu-id="d5a37-101">Die PipeConnection.GetHashAlgorithm-Methode von WCF verwendet nun SHA256</span><span class="sxs-lookup"><span data-stu-id="d5a37-101">WCF PipeConnection.GetHashAlgorithm now uses SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="d5a37-102">Details</span><span class="sxs-lookup"><span data-stu-id="d5a37-102">Details</span></span>

<span data-ttu-id="d5a37-103">Ab .NET Framework 4.7.1 verwendet Windows Communication Foundation einen SHA256-Hash, um zufällige Namen für Named Pipes zu generieren.</span><span class="sxs-lookup"><span data-stu-id="d5a37-103">Starting with the .NET Framework 4.7.1, Windows Communication Foundation uses a SHA256 hash to generate random names for named pipes.</span></span> <span data-ttu-id="d5a37-104">In .NET Framework 4.7 und früheren Versionen wurde ein SHA1-Hash verwendet.</span><span class="sxs-lookup"><span data-stu-id="d5a37-104">In the .NET Framework 4.7 and earlier versions, it used a SHA1 hash.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d5a37-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="d5a37-105">Suggestion</span></span>

<span data-ttu-id="d5a37-106">Wenn Kompatibilitätsprobleme durch diese Änderung an .NET Framework 4.7.1 oder höher auftreten, können Sie diese deaktivieren, indem Sie folgende Zeile zum Abschnitt `<runtime>` Ihrer App.config-Datei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="d5a37-106">If you run into compatibility issue with this change on the .NET Framework 4.7.1 or later, you can opt-out it by adding the following line to the `<runtime>` section of your app.config file:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="d5a37-107">name</span><span class="sxs-lookup"><span data-stu-id="d5a37-107">Name</span></span>    | <span data-ttu-id="d5a37-108">Wert</span><span class="sxs-lookup"><span data-stu-id="d5a37-108">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="d5a37-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="d5a37-109">Scope</span></span>   | <span data-ttu-id="d5a37-110">Gering</span><span class="sxs-lookup"><span data-stu-id="d5a37-110">Minor</span></span>   |
| <span data-ttu-id="d5a37-111">Version</span><span class="sxs-lookup"><span data-stu-id="d5a37-111">Version</span></span> | <span data-ttu-id="d5a37-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="d5a37-112">4.7.1</span></span>   |
| <span data-ttu-id="d5a37-113">Typ</span><span class="sxs-lookup"><span data-stu-id="d5a37-113">Type</span></span>    | <span data-ttu-id="d5a37-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="d5a37-114">Runtime</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="d5a37-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="d5a37-115">Affected APIs</span></span>

<span data-ttu-id="d5a37-116">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="d5a37-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
