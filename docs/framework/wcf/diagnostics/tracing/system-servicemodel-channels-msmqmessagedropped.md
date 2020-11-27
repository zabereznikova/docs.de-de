---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: 6e8b134f61d2dc9bd5daf541db4ec81604166baa
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96260382"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a><span data-ttu-id="69153-102">System.ServiceModel.Channels.MsmqMessageDropped</span><span class="sxs-lookup"><span data-stu-id="69153-102">System.ServiceModel.Channels.MsmqMessageDropped</span></span>

<span data-ttu-id="69153-103">MSMQ hat die Nachricht verworfen.</span><span class="sxs-lookup"><span data-stu-id="69153-103">MSMQ dropped the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="69153-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="69153-104">Description</span></span>  

 <span data-ttu-id="69153-105">Die Ablaufverfolgung gibt an, dass eine MSMQ-Nachricht gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="69153-105">The trace indicates that an MSMQ message was dropped.</span></span> <span data-ttu-id="69153-106">MSMQ-Nachrichten können gelöscht werden, wenn Windows Communication Foundation (WCF) (das entweder mit NetMsmqBinding oder MsmqIntegrationBinding verwendet wird) nicht verarbeitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="69153-106">MSMQ messages can be dropped when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="69153-107">Solche Nachrichten werden als beschädigte Nachrichten bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="69153-107">Such messages are referred to as poison messages.</span></span>  
  
 <span data-ttu-id="69153-108">Eine beschädigte Nachricht wird gelöscht, wenn die `ReceiveErrorHandling`-Eigenschaft von NetMsmqBinding oder MsmqIntegrationBinding auf `Drop` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="69153-108">A poison message is dropped when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Drop`.</span></span> <span data-ttu-id="69153-109">Eine gelöschte Nachricht wird aus der Warteschlange entfernt und ist nicht mehr wiederherstellbar.</span><span class="sxs-lookup"><span data-stu-id="69153-109">A dropped message is removed from the queue and is no longer recoverable.</span></span>  
  
 <span data-ttu-id="69153-110">Weitere Informationen darüber, wann Nachrichten beschädigt werden und wie Sie den Dienst so konfigurieren, dass Sie entsprechend behandelt werden, finden Sie unter [Behandlung](../../feature-details/poison-message-handling.md)nicht verarbeitbarer Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="69153-110">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69153-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="69153-111">See also</span></span>

- [<span data-ttu-id="69153-112">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="69153-112">Tracing</span></span>](index.md)
- [<span data-ttu-id="69153-113">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="69153-113">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="69153-114">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="69153-114">Administration and Diagnostics</span></span>](../index.md)
- [<span data-ttu-id="69153-115">Behandlung nicht verarbeitbarer Nachrichten</span><span class="sxs-lookup"><span data-stu-id="69153-115">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
