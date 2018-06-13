---
title: System.ServiceModel.MessageClosedAgain
ms.date: 03/30/2017
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
ms.openlocfilehash: 3a73834888ae4a8945bd71492d787e23868fa5e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33480742"
---
# <a name="systemservicemodelmessageclosedagain"></a><span data-ttu-id="fee36-102">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="fee36-102">System.ServiceModel.MessageClosedAgain</span></span>
<span data-ttu-id="fee36-103">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="fee36-103">System.ServiceModel.MessageClosedAgain</span></span>  
  
## <a name="description"></a><span data-ttu-id="fee36-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fee36-104">Description</span></span>  
 <span data-ttu-id="fee36-105">Eine Nachricht wurde wieder geschlossen.</span><span class="sxs-lookup"><span data-stu-id="fee36-105">A message was closed again.</span></span>  
  
 <span data-ttu-id="fee36-106">Eine Nachricht sollte nur einmal geschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="fee36-106">A message should be closed only once.</span></span> <span data-ttu-id="fee36-107">Wird diese Ablaufverfolgung in Benutzererweiterungscode ausgegeben, weist dies darauf hin, dass der Benutzererweiterungscode im Begriff ist, eine Nachricht zu schließen, die bereits geschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="fee36-107">If this trace is being emitted in user extension code, it indicates that the user extension code is closing a message that has already been closed.</span></span> <span data-ttu-id="fee36-108">Wird diese Ablaufverfolgung in Produktcode ausgegeben, weist dies darauf hin, dass der Benutzererweiterungscode eine Nachricht möglicherweise zu früh schließt.</span><span class="sxs-lookup"><span data-stu-id="fee36-108">If this trace is being emitted through product code, it indicates that the user extension code could potentially be closing a message too early.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fee36-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fee36-109">See Also</span></span>  
 [<span data-ttu-id="fee36-110">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="fee36-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="fee36-111">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="fee36-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="fee36-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="fee36-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
