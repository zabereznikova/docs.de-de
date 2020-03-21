---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.date: 03/30/2017
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
ms.openlocfilehash: 8f783dcd4b966ed89c24d724918a3923c5a2d0b1
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674773"
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a><span data-ttu-id="246f7-102">System.ServiceModel.Channels.MsmqMessageRejected</span><span class="sxs-lookup"><span data-stu-id="246f7-102">System.ServiceModel.Channels.MsmqMessageRejected</span></span>
<span data-ttu-id="246f7-103">MSMQ hat die Nachricht abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="246f7-103">MSMQ rejected the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="246f7-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="246f7-104">Description</span></span>  
 <span data-ttu-id="246f7-105">Diese Ablaufverfolgung gibt an, dass eine MSMQ-Nachricht abgelehnt wurde.</span><span class="sxs-lookup"><span data-stu-id="246f7-105">This trace indicates that an MSMQ message was rejected.</span></span>  
  
 <span data-ttu-id="246f7-106">MSMQ-Nachrichten können abgelehnt werden, wenn Windows Communication Foundation (WCF) (wird entweder mit NetMsmqBinding oder MsmqIntegrationBinding) nicht verarbeitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="246f7-106">MSMQ messages can be rejected when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="246f7-107">Solche Nachrichten werden als beschädigte Nachrichten bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="246f7-107">Such messages are referred to as poison messages.</span></span> <span data-ttu-id="246f7-108">Eine beschädigte Nachricht wird abgelehnt, wenn die `ReceiveErrorHandling`-Eigenschaft von NetMsmqBinding oder MsmqIntegrationBinding auf `Reject` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="246f7-108">A poison message is rejected when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="246f7-109">Eine abgelehnte Nachricht wird an die [Dead-Letter-Warteschlange](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures)des Absenders zurückgesendet.</span><span class="sxs-lookup"><span data-stu-id="246f7-109">A rejected message is delivered back to the sender’s [Dead-Letter Queue](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures).</span></span>  
  
 <span data-ttu-id="246f7-110">Weitere Informationen dazu, wann Nachrichten zu Gift werden und wie Sie Ihren Dienst so konfigurieren, dass er entsprechend behandelt wird, finden Sie unter [Gift-Nachrichten-Handhabung](../../feature-details/poison-message-handling.md).</span><span class="sxs-lookup"><span data-stu-id="246f7-110">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
 <span data-ttu-id="246f7-111">Weitere Informationen darüber, was eine abgelehnte Nachricht in MSMQ bedeutet, finden Sie unter [MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85)).</span><span class="sxs-lookup"><span data-stu-id="246f7-111">For more information on what a rejected message means in MSMQ, see [MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="246f7-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="246f7-112">See also</span></span>

- [<span data-ttu-id="246f7-113">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="246f7-113">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="246f7-114">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="246f7-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="246f7-115">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="246f7-115">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="246f7-116">Behandlung nicht verarbeitbarer Nachrichten</span><span class="sxs-lookup"><span data-stu-id="246f7-116">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
- <span data-ttu-id="246f7-117">[MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span><span class="sxs-lookup"><span data-stu-id="246f7-117">[MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span></span>
