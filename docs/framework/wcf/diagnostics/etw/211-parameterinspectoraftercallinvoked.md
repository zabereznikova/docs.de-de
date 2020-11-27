---
title: 211 - ParameterInspectorAfterCallInvoked
ms.date: 03/30/2017
ms.assetid: c0e21297-10b8-4456-a0e1-e019145cd5ac
ms.openlocfilehash: 7027b6557520a9ccb587f8d383d3598571da5838
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279063"
---
# <a name="211---parameterinspectoraftercallinvoked"></a><span data-ttu-id="9552f-102">211 - ParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="9552f-102">211 - ParameterInspectorAfterCallInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="9552f-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9552f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9552f-104">id</span><span class="sxs-lookup"><span data-stu-id="9552f-104">ID</span></span>|<span data-ttu-id="9552f-105">211</span><span class="sxs-lookup"><span data-stu-id="9552f-105">211</span></span>|  
|<span data-ttu-id="9552f-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="9552f-106">Keywords</span></span>|<span data-ttu-id="9552f-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9552f-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="9552f-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="9552f-108">Level</span></span>|<span data-ttu-id="9552f-109">Information</span><span class="sxs-lookup"><span data-stu-id="9552f-109">Information</span></span>|  
|<span data-ttu-id="9552f-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="9552f-110">Channel</span></span>|<span data-ttu-id="9552f-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="9552f-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9552f-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9552f-112">Description</span></span>  

 <span data-ttu-id="9552f-113">Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `AfterCall`-Methode auf einem `ParameterInspector` aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="9552f-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9552f-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="9552f-114">Message</span></span>  

 <span data-ttu-id="9552f-115">Der Verteiler hat 'AfterCall' auf einem ParameterInspector vom Typ '%1' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="9552f-115">The Dispatcher invoked 'AfterCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9552f-116">Details</span><span class="sxs-lookup"><span data-stu-id="9552f-116">Details</span></span>  
  
|<span data-ttu-id="9552f-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="9552f-117">Data Item Name</span></span>|<span data-ttu-id="9552f-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="9552f-118">Data Item Type</span></span>|<span data-ttu-id="9552f-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9552f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9552f-120">Typname</span><span class="sxs-lookup"><span data-stu-id="9552f-120">Type Name</span></span>|`xs:string`|<span data-ttu-id="9552f-121">Der CLR-FullName des aufgerufenen `ParameterInspector`-Typs.</span><span class="sxs-lookup"><span data-stu-id="9552f-121">The CLR FullName of the type of the invoked `ParameterInspector`.</span></span>|  
|<span data-ttu-id="9552f-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="9552f-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="9552f-123">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="9552f-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="9552f-124">Sein Format ist als "Website Name Anwendungspfad für virtuelle Computer&#124;virtuellen Dienst Pfad&#124;Dienst Name '" definiert.</span><span class="sxs-lookup"><span data-stu-id="9552f-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="9552f-125">Beispiel: "Default Web Site/calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="9552f-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="9552f-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9552f-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="9552f-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="9552f-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
