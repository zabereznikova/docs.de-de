---
ms.openlocfilehash: 7f8f97adcca7e66fa5756212bb977daadd92b8b6
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497194"
---
### <a name="x509certificate2tostringboolean-does-not-throw-now-when-net-cannot-handle-the-certificate"></a><span data-ttu-id="6fd60-101">„X509Certificate2.ToString(Boolean)“ wird jetzt nicht mehr ausgelöst, wenn .NET das Zertifikat nicht verarbeiten kann</span><span class="sxs-lookup"><span data-stu-id="6fd60-101">X509Certificate2.ToString(Boolean) does not throw now when .NET cannot handle the certificate</span></span>

#### <a name="details"></a><span data-ttu-id="6fd60-102">Details</span><span class="sxs-lookup"><span data-stu-id="6fd60-102">Details</span></span>

<span data-ttu-id="6fd60-103">Zuvor wurde diese Methode in .NET Framework 4.5.2 ausgelöst, wenn <code>true</code> für den ausführlichen Parameter übergeben wurde und Zertifikate installiert waren, die von .NET Framework nicht unterstützt wurden.</span><span class="sxs-lookup"><span data-stu-id="6fd60-103">In .NET Framework 4.5.2 and earlier versions, this method would throw if <code>true</code> was passed for the verbose parameter and there were certificates installed that weren't supported by the .NET Framework.</span></span> <span data-ttu-id="6fd60-104">Nun wird die Methode erfolgreich ausgeführt und gibt eine gültige Zeichenfolge zurück, die die Teile des Zertifikats auslässt, auf die nicht zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="6fd60-104">Now, the method will succeed and return a valid string that omits the inaccessible portions of the certificate.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6fd60-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="6fd60-105">Suggestion</span></span>

<span data-ttu-id="6fd60-106">Jeder von <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> abhängige Code sollte aktualisiert werden, um zu erwarten, dass die zurückgegebene Zeichenfolge einige Zertifikatsdaten in einigen Fällen ausschließt (z.B. den öffentlichen Schlüssel, den privaten Schlüssel und die Erweiterungen), in denen zuvor die API ausgelöst worden wäre.</span><span class="sxs-lookup"><span data-stu-id="6fd60-106">Any code depending on <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> should be updated to expect that the returned string may exclude some certificate data (such as public key, private key, and extensions) in some cases in which the API would have previously thrown.</span></span>

| <span data-ttu-id="6fd60-107">name</span><span class="sxs-lookup"><span data-stu-id="6fd60-107">Name</span></span>    | <span data-ttu-id="6fd60-108">Wert</span><span class="sxs-lookup"><span data-stu-id="6fd60-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6fd60-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="6fd60-109">Scope</span></span>   |<span data-ttu-id="6fd60-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6fd60-110">Edge</span></span>|
|<span data-ttu-id="6fd60-111">Version</span><span class="sxs-lookup"><span data-stu-id="6fd60-111">Version</span></span>|<span data-ttu-id="6fd60-112">4.6</span><span class="sxs-lookup"><span data-stu-id="6fd60-112">4.6</span></span>|
|<span data-ttu-id="6fd60-113">Typ</span><span class="sxs-lookup"><span data-stu-id="6fd60-113">Type</span></span>|<span data-ttu-id="6fd60-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="6fd60-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="6fd60-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="6fd60-115">Affected APIs</span></span>

- <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)`

-->
