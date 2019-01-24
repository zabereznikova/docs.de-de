---
title: System.ServiceModel.Activation.WebHostServiceCloseFailed
ms.date: 03/30/2017
ms.assetid: 3cab9856-a5cf-4f0e-a0cb-89425e368f8e
ms.openlocfilehash: 0ed3a9a1c16247f94c739a43d84d51e4750b3c2f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597657"
---
# <a name="systemservicemodelactivationwebhostserviceclosefailed"></a><span data-ttu-id="207e3-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span><span class="sxs-lookup"><span data-stu-id="207e3-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span></span>
<span data-ttu-id="207e3-103">Tritt auf, wenn ein Dienst nicht problemlos geschlossen werden kann und abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="207e3-103">Occurs when a service cannot be closed gracefully and is aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="207e3-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="207e3-104">Description</span></span>  
 <span data-ttu-id="207e3-105">Dieser Fehlercode wird nur in der Protokolldatei angezeigt.</span><span class="sxs-lookup"><span data-stu-id="207e3-105">This error code only appears in the log file.</span></span> <span data-ttu-id="207e3-106">Dies weist üblicherweise auf einen Programmierungsfehler hin, z. B. wenn Sie versuchen, einen Dienst zu schließen, nachdem der Abbruch bereits aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="207e3-106">It usually indicates a programming error, for example, when you try to close a service after Abort has already been called.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="207e3-107">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="207e3-107">Troubleshooting</span></span>  
 <span data-ttu-id="207e3-108">Überprüfen Sie den Quellcode der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="207e3-108">Check the application source code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="207e3-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="207e3-109">See also</span></span>
- [<span data-ttu-id="207e3-110">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="207e3-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="207e3-111">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="207e3-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="207e3-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="207e3-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
