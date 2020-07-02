---
ms.openlocfilehash: 51208762cea2a5688c5d43e5d444d4e014e5f0b4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621318"
---
### <a name="x509certificate2tostringboolean-does-not-throw-now-when-net-cannot-handle-the-certificate"></a><span data-ttu-id="ae344-101">„X509Certificate2.ToString(Boolean)“ wird jetzt nicht mehr ausgelöst, wenn .NET das Zertifikat nicht verarbeiten kann</span><span class="sxs-lookup"><span data-stu-id="ae344-101">X509Certificate2.ToString(Boolean) does not throw now when .NET cannot handle the certificate</span></span>

#### <a name="details"></a><span data-ttu-id="ae344-102">Details</span><span class="sxs-lookup"><span data-stu-id="ae344-102">Details</span></span>

<span data-ttu-id="ae344-103">Zuvor wurde diese Methode in .NET Framework 4.5.2 ausgelöst, wenn <code>true</code> für den ausführlichen Parameter übergeben wurde und Zertifikate installiert waren, die von .NET Framework nicht unterstützt wurden.</span><span class="sxs-lookup"><span data-stu-id="ae344-103">In .NET Framework 4.5.2 and earlier versions, this method would throw if <code>true</code> was passed for the verbose parameter and there were certificates installed that weren't supported by the .NET Framework.</span></span> <span data-ttu-id="ae344-104">Nun wird die Methode erfolgreich ausgeführt und gibt eine gültige Zeichenfolge zurück, die die Teile des Zertifikats auslässt, auf die nicht zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="ae344-104">Now, the method will succeed and return a valid string that omits the inaccessible portions of the certificate.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ae344-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="ae344-105">Suggestion</span></span>

<span data-ttu-id="ae344-106">Jeder von <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> abhängige Code sollte aktualisiert werden, um zu erwarten, dass die zurückgegebene Zeichenfolge einige Zertifikatsdaten in einigen Fällen ausschließt (z.B. den öffentlichen Schlüssel, den privaten Schlüssel und die Erweiterungen), in denen zuvor die API ausgelöst worden wäre.</span><span class="sxs-lookup"><span data-stu-id="ae344-106">Any code depending on <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> should be updated to expect that the returned string may exclude some certificate data (such as public key, private key, and extensions) in some cases in which the API would have previously thrown.</span></span>

| <span data-ttu-id="ae344-107">name</span><span class="sxs-lookup"><span data-stu-id="ae344-107">Name</span></span>    | <span data-ttu-id="ae344-108">Wert</span><span class="sxs-lookup"><span data-stu-id="ae344-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ae344-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="ae344-109">Scope</span></span>   |<span data-ttu-id="ae344-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ae344-110">Edge</span></span>|
|<span data-ttu-id="ae344-111">Version</span><span class="sxs-lookup"><span data-stu-id="ae344-111">Version</span></span>|<span data-ttu-id="ae344-112">4.6</span><span class="sxs-lookup"><span data-stu-id="ae344-112">4.6</span></span>|
|<span data-ttu-id="ae344-113">Typ</span><span class="sxs-lookup"><span data-stu-id="ae344-113">Type</span></span>|<span data-ttu-id="ae344-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="ae344-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ae344-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="ae344-115">Affected APIs</span></span>

-<xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType></li></ul>|
