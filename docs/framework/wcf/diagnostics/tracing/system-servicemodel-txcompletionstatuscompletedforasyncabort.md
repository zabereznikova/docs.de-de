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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2a99e8b3158da9d473d50bc7792ce9e2aa19bb27
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodeltxcompletionstatuscompletedforasyncabort"></a><span data-ttu-id="2ca94-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="2ca94-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span></span>
<span data-ttu-id="2ca94-103">Die angegebene Transaktion für den angegebenen Vorgang wurde aufgrund eines asynchronen Abbruchs abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="2ca94-103">The specified transaction for the specified operation was completed due to asynchronous abort.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2ca94-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ca94-104">Description</span></span>  
 <span data-ttu-id="2ca94-105">Die aktuelle Transaktion wurde abgebrochen, weil ein anderer Teilnehmer für den Abbruch votiert hat, weil Zeitüberschreitungen aufgetreten sind oder weil ein anderer Fehler bei einem Teilnehmer einer Transaktion aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="2ca94-105">The current transaction was aborted due to another participant voting for Abort, time-outs occurring, or another error inside the participant of a transaction.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="2ca94-106">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="2ca94-106">Troubleshooting</span></span>  
 <span data-ttu-id="2ca94-107">Wenn dieser Abbruch unerwartet erfolgt, überprüfen Sie alle Systemprotokolle, um den wirklichen Grund für den Abbruch zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="2ca94-107">If this abort is unexpected, check all system logs to determine the real reason for the abort.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ca94-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ca94-108">See Also</span></span>  
 [<span data-ttu-id="2ca94-109">Ereignisablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="2ca94-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="2ca94-110">Verwenden der Ablaufverfolgung beheben</span><span class="sxs-lookup"><span data-stu-id="2ca94-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="2ca94-111">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="2ca94-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
