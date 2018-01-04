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
ms.workload: dotnet
ms.openlocfilehash: cd70b4154a388ecb30518f03773d2a296258d7b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelshttpsclientcertificatenotpresent"></a><span data-ttu-id="0e6e0-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span><span class="sxs-lookup"><span data-stu-id="0e6e0-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span></span>
<span data-ttu-id="0e6e0-103">Ein Clientzertifikat ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0e6e0-103">Client certificate is required.</span></span> <span data-ttu-id="0e6e0-104">Es wurde kein Zertifikat in der Anforderung gefunden.</span><span class="sxs-lookup"><span data-stu-id="0e6e0-104">No certificate was found in the request.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0e6e0-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e6e0-105">Description</span></span>  
 <span data-ttu-id="0e6e0-106">Diese Ablaufverfolgung gibt an, dass der HTTP-Listener eine HTTPS-Anforderung empfangen hat, die keinem Clientzertifikat zugeordnet war.</span><span class="sxs-lookup"><span data-stu-id="0e6e0-106">This trace indicates that the HTTPS listener received an HTTPS request that was not associated with a client certificate.</span></span> <span data-ttu-id="0e6e0-107">Da der Listener so konfiguriert wurde, dass für alle HTTPS-Anforderungen Clientzertifikate erforderlich sind, konnte der Listener die Authentizität des Clients nicht überprüfen.</span><span class="sxs-lookup"><span data-stu-id="0e6e0-107">Since the listener was configured to require client certificates on all HTTPS requests, the listener failed to validate the client’s authenticity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e6e0-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e6e0-108">See Also</span></span>  
 [<span data-ttu-id="0e6e0-109">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="0e6e0-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="0e6e0-110">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="0e6e0-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="0e6e0-111">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="0e6e0-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
