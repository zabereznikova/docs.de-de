---
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.date: 03/30/2017
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
ms.openlocfilehash: d8edb8e916578247e62e3a3eb3b11b80f93416cd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286954"
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a><span data-ttu-id="3be56-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span><span class="sxs-lookup"><span data-stu-id="3be56-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span></span>

<span data-ttu-id="3be56-103">Eine Ausnahme ist aufgetreten, während die Verbindungen in diesem Verbindungspool geschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="3be56-103">An exception occurred while closing the connections in this connection pool.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3be56-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3be56-104">Description</span></span>  

 <span data-ttu-id="3be56-105">Diese Ablauf Verfolgung auf Fehler Ebene zeigt an, dass beim Schließen der Verbindungspools, die von Windows Communication Foundation (WCF)-Funktion zum Verbindungspooling verwendet werden, ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="3be56-105">This error level trace indicates that an error has occurred while closing the connection pools used by Windows Communication Foundation (WCF)’s connection pooling feature.</span></span> <span data-ttu-id="3be56-106">Eine mögliche Ursache dafür ist das fehlgeschlagene Schließen einer gepoolten Verbindung oder einer Gruppe gepoolter Verbindungen innerhalb des CloseTimeout.</span><span class="sxs-lookup"><span data-stu-id="3be56-106">One possible reason for this is an unsuccessful closure of a pooled connection, or a set of pooled connections within the CloseTimeout.</span></span> <span data-ttu-id="3be56-107">Wenn diese Ausnahme ausgelöst wird, werden die restlichen nicht geschlossenen Verbindungen innerhalb dieses Pools abgebrochen. Nicht geschlossene Verbindungen innerhalb anderer Pools werden aufgegeben.</span><span class="sxs-lookup"><span data-stu-id="3be56-107">When this exception is thrown, any remaining unclosed connections within that pool are aborted; unclosed connections within other pools are abandoned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3be56-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3be56-108">See also</span></span>

- [<span data-ttu-id="3be56-109">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="3be56-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="3be56-110">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="3be56-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="3be56-111">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="3be56-111">Administration and Diagnostics</span></span>](../index.md)
