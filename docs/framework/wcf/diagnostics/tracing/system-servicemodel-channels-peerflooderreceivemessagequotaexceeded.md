---
title: System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded
ms.date: 03/30/2017
ms.assetid: b8371d0a-843e-440b-b86a-6996db131cb0
ms.openlocfilehash: 3ce6b3021f47708c222c3ec5a88d474d17106748
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54500990"
---
# <a name="systemservicemodelchannelspeerflooderreceivemessagequotaexceeded"></a><span data-ttu-id="90aaf-102">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span><span class="sxs-lookup"><span data-stu-id="90aaf-102">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span></span>
<span data-ttu-id="90aaf-103">Die Empfangsrate eingehender Nachrichten ist zu hoch.</span><span class="sxs-lookup"><span data-stu-id="90aaf-103">The inbound receive rate of messages is too high.</span></span>  
  
## <a name="description"></a><span data-ttu-id="90aaf-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90aaf-104">Description</span></span>  
 <span data-ttu-id="90aaf-105">Diese Ablaufverfolgung tritt auf, wenn versucht wird, eingehende Nachrichten zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="90aaf-105">This trace occurs when attempting to process inbound messages.</span></span> <span data-ttu-id="90aaf-106">Eine Nachricht konnte nicht an einen bestimmten Nachbarn weitergeleitet werden, da das festgelegte Kontingent für diesen Nachbarn überschritten wurde.</span><span class="sxs-lookup"><span data-stu-id="90aaf-106">A message could not be forwarded to a specific neighbor because the quota set for that neighbor has been exceeded.</span></span> <span data-ttu-id="90aaf-107">Dies tritt auf, wenn ein nicht reagierender Nachbar das Backlog der anstehenden Nachrichten für diesen Nachbarn nicht löst.</span><span class="sxs-lookup"><span data-stu-id="90aaf-107">This occurs when an unresponsive neighbor fails to clear a backlog of messages pending for that neighbor.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="90aaf-108">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="90aaf-108">Troubleshooting</span></span>  
 <span data-ttu-id="90aaf-109">Reduzieren Sie die Rate, mit der Nachrichten innerhalb des Mesh gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="90aaf-109">Reduce the rate at which messages are sent within the mesh.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90aaf-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90aaf-110">See also</span></span>
- [<span data-ttu-id="90aaf-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="90aaf-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="90aaf-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="90aaf-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="90aaf-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="90aaf-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
