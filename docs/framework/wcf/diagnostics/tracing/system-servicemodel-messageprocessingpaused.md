---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: 85bec8255e0d20d6e76ea354e5b8c42b83d7d8e6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598150"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="f8841-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="f8841-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="f8841-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="f8841-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="f8841-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f8841-104">Description</span></span>  
 <span data-ttu-id="f8841-105">Zwischen den Threads wurde umgeschaltet, während sie eine Nachricht verarbeitet haben.</span><span class="sxs-lookup"><span data-stu-id="f8841-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="f8841-106">Nachrichtenverarbeitung kann aus den folgenden Gründen angehalten werden:</span><span class="sxs-lookup"><span data-stu-id="f8841-106">Message processing can be paused by the following reasons:</span></span>  
  
- <span data-ttu-id="f8841-107">ConcurrencyMode ist einzeln oder wiedereintrittsfähig, und der Dienst verarbeitet eine andere Nachricht.</span><span class="sxs-lookup"><span data-stu-id="f8841-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
- <span data-ttu-id="f8841-108">Transaktion wird aktiviert, und der Dienst verarbeitet eine andere Transaktion.</span><span class="sxs-lookup"><span data-stu-id="f8841-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
- <span data-ttu-id="f8841-109">Der Synchronisierungskontext ist nicht aktuell.</span><span class="sxs-lookup"><span data-stu-id="f8841-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8841-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f8841-110">See also</span></span>

- [<span data-ttu-id="f8841-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="f8841-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="f8841-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="f8841-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="f8841-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="f8841-113">Administration and Diagnostics</span></span>](../index.md)
