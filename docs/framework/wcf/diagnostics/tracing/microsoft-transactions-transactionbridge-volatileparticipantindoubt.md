---
title: Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt
ms.date: 03/30/2017
ms.assetid: 3e8fc825-9f22-47e7-9c16-d64ef291c932
ms.openlocfilehash: b25debfd9b1e6de6b93fd4dfa8b96925718d9d87
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550837"
---
# <a name="microsofttransactionstransactionbridgevolatileparticipantindoubt"></a><span data-ttu-id="4cd1c-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span><span class="sxs-lookup"><span data-stu-id="4cd1c-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span></span>
<span data-ttu-id="4cd1c-103">Der WS-AT-Protokolldienst hat eine Prepared- oder eine Replay-Nachricht von einem nicht erkannten flüchtigen Teilnehmer empfangen.</span><span class="sxs-lookup"><span data-stu-id="4cd1c-103">The WS-AT protocol service received a Prepared or Replay message from an unrecognized volatile participant.</span></span> <span data-ttu-id="4cd1c-104">Dem Teilnehmer wurde ein Fehler zurückgegeben, der aussagt, dass das Ergebnis der Transaktion zweifelhaft ist.</span><span class="sxs-lookup"><span data-stu-id="4cd1c-104">A fault was returned to the participant, declares that the transaction's outcome is in doubt.</span></span>  
  
## <a name="description"></a><span data-ttu-id="4cd1c-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4cd1c-105">Description</span></span>  
 <span data-ttu-id="4cd1c-106">Verfolgt nach, wann der lokale Transaction Manager eine Prepared- oder Replay-Nachricht von einer flüchtigen Eintragung erhält, die er bereits vergessen hat.</span><span class="sxs-lookup"><span data-stu-id="4cd1c-106">Traced when the local Transaction Manager receives a Prepared or Replay message from a Volatile enlistment that it has already forgotten.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="4cd1c-107">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="4cd1c-107">Troubleshooting</span></span>  
 <span data-ttu-id="4cd1c-108">Untersuchen Sie die potenziellen Ursachen von verspätet ankommenden Nachrichten vom flüchtigen Teilnehmer.</span><span class="sxs-lookup"><span data-stu-id="4cd1c-108">Investigate potential causes of late messages coming from the Volatile participant.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cd1c-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4cd1c-109">See also</span></span>
- [<span data-ttu-id="4cd1c-110">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="4cd1c-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="4cd1c-111">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="4cd1c-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="4cd1c-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="4cd1c-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
