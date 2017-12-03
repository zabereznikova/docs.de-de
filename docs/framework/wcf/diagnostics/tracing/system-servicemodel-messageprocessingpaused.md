---
title: System.ServiceModel.MessageProcessingPaused
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 33d05eaa94ec0efdf6d18d03d9d38bda6f0c9eb7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="98ad6-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="98ad6-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="98ad6-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="98ad6-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="98ad6-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="98ad6-104">Description</span></span>  
 <span data-ttu-id="98ad6-105">Zwischen den Threads wurde umgeschaltet, während sie eine Nachricht verarbeitet haben.</span><span class="sxs-lookup"><span data-stu-id="98ad6-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="98ad6-106">Nachrichtenverarbeitung kann aus den folgenden Gründen angehalten werden:</span><span class="sxs-lookup"><span data-stu-id="98ad6-106">Message processing can be paused by the following reasons:</span></span>  
  
-   <span data-ttu-id="98ad6-107">ConcurrencyMode ist einzeln oder wiedereintrittsfähig, und der Dienst verarbeitet eine andere Nachricht.</span><span class="sxs-lookup"><span data-stu-id="98ad6-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
-   <span data-ttu-id="98ad6-108">Transaktion wird aktiviert, und der Dienst verarbeitet eine andere Transaktion.</span><span class="sxs-lookup"><span data-stu-id="98ad6-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
-   <span data-ttu-id="98ad6-109">Der Synchronisierungskontext ist nicht aktuell.</span><span class="sxs-lookup"><span data-stu-id="98ad6-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98ad6-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98ad6-110">See Also</span></span>  
 [<span data-ttu-id="98ad6-111">Ereignisablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="98ad6-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="98ad6-112">Verwenden der Ablaufverfolgung beheben</span><span class="sxs-lookup"><span data-stu-id="98ad6-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="98ad6-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="98ad6-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
