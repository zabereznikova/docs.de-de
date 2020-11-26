---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.date: 03/30/2017
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
ms.openlocfilehash: bfa279887339f025e4cb7c9c455fd25098684073
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236610"
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a><span data-ttu-id="c1437-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span><span class="sxs-lookup"><span data-stu-id="c1437-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span></span>

<span data-ttu-id="c1437-103">Der WS-AT-Protokolldienst hat eine Replay-Nachricht von einem permanenten Teilnehmer empfangen, der nicht auf die Prepare-Nachricht geantwortet hat.</span><span class="sxs-lookup"><span data-stu-id="c1437-103">The WS-AT protocol service received a Replay message from a durable participant, which did not respond to Prepare.</span></span> <span data-ttu-id="c1437-104">Infolgedessen wurde die Transaktion abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="c1437-104">Consequently, the transaction was aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c1437-105">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c1437-105">Description</span></span>  

 <span data-ttu-id="c1437-106">Aufgezeichnet, wenn eine Replay-Nachricht empfangen wird, während ein permanenter Teilnehmer sich immer noch in der Vorbereitung befindet.</span><span class="sxs-lookup"><span data-stu-id="c1437-106">Traced if a Replay message is received while a Durable participant is still Preparing.</span></span> <span data-ttu-id="c1437-107">Dies ist eine ungültige Nachricht für diesen Zustand, und die Transaktion wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="c1437-107">This is an illegal message for this state and the transaction is going to be aborted.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="c1437-108">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="c1437-108">Troubleshooting</span></span>

<span data-ttu-id="c1437-109">Der Empfang dieses Fehlers kann darauf hindeuten, dass ein dauerhafter Teilnehmer (einschließlich untergeordneter transactionmanagers) nach einem Fehler wieder hergestellt wurde. Es ist jedoch nicht sicher, dass das Transaktions Ergebnis nicht sicher ist, und fordert seinen Status an.</span><span class="sxs-lookup"><span data-stu-id="c1437-109">Receiving this error can indicate that a Durable participant (including Subordinate TransactionManagers) has recovered from failure; however, it is unsure of the transaction outcome and requests its status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1437-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c1437-110">See also</span></span>

- [<span data-ttu-id="c1437-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="c1437-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="c1437-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="c1437-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="c1437-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="c1437-113">Administration and Diagnostics</span></span>](../index.md)
