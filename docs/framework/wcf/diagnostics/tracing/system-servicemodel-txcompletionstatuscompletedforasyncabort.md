---
title: System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort
ms.date: 03/30/2017
ms.assetid: 155c3203-2e17-4709-b896-2254e22da45e
ms.openlocfilehash: 3d43524b7141a134b9560e92da66ef2349b8119a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631284"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforasyncabort"></a><span data-ttu-id="5cbeb-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="5cbeb-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span></span>
<span data-ttu-id="5cbeb-103">Die angegebene Transaktion für den angegebenen Vorgang wurde aufgrund eines asynchronen Abbruchs abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="5cbeb-103">The specified transaction for the specified operation was completed due to asynchronous abort.</span></span>  
  
## <a name="description"></a><span data-ttu-id="5cbeb-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5cbeb-104">Description</span></span>  
 <span data-ttu-id="5cbeb-105">Die aktuelle Transaktion wurde abgebrochen, weil ein anderer Teilnehmer für den Abbruch votiert hat, weil Zeitüberschreitungen aufgetreten sind oder weil ein anderer Fehler bei einem Teilnehmer einer Transaktion aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="5cbeb-105">The current transaction was aborted due to another participant voting for Abort, time-outs occurring, or another error inside the participant of a transaction.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="5cbeb-106">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="5cbeb-106">Troubleshooting</span></span>  
 <span data-ttu-id="5cbeb-107">Wenn dieser Abbruch unerwartet erfolgt, überprüfen Sie alle Systemprotokolle, um den wirklichen Grund für den Abbruch zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="5cbeb-107">If this abort is unexpected, check all system logs to determine the real reason for the abort.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cbeb-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5cbeb-108">See also</span></span>
- [<span data-ttu-id="5cbeb-109">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="5cbeb-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="5cbeb-110">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="5cbeb-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="5cbeb-111">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="5cbeb-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
