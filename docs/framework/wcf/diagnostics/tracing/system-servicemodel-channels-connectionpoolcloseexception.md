---
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0ea98388efe14ac0d18a94ec056a441096a4d7c0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a><span data-ttu-id="838f9-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span><span class="sxs-lookup"><span data-stu-id="838f9-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span></span>
<span data-ttu-id="838f9-103">Eine Ausnahme ist aufgetreten, während die Verbindungen in diesem Verbindungspool geschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="838f9-103">An exception occurred while closing the connections in this connection pool.</span></span>  
  
## <a name="description"></a><span data-ttu-id="838f9-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="838f9-104">Description</span></span>  
 <span data-ttu-id="838f9-105">Diese Ablaufverfolgung auf Fehlerebene gibt an, dass der Fehler aufgetreten ist, während die Verbindungspools geschlossen wurden, die von der Funktion für Verbindungspooling von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="838f9-105">This error level trace indicates that an error has occurred while closing the connection pools used by [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]’s connection pooling feature.</span></span> <span data-ttu-id="838f9-106">Eine mögliche Ursache dafür ist das fehlgeschlagene Schließen einer gepoolten Verbindung oder einer Gruppe gepoolter Verbindungen innerhalb des CloseTimeout.</span><span class="sxs-lookup"><span data-stu-id="838f9-106">One possible reason for this is an unsuccessful closure of a pooled connection, or a set of pooled connections within the CloseTimeout.</span></span> <span data-ttu-id="838f9-107">Wenn diese Ausnahme ausgelöst wird, werden die restlichen nicht geschlossenen Verbindungen innerhalb dieses Pools abgebrochen. Nicht geschlossene Verbindungen innerhalb anderer Pools werden aufgegeben.</span><span class="sxs-lookup"><span data-stu-id="838f9-107">When this exception is thrown, any remaining unclosed connections within that pool are aborted; unclosed connections within other pools are abandoned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="838f9-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="838f9-108">See Also</span></span>  
 [<span data-ttu-id="838f9-109">Ereignisablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="838f9-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="838f9-110">Verwenden der Ablaufverfolgung beheben</span><span class="sxs-lookup"><span data-stu-id="838f9-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="838f9-111">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="838f9-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
