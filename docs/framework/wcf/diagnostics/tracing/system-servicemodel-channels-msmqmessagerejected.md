---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.date: 03/30/2017
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
ms.openlocfilehash: 87d6e6fc3205fff9bd977ebe77004dfa489098cb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54681221"
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a><span data-ttu-id="4d486-102">System.ServiceModel.Channels.MsmqMessageRejected</span><span class="sxs-lookup"><span data-stu-id="4d486-102">System.ServiceModel.Channels.MsmqMessageRejected</span></span>
<span data-ttu-id="4d486-103">MSMQ hat die Nachricht abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="4d486-103">MSMQ rejected the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="4d486-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4d486-104">Description</span></span>  
 <span data-ttu-id="4d486-105">Diese Ablaufverfolgung gibt an, dass eine MSMQ-Nachricht abgelehnt wurde.</span><span class="sxs-lookup"><span data-stu-id="4d486-105">This trace indicates that an MSMQ message was rejected.</span></span>  
  
 <span data-ttu-id="4d486-106">MSMQ-Nachrichten können abgelehnt werden, wenn Windows Communication Foundation (WCF) (mit NetMsmqBinding oder MsmqIntegrationBinding verwendet) nicht verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="4d486-106">MSMQ messages can be rejected when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="4d486-107">Solche Nachrichten werden als beschädigte Nachrichten bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="4d486-107">Such messages are referred to as poison messages.</span></span> <span data-ttu-id="4d486-108">Eine beschädigte Nachricht wird abgelehnt, wenn die `ReceiveErrorHandling`-Eigenschaft von NetMsmqBinding oder MsmqIntegrationBinding auf `Reject` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="4d486-108">A poison message is rejected when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="4d486-109">Eine abgelehnte Nachricht wird zurück an des Absenders des übermittelt [Dead Letter-Warteschlange](https://go.microsoft.com/fwlink/?LinkID=99544).</span><span class="sxs-lookup"><span data-stu-id="4d486-109">A rejected message is delivered back to the sender’s [Dead-Letter Queue](https://go.microsoft.com/fwlink/?LinkID=99544).</span></span>  
  
 <span data-ttu-id="4d486-110">Finden Sie unter [Behandlung beschädigter Nachrichten](https://go.microsoft.com/fwlink/?LinkID=99546) Weitere Einzelheiten, wann Nachrichten beschädigt werden und wie Sie den Dienst, damit sie richtig verarbeitet konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4d486-110">See [Poison-Message Handling](https://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
 <span data-ttu-id="4d486-111">Finden Sie unter [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkID=99548) Weitere Einzelheiten, was eine abgelehnte Nachricht in MSMQ bedeutet.</span><span class="sxs-lookup"><span data-stu-id="4d486-111">See [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkID=99548) for more details on what a rejected message means in MSMQ.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d486-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d486-112">See also</span></span>
- [<span data-ttu-id="4d486-113">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="4d486-113">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="4d486-114">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="4d486-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="4d486-115">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="4d486-115">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="4d486-116">Handhabung beschädigter Nachrichten</span><span class="sxs-lookup"><span data-stu-id="4d486-116">Poison-Message Handling</span></span>](https://go.microsoft.com/fwlink/?LinkID=99546)
- [<span data-ttu-id="4d486-117">MQMarkMessageRejected</span><span class="sxs-lookup"><span data-stu-id="4d486-117">MQMarkMessageRejected</span></span>](https://go.microsoft.com/fwlink/?LinkID=99548)
