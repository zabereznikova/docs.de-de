---
title: System.ServiceModel.MessageClosedAgain
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7f3963fe28ccaf55b3946254e395b770619c8f22
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelmessageclosedagain"></a><span data-ttu-id="b4d66-102">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="b4d66-102">System.ServiceModel.MessageClosedAgain</span></span>
<span data-ttu-id="b4d66-103">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="b4d66-103">System.ServiceModel.MessageClosedAgain</span></span>  
  
## <a name="description"></a><span data-ttu-id="b4d66-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4d66-104">Description</span></span>  
 <span data-ttu-id="b4d66-105">Eine Nachricht wurde wieder geschlossen.</span><span class="sxs-lookup"><span data-stu-id="b4d66-105">A message was closed again.</span></span>  
  
 <span data-ttu-id="b4d66-106">Eine Nachricht sollte nur einmal geschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="b4d66-106">A message should be closed only once.</span></span> <span data-ttu-id="b4d66-107">Wird diese Ablaufverfolgung in Benutzererweiterungscode ausgegeben, weist dies darauf hin, dass der Benutzererweiterungscode im Begriff ist, eine Nachricht zu schließen, die bereits geschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="b4d66-107">If this trace is being emitted in user extension code, it indicates that the user extension code is closing a message that has already been closed.</span></span> <span data-ttu-id="b4d66-108">Wird diese Ablaufverfolgung in Produktcode ausgegeben, weist dies darauf hin, dass der Benutzererweiterungscode eine Nachricht möglicherweise zu früh schließt.</span><span class="sxs-lookup"><span data-stu-id="b4d66-108">If this trace is being emitted through product code, it indicates that the user extension code could potentially be closing a message too early.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4d66-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4d66-109">See Also</span></span>  
 [<span data-ttu-id="b4d66-110">Ereignisablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="b4d66-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="b4d66-111">Verwenden der Ablaufverfolgung beheben</span><span class="sxs-lookup"><span data-stu-id="b4d66-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="b4d66-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="b4d66-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
