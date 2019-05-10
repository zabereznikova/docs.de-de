---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: 7dcdb9fdd6a283f692897cbbb49cd1f2d1dd661e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586790"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="72f73-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="72f73-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="72f73-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="72f73-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="72f73-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="72f73-104">Description</span></span>  
 <span data-ttu-id="72f73-105">Zwischen den Threads wurde umgeschaltet, während sie eine Nachricht verarbeitet haben.</span><span class="sxs-lookup"><span data-stu-id="72f73-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="72f73-106">Nachrichtenverarbeitung kann aus den folgenden Gründen angehalten werden:</span><span class="sxs-lookup"><span data-stu-id="72f73-106">Message processing can be paused by the following reasons:</span></span>  
  
- <span data-ttu-id="72f73-107">ConcurrencyMode ist einzeln oder wiedereintrittsfähig, und der Dienst verarbeitet eine andere Nachricht.</span><span class="sxs-lookup"><span data-stu-id="72f73-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
- <span data-ttu-id="72f73-108">Transaktion wird aktiviert, und der Dienst verarbeitet eine andere Transaktion.</span><span class="sxs-lookup"><span data-stu-id="72f73-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
- <span data-ttu-id="72f73-109">Der Synchronisierungskontext ist nicht aktuell.</span><span class="sxs-lookup"><span data-stu-id="72f73-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72f73-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72f73-110">See also</span></span>

- [<span data-ttu-id="72f73-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="72f73-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="72f73-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="72f73-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="72f73-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="72f73-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
