---
title: Nicht autorisierte Sicherheitsaufrufe pro Sekunde
ms.date: 03/30/2017
ms.assetid: 0f189767-8c05-478a-8f0b-9228e5d351e5
ms.openlocfilehash: 15890506aece94a07d4b97101519007accf3570a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61915914"
---
# <a name="security-calls-not-authorized-per-second"></a><span data-ttu-id="3bd16-102">Nicht autorisierte Sicherheitsaufrufe pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="3bd16-102">Security Calls Not Authorized Per Second</span></span>
<span data-ttu-id="3bd16-103">Indikatorname: Nicht autorisierte Sicherheitsaufrufe pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="3bd16-103">Counter Name: Security Calls Not Authorized Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3bd16-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3bd16-104">Description</span></span>  
 <span data-ttu-id="3bd16-105">Die Anzahl der Aufrufe, die in diesem Vorgang in einer Sekunde keine Autorisierung erhielten.</span><span class="sxs-lookup"><span data-stu-id="3bd16-105">Number of calls that failed authorization in this operation in a second.</span></span>  
  
 <span data-ttu-id="3bd16-106">Dieser Indikator wird erhöht, wenn die <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A>-Methode `false` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3bd16-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span> <span data-ttu-id="3bd16-107">Er gibt an, dass die eingehende Nachricht von einem gültigen Benutzer stammt und ordnungsgemäß geschützt ist, der Benutzer jedoch nicht für die Durchführung spezifischer Aufgaben autorisiert ist.</span><span class="sxs-lookup"><span data-stu-id="3bd16-107">It indicates that the incoming message is from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="3bd16-108">Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="3bd16-108">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="3bd16-109">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="3bd16-109">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
