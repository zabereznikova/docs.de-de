---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.date: 03/30/2017
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
ms.openlocfilehash: 69da35f65e04a3cba15885c4fe6e57d63762cb1c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96260343"
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a><span data-ttu-id="35b9f-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span><span class="sxs-lookup"><span data-stu-id="35b9f-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span></span>

<span data-ttu-id="35b9f-103">Nicht verarbeitbare Nachrichten wurden abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="35b9f-103">Poison message rejected.</span></span>  
  
## <a name="description"></a><span data-ttu-id="35b9f-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="35b9f-104">Description</span></span>  

 <span data-ttu-id="35b9f-105">Die Ablaufverfolgung gibt an, dass eine nicht verarbeitbare Nachricht erkannt und anschließend abgelehnt wurde.</span><span class="sxs-lookup"><span data-stu-id="35b9f-105">The trace indicates that a poison message was encountered and subsequently rejected.</span></span> <span data-ttu-id="35b9f-106">Dies geschieht, wenn die `ReceiveErrorHandling`-Eigenschaft von NetMsmqBinding oder MsmqIntegrationBinding auf `Reject` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="35b9f-106">This occurs when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="35b9f-107">Eine abgelehnte Nachricht wird zurück an die [Warteschlange](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)für unzustellbare Nachrichten des Absenders übermittelt.</span><span class="sxs-lookup"><span data-stu-id="35b9f-107">A rejected message is delivered back to the sender’s [Dead-Letter Queue](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md).</span></span>  
  
 <span data-ttu-id="35b9f-108">Weitere Informationen darüber, wann Nachrichten beschädigt werden und wie Sie den Dienst so konfigurieren, dass Sie entsprechend behandelt werden, finden Sie unter [Behandlung](../../feature-details/poison-message-handling.md)nicht verarbeitbarer Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="35b9f-108">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span> <span data-ttu-id="35b9f-109">Weitere Informationen dazu, was eine abgelehnte Nachricht in MSMQ bedeutet, finden Sie unter [mqmarkmessagereworfene](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="35b9f-109">For more information on what a rejected message means in MSMQ, see [MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35b9f-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="35b9f-110">See also</span></span>

- [<span data-ttu-id="35b9f-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="35b9f-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="35b9f-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="35b9f-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="35b9f-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="35b9f-113">Administration and Diagnostics</span></span>](../index.md)
- [<span data-ttu-id="35b9f-114">Behandlung nicht verarbeitbarer Nachrichten</span><span class="sxs-lookup"><span data-stu-id="35b9f-114">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
- <span data-ttu-id="35b9f-115">[Mqmarkmessagereworfene](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="35b9f-115">[MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85))</span></span>
