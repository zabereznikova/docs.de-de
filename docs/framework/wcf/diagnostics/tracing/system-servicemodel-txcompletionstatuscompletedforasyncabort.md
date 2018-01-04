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
ms.workload: dotnet
ms.openlocfilehash: cf6c70bdcfc402322dd1f20bbff2be74c111798a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodeltxcompletionstatuscompletedforasyncabort"></a><span data-ttu-id="731dd-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="731dd-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span></span>
<span data-ttu-id="731dd-103">Die angegebene Transaktion für den angegebenen Vorgang wurde aufgrund eines asynchronen Abbruchs abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="731dd-103">The specified transaction for the specified operation was completed due to asynchronous abort.</span></span>  
  
## <a name="description"></a><span data-ttu-id="731dd-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="731dd-104">Description</span></span>  
 <span data-ttu-id="731dd-105">Die aktuelle Transaktion wurde abgebrochen, weil ein anderer Teilnehmer für den Abbruch votiert hat, weil Zeitüberschreitungen aufgetreten sind oder weil ein anderer Fehler bei einem Teilnehmer einer Transaktion aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="731dd-105">The current transaction was aborted due to another participant voting for Abort, time-outs occurring, or another error inside the participant of a transaction.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="731dd-106">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="731dd-106">Troubleshooting</span></span>  
 <span data-ttu-id="731dd-107">Wenn dieser Abbruch unerwartet erfolgt, überprüfen Sie alle Systemprotokolle, um den wirklichen Grund für den Abbruch zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="731dd-107">If this abort is unexpected, check all system logs to determine the real reason for the abort.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="731dd-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="731dd-108">See Also</span></span>  
 [<span data-ttu-id="731dd-109">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="731dd-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="731dd-110">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="731dd-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="731dd-111">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="731dd-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
