---
title: System.ServiceModel.Activation.WebHostServiceCloseFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3cab9856-a5cf-4f0e-a0cb-89425e368f8e
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cc2b0dc75e8e8748e25c1faf28150e0c156a20ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelactivationwebhostserviceclosefailed"></a><span data-ttu-id="8ed14-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span><span class="sxs-lookup"><span data-stu-id="8ed14-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span></span>
<span data-ttu-id="8ed14-103">Tritt auf, wenn ein Dienst nicht problemlos geschlossen werden kann und abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="8ed14-103">Occurs when a service cannot be closed gracefully and is aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8ed14-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8ed14-104">Description</span></span>  
 <span data-ttu-id="8ed14-105">Dieser Fehlercode wird nur in der Protokolldatei angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8ed14-105">This error code only appears in the log file.</span></span> <span data-ttu-id="8ed14-106">Dies weist üblicherweise auf einen Programmierungsfehler hin, z. B. wenn Sie versuchen, einen Dienst zu schließen, nachdem der Abbruch bereits aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="8ed14-106">It usually indicates a programming error, for example, when you try to close a service after Abort has already been called.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="8ed14-107">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="8ed14-107">Troubleshooting</span></span>  
 <span data-ttu-id="8ed14-108">Überprüfen Sie den Quellcode der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="8ed14-108">Check the application source code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ed14-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ed14-109">See Also</span></span>  
 [<span data-ttu-id="8ed14-110">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="8ed14-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="8ed14-111">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="8ed14-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="8ed14-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="8ed14-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
