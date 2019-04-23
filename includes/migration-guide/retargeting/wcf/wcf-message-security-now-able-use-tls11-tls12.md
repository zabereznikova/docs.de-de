---
ms.openlocfilehash: 0a3dc43ebdc58d54675f2264a8ee56d9f4358cd8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804049"
---
### <a name="wcf-message-security-now-is-able-to-use-tls11-and-tls12"></a><span data-ttu-id="b06d9-101">WCF-Nachrichtensicherheit kann jetzt TLS1.1 und TLS1.2 verwenden</span><span class="sxs-lookup"><span data-stu-id="b06d9-101">WCF message security now is able to use TLS1.1 and TLS1.2</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b06d9-102">Details</span><span class="sxs-lookup"><span data-stu-id="b06d9-102">Details</span></span>|<span data-ttu-id="b06d9-103">Ab .NET Framework 4.7 können Kunden über die Anwendungskonfigurationseinstellungen neben SSL3.0 und TLS1.0 entweder TLS1.1 oder TLS1.2 in WCF-Nachrichtensicherheit konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b06d9-103">Starting in the .NET Framework 4.7, customers can configure either TLS1.1 or TLS1.2 in WCF message security in addition to SSL3.0 and TLS1.0 through application configuration settings.</span></span>|
|<span data-ttu-id="b06d9-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="b06d9-104">Suggestion</span></span>|<span data-ttu-id="b06d9-105">In .NET Framework 4.7 werden TLS1.1 und TLS1.2 in WCF-Nachrichtensicherheit standardmäßig nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b06d9-105">In the .NET Framework 4.7, support for TLS1.1 and TLS1.2 in WCF message security is disabled by default.</span></span> <span data-ttu-id="b06d9-106">Sie können die Unterstützung aktivieren, indem Sie die folgende Zeile zum Abschnitt <code>&lt;runtime&gt;</code> der app.config- oder der web.config-Datei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="b06d9-106">You can enable it by adding the following line to the <code>&lt;runtime&gt;</code> section of the app.config or web.config file:</span></span><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="b06d9-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="b06d9-107">Scope</span></span>|<span data-ttu-id="b06d9-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b06d9-108">Edge</span></span>|
|<span data-ttu-id="b06d9-109">Version</span><span class="sxs-lookup"><span data-stu-id="b06d9-109">Version</span></span>|<span data-ttu-id="b06d9-110">4.7</span><span class="sxs-lookup"><span data-stu-id="b06d9-110">4.7</span></span>|
|<span data-ttu-id="b06d9-111">Typ</span><span class="sxs-lookup"><span data-stu-id="b06d9-111">Type</span></span>|<span data-ttu-id="b06d9-112">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="b06d9-112">Retargeting</span></span>|
