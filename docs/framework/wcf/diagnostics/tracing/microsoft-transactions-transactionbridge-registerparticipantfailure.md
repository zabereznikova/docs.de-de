---
title: Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure
ms.date: 03/30/2017
ms.assetid: 3a4ead79-8550-4037-84e3-fd70ff56e001
ms.openlocfilehash: fb5e50e7332269690a200334ef936dd0d5525e9c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33475113"
---
# <a name="microsofttransactionstransactionbridgeregisterparticipantfailure"></a><span data-ttu-id="13cab-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span><span class="sxs-lookup"><span data-stu-id="13cab-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span></span>
<span data-ttu-id="13cab-103">Der WS-AT-Protokolldienst konnte keinen Teilnehmer für ein Steuerprotokoll registrieren.</span><span class="sxs-lookup"><span data-stu-id="13cab-103">The WS-AT protocol service failed to register a participant for a control protocol.</span></span>  
  
## <a name="description"></a><span data-ttu-id="13cab-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="13cab-104">Description</span></span>  
 <span data-ttu-id="13cab-105">Wird nachverfolgt, wenn MSDTC eine ungültige Registrierungsanforderung erkennt.</span><span class="sxs-lookup"><span data-stu-id="13cab-105">Traced if MSDTC detects an invalid Registration request.</span></span> <span data-ttu-id="13cab-106">Dies kann durch mehrere Abschlussregistrierungsanforderungen und interne Fehler verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="13cab-106">This can be caused by  multiple Completion registration requests and internal errors.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="13cab-107">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="13cab-107">Troubleshooting</span></span>  
 <span data-ttu-id="13cab-108">Versuchen Sie nicht, mehr als einmal einen Abschluss zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="13cab-108">Do not try to Register for Completion more than once.</span></span>  <span data-ttu-id="13cab-109">Überprüfen Sie darüber hinaus die Statuszeichenfolge innerhalb der Ablaufverfolgungsnachricht, um zu bestimmen, ob irgendein ausführbares Element vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="13cab-109">Also, inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13cab-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13cab-110">See Also</span></span>  
 [<span data-ttu-id="13cab-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="13cab-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="13cab-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="13cab-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="13cab-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="13cab-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
