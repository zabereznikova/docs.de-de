---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: 07bef8b391a03f2c011e1d1a7c7fb4fad908e022
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2018
ms.locfileid: "47199813"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a><span data-ttu-id="bebeb-102">System.ServiceModel.Channels.MsmqMessageDropped</span><span class="sxs-lookup"><span data-stu-id="bebeb-102">System.ServiceModel.Channels.MsmqMessageDropped</span></span>
<span data-ttu-id="bebeb-103">MSMQ hat die Nachricht verworfen.</span><span class="sxs-lookup"><span data-stu-id="bebeb-103">MSMQ dropped the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="bebeb-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bebeb-104">Description</span></span>  
 <span data-ttu-id="bebeb-105">Die Ablaufverfolgung gibt an, dass eine MSMQ-Nachricht gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="bebeb-105">The trace indicates that an MSMQ message was dropped.</span></span> <span data-ttu-id="bebeb-106">MSMQ-Nachrichten können gelöscht werden, wenn Windows Communication Foundation (WCF) (mit NetMsmqBinding oder MsmqIntegrationBinding verwendet) nicht verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="bebeb-106">MSMQ messages can be dropped when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="bebeb-107">Solche Nachrichten werden als beschädigte Nachrichten bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="bebeb-107">Such messages are referred to as poison messages.</span></span>  
  
 <span data-ttu-id="bebeb-108">Eine beschädigte Nachricht wird gelöscht, wenn die `ReceiveErrorHandling`-Eigenschaft von NetMsmqBinding oder MsmqIntegrationBinding auf `Drop` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="bebeb-108">A poison message is dropped when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Drop`.</span></span> <span data-ttu-id="bebeb-109">Eine gelöschte Nachricht wird aus der Warteschlange entfernt und ist nicht mehr wiederherstellbar.</span><span class="sxs-lookup"><span data-stu-id="bebeb-109">A dropped message is removed from the queue and is no longer recoverable.</span></span>  
  
 <span data-ttu-id="bebeb-110">Finden Sie unter [Behandlung beschädigter Nachrichten](https://go.microsoft.com/fwlink/?LinkID=99546) Weitere Einzelheiten, wann Nachrichten beschädigt werden und wie Sie den Dienst, damit sie richtig verarbeitet konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="bebeb-110">See [Poison-Message Handling](https://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bebeb-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bebeb-111">See Also</span></span>  
 [<span data-ttu-id="bebeb-112">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="bebeb-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="bebeb-113">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="bebeb-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="bebeb-114">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="bebeb-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [<span data-ttu-id="bebeb-115">Handhabung beschädigter Nachrichten</span><span class="sxs-lookup"><span data-stu-id="bebeb-115">Poison-Message Handling</span></span>](https://go.microsoft.com/fwlink/?LinkID=99546)
