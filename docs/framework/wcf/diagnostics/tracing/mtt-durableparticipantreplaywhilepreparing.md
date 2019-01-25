---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.date: 03/30/2017
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
ms.openlocfilehash: 3b51a100677221866186b2e24f34396c012d11c1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603130"
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a><span data-ttu-id="6b2b2-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span><span class="sxs-lookup"><span data-stu-id="6b2b2-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span></span>
<span data-ttu-id="6b2b2-103">Der WS-AT-Protokolldienst hat eine Replay-Nachricht von einem permanenten Teilnehmer empfangen, der nicht auf die Prepare-Nachricht geantwortet hat.</span><span class="sxs-lookup"><span data-stu-id="6b2b2-103">The WS-AT protocol service received a Replay message from a durable participant, which did not respond to Prepare.</span></span> <span data-ttu-id="6b2b2-104">Infolgedessen wurde die Transaktion abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="6b2b2-104">Consequently, the transaction was aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6b2b2-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6b2b2-105">Description</span></span>  
 <span data-ttu-id="6b2b2-106">Aufgezeichnet, wenn eine Replay-Nachricht empfangen wird, während ein permanenter Teilnehmer sich immer noch in der Vorbereitung befindet.</span><span class="sxs-lookup"><span data-stu-id="6b2b2-106">Traced if a Replay message is received while a Durable participant is still Preparing.</span></span> <span data-ttu-id="6b2b2-107">Dies ist eine ungültige Nachricht für diesen Zustand, und die Transaktion wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="6b2b2-107">This is an illegal message for this state and the transaction is going to be aborted.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="6b2b2-108">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="6b2b2-108">Troubleshooting</span></span>  
 <span data-ttu-id="6b2b2-109">Dieser Fehler kann darauf hinweisen, dass ein permanenter Teilnehmer (einschließlich untergeordneter Transaktions-Manager) nach einem Fehler wiederhergestellt wurde, das Transaktionsergebnis jedoch unsicher ist und der Zustand daher angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="6b2b2-109">Receiving this error can indiate that a Durable participant (including Subordinate TransactionManagers) has recovered from failure, however it is unsure of the transaction outcome and request its status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b2b2-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b2b2-110">See also</span></span>
- [<span data-ttu-id="6b2b2-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="6b2b2-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="6b2b2-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="6b2b2-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="6b2b2-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="6b2b2-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
