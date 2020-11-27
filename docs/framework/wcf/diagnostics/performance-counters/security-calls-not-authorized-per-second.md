---
title: Nicht autorisierte Sicherheitsaufrufe pro Sekunde
ms.date: 03/30/2017
ms.assetid: 0f189767-8c05-478a-8f0b-9228e5d351e5
ms.openlocfilehash: 1e1e58946783c2eb376ae6ba50c3595c037a1e00
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276112"
---
# <a name="security-calls-not-authorized-per-second"></a><span data-ttu-id="b85ec-102">Nicht autorisierte Sicherheitsaufrufe pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="b85ec-102">Security Calls Not Authorized Per Second</span></span>

<span data-ttu-id="b85ec-103">Indikatorname: Security Calls Not Authorized Per Second.</span><span class="sxs-lookup"><span data-stu-id="b85ec-103">Counter Name: Security Calls Not Authorized Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b85ec-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b85ec-104">Description</span></span>  

 <span data-ttu-id="b85ec-105">Die Anzahl der Aufrufe, die in diesem Vorgang in einer Sekunde keine Autorisierung erhielten.</span><span class="sxs-lookup"><span data-stu-id="b85ec-105">Number of calls that failed authorization in this operation in a second.</span></span>  
  
 <span data-ttu-id="b85ec-106">Dieser Indikator wird erhöht, wenn die <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A>-Methode `false` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="b85ec-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span> <span data-ttu-id="b85ec-107">Er gibt an, dass die eingehende Nachricht von einem gültigen Benutzer stammt und ordnungsgemäß geschützt ist, der Benutzer jedoch nicht für die Durchführung spezifischer Aufgaben autorisiert ist.</span><span class="sxs-lookup"><span data-stu-id="b85ec-107">It indicates that the incoming message is from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="b85ec-108">Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))des Leistungs Zählers, dessen Wert mit der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="b85ec-108">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="b85ec-109">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="b85ec-109">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
