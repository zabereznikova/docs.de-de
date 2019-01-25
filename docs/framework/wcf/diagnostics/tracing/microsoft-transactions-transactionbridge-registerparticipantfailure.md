---
title: Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure
ms.date: 03/30/2017
ms.assetid: 3a4ead79-8550-4037-84e3-fd70ff56e001
ms.openlocfilehash: b94c017f6ed3a76a6bc5ed2cb970877ad18ef9ea
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610421"
---
# <a name="microsofttransactionstransactionbridgeregisterparticipantfailure"></a><span data-ttu-id="c0005-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span><span class="sxs-lookup"><span data-stu-id="c0005-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span></span>
<span data-ttu-id="c0005-103">Der WS-AT-Protokolldienst konnte keinen Teilnehmer für ein Steuerprotokoll registrieren.</span><span class="sxs-lookup"><span data-stu-id="c0005-103">The WS-AT protocol service failed to register a participant for a control protocol.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c0005-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c0005-104">Description</span></span>  
 <span data-ttu-id="c0005-105">Wird nachverfolgt, wenn MSDTC eine ungültige Registrierungsanforderung erkennt.</span><span class="sxs-lookup"><span data-stu-id="c0005-105">Traced if MSDTC detects an invalid Registration request.</span></span> <span data-ttu-id="c0005-106">Dies kann durch mehrere Abschlussregistrierungsanforderungen und interne Fehler verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="c0005-106">This can be caused by  multiple Completion registration requests and internal errors.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="c0005-107">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="c0005-107">Troubleshooting</span></span>  
 <span data-ttu-id="c0005-108">Versuchen Sie nicht, mehr als einmal einen Abschluss zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="c0005-108">Do not try to Register for Completion more than once.</span></span>  <span data-ttu-id="c0005-109">Überprüfen Sie darüber hinaus die Statuszeichenfolge innerhalb der Ablaufverfolgungsnachricht, um zu bestimmen, ob irgendein ausführbares Element vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c0005-109">Also, inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0005-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0005-110">See also</span></span>
- [<span data-ttu-id="c0005-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="c0005-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="c0005-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="c0005-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="c0005-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="c0005-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
