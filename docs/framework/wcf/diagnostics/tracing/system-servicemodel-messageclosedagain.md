---
title: System.ServiceModel.MessageClosedAgain
ms.date: 03/30/2017
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
ms.openlocfilehash: bcac4683655476c6aa868232b0483336b815b6cc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54705981"
---
# <a name="systemservicemodelmessageclosedagain"></a><span data-ttu-id="03fdf-102">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="03fdf-102">System.ServiceModel.MessageClosedAgain</span></span>
<span data-ttu-id="03fdf-103">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="03fdf-103">System.ServiceModel.MessageClosedAgain</span></span>  
  
## <a name="description"></a><span data-ttu-id="03fdf-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="03fdf-104">Description</span></span>  
 <span data-ttu-id="03fdf-105">Eine Nachricht wurde wieder geschlossen.</span><span class="sxs-lookup"><span data-stu-id="03fdf-105">A message was closed again.</span></span>  
  
 <span data-ttu-id="03fdf-106">Eine Nachricht sollte nur einmal geschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="03fdf-106">A message should be closed only once.</span></span> <span data-ttu-id="03fdf-107">Wird diese Ablaufverfolgung in Benutzererweiterungscode ausgegeben, weist dies darauf hin, dass der Benutzererweiterungscode im Begriff ist, eine Nachricht zu schließen, die bereits geschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="03fdf-107">If this trace is being emitted in user extension code, it indicates that the user extension code is closing a message that has already been closed.</span></span> <span data-ttu-id="03fdf-108">Wird diese Ablaufverfolgung in Produktcode ausgegeben, weist dies darauf hin, dass der Benutzererweiterungscode eine Nachricht möglicherweise zu früh schließt.</span><span class="sxs-lookup"><span data-stu-id="03fdf-108">If this trace is being emitted through product code, it indicates that the user extension code could potentially be closing a message too early.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03fdf-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03fdf-109">See also</span></span>
- [<span data-ttu-id="03fdf-110">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="03fdf-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="03fdf-111">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="03fdf-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="03fdf-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="03fdf-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
