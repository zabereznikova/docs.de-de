---
title: System.ServiceModel.Channels.HttpsClientCertificateNotPresent
ms.date: 03/30/2017
ms.assetid: b13ef1b6-e340-401d-93ca-2710c3842205
ms.openlocfilehash: 15ae13563cfcfb3765559cafb2d31bd6482df7b2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59201181"
---
# <a name="systemservicemodelchannelshttpsclientcertificatenotpresent"></a><span data-ttu-id="87340-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span><span class="sxs-lookup"><span data-stu-id="87340-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span></span>
<span data-ttu-id="87340-103">Ein Clientzertifikat ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="87340-103">Client certificate is required.</span></span> <span data-ttu-id="87340-104">Es wurde kein Zertifikat in der Anforderung gefunden.</span><span class="sxs-lookup"><span data-stu-id="87340-104">No certificate was found in the request.</span></span>  
  
## <a name="description"></a><span data-ttu-id="87340-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87340-105">Description</span></span>  
 <span data-ttu-id="87340-106">Diese Ablaufverfolgung gibt an, dass der HTTP-Listener eine HTTPS-Anforderung empfangen hat, die keinem Clientzertifikat zugeordnet war.</span><span class="sxs-lookup"><span data-stu-id="87340-106">This trace indicates that the HTTPS listener received an HTTPS request that was not associated with a client certificate.</span></span> <span data-ttu-id="87340-107">Da der Listener so konfiguriert wurde, dass für alle HTTPS-Anforderungen Clientzertifikate erforderlich sind, konnte der Listener die Authentizität des Clients nicht überprüfen.</span><span class="sxs-lookup"><span data-stu-id="87340-107">Since the listener was configured to require client certificates on all HTTPS requests, the listener failed to validate the client’s authenticity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87340-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87340-108">See also</span></span>

- [<span data-ttu-id="87340-109">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="87340-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="87340-110">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="87340-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="87340-111">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="87340-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
