---
title: Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure
ms.date: 03/30/2017
ms.assetid: 3a4ead79-8550-4037-84e3-fd70ff56e001
ms.openlocfilehash: 2f0198d3c288b4c3833cdac8e5f943ba822c22e9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96252022"
---
# <a name="microsofttransactionstransactionbridgeregisterparticipantfailure"></a><span data-ttu-id="3568a-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span><span class="sxs-lookup"><span data-stu-id="3568a-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span></span>

<span data-ttu-id="3568a-103">Der WS-AT-Protokolldienst konnte keinen Teilnehmer für ein Steuerprotokoll registrieren.</span><span class="sxs-lookup"><span data-stu-id="3568a-103">The WS-AT protocol service failed to register a participant for a control protocol.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3568a-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3568a-104">Description</span></span>  

 <span data-ttu-id="3568a-105">Wird nachverfolgt, wenn MSDTC eine ungültige Registrierungsanforderung erkennt.</span><span class="sxs-lookup"><span data-stu-id="3568a-105">Traced if MSDTC detects an invalid Registration request.</span></span> <span data-ttu-id="3568a-106">Dies kann durch mehrere Abschlussregistrierungsanforderungen und interne Fehler verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="3568a-106">This can be caused by  multiple Completion registration requests and internal errors.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="3568a-107">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="3568a-107">Troubleshooting</span></span>  

 <span data-ttu-id="3568a-108">Versuchen Sie nicht, mehr als einmal einen Abschluss zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="3568a-108">Do not try to Register for Completion more than once.</span></span>  <span data-ttu-id="3568a-109">Überprüfen Sie darüber hinaus die Statuszeichenfolge innerhalb der Ablaufverfolgungsnachricht, um zu bestimmen, ob irgendein ausführbares Element vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="3568a-109">Also, inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3568a-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3568a-110">See also</span></span>

- [<span data-ttu-id="3568a-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="3568a-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="3568a-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="3568a-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="3568a-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="3568a-113">Administration and Diagnostics</span></span>](../index.md)
