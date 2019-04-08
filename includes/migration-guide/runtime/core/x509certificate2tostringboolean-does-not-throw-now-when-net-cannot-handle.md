---
ms.openlocfilehash: d48519443aeee05617538cf2cc12bea49ad3e16d
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761275"
---
### <a name="x509certificate2tostringboolean-does-not-throw-now-when-net-cannot-handle-the-certificate"></a><span data-ttu-id="73f5f-101">„X509Certificate2.ToString(Boolean)“ wird jetzt nicht mehr ausgelöst, wenn .NET das Zertifikat nicht verarbeiten kann</span><span class="sxs-lookup"><span data-stu-id="73f5f-101">X509Certificate2.ToString(Boolean) does not throw now when .NET cannot handle the certificate</span></span>

|   |   |
|---|---|
|<span data-ttu-id="73f5f-102">Details</span><span class="sxs-lookup"><span data-stu-id="73f5f-102">Details</span></span>|<span data-ttu-id="73f5f-103">Zuvor wurde diese Methode in .NET Framework 4.5.2 ausgelöst, wenn <code>true</code> für den ausführlichen Parameter übergeben wurde und Zertifikate installiert waren, die von .NET Framework nicht unterstützt wurden.</span><span class="sxs-lookup"><span data-stu-id="73f5f-103">In .NET Framework 4.5.2 and earlier versions, this method would throw if <code>true</code> was passed for the verbose parameter and there were certificates installed that weren't supported by the .NET Framework.</span></span> <span data-ttu-id="73f5f-104">Nun wird die Methode erfolgreich ausgeführt und gibt eine gültige Zeichenfolge zurück, die die Teile des Zertifikats auslässt, auf die nicht zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="73f5f-104">Now, the method will succeed and return a valid string that omits the inaccessible portions of the certificate.</span></span>|
|<span data-ttu-id="73f5f-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="73f5f-105">Suggestion</span></span>|<span data-ttu-id="73f5f-106">Jeder von <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> abhängige Code sollte aktualisiert werden, um zu erwarten, dass die zurückgegebene Zeichenfolge einige Zertifikatsdaten in einigen Fällen ausschließt (z.B. den öffentlichen Schlüssel, den privaten Schlüssel und die Erweiterungen), in denen zuvor die API ausgelöst worden wäre.</span><span class="sxs-lookup"><span data-stu-id="73f5f-106">Any code depending on <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> should be updated to expect that the returned string may exclude some certificate data (such as public key, private key, and extensions) in some cases in which the API would have previously thrown.</span></span>|
|<span data-ttu-id="73f5f-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="73f5f-107">Scope</span></span>|<span data-ttu-id="73f5f-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="73f5f-108">Edge</span></span>|
|<span data-ttu-id="73f5f-109">Version</span><span class="sxs-lookup"><span data-stu-id="73f5f-109">Version</span></span>|<span data-ttu-id="73f5f-110">4.6</span><span class="sxs-lookup"><span data-stu-id="73f5f-110">4.6</span></span>|
|<span data-ttu-id="73f5f-111">Typ</span><span class="sxs-lookup"><span data-stu-id="73f5f-111">Type</span></span>|<span data-ttu-id="73f5f-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="73f5f-112">Runtime</span></span>|
|<span data-ttu-id="73f5f-113">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="73f5f-113">Affected APIs</span></span>|<ul><li><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType></li></ul>|

