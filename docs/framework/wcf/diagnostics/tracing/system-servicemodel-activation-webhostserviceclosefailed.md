---
title: System.ServiceModel.Activation.WebHostServiceCloseFailed
ms.date: 03/30/2017
ms.assetid: 3cab9856-a5cf-4f0e-a0cb-89425e368f8e
ms.openlocfilehash: aa9df795ee8601a4c4f4e2ce7427ffb0dd530bba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33476486"
---
# <a name="systemservicemodelactivationwebhostserviceclosefailed"></a><span data-ttu-id="f3e06-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span><span class="sxs-lookup"><span data-stu-id="f3e06-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span></span>
<span data-ttu-id="f3e06-103">Tritt auf, wenn ein Dienst nicht problemlos geschlossen werden kann und abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="f3e06-103">Occurs when a service cannot be closed gracefully and is aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="f3e06-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f3e06-104">Description</span></span>  
 <span data-ttu-id="f3e06-105">Dieser Fehlercode wird nur in der Protokolldatei angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f3e06-105">This error code only appears in the log file.</span></span> <span data-ttu-id="f3e06-106">Dies weist üblicherweise auf einen Programmierungsfehler hin, z. B. wenn Sie versuchen, einen Dienst zu schließen, nachdem der Abbruch bereits aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="f3e06-106">It usually indicates a programming error, for example, when you try to close a service after Abort has already been called.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="f3e06-107">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="f3e06-107">Troubleshooting</span></span>  
 <span data-ttu-id="f3e06-108">Überprüfen Sie den Quellcode der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="f3e06-108">Check the application source code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3e06-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3e06-109">See Also</span></span>  
 [<span data-ttu-id="f3e06-110">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="f3e06-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="f3e06-111">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="f3e06-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="f3e06-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="f3e06-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
