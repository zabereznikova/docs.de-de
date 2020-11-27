---
title: System.ServiceModel.MessageClosedAgain
ms.date: 03/30/2017
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
ms.openlocfilehash: a8aa5e600789df1b64a8a3f1a6355aaae6a6cf4b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294429"
---
# <a name="systemservicemodelmessageclosedagain"></a><span data-ttu-id="c9c0b-102">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="c9c0b-102">System.ServiceModel.MessageClosedAgain</span></span>

<span data-ttu-id="c9c0b-103">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="c9c0b-103">System.ServiceModel.MessageClosedAgain</span></span>  
  
## <a name="description"></a><span data-ttu-id="c9c0b-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c9c0b-104">Description</span></span>  

 <span data-ttu-id="c9c0b-105">Eine Nachricht wurde wieder geschlossen.</span><span class="sxs-lookup"><span data-stu-id="c9c0b-105">A message was closed again.</span></span>  
  
 <span data-ttu-id="c9c0b-106">Eine Nachricht sollte nur einmal geschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="c9c0b-106">A message should be closed only once.</span></span> <span data-ttu-id="c9c0b-107">Wird diese Ablaufverfolgung in Benutzererweiterungscode ausgegeben, weist dies darauf hin, dass der Benutzererweiterungscode im Begriff ist, eine Nachricht zu schließen, die bereits geschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="c9c0b-107">If this trace is being emitted in user extension code, it indicates that the user extension code is closing a message that has already been closed.</span></span> <span data-ttu-id="c9c0b-108">Wird diese Ablaufverfolgung in Produktcode ausgegeben, weist dies darauf hin, dass der Benutzererweiterungscode eine Nachricht möglicherweise zu früh schließt.</span><span class="sxs-lookup"><span data-stu-id="c9c0b-108">If this trace is being emitted through product code, it indicates that the user extension code could potentially be closing a message too early.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9c0b-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c9c0b-109">See also</span></span>

- [<span data-ttu-id="c9c0b-110">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="c9c0b-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="c9c0b-111">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="c9c0b-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="c9c0b-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="c9c0b-112">Administration and Diagnostics</span></span>](../index.md)
