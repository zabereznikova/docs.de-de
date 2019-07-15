---
ms.openlocfilehash: d48519443aeee05617538cf2cc12bea49ad3e16d
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858522"
---
### <a name="x509certificate2tostringboolean-does-not-throw-now-when-net-cannot-handle-the-certificate"></a><span data-ttu-id="238ea-101">„X509Certificate2.ToString(Boolean)“ wird jetzt nicht mehr ausgelöst, wenn .NET das Zertifikat nicht verarbeiten kann</span><span class="sxs-lookup"><span data-stu-id="238ea-101">X509Certificate2.ToString(Boolean) does not throw now when .NET cannot handle the certificate</span></span>

|   |   |
|---|---|
|<span data-ttu-id="238ea-102">Details</span><span class="sxs-lookup"><span data-stu-id="238ea-102">Details</span></span>|<span data-ttu-id="238ea-103">Zuvor wurde diese Methode in .NET Framework 4.5.2 ausgelöst, wenn <code>true</code> für den ausführlichen Parameter übergeben wurde und Zertifikate installiert waren, die von .NET Framework nicht unterstützt wurden.</span><span class="sxs-lookup"><span data-stu-id="238ea-103">In .NET Framework 4.5.2 and earlier versions, this method would throw if <code>true</code> was passed for the verbose parameter and there were certificates installed that weren't supported by the .NET Framework.</span></span> <span data-ttu-id="238ea-104">Nun wird die Methode erfolgreich ausgeführt und gibt eine gültige Zeichenfolge zurück, die die Teile des Zertifikats auslässt, auf die nicht zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="238ea-104">Now, the method will succeed and return a valid string that omits the inaccessible portions of the certificate.</span></span>|
|<span data-ttu-id="238ea-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="238ea-105">Suggestion</span></span>|<span data-ttu-id="238ea-106">Jeder von <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> abhängige Code sollte aktualisiert werden, um zu erwarten, dass die zurückgegebene Zeichenfolge einige Zertifikatsdaten in einigen Fällen ausschließt (z.B. den öffentlichen Schlüssel, den privaten Schlüssel und die Erweiterungen), in denen zuvor die API ausgelöst worden wäre.</span><span class="sxs-lookup"><span data-stu-id="238ea-106">Any code depending on <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> should be updated to expect that the returned string may exclude some certificate data (such as public key, private key, and extensions) in some cases in which the API would have previously thrown.</span></span>|
|<span data-ttu-id="238ea-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="238ea-107">Scope</span></span>|<span data-ttu-id="238ea-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="238ea-108">Edge</span></span>|
|<span data-ttu-id="238ea-109">Version</span><span class="sxs-lookup"><span data-stu-id="238ea-109">Version</span></span>|<span data-ttu-id="238ea-110">4.6</span><span class="sxs-lookup"><span data-stu-id="238ea-110">4.6</span></span>|
|<span data-ttu-id="238ea-111">Typ</span><span class="sxs-lookup"><span data-stu-id="238ea-111">Type</span></span>|<span data-ttu-id="238ea-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="238ea-112">Runtime</span></span>|
|<span data-ttu-id="238ea-113">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="238ea-113">Affected APIs</span></span>|<ul><li><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType></li></ul>|

