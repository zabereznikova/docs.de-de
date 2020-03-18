---
ms.openlocfilehash: 0a3dc43ebdc58d54675f2264a8ee56d9f4358cd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859085"
---
### <a name="wcf-message-security-now-is-able-to-use-tls11-and-tls12"></a><span data-ttu-id="56018-101">WCF-Nachrichtensicherheit kann jetzt TLS1.1 und TLS1.2 verwenden</span><span class="sxs-lookup"><span data-stu-id="56018-101">WCF message security now is able to use TLS1.1 and TLS1.2</span></span>

|   |   |
|---|---|
|<span data-ttu-id="56018-102">Details</span><span class="sxs-lookup"><span data-stu-id="56018-102">Details</span></span>|<span data-ttu-id="56018-103">Ab .NET Framework 4.7 können Kunden über die Anwendungskonfigurationseinstellungen neben SSL3.0 und TLS1.0 entweder TLS1.1 oder TLS1.2 in WCF-Nachrichtensicherheit konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="56018-103">Starting in the .NET Framework 4.7, customers can configure either TLS1.1 or TLS1.2 in WCF message security in addition to SSL3.0 and TLS1.0 through application configuration settings.</span></span>|
|<span data-ttu-id="56018-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="56018-104">Suggestion</span></span>|<span data-ttu-id="56018-105">In .NET Framework 4.7 werden TLS1.1 und TLS1.2 in WCF-Nachrichtensicherheit standardmäßig nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="56018-105">In the .NET Framework 4.7, support for TLS1.1 and TLS1.2 in WCF message security is disabled by default.</span></span> <span data-ttu-id="56018-106">Sie können die Unterstützung aktivieren, indem Sie die folgende Zeile zum Abschnitt <code>&lt;runtime&gt;</code> der app.config- oder der web.config-Datei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="56018-106">You can enable it by adding the following line to the <code>&lt;runtime&gt;</code> section of the app.config or web.config file:</span></span><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="56018-107">`Scope`</span><span class="sxs-lookup"><span data-stu-id="56018-107">Scope</span></span>|<span data-ttu-id="56018-108">Edge</span><span class="sxs-lookup"><span data-stu-id="56018-108">Edge</span></span>|
|<span data-ttu-id="56018-109">Version</span><span class="sxs-lookup"><span data-stu-id="56018-109">Version</span></span>|<span data-ttu-id="56018-110">4.7</span><span class="sxs-lookup"><span data-stu-id="56018-110">4.7</span></span>|
|<span data-ttu-id="56018-111">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="56018-111">Type</span></span>|<span data-ttu-id="56018-112">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="56018-112">Retargeting</span></span>|
