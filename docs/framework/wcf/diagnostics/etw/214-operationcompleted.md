---
title: 214 - OperationCompleted
ms.date: 03/30/2017
ms.assetid: a6287eef-023f-4816-813c-1802c82366df
ms.openlocfilehash: 6147c70448efb122cb43a2b42a1e9b59980fab29
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278946"
---
# <a name="214---operationcompleted"></a><span data-ttu-id="49d2d-102">214 - OperationCompleted</span><span class="sxs-lookup"><span data-stu-id="49d2d-102">214 - OperationCompleted</span></span>

## <a name="properties"></a><span data-ttu-id="49d2d-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="49d2d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="49d2d-104">id</span><span class="sxs-lookup"><span data-stu-id="49d2d-104">ID</span></span>|<span data-ttu-id="49d2d-105">214</span><span class="sxs-lookup"><span data-stu-id="49d2d-105">214</span></span>|  
|<span data-ttu-id="49d2d-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="49d2d-106">Keywords</span></span>|<span data-ttu-id="49d2d-107">HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="49d2d-107">HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="49d2d-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="49d2d-108">Level</span></span>|<span data-ttu-id="49d2d-109">Information</span><span class="sxs-lookup"><span data-stu-id="49d2d-109">Information</span></span>|  
|<span data-ttu-id="49d2d-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="49d2d-110">Channel</span></span>|<span data-ttu-id="49d2d-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="49d2d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="49d2d-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="49d2d-112">Description</span></span>  

 <span data-ttu-id="49d2d-113">Dieses Ereignis wird ausgegeben, wenn der standardmäßige `OperationInvoker` des Dienstmodells das Aufrufen einer Methode abgeschlossen hat, ohne dass diese Methode eine Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="49d2d-113">This event is emitted when the Service Model's default `OperationInvoker` has completed a call to a method without that method throwing an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="49d2d-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="49d2d-114">Message</span></span>  

 <span data-ttu-id="49d2d-115">Ein OperationInvoker hat den Aufruf der '%1'-Methode abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="49d2d-115">An OperationInvoker completed the call to the '%1' method.</span></span> <span data-ttu-id="49d2d-116">Die Methodenaufrufdauer betrug '%2' ms.</span><span class="sxs-lookup"><span data-stu-id="49d2d-116">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="49d2d-117">Details</span><span class="sxs-lookup"><span data-stu-id="49d2d-117">Details</span></span>  
  
|<span data-ttu-id="49d2d-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="49d2d-118">Data Item Name</span></span>|<span data-ttu-id="49d2d-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="49d2d-119">Data Item Type</span></span>|<span data-ttu-id="49d2d-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="49d2d-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="49d2d-121">Methodenname</span><span class="sxs-lookup"><span data-stu-id="49d2d-121">Method Name</span></span>|`xs:string`|<span data-ttu-id="49d2d-122">Der CLR-Name der Methode, die vom `OperationInvoker` aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="49d2d-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="49d2d-123">Duration</span><span class="sxs-lookup"><span data-stu-id="49d2d-123">Duration</span></span>|`xs:long`|<span data-ttu-id="49d2d-124">Die Zeit, in Millisekunden, die der `OperationInvoker` zum Aufrufen der Methode benötigt hat.</span><span class="sxs-lookup"><span data-stu-id="49d2d-124">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="49d2d-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="49d2d-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="49d2d-126">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="49d2d-126">For web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="49d2d-127">Sein Format ist als "Website Name Anwendungspfad für virtuelle Computer&#124;virtuellen Dienst Pfad&#124;Dienst Name '" definiert.</span><span class="sxs-lookup"><span data-stu-id="49d2d-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="49d2d-128">Beispiel: "Default Web Site/calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="49d2d-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="49d2d-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="49d2d-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="49d2d-130">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="49d2d-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
