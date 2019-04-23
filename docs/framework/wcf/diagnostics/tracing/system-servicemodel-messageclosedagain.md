---
title: System.ServiceModel.MessageClosedAgain
ms.date: 03/30/2017
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
ms.openlocfilehash: a18355d55359df665d0e936ce95da34bf07aec6a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59181336"
---
# <a name="systemservicemodelmessageclosedagain"></a><span data-ttu-id="6b715-102">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="6b715-102">System.ServiceModel.MessageClosedAgain</span></span>
<span data-ttu-id="6b715-103">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="6b715-103">System.ServiceModel.MessageClosedAgain</span></span>  
  
## <a name="description"></a><span data-ttu-id="6b715-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6b715-104">Description</span></span>  
 <span data-ttu-id="6b715-105">Eine Nachricht wurde wieder geschlossen.</span><span class="sxs-lookup"><span data-stu-id="6b715-105">A message was closed again.</span></span>  
  
 <span data-ttu-id="6b715-106">Eine Nachricht sollte nur einmal geschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="6b715-106">A message should be closed only once.</span></span> <span data-ttu-id="6b715-107">Wird diese Ablaufverfolgung in Benutzererweiterungscode ausgegeben, weist dies darauf hin, dass der Benutzererweiterungscode im Begriff ist, eine Nachricht zu schließen, die bereits geschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="6b715-107">If this trace is being emitted in user extension code, it indicates that the user extension code is closing a message that has already been closed.</span></span> <span data-ttu-id="6b715-108">Wird diese Ablaufverfolgung in Produktcode ausgegeben, weist dies darauf hin, dass der Benutzererweiterungscode eine Nachricht möglicherweise zu früh schließt.</span><span class="sxs-lookup"><span data-stu-id="6b715-108">If this trace is being emitted through product code, it indicates that the user extension code could potentially be closing a message too early.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b715-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b715-109">See also</span></span>

- [<span data-ttu-id="6b715-110">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="6b715-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="6b715-111">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="6b715-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="6b715-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="6b715-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
