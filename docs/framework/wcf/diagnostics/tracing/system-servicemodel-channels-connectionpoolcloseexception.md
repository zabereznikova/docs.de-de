---
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.date: 03/30/2017
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
ms.openlocfilehash: 3dd28276cd3a39497c0387f5b9d0adec23d07c37
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666832"
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a><span data-ttu-id="6b012-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span><span class="sxs-lookup"><span data-stu-id="6b012-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span></span>
<span data-ttu-id="6b012-103">Eine Ausnahme ist aufgetreten, während die Verbindungen in diesem Verbindungspool geschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="6b012-103">An exception occurred while closing the connections in this connection pool.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6b012-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6b012-104">Description</span></span>  
 <span data-ttu-id="6b012-105">Diese Ablaufverfolgung auf Fehlerebene gibt an, dass ein Fehler aufgetreten ist, während die Verbindungspools geschlossen, die von Windows Communication Foundation (WCF) Verbindungspooling-Funktion verwendet.</span><span class="sxs-lookup"><span data-stu-id="6b012-105">This error level trace indicates that an error has occurred while closing the connection pools used by Windows Communication Foundation (WCF)’s connection pooling feature.</span></span> <span data-ttu-id="6b012-106">Eine mögliche Ursache dafür ist das fehlgeschlagene Schließen einer gepoolten Verbindung oder einer Gruppe gepoolter Verbindungen innerhalb des CloseTimeout.</span><span class="sxs-lookup"><span data-stu-id="6b012-106">One possible reason for this is an unsuccessful closure of a pooled connection, or a set of pooled connections within the CloseTimeout.</span></span> <span data-ttu-id="6b012-107">Wenn diese Ausnahme ausgelöst wird, werden die restlichen nicht geschlossenen Verbindungen innerhalb dieses Pools abgebrochen. Nicht geschlossene Verbindungen innerhalb anderer Pools werden aufgegeben.</span><span class="sxs-lookup"><span data-stu-id="6b012-107">When this exception is thrown, any remaining unclosed connections within that pool are aborted; unclosed connections within other pools are abandoned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b012-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b012-108">See also</span></span>

- [<span data-ttu-id="6b012-109">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="6b012-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="6b012-110">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="6b012-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="6b012-111">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="6b012-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
