---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: 6fb1463b811d985f54b9a99e59d1280eaa040256
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33482813"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="98c1a-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="98c1a-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="98c1a-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="98c1a-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="98c1a-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="98c1a-104">Description</span></span>  
 <span data-ttu-id="98c1a-105">Zwischen den Threads wurde umgeschaltet, während sie eine Nachricht verarbeitet haben.</span><span class="sxs-lookup"><span data-stu-id="98c1a-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="98c1a-106">Nachrichtenverarbeitung kann aus den folgenden Gründen angehalten werden:</span><span class="sxs-lookup"><span data-stu-id="98c1a-106">Message processing can be paused by the following reasons:</span></span>  
  
-   <span data-ttu-id="98c1a-107">ConcurrencyMode ist einzeln oder wiedereintrittsfähig, und der Dienst verarbeitet eine andere Nachricht.</span><span class="sxs-lookup"><span data-stu-id="98c1a-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
-   <span data-ttu-id="98c1a-108">Transaktion wird aktiviert, und der Dienst verarbeitet eine andere Transaktion.</span><span class="sxs-lookup"><span data-stu-id="98c1a-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
-   <span data-ttu-id="98c1a-109">Der Synchronisierungskontext ist nicht aktuell.</span><span class="sxs-lookup"><span data-stu-id="98c1a-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98c1a-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98c1a-110">See Also</span></span>  
 [<span data-ttu-id="98c1a-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="98c1a-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="98c1a-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="98c1a-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="98c1a-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="98c1a-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
