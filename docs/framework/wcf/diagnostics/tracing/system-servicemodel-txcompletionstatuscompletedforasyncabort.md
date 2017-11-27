---
title: System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 155c3203-2e17-4709-b896-2254e22da45e
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3595b98ca8c78fb6bdf86a08dcd56b37a4770405
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodeltxcompletionstatuscompletedforasyncabort"></a><span data-ttu-id="c0073-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="c0073-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span></span>
<span data-ttu-id="c0073-103">Die angegebene Transaktion für den angegebenen Vorgang wurde aufgrund eines asynchronen Abbruchs abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="c0073-103">The specified transaction for the specified operation was completed due to asynchronous abort.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c0073-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c0073-104">Description</span></span>  
 <span data-ttu-id="c0073-105">Die aktuelle Transaktion wurde abgebrochen, weil ein anderer Teilnehmer für den Abbruch votiert hat, weil Zeitüberschreitungen aufgetreten sind oder weil ein anderer Fehler bei einem Teilnehmer einer Transaktion aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="c0073-105">The current transaction was aborted due to another participant voting for Abort, time-outs occurring, or another error inside the participant of a transaction.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="c0073-106">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="c0073-106">Troubleshooting</span></span>  
 <span data-ttu-id="c0073-107">Wenn dieser Abbruch unerwartet erfolgt, überprüfen Sie alle Systemprotokolle, um den wirklichen Grund für den Abbruch zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="c0073-107">If this abort is unexpected, check all system logs to determine the real reason for the abort.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0073-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0073-108">See Also</span></span>  
 [<span data-ttu-id="c0073-109">Ereignisablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="c0073-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="c0073-110">Verwenden der Ablaufverfolgung beheben</span><span class="sxs-lookup"><span data-stu-id="c0073-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="c0073-111">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="c0073-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
