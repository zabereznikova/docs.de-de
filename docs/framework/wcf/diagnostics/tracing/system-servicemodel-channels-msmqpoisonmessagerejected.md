---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.date: 03/30/2017
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
ms.openlocfilehash: c5401bae1d8e7f61939d8de321353f59f412f966
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90535332"
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a><span data-ttu-id="a9384-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span><span class="sxs-lookup"><span data-stu-id="a9384-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span></span>
<span data-ttu-id="a9384-103">Nicht verarbeitbare Nachrichten wurden abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="a9384-103">Poison message rejected.</span></span>  
  
## <a name="description"></a><span data-ttu-id="a9384-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a9384-104">Description</span></span>  

 <span data-ttu-id="a9384-105">Die Ablaufverfolgung gibt an, dass eine nicht verarbeitbare Nachricht erkannt und anschließend abgelehnt wurde.</span><span class="sxs-lookup"><span data-stu-id="a9384-105">The trace indicates that a poison message was encountered and subsequently rejected.</span></span> <span data-ttu-id="a9384-106">Dies geschieht, wenn die `ReceiveErrorHandling`-Eigenschaft von NetMsmqBinding oder MsmqIntegrationBinding auf `Reject` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="a9384-106">This occurs when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="a9384-107">Eine abgelehnte Nachricht wird zurück an die [Warteschlange](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)für unzustellbare Nachrichten des Absenders übermittelt.</span><span class="sxs-lookup"><span data-stu-id="a9384-107">A rejected message is delivered back to the sender’s [Dead-Letter Queue](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md).</span></span>  
  
 <span data-ttu-id="a9384-108">Weitere Informationen darüber, wann Nachrichten beschädigt werden und wie Sie den Dienst so konfigurieren, dass Sie entsprechend behandelt werden, finden Sie unter [Behandlung](../../feature-details/poison-message-handling.md)nicht verarbeitbarer Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="a9384-108">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span> <span data-ttu-id="a9384-109">Weitere Informationen dazu, was eine abgelehnte Nachricht in MSMQ bedeutet, finden Sie unter [mqmarkmessagereworfene](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="a9384-109">For more information on what a rejected message means in MSMQ, see [MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9384-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9384-110">See also</span></span>

- [<span data-ttu-id="a9384-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="a9384-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="a9384-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="a9384-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="a9384-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="a9384-113">Administration and Diagnostics</span></span>](../index.md)
- [<span data-ttu-id="a9384-114">Behandlung nicht verarbeitbarer Nachrichten</span><span class="sxs-lookup"><span data-stu-id="a9384-114">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
- <span data-ttu-id="a9384-115">[Mqmarkmessagereworfene](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="a9384-115">[MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85))</span></span>
