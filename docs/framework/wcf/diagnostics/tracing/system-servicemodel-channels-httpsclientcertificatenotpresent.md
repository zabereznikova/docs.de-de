---
title: System.ServiceModel.Channels.HttpsClientCertificateNotPresent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b13ef1b6-e340-401d-93ca-2710c3842205
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3a9eb867826fbf1e4028f57e5118ff18d4329b23
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelchannelshttpsclientcertificatenotpresent"></a><span data-ttu-id="3c603-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span><span class="sxs-lookup"><span data-stu-id="3c603-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span></span>
<span data-ttu-id="3c603-103">Ein Clientzertifikat ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3c603-103">Client certificate is required.</span></span> <span data-ttu-id="3c603-104">Es wurde kein Zertifikat in der Anforderung gefunden.</span><span class="sxs-lookup"><span data-stu-id="3c603-104">No certificate was found in the request.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3c603-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3c603-105">Description</span></span>  
 <span data-ttu-id="3c603-106">Diese Ablaufverfolgung gibt an, dass der HTTP-Listener eine HTTPS-Anforderung empfangen hat, die keinem Clientzertifikat zugeordnet war.</span><span class="sxs-lookup"><span data-stu-id="3c603-106">This trace indicates that the HTTPS listener received an HTTPS request that was not associated with a client certificate.</span></span> <span data-ttu-id="3c603-107">Da der Listener so konfiguriert wurde, dass für alle HTTPS-Anforderungen Clientzertifikate erforderlich sind, konnte der Listener die Authentizität des Clients nicht überprüfen.</span><span class="sxs-lookup"><span data-stu-id="3c603-107">Since the listener was configured to require client certificates on all HTTPS requests, the listener failed to validate the client’s authenticity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c603-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c603-108">See Also</span></span>  
 [<span data-ttu-id="3c603-109">Ereignisablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="3c603-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="3c603-110">Verwenden der Ablaufverfolgung beheben</span><span class="sxs-lookup"><span data-stu-id="3c603-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="3c603-111">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="3c603-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
