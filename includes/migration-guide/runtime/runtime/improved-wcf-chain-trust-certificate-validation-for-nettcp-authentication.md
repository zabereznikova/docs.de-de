---
ms.openlocfilehash: c8f017084fc1ec1eca636ef0178a40559e15b2c5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497094"
---
### <a name="improved-wcf-chain-trust-certificate-validation-for-nettcp-certificate-authentication"></a><span data-ttu-id="0f39b-101">Verbesserte WCF-Zertifikatkettenüberprüfung für die Net.Tcp-Zertifikatauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="0f39b-101">Improved WCF chain trust certificate validation for Net.Tcp certificate authentication</span></span>

#### <a name="details"></a><span data-ttu-id="0f39b-102">Details</span><span class="sxs-lookup"><span data-stu-id="0f39b-102">Details</span></span>

<span data-ttu-id="0f39b-103">.NET Framework 4.7.2 verbessert die Zertifikatkettenüberprüfung, wenn Zertifikatauthentifizierung mit Transportsicherheit mit WCF verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0f39b-103">.NET Framework 4.7.2 improves chain trust certificate validation when using certificate authentication with transport security with WCF.</span></span> <span data-ttu-id="0f39b-104">Durch diese Verbesserung müssen Clientzertifikate, die verwendet werden, um die Authentifizierung mit einem Server auszuführen, für Clientauthentifizierung konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="0f39b-104">With this improvement, client certificates that are used to authenticate to a server must be configured for client authentication.</span></span>  <span data-ttu-id="0f39b-105">Entsprechend müssen auch Serverzertifikate, die zur Authentifizierung eines Servers dienen, für Serverauthentifizierung konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="0f39b-105">Similarly server certificates that are for the authenticating a server must be configured for server authentication.</span></span> <span data-ttu-id="0f39b-106">Wenn das Stammzertifikat deaktiviert ist, schlägt die Überprüfung der Zertifikatkette aufgrund dieser Änderung fehl.</span><span class="sxs-lookup"><span data-stu-id="0f39b-106">With this change, if the root certificate is disabled, the certificate chain validation fails.</span></span> <span data-ttu-id="0f39b-107">Für .NET Framework 3.5 und höhere Versionen wurde über das Windows-Sicherheitsrollup die gleiche Änderung vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="0f39b-107">The same change was also made to .NET Framework 3.5 and later versions via Windows security roll-up.</span></span> <span data-ttu-id="0f39b-108">Weitere Informationen finden Sie [hier](https://support.microsoft.com/help/4055269/security-only-update-for-net-framework-3-5-1-4-5-2-4-6-4-6-1-4-6-2-4-7). Diese Änderung ist standardmäßig aktiviert und kann durch eine Konfigurationseinstellung deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="0f39b-108">You can find more information [here](https://support.microsoft.com/help/4055269/security-only-update-for-net-framework-3-5-1-4-5-2-4-6-4-6-1-4-6-2-4-7).This change is on by default and can be turned off by a configuration setting.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0f39b-109">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="0f39b-109">Suggestion</span></span>

<ul><li><span data-ttu-id="0f39b-110">Überprüfen Sie, ob Ihre Server- und Clientzertifizierung über die erforderliche EKU-OID verfügt.</span><span class="sxs-lookup"><span data-stu-id="0f39b-110">Validate if your server and client certification has the required EKU OID.</span></span> <span data-ttu-id="0f39b-111">Wenn dies nicht der Fall ist, aktualisieren Sie Ihre Zertifizierung.</span><span class="sxs-lookup"><span data-stu-id="0f39b-111">If not, update your certification.</span></span></li><li><span data-ttu-id="0f39b-112">Überprüfen Sie, ob Ihr Stammzertifikat ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="0f39b-112">Validate if your root certificate is invalid.</span></span> <span data-ttu-id="0f39b-113">Wenn dies der Fall ist, aktualisieren Sie das Stammzertifikat.</span><span class="sxs-lookup"><span data-stu-id="0f39b-113">If so, update the root certificate.</span></span></li><li><span data-ttu-id="0f39b-114">So deaktivieren Sie die Änderung: Wenn Sie das Zertifikat nicht aktualisieren können, können Sie diese wichtige Änderung mit der folgenden Konfigurationsänderung vorübergehend umgehen. Wenn Sie die Änderung deaktivieren, wird Ihr System jedoch für das Sicherheitsproblem anfällig.</span><span class="sxs-lookup"><span data-stu-id="0f39b-114">How to opt out of the change: If you can't update the certificate, you can work around the breaking change temporarily with the following configration setting,  However, opting out of the change will leave your system vulnerable to the security issue.</span></span></li></ul><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;wcf:useLegacyCertificateUsagePolicy&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="0f39b-115">name</span><span class="sxs-lookup"><span data-stu-id="0f39b-115">Name</span></span>    | <span data-ttu-id="0f39b-116">Wert</span><span class="sxs-lookup"><span data-stu-id="0f39b-116">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0f39b-117">Bereich</span><span class="sxs-lookup"><span data-stu-id="0f39b-117">Scope</span></span>   |<span data-ttu-id="0f39b-118">Gering</span><span class="sxs-lookup"><span data-stu-id="0f39b-118">Minor</span></span>|
|<span data-ttu-id="0f39b-119">Version</span><span class="sxs-lookup"><span data-stu-id="0f39b-119">Version</span></span>|<span data-ttu-id="0f39b-120">4.7.2</span><span class="sxs-lookup"><span data-stu-id="0f39b-120">4.7.2</span></span>|
|<span data-ttu-id="0f39b-121">Typ</span><span class="sxs-lookup"><span data-stu-id="0f39b-121">Type</span></span>|<span data-ttu-id="0f39b-122">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="0f39b-122">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="0f39b-123">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="0f39b-123">Affected APIs</span></span>

<span data-ttu-id="0f39b-124">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="0f39b-124">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
