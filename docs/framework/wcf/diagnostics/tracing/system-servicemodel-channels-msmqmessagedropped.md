---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1d4b819b47d682a81bdcc031cc6b09604b072be7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a><span data-ttu-id="8215e-102">System.ServiceModel.Channels.MsmqMessageDropped</span><span class="sxs-lookup"><span data-stu-id="8215e-102">System.ServiceModel.Channels.MsmqMessageDropped</span></span>
<span data-ttu-id="8215e-103">MSMQ hat die Nachricht verworfen.</span><span class="sxs-lookup"><span data-stu-id="8215e-103">MSMQ dropped the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8215e-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8215e-104">Description</span></span>  
 <span data-ttu-id="8215e-105">Die Ablaufverfolgung gibt an, dass eine MSMQ-Nachricht gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="8215e-105">The trace indicates that an MSMQ message was dropped.</span></span> <span data-ttu-id="8215e-106">MSMQ-Nachrichten können gelöscht werden, wenn [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (unter Verwendung von NetMsmqBinding oder MsmqIntegrationBinding) sie nicht verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="8215e-106">MSMQ messages can be dropped when [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="8215e-107">Solche Nachrichten werden als beschädigte Nachrichten bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="8215e-107">Such messages are referred to as poison messages.</span></span>  
  
 <span data-ttu-id="8215e-108">Eine beschädigte Nachricht wird gelöscht, wenn die `ReceiveErrorHandling`-Eigenschaft von NetMsmqBinding oder MsmqIntegrationBinding auf `Drop` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="8215e-108">A poison message is dropped when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Drop`.</span></span> <span data-ttu-id="8215e-109">Eine gelöschte Nachricht wird aus der Warteschlange entfernt und ist nicht mehr wiederherstellbar.</span><span class="sxs-lookup"><span data-stu-id="8215e-109">A dropped message is removed from the queue and is no longer recoverable.</span></span>  
  
 <span data-ttu-id="8215e-110">Finden Sie unter [verarbeitbarer Behandlung von](http://go.microsoft.com/fwlink/?LinkID=99546) detaillierte Informationen auf, wenn Nachrichten werden und wie Sie den Dienst, damit sie richtig verarbeitet konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8215e-110">See [Poison-Message Handling](http://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8215e-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8215e-111">See Also</span></span>  
 [<span data-ttu-id="8215e-112">Ereignisablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="8215e-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="8215e-113">Verwenden der Ablaufverfolgung beheben</span><span class="sxs-lookup"><span data-stu-id="8215e-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="8215e-114">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="8215e-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [<span data-ttu-id="8215e-115">Handhabung beschädigter Nachrichten</span><span class="sxs-lookup"><span data-stu-id="8215e-115">Poison-Message Handling</span></span>](http://go.microsoft.com/fwlink/?LinkID=99546)
