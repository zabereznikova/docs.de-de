---
title: System.ServiceModel.TxCompletionStatusCompletedForError
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ade4722-a6d5-471c-b960-1cfea4ea2aa9
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 25106bffe6d541a89c786035db3d3266d861fd5b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodeltxcompletionstatuscompletedforerror"></a><span data-ttu-id="4f9dd-102">System.ServiceModel.TxCompletionStatusCompletedForError</span><span class="sxs-lookup"><span data-stu-id="4f9dd-102">System.ServiceModel.TxCompletionStatusCompletedForError</span></span>
<span data-ttu-id="4f9dd-103">Die angegebene Transaktion für den angegebenen Vorgang wurde aufgrund einer unbehandelten Ausführungsausnahme abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="4f9dd-103">The specified transaction for the specified operation was completed due to an unhandled execution exception.</span></span>  
  
## <a name="description"></a><span data-ttu-id="4f9dd-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4f9dd-104">Description</span></span>  
 <span data-ttu-id="4f9dd-105">Wird nachverfolgt, wenn ein Fehler während eines Versuchs, die aktuelle Transaktion abzuschließen, auftritt.</span><span class="sxs-lookup"><span data-stu-id="4f9dd-105">Traced when an error occurs during an attempt to complete the current transaction.</span></span> <span data-ttu-id="4f9dd-106">Dies geschieht, bevor eine Antwort oder ein Fehler an den Aufrufer gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="4f9dd-106">This happens before a reply or fault is sent to the caller.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="4f9dd-107">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="4f9dd-107">Troubleshooting</span></span>  
 <span data-ttu-id="4f9dd-108">Überprüfen Sie die verfolgte Nachricht auf die Ausnahmenachricht und alle ausführbaren Elemente.</span><span class="sxs-lookup"><span data-stu-id="4f9dd-108">Inspect the traced message for the exception message and any actionable items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f9dd-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f9dd-109">See Also</span></span>  
 [<span data-ttu-id="4f9dd-110">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="4f9dd-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="4f9dd-111">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="4f9dd-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="4f9dd-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="4f9dd-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
