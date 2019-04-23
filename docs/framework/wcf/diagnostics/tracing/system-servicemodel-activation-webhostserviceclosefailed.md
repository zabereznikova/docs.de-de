---
title: System.ServiceModel.Activation.WebHostServiceCloseFailed
ms.date: 03/30/2017
ms.assetid: 3cab9856-a5cf-4f0e-a0cb-89425e368f8e
ms.openlocfilehash: afe84db3d4df8914ff1ed001b064439d581ead89
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59085389"
---
# <a name="systemservicemodelactivationwebhostserviceclosefailed"></a><span data-ttu-id="02809-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span><span class="sxs-lookup"><span data-stu-id="02809-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span></span>
<span data-ttu-id="02809-103">Tritt auf, wenn ein Dienst nicht problemlos geschlossen werden kann und abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="02809-103">Occurs when a service cannot be closed gracefully and is aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="02809-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="02809-104">Description</span></span>  
 <span data-ttu-id="02809-105">Dieser Fehlercode wird nur in der Protokolldatei angezeigt.</span><span class="sxs-lookup"><span data-stu-id="02809-105">This error code only appears in the log file.</span></span> <span data-ttu-id="02809-106">Dies weist üblicherweise auf einen Programmierungsfehler hin, z. B. wenn Sie versuchen, einen Dienst zu schließen, nachdem der Abbruch bereits aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="02809-106">It usually indicates a programming error, for example, when you try to close a service after Abort has already been called.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="02809-107">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="02809-107">Troubleshooting</span></span>  
 <span data-ttu-id="02809-108">Überprüfen Sie den Quellcode der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="02809-108">Check the application source code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02809-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02809-109">See also</span></span>

- [<span data-ttu-id="02809-110">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="02809-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="02809-111">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="02809-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="02809-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="02809-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
