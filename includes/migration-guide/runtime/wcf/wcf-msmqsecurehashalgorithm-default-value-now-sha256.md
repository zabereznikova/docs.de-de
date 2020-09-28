---
ms.openlocfilehash: 7c0227980aa5d90f3788783088bcd7cd9509ed66
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770782"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a><span data-ttu-id="00c72-101">Der WCF-Standardwert MsmqSecureHashAlgorithm ist jetzt SHA256</span><span class="sxs-lookup"><span data-stu-id="00c72-101">WCF MsmqSecureHashAlgorithm default value is now SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="00c72-102">Details</span><span class="sxs-lookup"><span data-stu-id="00c72-102">Details</span></span>

<span data-ttu-id="00c72-103">Ab .NET Framework 4.7.1 ist SHA256 der Standardalgorithmus zum Signieren von Msmq-Nachrichten in WCF.</span><span class="sxs-lookup"><span data-stu-id="00c72-103">Starting with the .NET Framework 4.7.1, the default message signing algorithm in WCF for Msmq messages is SHA256.</span></span> <span data-ttu-id="00c72-104">In .NET Framework 4.7 und früheren Versionen ist SHA1 der Standardalgorithmus zum Signieren von Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="00c72-104">In the .NET Framework 4.7 and earlier versions, the default message signing algorithm is SHA1.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="00c72-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="00c72-105">Suggestion</span></span>

<span data-ttu-id="00c72-106">Wenn Kompatibilitätsprobleme durch diese Änderung an .NET Framework 4.7.1 oder höher auftreten, können Sie diese beseitigen, indem Sie folgende Zeile zum Abschnitt `<runtime>` Ihrer app.config-Datei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="00c72-106">If you run into compatibility issues with this change on the .NET Framework 4.7.1 or later, you can opt-out the change by adding the following line to the `<runtime>` section of your app.config file:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; />
  </runtime>
</configuration>
```

| <span data-ttu-id="00c72-107">name</span><span class="sxs-lookup"><span data-stu-id="00c72-107">Name</span></span>    | <span data-ttu-id="00c72-108">Wert</span><span class="sxs-lookup"><span data-stu-id="00c72-108">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="00c72-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="00c72-109">Scope</span></span>   | <span data-ttu-id="00c72-110">Gering</span><span class="sxs-lookup"><span data-stu-id="00c72-110">Minor</span></span>   |
| <span data-ttu-id="00c72-111">Version</span><span class="sxs-lookup"><span data-stu-id="00c72-111">Version</span></span> | <span data-ttu-id="00c72-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="00c72-112">4.7.1</span></span>   |
| <span data-ttu-id="00c72-113">Typ</span><span class="sxs-lookup"><span data-stu-id="00c72-113">Type</span></span>    | <span data-ttu-id="00c72-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="00c72-114">Runtime</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="00c72-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="00c72-115">Affected APIs</span></span>

<span data-ttu-id="00c72-116">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="00c72-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
