---
title: System.ServiceModel.Activation.WebHostServiceCloseFailed
ms.date: 03/30/2017
ms.assetid: 3cab9856-a5cf-4f0e-a0cb-89425e368f8e
ms.openlocfilehash: e39ca97bdefafee840206036f89e8b165609516a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263008"
---
# <a name="systemservicemodelactivationwebhostserviceclosefailed"></a><span data-ttu-id="3fa32-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span><span class="sxs-lookup"><span data-stu-id="3fa32-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span></span>

<span data-ttu-id="3fa32-103">Tritt auf, wenn ein Dienst nicht problemlos geschlossen werden kann und abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="3fa32-103">Occurs when a service cannot be closed gracefully and is aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3fa32-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3fa32-104">Description</span></span>  

 <span data-ttu-id="3fa32-105">Dieser Fehlercode wird nur in der Protokolldatei angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3fa32-105">This error code only appears in the log file.</span></span> <span data-ttu-id="3fa32-106">Dies weist üblicherweise auf einen Programmierungsfehler hin, z. B. wenn Sie versuchen, einen Dienst zu schließen, nachdem der Abbruch bereits aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="3fa32-106">It usually indicates a programming error, for example, when you try to close a service after Abort has already been called.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="3fa32-107">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="3fa32-107">Troubleshooting</span></span>  

 <span data-ttu-id="3fa32-108">Überprüfen Sie den Quellcode der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="3fa32-108">Check the application source code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fa32-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3fa32-109">See also</span></span>

- [<span data-ttu-id="3fa32-110">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="3fa32-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="3fa32-111">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="3fa32-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="3fa32-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="3fa32-112">Administration and Diagnostics</span></span>](../index.md)
