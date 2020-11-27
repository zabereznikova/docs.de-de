---
title: System.ServiceModel.Channels.HttpsClientCertificateNotPresent
ms.date: 03/30/2017
ms.assetid: b13ef1b6-e340-401d-93ca-2710c3842205
ms.openlocfilehash: 9ec25138130311f8cdd9af8fb32a3e80fb33ed68
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258087"
---
# <a name="systemservicemodelchannelshttpsclientcertificatenotpresent"></a><span data-ttu-id="6ab6e-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span><span class="sxs-lookup"><span data-stu-id="6ab6e-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span></span>

<span data-ttu-id="6ab6e-103">Ein Clientzertifikat ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6ab6e-103">Client certificate is required.</span></span> <span data-ttu-id="6ab6e-104">Es wurde kein Zertifikat in der Anforderung gefunden.</span><span class="sxs-lookup"><span data-stu-id="6ab6e-104">No certificate was found in the request.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6ab6e-105">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6ab6e-105">Description</span></span>  

 <span data-ttu-id="6ab6e-106">Diese Ablaufverfolgung gibt an, dass der HTTP-Listener eine HTTPS-Anforderung empfangen hat, die keinem Clientzertifikat zugeordnet war.</span><span class="sxs-lookup"><span data-stu-id="6ab6e-106">This trace indicates that the HTTPS listener received an HTTPS request that was not associated with a client certificate.</span></span> <span data-ttu-id="6ab6e-107">Da der Listener so konfiguriert wurde, dass für alle HTTPS-Anforderungen Clientzertifikate erforderlich sind, konnte der Listener die Authentizität des Clients nicht überprüfen.</span><span class="sxs-lookup"><span data-stu-id="6ab6e-107">Since the listener was configured to require client certificates on all HTTPS requests, the listener failed to validate the client’s authenticity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ab6e-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6ab6e-108">See also</span></span>

- [<span data-ttu-id="6ab6e-109">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="6ab6e-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="6ab6e-110">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="6ab6e-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="6ab6e-111">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="6ab6e-111">Administration and Diagnostics</span></span>](../index.md)
