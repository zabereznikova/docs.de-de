---
title: Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed
ms.date: 03/30/2017
ms.assetid: 96474056-0418-41e4-8c75-bbc0a853eaba
ms.openlocfilehash: 3745c542986d405312a308fcf50ba6d7b6f93a1c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074182"
---
# <a name="microsofttransactionstransactionbridgeregistrationcoordinatorfailed"></a><span data-ttu-id="70d80-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed</span><span class="sxs-lookup"><span data-stu-id="70d80-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed</span></span>
<span data-ttu-id="70d80-103">Der WS-AT-Protokolldienst konnte eine Register-Nachricht nicht an seinen Koordinator senden.</span><span class="sxs-lookup"><span data-stu-id="70d80-103">The WS-AT protocol service failed to send a Register message to its coordinator</span></span>  
  
## <a name="description"></a><span data-ttu-id="70d80-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="70d80-104">Description</span></span>  
 <span data-ttu-id="70d80-105">Wird nachverfolgt, wenn der lokale Transaktions-Manager nicht beim übergeordneten Transaktions-Manager registriert wird, da keine Nachricht gesendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="70d80-105">Traced if the local TransactionManager is not able to Register with its superior TransactionManager due to the inability to send a message.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="70d80-106">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="70d80-106">Troubleshooting</span></span>  
 <span data-ttu-id="70d80-107">Überprüfen Sie die Ablaufverfolgungsnachricht zu der Ausnahme, die den Sendefehler der Nachricht verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="70d80-107">Inspect the trace message for the exception causing the message send failure</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70d80-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70d80-108">See also</span></span>

- [<span data-ttu-id="70d80-109">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="70d80-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="70d80-110">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="70d80-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="70d80-111">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="70d80-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
