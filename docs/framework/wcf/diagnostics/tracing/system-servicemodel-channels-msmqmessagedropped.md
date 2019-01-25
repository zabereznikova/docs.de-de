---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: 6218948e89288e76034d7c3f032f3c585e286c3d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54570537"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a><span data-ttu-id="868e9-102">System.ServiceModel.Channels.MsmqMessageDropped</span><span class="sxs-lookup"><span data-stu-id="868e9-102">System.ServiceModel.Channels.MsmqMessageDropped</span></span>
<span data-ttu-id="868e9-103">MSMQ hat die Nachricht verworfen.</span><span class="sxs-lookup"><span data-stu-id="868e9-103">MSMQ dropped the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="868e9-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="868e9-104">Description</span></span>  
 <span data-ttu-id="868e9-105">Die Ablaufverfolgung gibt an, dass eine MSMQ-Nachricht gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="868e9-105">The trace indicates that an MSMQ message was dropped.</span></span> <span data-ttu-id="868e9-106">MSMQ-Nachrichten können gelöscht werden, wenn Windows Communication Foundation (WCF) (mit NetMsmqBinding oder MsmqIntegrationBinding verwendet) nicht verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="868e9-106">MSMQ messages can be dropped when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="868e9-107">Solche Nachrichten werden als beschädigte Nachrichten bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="868e9-107">Such messages are referred to as poison messages.</span></span>  
  
 <span data-ttu-id="868e9-108">Eine beschädigte Nachricht wird gelöscht, wenn die `ReceiveErrorHandling`-Eigenschaft von NetMsmqBinding oder MsmqIntegrationBinding auf `Drop` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="868e9-108">A poison message is dropped when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Drop`.</span></span> <span data-ttu-id="868e9-109">Eine gelöschte Nachricht wird aus der Warteschlange entfernt und ist nicht mehr wiederherstellbar.</span><span class="sxs-lookup"><span data-stu-id="868e9-109">A dropped message is removed from the queue and is no longer recoverable.</span></span>  
  
 <span data-ttu-id="868e9-110">Finden Sie unter [Behandlung beschädigter Nachrichten](https://go.microsoft.com/fwlink/?LinkID=99546) Weitere Einzelheiten, wann Nachrichten beschädigt werden und wie Sie den Dienst, damit sie richtig verarbeitet konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="868e9-110">See [Poison-Message Handling](https://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="868e9-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="868e9-111">See also</span></span>
- [<span data-ttu-id="868e9-112">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="868e9-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="868e9-113">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="868e9-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="868e9-114">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="868e9-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="868e9-115">Handhabung beschädigter Nachrichten</span><span class="sxs-lookup"><span data-stu-id="868e9-115">Poison-Message Handling</span></span>](https://go.microsoft.com/fwlink/?LinkID=99546)
