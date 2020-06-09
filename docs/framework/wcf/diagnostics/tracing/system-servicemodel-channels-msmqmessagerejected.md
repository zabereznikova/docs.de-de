---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.date: 03/30/2017
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
ms.openlocfilehash: c388a9dc3569e20639de09abc5f4941b73c561ad
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84578050"
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a><span data-ttu-id="b2b50-102">System.ServiceModel.Channels.MsmqMessageRejected</span><span class="sxs-lookup"><span data-stu-id="b2b50-102">System.ServiceModel.Channels.MsmqMessageRejected</span></span>
<span data-ttu-id="b2b50-103">MSMQ hat die Nachricht abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="b2b50-103">MSMQ rejected the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b2b50-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b2b50-104">Description</span></span>  
 <span data-ttu-id="b2b50-105">Diese Ablaufverfolgung gibt an, dass eine MSMQ-Nachricht abgelehnt wurde.</span><span class="sxs-lookup"><span data-stu-id="b2b50-105">This trace indicates that an MSMQ message was rejected.</span></span>  
  
 <span data-ttu-id="b2b50-106">MSMQ-Nachrichten können abgelehnt werden, wenn Windows Communication Foundation (WCF) (mit NetMsmqBinding oder MsmqIntegrationBinding verwendet) Sie nicht verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="b2b50-106">MSMQ messages can be rejected when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="b2b50-107">Solche Nachrichten werden als beschädigte Nachrichten bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b2b50-107">Such messages are referred to as poison messages.</span></span> <span data-ttu-id="b2b50-108">Eine beschädigte Nachricht wird abgelehnt, wenn die `ReceiveErrorHandling`-Eigenschaft von NetMsmqBinding oder MsmqIntegrationBinding auf `Reject` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b2b50-108">A poison message is rejected when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="b2b50-109">Eine abgelehnte Nachricht wird zurück an die [Warteschlange](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures)für unzustellbare Nachrichten des Absenders übermittelt.</span><span class="sxs-lookup"><span data-stu-id="b2b50-109">A rejected message is delivered back to the sender’s [Dead-Letter Queue](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures).</span></span>  
  
 <span data-ttu-id="b2b50-110">Weitere Informationen darüber, wann Nachrichten beschädigt werden und wie Sie den Dienst so konfigurieren, dass Sie entsprechend behandelt werden, finden Sie unter [Behandlung](../../feature-details/poison-message-handling.md)nicht verarbeitbarer Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="b2b50-110">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
 <span data-ttu-id="b2b50-111">Weitere Informationen dazu, was eine abgelehnte Nachricht in MSMQ bedeutet, finden Sie unter [mqmarkmessagereworfene](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85)).</span><span class="sxs-lookup"><span data-stu-id="b2b50-111">For more information on what a rejected message means in MSMQ, see [MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2b50-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b2b50-112">See also</span></span>

- [<span data-ttu-id="b2b50-113">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="b2b50-113">Tracing</span></span>](index.md)
- [<span data-ttu-id="b2b50-114">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="b2b50-114">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="b2b50-115">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="b2b50-115">Administration and Diagnostics</span></span>](../index.md)
- [<span data-ttu-id="b2b50-116">Behandlung nicht verarbeitbarer Nachrichten</span><span class="sxs-lookup"><span data-stu-id="b2b50-116">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
- <span data-ttu-id="b2b50-117">[Mqmarkmessagereworfene](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span><span class="sxs-lookup"><span data-stu-id="b2b50-117">[MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span></span>
