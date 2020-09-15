---
ms.openlocfilehash: c646372104457e8bc5d418744847f3ee771c8d8b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614535"
---
### <a name="wcf-message-security-now-is-able-to-use-tls11-and-tls12"></a><span data-ttu-id="adc09-101">WCF-Nachrichtensicherheit kann jetzt TLS1.1 und TLS1.2 verwenden</span><span class="sxs-lookup"><span data-stu-id="adc09-101">WCF message security now is able to use TLS1.1 and TLS1.2</span></span>

#### <a name="details"></a><span data-ttu-id="adc09-102">Details</span><span class="sxs-lookup"><span data-stu-id="adc09-102">Details</span></span>

<span data-ttu-id="adc09-103">Ab .NET Framework 4.7 können Kunden über die Anwendungskonfigurationseinstellungen neben SSL3.0 und TLS1.0 entweder TLS1.1 oder TLS1.2 in WCF-Nachrichtensicherheit konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="adc09-103">Starting in the .NET Framework 4.7, customers can configure either TLS1.1 or TLS1.2 in WCF message security in addition to SSL3.0 and TLS1.0 through application configuration settings.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="adc09-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="adc09-104">Suggestion</span></span>

<span data-ttu-id="adc09-105">In .NET Framework 4.7 werden TLS1.1 und TLS1.2 in WCF-Nachrichtensicherheit standardmäßig nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="adc09-105">In the .NET Framework 4.7, support for TLS1.1 and TLS1.2 in WCF message security is disabled by default.</span></span> <span data-ttu-id="adc09-106">Sie können die Unterstützung aktivieren, indem Sie die folgende Zeile zum Abschnitt `<runtime>` der app.config- oder der web.config-Datei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="adc09-106">You can enable it by adding the following line to the `<runtime>` section of the app.config or web.config file:</span></span>

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false" />
</runtime>
```

| <span data-ttu-id="adc09-107">name</span><span class="sxs-lookup"><span data-stu-id="adc09-107">Name</span></span>    | <span data-ttu-id="adc09-108">Wert</span><span class="sxs-lookup"><span data-stu-id="adc09-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="adc09-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="adc09-109">Scope</span></span>   | <span data-ttu-id="adc09-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="adc09-110">Edge</span></span>        |
| <span data-ttu-id="adc09-111">Version</span><span class="sxs-lookup"><span data-stu-id="adc09-111">Version</span></span> | <span data-ttu-id="adc09-112">4.7</span><span class="sxs-lookup"><span data-stu-id="adc09-112">4.7</span></span>         |
| <span data-ttu-id="adc09-113">Typ</span><span class="sxs-lookup"><span data-stu-id="adc09-113">Type</span></span>    | <span data-ttu-id="adc09-114">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="adc09-114">Retargeting</span></span> |
