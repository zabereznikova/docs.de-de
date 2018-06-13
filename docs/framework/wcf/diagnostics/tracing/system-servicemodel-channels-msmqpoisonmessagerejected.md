---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.date: 03/30/2017
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
ms.openlocfilehash: 7dc1e4120caae7c4a592067f5e77ed4f56e82e6b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33478165"
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a><span data-ttu-id="3e698-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span><span class="sxs-lookup"><span data-stu-id="3e698-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span></span>
<span data-ttu-id="3e698-103">Nicht verarbeitbare Nachrichten wurden abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="3e698-103">Poison message rejected.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3e698-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3e698-104">Description</span></span>  
 <span data-ttu-id="3e698-105">Die Ablaufverfolgung gibt an, dass eine nicht verarbeitbare Nachricht erkannt und anschließend abgelehnt wurde.</span><span class="sxs-lookup"><span data-stu-id="3e698-105">The trace indicates that a poison message was encountered and subsequently rejected.</span></span> <span data-ttu-id="3e698-106">Dies geschieht, wenn die `ReceiveErrorHandling`-Eigenschaft von NetMsmqBinding oder MsmqIntegrationBinding auf `Reject` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="3e698-106">This occurs when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="3e698-107">Eine abgelehnte Nachricht wird an des Absenders übermittelt [Dead Letter-Warteschlange](http://go.microsoft.com/fwlink/?LinkId=99544).</span><span class="sxs-lookup"><span data-stu-id="3e698-107">A rejected message is delivered back to the sender’s [Dead-Letter Queue](http://go.microsoft.com/fwlink/?LinkId=99544).</span></span>  
  
 <span data-ttu-id="3e698-108">Finden Sie unter [verarbeitbarer Behandlung von](http://go.microsoft.com/fwlink/?LinkId=99546) detaillierte Informationen auf, wenn Nachrichten werden und wie Sie den Dienst, damit sie richtig verarbeitet konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3e698-108">See [Poison-Message Handling](http://go.microsoft.com/fwlink/?LinkId=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span> <span data-ttu-id="3e698-109">Finden Sie unter [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548) Weitere Informationen zur Bedeutung der einer abgelehnten Nachricht in MSMQ.</span><span class="sxs-lookup"><span data-stu-id="3e698-109">See [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548) for more details on what a rejected message means in MSMQ.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e698-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3e698-110">See Also</span></span>  
 [<span data-ttu-id="3e698-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="3e698-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="3e698-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="3e698-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="3e698-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="3e698-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [<span data-ttu-id="3e698-114">Handhabung beschädigter Nachrichten</span><span class="sxs-lookup"><span data-stu-id="3e698-114">Poison-Message Handling</span></span>](http://go.microsoft.com/fwlink/?LinkId=99546)  
 [<span data-ttu-id="3e698-115">MQMarkMessageRejected</span><span class="sxs-lookup"><span data-stu-id="3e698-115">MQMarkMessageRejected</span></span>](http://go.microsoft.com/fwlink/?LinkId=99548)
