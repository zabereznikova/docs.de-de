---
title: 207 - FaultProviderInvoked
ms.date: 03/30/2017
ms.assetid: b730d903-01c2-4deb-85a4-da12f8a21fe4
ms.openlocfilehash: 71381c9eee6aed4792500c8558db88e239bf89f7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295170"
---
# <a name="207---faultproviderinvoked"></a><span data-ttu-id="11ceb-102">207 - FaultProviderInvoked</span><span class="sxs-lookup"><span data-stu-id="11ceb-102">207 - FaultProviderInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="11ceb-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="11ceb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="11ceb-104">id</span><span class="sxs-lookup"><span data-stu-id="11ceb-104">ID</span></span>|<span data-ttu-id="11ceb-105">207</span><span class="sxs-lookup"><span data-stu-id="11ceb-105">207</span></span>|  
|<span data-ttu-id="11ceb-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="11ceb-106">Keywords</span></span>|<span data-ttu-id="11ceb-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="11ceb-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="11ceb-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="11ceb-108">Level</span></span>|<span data-ttu-id="11ceb-109">Information</span><span class="sxs-lookup"><span data-stu-id="11ceb-109">Information</span></span>|  
|<span data-ttu-id="11ceb-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="11ceb-110">Channel</span></span>|<span data-ttu-id="11ceb-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="11ceb-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="11ceb-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="11ceb-112">Description</span></span>  

 <span data-ttu-id="11ceb-113">Dieses Ereignis wird ausgegeben, nachdem ein `FaultProvider` aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="11ceb-113">This event is emitted after a `FaultProvider` has been invoked.</span></span>  
  
## <a name="message"></a><span data-ttu-id="11ceb-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="11ceb-114">Message</span></span>  

 <span data-ttu-id="11ceb-115">Der Verteiler hat einen FaultProvider vom Typ '%1' mit einer Ausnahme vom Typ '%2' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="11ceb-115">The Dispatcher invoked a FaultProvider of type '%1' with an exception of type '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="11ceb-116">Details</span><span class="sxs-lookup"><span data-stu-id="11ceb-116">Details</span></span>  
  
|<span data-ttu-id="11ceb-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="11ceb-117">Data Item Name</span></span>|<span data-ttu-id="11ceb-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="11ceb-118">Data Item Type</span></span>|<span data-ttu-id="11ceb-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="11ceb-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="11ceb-120">TypName</span><span class="sxs-lookup"><span data-stu-id="11ceb-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="11ceb-121">Der CLR-FullName des aufgerufenen `FaultProvider`-Typs.</span><span class="sxs-lookup"><span data-stu-id="11ceb-121">The CLR FullName of the type of the invoked `FaultProvider`.</span></span>|  
|<span data-ttu-id="11ceb-122">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="11ceb-122">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="11ceb-123">Der CLR-FullName der Ausnahme, die der `FaultProvider` verarbeitet hat.</span><span class="sxs-lookup"><span data-stu-id="11ceb-123">The CLR FullName of the exception that the `FaultProvider` has operated on.</span></span>|  
|<span data-ttu-id="11ceb-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="11ceb-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="11ceb-125">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="11ceb-125">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="11ceb-126">Sein Format ist als "Website Name Anwendungspfad für virtuelle Computer&#124;virtuellen Dienst Pfad&#124;Dienst Name '" definiert.</span><span class="sxs-lookup"><span data-stu-id="11ceb-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="11ceb-127">Beispiel: "Default Web Site/calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="11ceb-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="11ceb-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="11ceb-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="11ceb-129">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="11ceb-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
