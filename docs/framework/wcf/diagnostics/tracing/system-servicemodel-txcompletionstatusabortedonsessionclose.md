---
title: System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
ms.date: 03/30/2017
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
ms.openlocfilehash: 7b1f6a2f4a344b566c76d0095942b84a8a4e76f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166503"
---
# <a name="systemservicemodeltxcompletionstatusabortedonsessionclose"></a><span data-ttu-id="9c2f0-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="9c2f0-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span></span>
<span data-ttu-id="9c2f0-103">Die angegebene Transaktion wurde abgebrochen, weil sie nicht abgeschlossen war, als die Sitzung geschlossen wurde, und das TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute auf FALSE festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="9c2f0-103">The specified transaction was aborted because it was uncompleted when the session was closed and the TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute was set to false.</span></span>  
  
## <a name="description"></a><span data-ttu-id="9c2f0-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c2f0-104">Description</span></span>  
 <span data-ttu-id="9c2f0-105">Wird nachverfolgt, wenn die aktuelle aktive Sitzung geschlossen und die Transaktion nicht abgeschlossen wurde und TransactionAutoCompleteOnSessionClose auf `false` festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="9c2f0-105">Traced if the current active session was closed, and the transaction was not completed, and TransactionAutoCompleteOnSessionClose is set to `false`.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="9c2f0-106">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="9c2f0-106">Troubleshooting</span></span>  
 <span data-ttu-id="9c2f0-107">Diese Ablaufverfolgung gibt einen potenziellen Anwendungsfehler an, der untersucht werden sollte.</span><span class="sxs-lookup"><span data-stu-id="9c2f0-107">This trace indicates a potential application bug that should be investigated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c2f0-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c2f0-108">See also</span></span>

- [<span data-ttu-id="9c2f0-109">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="9c2f0-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="9c2f0-110">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="9c2f0-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="9c2f0-111">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="9c2f0-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
