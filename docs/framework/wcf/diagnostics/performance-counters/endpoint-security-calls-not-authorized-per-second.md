---
title: 'Endpunkt: Nicht autorisierte Sicherheitsaufrufe pro Sekunde'
ms.date: 03/30/2017
ms.assetid: c8a1547b-986b-45c1-b302-dea0cd4b516d
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 4cefdd7480c7d0e9475b1883e603d9db1f287d4a
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43799212"
---
# <a name="endpoint-security-calls-not-authorized-per-second"></a><span data-ttu-id="bbf28-102">Endpunkt: Nicht autorisierte Sicherheitsaufrufe pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="bbf28-102">Endpoint: Security Calls Not Authorized Per Second</span></span>
<span data-ttu-id="bbf28-103">Indikatorname: Security Calls Not Authorized Per Second.</span><span class="sxs-lookup"><span data-stu-id="bbf28-103">Counter Name: Security Calls Not Authorized Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="bbf28-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bbf28-104">Description</span></span>  
 <span data-ttu-id="bbf28-105">Anzahl der eingehenden Nachrichten in einer Sekunde, die von einem gültigen Benutzer stammen und ordnungsgemäß geschützt sind, wobei der Benutzer allerdings nicht für die Durchführung spezifischer Aufgaben autorisiert ist.</span><span class="sxs-lookup"><span data-stu-id="bbf28-105">Number of incoming messages in a second that are from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="bbf28-106">Dieser Indikator wird erhöht, wenn die <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A>-Methode `false` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="bbf28-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span>  
  
 <span data-ttu-id="bbf28-107">Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="bbf28-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="bbf28-108">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="bbf28-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
