---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: ac1dacef94d6446aa407e4a390b9561d033af1bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61927022"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="a5def-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="a5def-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="a5def-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="a5def-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="a5def-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a5def-104">Description</span></span>  
 <span data-ttu-id="a5def-105">Zwischen den Threads wurde umgeschaltet, während sie eine Nachricht verarbeitet haben.</span><span class="sxs-lookup"><span data-stu-id="a5def-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="a5def-106">Nachrichtenverarbeitung kann aus den folgenden Gründen angehalten werden:</span><span class="sxs-lookup"><span data-stu-id="a5def-106">Message processing can be paused by the following reasons:</span></span>  
  
- <span data-ttu-id="a5def-107">ConcurrencyMode ist einzeln oder wiedereintrittsfähig, und der Dienst verarbeitet eine andere Nachricht.</span><span class="sxs-lookup"><span data-stu-id="a5def-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
- <span data-ttu-id="a5def-108">Transaktion wird aktiviert, und der Dienst verarbeitet eine andere Transaktion.</span><span class="sxs-lookup"><span data-stu-id="a5def-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
- <span data-ttu-id="a5def-109">Der Synchronisierungskontext ist nicht aktuell.</span><span class="sxs-lookup"><span data-stu-id="a5def-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5def-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5def-110">See also</span></span>

- [<span data-ttu-id="a5def-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="a5def-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="a5def-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="a5def-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="a5def-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="a5def-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
