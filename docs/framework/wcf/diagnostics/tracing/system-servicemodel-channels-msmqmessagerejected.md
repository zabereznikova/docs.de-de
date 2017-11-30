---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ecbbd8bc0e798388f994432ea2d3f25396f7de97
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a><span data-ttu-id="ccadf-102">System.ServiceModel.Channels.MsmqMessageRejected</span><span class="sxs-lookup"><span data-stu-id="ccadf-102">System.ServiceModel.Channels.MsmqMessageRejected</span></span>
<span data-ttu-id="ccadf-103">MSMQ hat die Nachricht abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="ccadf-103">MSMQ rejected the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ccadf-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ccadf-104">Description</span></span>  
 <span data-ttu-id="ccadf-105">Diese Ablaufverfolgung gibt an, dass eine MSMQ-Nachricht abgelehnt wurde.</span><span class="sxs-lookup"><span data-stu-id="ccadf-105">This trace indicates that an MSMQ message was rejected.</span></span>  
  
 <span data-ttu-id="ccadf-106">MSMQ-Nachrichten können abgelehnt werden, wenn [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (entweder in Verbindung mit NetMsmqBinding oder mit MsmqIntegrationBinding verwendet) sie nicht verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="ccadf-106">MSMQ messages can be rejected when [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="ccadf-107">Solche Nachrichten werden als beschädigte Nachrichten bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ccadf-107">Such messages are referred to as poison messages.</span></span> <span data-ttu-id="ccadf-108">Eine beschädigte Nachricht wird abgelehnt, wenn die `ReceiveErrorHandling`-Eigenschaft von NetMsmqBinding oder MsmqIntegrationBinding auf `Reject` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ccadf-108">A poison message is rejected when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="ccadf-109">Eine abgelehnte Nachricht wird an des Absenders übermittelt [Dead Letter-Warteschlange](http://go.microsoft.com/fwlink/?LinkID=99544).</span><span class="sxs-lookup"><span data-stu-id="ccadf-109">A rejected message is delivered back to the sender’s [Dead-Letter Queue](http://go.microsoft.com/fwlink/?LinkID=99544).</span></span>  
  
 <span data-ttu-id="ccadf-110">Finden Sie unter [verarbeitbarer Behandlung von](http://go.microsoft.com/fwlink/?LinkID=99546) detaillierte Informationen auf, wenn Nachrichten werden und wie Sie den Dienst, damit sie richtig verarbeitet konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ccadf-110">See [Poison-Message Handling](http://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
 <span data-ttu-id="ccadf-111">Finden Sie unter [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkID=99548) Weitere Informationen zur Bedeutung der einer abgelehnten Nachricht in MSMQ.</span><span class="sxs-lookup"><span data-stu-id="ccadf-111">See [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkID=99548) for more details on what a rejected message means in MSMQ.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccadf-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ccadf-112">See Also</span></span>  
 [<span data-ttu-id="ccadf-113">Ereignisablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="ccadf-113">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="ccadf-114">Verwenden der Ablaufverfolgung beheben</span><span class="sxs-lookup"><span data-stu-id="ccadf-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="ccadf-115">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="ccadf-115">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [<span data-ttu-id="ccadf-116">Handhabung beschädigter Nachrichten</span><span class="sxs-lookup"><span data-stu-id="ccadf-116">Poison-Message Handling</span></span>](http://go.microsoft.com/fwlink/?LinkID=99546)  
 [<span data-ttu-id="ccadf-117">MQMarkMessageRejected</span><span class="sxs-lookup"><span data-stu-id="ccadf-117">MQMarkMessageRejected</span></span>](http://go.microsoft.com/fwlink/?LinkID=99548)
