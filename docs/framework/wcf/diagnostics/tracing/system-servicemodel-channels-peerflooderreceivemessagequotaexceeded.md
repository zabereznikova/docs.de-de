---
title: System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b8371d0a-843e-440b-b86a-6996db131cb0
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 136baabc0760826aa9ba76dc19862c9c4b60e16e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelspeerflooderreceivemessagequotaexceeded"></a><span data-ttu-id="275b8-102">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span><span class="sxs-lookup"><span data-stu-id="275b8-102">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span></span>
<span data-ttu-id="275b8-103">Die Empfangsrate eingehender Nachrichten ist zu hoch.</span><span class="sxs-lookup"><span data-stu-id="275b8-103">The inbound receive rate of messages is too high.</span></span>  
  
## <a name="description"></a><span data-ttu-id="275b8-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="275b8-104">Description</span></span>  
 <span data-ttu-id="275b8-105">Diese Ablaufverfolgung tritt auf, wenn versucht wird, eingehende Nachrichten zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="275b8-105">This trace occurs when attempting to process inbound messages.</span></span> <span data-ttu-id="275b8-106">Eine Nachricht konnte nicht an einen bestimmten Nachbarn weitergeleitet werden, da das festgelegte Kontingent für diesen Nachbarn überschritten wurde.</span><span class="sxs-lookup"><span data-stu-id="275b8-106">A message could not be forwarded to a specific neighbor because the quota set for that neighbor has been exceeded.</span></span> <span data-ttu-id="275b8-107">Dies tritt auf, wenn ein nicht reagierender Nachbar das Backlog der anstehenden Nachrichten für diesen Nachbarn nicht löst.</span><span class="sxs-lookup"><span data-stu-id="275b8-107">This occurs when an unresponsive neighbor fails to clear a backlog of messages pending for that neighbor.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="275b8-108">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="275b8-108">Troubleshooting</span></span>  
 <span data-ttu-id="275b8-109">Reduzieren Sie die Rate, mit der Nachrichten innerhalb des Mesh gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="275b8-109">Reduce the rate at which messages are sent within the mesh.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="275b8-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="275b8-110">See Also</span></span>  
 [<span data-ttu-id="275b8-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="275b8-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="275b8-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="275b8-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="275b8-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="275b8-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
