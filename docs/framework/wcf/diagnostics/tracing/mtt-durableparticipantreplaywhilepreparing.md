---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.date: 03/30/2017
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
ms.openlocfilehash: 93354fbdd0c1726280526ca07a8b3dd1c57c8a25
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2019
ms.locfileid: "67486766"
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a><span data-ttu-id="29586-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span><span class="sxs-lookup"><span data-stu-id="29586-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span></span>
<span data-ttu-id="29586-103">Der WS-AT-Protokolldienst hat eine Replay-Nachricht von einem permanenten Teilnehmer empfangen, der nicht auf die Prepare-Nachricht geantwortet hat.</span><span class="sxs-lookup"><span data-stu-id="29586-103">The WS-AT protocol service received a Replay message from a durable participant, which did not respond to Prepare.</span></span> <span data-ttu-id="29586-104">Infolgedessen wurde die Transaktion abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="29586-104">Consequently, the transaction was aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="29586-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="29586-105">Description</span></span>  
 <span data-ttu-id="29586-106">Aufgezeichnet, wenn eine Replay-Nachricht empfangen wird, während ein permanenter Teilnehmer sich immer noch in der Vorbereitung befindet.</span><span class="sxs-lookup"><span data-stu-id="29586-106">Traced if a Replay message is received while a Durable participant is still Preparing.</span></span> <span data-ttu-id="29586-107">Dies ist eine ungültige Nachricht für diesen Zustand, und die Transaktion wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="29586-107">This is an illegal message for this state and the transaction is going to be aborted.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="29586-108">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="29586-108">Troubleshooting</span></span>

<span data-ttu-id="29586-109">Dieser Fehler kann angeben, dass ein permanenter Teilnehmer (einschließlich untergeordneter Transaktions-Manager) nach Fehler wiederhergestellt wurde Es ist jedoch das Transaktionsergebnis nicht genau wissen, und fordert den Status.</span><span class="sxs-lookup"><span data-stu-id="29586-109">Receiving this error can indicate that a Durable participant (including Subordinate TransactionManagers) has recovered from failure; however, it is unsure of the transaction outcome and requests its status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29586-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29586-110">See also</span></span>

- [<span data-ttu-id="29586-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="29586-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="29586-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="29586-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="29586-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="29586-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
