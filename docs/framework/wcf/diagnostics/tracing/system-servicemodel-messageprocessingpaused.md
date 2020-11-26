---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: e4c8040d2350e3824b5d68dc6f32376007792a7f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96235115"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="3909e-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="3909e-102">System.ServiceModel.MessageProcessingPaused</span></span>

<span data-ttu-id="3909e-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="3909e-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="3909e-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3909e-104">Description</span></span>  

 <span data-ttu-id="3909e-105">Zwischen den Threads wurde umgeschaltet, während sie eine Nachricht verarbeitet haben.</span><span class="sxs-lookup"><span data-stu-id="3909e-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="3909e-106">Nachrichtenverarbeitung kann aus den folgenden Gründen angehalten werden:</span><span class="sxs-lookup"><span data-stu-id="3909e-106">Message processing can be paused by the following reasons:</span></span>  
  
- <span data-ttu-id="3909e-107">ConcurrencyMode ist einzeln oder wiedereintrittsfähig, und der Dienst verarbeitet eine andere Nachricht.</span><span class="sxs-lookup"><span data-stu-id="3909e-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
- <span data-ttu-id="3909e-108">Transaktion wird aktiviert, und der Dienst verarbeitet eine andere Transaktion.</span><span class="sxs-lookup"><span data-stu-id="3909e-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
- <span data-ttu-id="3909e-109">Der Synchronisierungskontext ist nicht aktuell.</span><span class="sxs-lookup"><span data-stu-id="3909e-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3909e-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3909e-110">See also</span></span>

- [<span data-ttu-id="3909e-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="3909e-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="3909e-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="3909e-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="3909e-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="3909e-113">Administration and Diagnostics</span></span>](../index.md)
