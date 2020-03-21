---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.date: 03/30/2017
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
ms.openlocfilehash: 6b0e6e3ebcf5d414e9dbbcecd09ba2e8bb3ddd3a
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674812"
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a><span data-ttu-id="da3e5-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span><span class="sxs-lookup"><span data-stu-id="da3e5-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span></span>
<span data-ttu-id="da3e5-103">Nicht verarbeitbare Nachrichten wurden abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="da3e5-103">Poison message rejected.</span></span>  
  
## <a name="description"></a><span data-ttu-id="da3e5-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="da3e5-104">Description</span></span>  

 <span data-ttu-id="da3e5-105">Die Ablaufverfolgung gibt an, dass eine nicht verarbeitbare Nachricht erkannt und anschließend abgelehnt wurde.</span><span class="sxs-lookup"><span data-stu-id="da3e5-105">The trace indicates that a poison message was encountered and subsequently rejected.</span></span> <span data-ttu-id="da3e5-106">Dies geschieht, wenn die `ReceiveErrorHandling`-Eigenschaft von NetMsmqBinding oder MsmqIntegrationBinding auf `Reject` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="da3e5-106">This occurs when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="da3e5-107">Eine abgelehnte Nachricht wird an die [Dead-Letter-Warteschlange](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)des Absenders zurückgesendet.</span><span class="sxs-lookup"><span data-stu-id="da3e5-107">A rejected message is delivered back to the sender’s [Dead-Letter Queue](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md).</span></span>  
  
 <span data-ttu-id="da3e5-108">Weitere Informationen dazu, wann Nachrichten zu Gift werden und wie Sie Ihren Dienst so konfigurieren, dass er entsprechend behandelt wird, finden Sie unter [Gift-Nachrichten-Handhabung](../../feature-details/poison-message-handling.md).</span><span class="sxs-lookup"><span data-stu-id="da3e5-108">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span> <span data-ttu-id="da3e5-109">Weitere Informationen darüber, was eine abgelehnte Nachricht in MSMQ bedeutet, finden Sie unter [MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85)).</span><span class="sxs-lookup"><span data-stu-id="da3e5-109">For more information on what a rejected message means in MSMQ, see [MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da3e5-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="da3e5-110">See also</span></span>

- [<span data-ttu-id="da3e5-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="da3e5-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="da3e5-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="da3e5-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="da3e5-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="da3e5-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="da3e5-114">Behandlung nicht verarbeitbarer Nachrichten</span><span class="sxs-lookup"><span data-stu-id="da3e5-114">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
- <span data-ttu-id="da3e5-115">[MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span><span class="sxs-lookup"><span data-stu-id="da3e5-115">[MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span></span>
