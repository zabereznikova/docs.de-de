---
title: System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
ms.date: 03/30/2017
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
ms.openlocfilehash: 0d8c77d01351b0c62e0186e5aee69ca70aebe15e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274321"
---
# <a name="systemservicemodeltxcompletionstatusabortedonsessionclose"></a><span data-ttu-id="e3769-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="e3769-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span></span>

<span data-ttu-id="e3769-103">Die angegebene Transaktion wurde abgebrochen, weil sie nicht abgeschlossen war, als die Sitzung geschlossen wurde, und das TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute auf FALSE festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="e3769-103">The specified transaction was aborted because it was uncompleted when the session was closed and the TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute was set to false.</span></span>  
  
## <a name="description"></a><span data-ttu-id="e3769-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e3769-104">Description</span></span>  

 <span data-ttu-id="e3769-105">Wird nachverfolgt, wenn die aktuelle aktive Sitzung geschlossen und die Transaktion nicht abgeschlossen wurde und TransactionAutoCompleteOnSessionClose auf `false` festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="e3769-105">Traced if the current active session was closed, and the transaction was not completed, and TransactionAutoCompleteOnSessionClose is set to `false`.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="e3769-106">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="e3769-106">Troubleshooting</span></span>  

 <span data-ttu-id="e3769-107">Diese Ablaufverfolgung gibt einen potenziellen Anwendungsfehler an, der untersucht werden sollte.</span><span class="sxs-lookup"><span data-stu-id="e3769-107">This trace indicates a potential application bug that should be investigated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3769-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e3769-108">See also</span></span>

- [<span data-ttu-id="e3769-109">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="e3769-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="e3769-110">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="e3769-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="e3769-111">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="e3769-111">Administration and Diagnostics</span></span>](../index.md)
