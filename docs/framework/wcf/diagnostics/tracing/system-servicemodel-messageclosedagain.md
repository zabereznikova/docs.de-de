---
title: System.ServiceModel.MessageClosedAgain
ms.date: 03/30/2017
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
ms.openlocfilehash: d341953b8e12b14e6a3fe8a477c16a1b3a4454ae
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84580436"
---
# <a name="systemservicemodelmessageclosedagain"></a><span data-ttu-id="eb252-102">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="eb252-102">System.ServiceModel.MessageClosedAgain</span></span>
<span data-ttu-id="eb252-103">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="eb252-103">System.ServiceModel.MessageClosedAgain</span></span>  
  
## <a name="description"></a><span data-ttu-id="eb252-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="eb252-104">Description</span></span>  
 <span data-ttu-id="eb252-105">Eine Nachricht wurde wieder geschlossen.</span><span class="sxs-lookup"><span data-stu-id="eb252-105">A message was closed again.</span></span>  
  
 <span data-ttu-id="eb252-106">Eine Nachricht sollte nur einmal geschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="eb252-106">A message should be closed only once.</span></span> <span data-ttu-id="eb252-107">Wird diese Ablaufverfolgung in Benutzererweiterungscode ausgegeben, weist dies darauf hin, dass der Benutzererweiterungscode im Begriff ist, eine Nachricht zu schließen, die bereits geschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="eb252-107">If this trace is being emitted in user extension code, it indicates that the user extension code is closing a message that has already been closed.</span></span> <span data-ttu-id="eb252-108">Wird diese Ablaufverfolgung in Produktcode ausgegeben, weist dies darauf hin, dass der Benutzererweiterungscode eine Nachricht möglicherweise zu früh schließt.</span><span class="sxs-lookup"><span data-stu-id="eb252-108">If this trace is being emitted through product code, it indicates that the user extension code could potentially be closing a message too early.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb252-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eb252-109">See also</span></span>

- [<span data-ttu-id="eb252-110">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="eb252-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="eb252-111">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="eb252-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="eb252-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="eb252-112">Administration and Diagnostics</span></span>](../index.md)
