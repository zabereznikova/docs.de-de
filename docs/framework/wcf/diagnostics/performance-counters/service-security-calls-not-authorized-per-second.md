---
title: 'Dienst: Nicht autorisierte Sicherheitsaufrufe pro Sekunde'
ms.date: 03/30/2017
ms.assetid: 1eeade5a-ea62-4757-b1f9-1b1b1746abd1
ms.openlocfilehash: db9e333f740f19e4f82ea0f1306a11e6c21ba996
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236922"
---
# <a name="service-security-calls-not-authorized-per-second"></a><span data-ttu-id="78585-102">Dienst: Nicht autorisierte Sicherheitsaufrufe pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="78585-102">Service: Security Calls Not Authorized Per Second</span></span>

<span data-ttu-id="78585-103">Zählername: Nicht autorisierte Sicherheitsaufrufe pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="78585-103">Counter name: Security Calls Not Authorized Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="78585-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="78585-104">Description</span></span>  

 <span data-ttu-id="78585-105">Anzahl der eingehenden Nachrichten in einer Sekunde, die von einem gültigen Benutzer stammen und ordnungsgemäß geschützt sind, wobei der Benutzer allerdings nicht für die Durchführung spezifischer Aufgaben autorisiert ist.</span><span class="sxs-lookup"><span data-stu-id="78585-105">Number of incoming messages in one second, which are from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="78585-106">Dieser Indikator wird erhöht, wenn die <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A>-Methode `false` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="78585-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span>  
  
 <span data-ttu-id="78585-107">Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))des Leistungs Zählers, dessen Wert mit der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="78585-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="78585-108">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="78585-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
