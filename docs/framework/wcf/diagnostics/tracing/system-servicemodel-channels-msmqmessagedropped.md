---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: e80fecf508158dcb53f08b75c8f9486c13e403a4
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674797"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a><span data-ttu-id="ad93c-102">System.ServiceModel.Channels.MsmqMessageDropped</span><span class="sxs-lookup"><span data-stu-id="ad93c-102">System.ServiceModel.Channels.MsmqMessageDropped</span></span>
<span data-ttu-id="ad93c-103">MSMQ hat die Nachricht verworfen.</span><span class="sxs-lookup"><span data-stu-id="ad93c-103">MSMQ dropped the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ad93c-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ad93c-104">Description</span></span>  
 <span data-ttu-id="ad93c-105">Die Ablaufverfolgung gibt an, dass eine MSMQ-Nachricht gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="ad93c-105">The trace indicates that an MSMQ message was dropped.</span></span> <span data-ttu-id="ad93c-106">MSMQ-Nachrichten können gelöscht werden, wenn Windows Communication Foundation (WCF) (wird entweder mit NetMsmqBinding oder MsmqIntegrationBinding verwendet) nicht verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="ad93c-106">MSMQ messages can be dropped when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="ad93c-107">Solche Nachrichten werden als beschädigte Nachrichten bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ad93c-107">Such messages are referred to as poison messages.</span></span>  
  
 <span data-ttu-id="ad93c-108">Eine beschädigte Nachricht wird gelöscht, wenn die `ReceiveErrorHandling`-Eigenschaft von NetMsmqBinding oder MsmqIntegrationBinding auf `Drop` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ad93c-108">A poison message is dropped when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Drop`.</span></span> <span data-ttu-id="ad93c-109">Eine gelöschte Nachricht wird aus der Warteschlange entfernt und ist nicht mehr wiederherstellbar.</span><span class="sxs-lookup"><span data-stu-id="ad93c-109">A dropped message is removed from the queue and is no longer recoverable.</span></span>  
  
 <span data-ttu-id="ad93c-110">Weitere Informationen dazu, wann Nachrichten zu Gift werden und wie Sie Ihren Dienst so konfigurieren, dass er entsprechend behandelt wird, finden Sie unter [Gift-Nachrichten-Handhabung](../../feature-details/poison-message-handling.md).</span><span class="sxs-lookup"><span data-stu-id="ad93c-110">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad93c-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ad93c-111">See also</span></span>

- [<span data-ttu-id="ad93c-112">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="ad93c-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="ad93c-113">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="ad93c-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="ad93c-114">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="ad93c-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="ad93c-115">Behandlung nicht verarbeitbarer Nachrichten</span><span class="sxs-lookup"><span data-stu-id="ad93c-115">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
