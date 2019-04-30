---
title: 214 - OperationCompleted
ms.date: 03/30/2017
ms.assetid: a6287eef-023f-4816-813c-1802c82366df
ms.openlocfilehash: da1021b674b555b683f8f745f5a2a0073c9567e8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967998"
---
# <a name="214---operationcompleted"></a><span data-ttu-id="659e7-102">214 - OperationCompleted</span><span class="sxs-lookup"><span data-stu-id="659e7-102">214 - OperationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="659e7-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="659e7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="659e7-104">ID</span><span class="sxs-lookup"><span data-stu-id="659e7-104">ID</span></span>|<span data-ttu-id="659e7-105">214</span><span class="sxs-lookup"><span data-stu-id="659e7-105">214</span></span>|  
|<span data-ttu-id="659e7-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="659e7-106">Keywords</span></span>|<span data-ttu-id="659e7-107">HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="659e7-107">HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="659e7-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="659e7-108">Level</span></span>|<span data-ttu-id="659e7-109">Information</span><span class="sxs-lookup"><span data-stu-id="659e7-109">Information</span></span>|  
|<span data-ttu-id="659e7-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="659e7-110">Channel</span></span>|<span data-ttu-id="659e7-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="659e7-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="659e7-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="659e7-112">Description</span></span>  
 <span data-ttu-id="659e7-113">Dieses Ereignis wird ausgegeben, wenn der standardmäßige `OperationInvoker` des Dienstmodells das Aufrufen einer Methode abgeschlossen hat, ohne dass diese Methode eine Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="659e7-113">This event is emitted when the Service Model's default `OperationInvoker` has completed a call to a method without that method throwing an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="659e7-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="659e7-114">Message</span></span>  
 <span data-ttu-id="659e7-115">Ein OperationInvoker hat den Aufruf der '%1'-Methode abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="659e7-115">An OperationInvoker completed the call to the '%1' method.</span></span> <span data-ttu-id="659e7-116">Die Methodenaufrufdauer betrug '%2' ms.</span><span class="sxs-lookup"><span data-stu-id="659e7-116">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="659e7-117">Details</span><span class="sxs-lookup"><span data-stu-id="659e7-117">Details</span></span>  
  
|<span data-ttu-id="659e7-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="659e7-118">Data Item Name</span></span>|<span data-ttu-id="659e7-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="659e7-119">Data Item Type</span></span>|<span data-ttu-id="659e7-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="659e7-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="659e7-121">Methodenname</span><span class="sxs-lookup"><span data-stu-id="659e7-121">Method Name</span></span>|`xs:string`|<span data-ttu-id="659e7-122">Der CLR-Name der Methode, die vom `OperationInvoker` aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="659e7-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="659e7-123">Dauer</span><span class="sxs-lookup"><span data-stu-id="659e7-123">Duration</span></span>|`xs:long`|<span data-ttu-id="659e7-124">Die Zeit, in Millisekunden, die der `OperationInvoker` zum Aufrufen der Methode benötigt hat.</span><span class="sxs-lookup"><span data-stu-id="659e7-124">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="659e7-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="659e7-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="659e7-126">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="659e7-126">For web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="659e7-127">Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="659e7-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="659e7-128">Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="659e7-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="659e7-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="659e7-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="659e7-130">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="659e7-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
