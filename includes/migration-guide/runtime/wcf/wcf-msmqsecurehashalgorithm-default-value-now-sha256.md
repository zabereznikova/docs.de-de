---
ms.openlocfilehash: a2d4b7592727ca20ee79867094d6972eb9c4baed
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760429"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a><span data-ttu-id="d2c63-101">Der WCF-Standardwert MsmqSecureHashAlgorithm ist jetzt SHA256</span><span class="sxs-lookup"><span data-stu-id="d2c63-101">WCF MsmqSecureHashAlgorithm default value is now SHA256</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d2c63-102">Details</span><span class="sxs-lookup"><span data-stu-id="d2c63-102">Details</span></span>|<span data-ttu-id="d2c63-103">Ab .NET Framework 4.7.1 ist SHA256 der Standardalgorithmus zum Signieren von Msmq-Nachrichten in WCF.</span><span class="sxs-lookup"><span data-stu-id="d2c63-103">Starting with the .NET Framework 4.7.1, the default message signing algorithm in WCF for Msmq messages is SHA256.</span></span> <span data-ttu-id="d2c63-104">In .NET Framework 4.7 und früheren Versionen ist SHA1 der Standardalgorithmus zum Signieren von Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="d2c63-104">In the .NET Framework 4.7 and earlier versions, the default message signing algorithm is SHA1.</span></span>|
|<span data-ttu-id="d2c63-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="d2c63-105">Suggestion</span></span>|<span data-ttu-id="d2c63-106">Wenn Kompatibilitätsprobleme durch diese Änderung an .NET Framework 4.7.1 oder höher auftreten, können Sie diese deaktivieren, indem Sie folgende Zeile zum Abschnitt <code>&lt;runtime&gt;</code> Ihrer App.config-Datei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="d2c63-106">If you run into compatibility issues with this change on the .NET Framework 4.7.1 or later, you can opt-out the change by adding the following line to the <code>&lt;runtime&gt;</code>section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="d2c63-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="d2c63-107">Scope</span></span>|<span data-ttu-id="d2c63-108">Gering</span><span class="sxs-lookup"><span data-stu-id="d2c63-108">Minor</span></span>|
|<span data-ttu-id="d2c63-109">Version</span><span class="sxs-lookup"><span data-stu-id="d2c63-109">Version</span></span>|<span data-ttu-id="d2c63-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="d2c63-110">4.7.1</span></span>|
|<span data-ttu-id="d2c63-111">Typ</span><span class="sxs-lookup"><span data-stu-id="d2c63-111">Type</span></span>|<span data-ttu-id="d2c63-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="d2c63-112">Runtime</span></span>|

