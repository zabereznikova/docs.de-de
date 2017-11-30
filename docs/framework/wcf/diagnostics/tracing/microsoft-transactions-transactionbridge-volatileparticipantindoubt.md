---
title: Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3e8fc825-9f22-47e7-9c16-d64ef291c932
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3b497231326c640b93b96500df39732104e0f0c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="microsofttransactionstransactionbridgevolatileparticipantindoubt"></a><span data-ttu-id="1cb95-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span><span class="sxs-lookup"><span data-stu-id="1cb95-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span></span>
<span data-ttu-id="1cb95-103">Der WS-AT-Protokolldienst hat eine Prepared- oder eine Replay-Nachricht von einem nicht erkannten flüchtigen Teilnehmer empfangen.</span><span class="sxs-lookup"><span data-stu-id="1cb95-103">The WS-AT protocol service received a Prepared or Replay message from an unrecognized volatile participant.</span></span> <span data-ttu-id="1cb95-104">Dem Teilnehmer wurde ein Fehler zurückgegeben, der aussagt, dass das Ergebnis der Transaktion zweifelhaft ist.</span><span class="sxs-lookup"><span data-stu-id="1cb95-104">A fault was returned to the participant, declares that the transaction's outcome is in doubt.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1cb95-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1cb95-105">Description</span></span>  
 <span data-ttu-id="1cb95-106">Verfolgt nach, wann der lokale Transaction Manager eine Prepared- oder Replay-Nachricht von einer flüchtigen Eintragung erhält, die er bereits vergessen hat.</span><span class="sxs-lookup"><span data-stu-id="1cb95-106">Traced when the local Transaction Manager receives a Prepared or Replay message from a Volatile enlistment that it has already forgotten.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="1cb95-107">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="1cb95-107">Troubleshooting</span></span>  
 <span data-ttu-id="1cb95-108">Untersuchen Sie die potenziellen Ursachen von verspätet ankommenden Nachrichten vom flüchtigen Teilnehmer.</span><span class="sxs-lookup"><span data-stu-id="1cb95-108">Investigate potential causes of late messages coming from the Volatile participant.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cb95-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1cb95-109">See Also</span></span>  
 [<span data-ttu-id="1cb95-110">Ereignisablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="1cb95-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="1cb95-111">Verwenden der Ablaufverfolgung beheben</span><span class="sxs-lookup"><span data-stu-id="1cb95-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="1cb95-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="1cb95-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
