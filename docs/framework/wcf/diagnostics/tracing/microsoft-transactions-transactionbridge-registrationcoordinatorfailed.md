---
title: Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed
ms.date: 03/30/2017
ms.assetid: 96474056-0418-41e4-8c75-bbc0a853eaba
ms.openlocfilehash: 3745c542986d405312a308fcf50ba6d7b6f93a1c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074182"
---
# <a name="microsofttransactionstransactionbridgeregistrationcoordinatorfailed"></a><span data-ttu-id="9aa64-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed</span><span class="sxs-lookup"><span data-stu-id="9aa64-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed</span></span>
<span data-ttu-id="9aa64-103">Der WS-AT-Protokolldienst konnte eine Register-Nachricht nicht an seinen Koordinator senden.</span><span class="sxs-lookup"><span data-stu-id="9aa64-103">The WS-AT protocol service failed to send a Register message to its coordinator</span></span>  
  
## <a name="description"></a><span data-ttu-id="9aa64-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9aa64-104">Description</span></span>  
 <span data-ttu-id="9aa64-105">Wird nachverfolgt, wenn der lokale Transaktions-Manager nicht beim übergeordneten Transaktions-Manager registriert wird, da keine Nachricht gesendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="9aa64-105">Traced if the local TransactionManager is not able to Register with its superior TransactionManager due to the inability to send a message.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="9aa64-106">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="9aa64-106">Troubleshooting</span></span>  
 <span data-ttu-id="9aa64-107">Überprüfen Sie die Ablaufverfolgungsnachricht zu der Ausnahme, die den Sendefehler der Nachricht verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="9aa64-107">Inspect the trace message for the exception causing the message send failure</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aa64-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9aa64-108">See also</span></span>

- [<span data-ttu-id="9aa64-109">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="9aa64-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="9aa64-110">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="9aa64-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="9aa64-111">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="9aa64-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
