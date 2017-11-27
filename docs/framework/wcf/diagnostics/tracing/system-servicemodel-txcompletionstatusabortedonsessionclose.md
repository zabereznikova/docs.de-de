---
title: System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1e9ab5af359b833452664f534e3627f477246fa6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodeltxcompletionstatusabortedonsessionclose"></a><span data-ttu-id="8cb63-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="8cb63-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span></span>
<span data-ttu-id="8cb63-103">Die angegebene Transaktion wurde abgebrochen, weil sie nicht abgeschlossen war, als die Sitzung geschlossen wurde, und das TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute auf FALSE festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="8cb63-103">The specified transaction was aborted because it was uncompleted when the session was closed and the TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute was set to false.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8cb63-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8cb63-104">Description</span></span>  
 <span data-ttu-id="8cb63-105">Wird nachverfolgt, wenn die aktuelle aktive Sitzung geschlossen und die Transaktion nicht abgeschlossen wurde und TransactionAutoCompleteOnSessionClose auf `false` festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="8cb63-105">Traced if the current active session was closed, and the transaction was not completed, and TransactionAutoCompleteOnSessionClose is set to `false`.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="8cb63-106">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="8cb63-106">Troubleshooting</span></span>  
 <span data-ttu-id="8cb63-107">Diese Ablaufverfolgung gibt einen potenziellen Anwendungsfehler an, der untersucht werden sollte.</span><span class="sxs-lookup"><span data-stu-id="8cb63-107">This trace indicates a potential application bug that should be investigated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cb63-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8cb63-108">See Also</span></span>  
 [<span data-ttu-id="8cb63-109">Ereignisablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="8cb63-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="8cb63-110">Verwenden der Ablaufverfolgung beheben</span><span class="sxs-lookup"><span data-stu-id="8cb63-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="8cb63-111">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="8cb63-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
