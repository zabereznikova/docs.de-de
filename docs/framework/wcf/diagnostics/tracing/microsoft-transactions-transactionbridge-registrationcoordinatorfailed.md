---
title: Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96474056-0418-41e4-8c75-bbc0a853eaba
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 09f5e127f32b791272dc17c09102af198b3a923c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="microsofttransactionstransactionbridgeregistrationcoordinatorfailed"></a><span data-ttu-id="8f377-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed</span><span class="sxs-lookup"><span data-stu-id="8f377-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed</span></span>
<span data-ttu-id="8f377-103">Der WS-AT-Protokolldienst konnte eine Register-Nachricht nicht an seinen Koordinator senden.</span><span class="sxs-lookup"><span data-stu-id="8f377-103">The WS-AT protocol service failed to send a Register message to its coordinator</span></span>  
  
## <a name="description"></a><span data-ttu-id="8f377-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f377-104">Description</span></span>  
 <span data-ttu-id="8f377-105">Wird nachverfolgt, wenn der lokale TransactionManager nicht beim übergeordneten TransactionManager registriert wird, da keine Nachricht gesendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="8f377-105">Traced if the local TransactionManager is not able to Register with its superior TransactionManager due to the inability to send a message.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="8f377-106">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="8f377-106">Troubleshooting</span></span>  
 <span data-ttu-id="8f377-107">Überprüfen Sie die Ablaufverfolgungsnachricht zu der Ausnahme, die den Sendefehler der Nachricht verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="8f377-107">Inspect the trace message for the exception causing the message send failure</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f377-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f377-108">See Also</span></span>  
 [<span data-ttu-id="8f377-109">Ereignisablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="8f377-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="8f377-110">Verwenden der Ablaufverfolgung beheben</span><span class="sxs-lookup"><span data-stu-id="8f377-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="8f377-111">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="8f377-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
