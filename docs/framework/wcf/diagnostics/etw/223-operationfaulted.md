---
title: 223 - OperationFaulted
ms.date: 03/30/2017
ms.assetid: 2f7d89d7-3a6a-40fe-9610-5424eb6bbf61
ms.openlocfilehash: 310e91320d27dd9817302fc14ef088d180152b73
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263073"
---
# <a name="223---operationfaulted"></a><span data-ttu-id="5228e-102">223 - OperationFaulted</span><span class="sxs-lookup"><span data-stu-id="5228e-102">223 - OperationFaulted</span></span>

## <a name="properties"></a><span data-ttu-id="5228e-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="5228e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5228e-104">id</span><span class="sxs-lookup"><span data-stu-id="5228e-104">ID</span></span>|<span data-ttu-id="5228e-105">223</span><span class="sxs-lookup"><span data-stu-id="5228e-105">223</span></span>|  
|<span data-ttu-id="5228e-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="5228e-106">Keywords</span></span>|<span data-ttu-id="5228e-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="5228e-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="5228e-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="5228e-108">Level</span></span>|<span data-ttu-id="5228e-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="5228e-109">Warning</span></span>|  
|<span data-ttu-id="5228e-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="5228e-110">Channel</span></span>|<span data-ttu-id="5228e-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="5228e-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5228e-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5228e-112">Description</span></span>  

 <span data-ttu-id="5228e-113">Dieses Ereignis wird ausgegeben, wenn beim Aufrufen der Methode der standardmäßige `OperationInvoker` des Dienstmodells auf eine Ausnahme gestoßen ist, die von `FaultException` abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="5228e-113">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception deriving from `FaultException` while invoking its method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5228e-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="5228e-114">Message</span></span>  

 <span data-ttu-id="5228e-115">Die '%1'-Methode hat beim Aufrufen von OperationInvoker eine FaultException ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="5228e-115">The '%1' method threw a FaultException when invoked by the OperationInvoker.</span></span> <span data-ttu-id="5228e-116">Die Methodenaufrufdauer betrug '%2' ms.</span><span class="sxs-lookup"><span data-stu-id="5228e-116">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5228e-117">Details</span><span class="sxs-lookup"><span data-stu-id="5228e-117">Details</span></span>  
  
|<span data-ttu-id="5228e-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="5228e-118">Data Item Name</span></span>|<span data-ttu-id="5228e-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="5228e-119">Data Item Type</span></span>|<span data-ttu-id="5228e-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5228e-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5228e-121">MethodName</span><span class="sxs-lookup"><span data-stu-id="5228e-121">MethodName</span></span>|`xs:string`|<span data-ttu-id="5228e-122">Der CLR-Name der Methode, die vom `OperationInvoker` aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="5228e-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="5228e-123">Duration</span><span class="sxs-lookup"><span data-stu-id="5228e-123">Duration</span></span>|`xs:long`|<span data-ttu-id="5228e-124">Die Zeit, in Millisekunden, die der `OperationInvoker` zum Aufrufen der Methode benötigt hat.</span><span class="sxs-lookup"><span data-stu-id="5228e-124">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="5228e-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="5228e-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="5228e-126">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="5228e-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="5228e-127">Sein Format ist als "Website Name Anwendungspfad für virtuelle Computer&#124;virtuellen Dienst Pfad&#124;Dienst Name '" definiert.</span><span class="sxs-lookup"><span data-stu-id="5228e-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="5228e-128">Beispiel: "Default Web Site/calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="5228e-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="5228e-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5228e-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="5228e-130">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="5228e-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
