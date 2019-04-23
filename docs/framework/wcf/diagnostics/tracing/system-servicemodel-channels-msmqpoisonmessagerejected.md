---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.date: 03/30/2017
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
ms.openlocfilehash: 562399c1d45dc73c7c88bd165e9f95ee1bcfa19d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59125080"
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a><span data-ttu-id="4ba95-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span><span class="sxs-lookup"><span data-stu-id="4ba95-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span></span>
<span data-ttu-id="4ba95-103">Nicht verarbeitbare Nachrichten wurden abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="4ba95-103">Poison message rejected.</span></span>  
  
## <a name="description"></a><span data-ttu-id="4ba95-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4ba95-104">Description</span></span>  
 <span data-ttu-id="4ba95-105">Die Ablaufverfolgung gibt an, dass eine nicht verarbeitbare Nachricht erkannt und anschließend abgelehnt wurde.</span><span class="sxs-lookup"><span data-stu-id="4ba95-105">The trace indicates that a poison message was encountered and subsequently rejected.</span></span> <span data-ttu-id="4ba95-106">Dies geschieht, wenn die `ReceiveErrorHandling`-Eigenschaft von NetMsmqBinding oder MsmqIntegrationBinding auf `Reject` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="4ba95-106">This occurs when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="4ba95-107">Eine abgelehnte Nachricht wird zurück an des Absenders des übermittelt [Dead Letter-Warteschlange](https://go.microsoft.com/fwlink/?LinkId=99544).</span><span class="sxs-lookup"><span data-stu-id="4ba95-107">A rejected message is delivered back to the sender’s [Dead-Letter Queue](https://go.microsoft.com/fwlink/?LinkId=99544).</span></span>  
  
 <span data-ttu-id="4ba95-108">Finden Sie unter [Behandlung beschädigter Nachrichten](https://go.microsoft.com/fwlink/?LinkId=99546) Weitere Einzelheiten, wann Nachrichten beschädigt werden und wie Sie den Dienst, damit sie richtig verarbeitet konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4ba95-108">See [Poison-Message Handling](https://go.microsoft.com/fwlink/?LinkId=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span> <span data-ttu-id="4ba95-109">Finden Sie unter [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkId=99548) Weitere Einzelheiten, was eine abgelehnte Nachricht in MSMQ bedeutet.</span><span class="sxs-lookup"><span data-stu-id="4ba95-109">See [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkId=99548) for more details on what a rejected message means in MSMQ.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ba95-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ba95-110">See also</span></span>

- [<span data-ttu-id="4ba95-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="4ba95-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="4ba95-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="4ba95-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="4ba95-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="4ba95-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="4ba95-114">Handhabung beschädigter Nachrichten</span><span class="sxs-lookup"><span data-stu-id="4ba95-114">Poison-Message Handling</span></span>](https://go.microsoft.com/fwlink/?LinkId=99546)
- [<span data-ttu-id="4ba95-115">MQMarkMessageRejected</span><span class="sxs-lookup"><span data-stu-id="4ba95-115">MQMarkMessageRejected</span></span>](https://go.microsoft.com/fwlink/?LinkId=99548)
