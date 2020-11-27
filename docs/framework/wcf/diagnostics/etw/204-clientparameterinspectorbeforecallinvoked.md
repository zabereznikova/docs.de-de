---
title: 204 - ClientParameterInspectorBeforeCallInvoked
ms.date: 03/30/2017
ms.assetid: 8253555a-9002-4565-8ede-33d7a33a895f
ms.openlocfilehash: a7db8c9fa87518c59969f3089ff033fa8c912577
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275787"
---
# <a name="204---clientparameterinspectorbeforecallinvoked"></a><span data-ttu-id="82d8f-102">204 - ClientParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="82d8f-102">204 - ClientParameterInspectorBeforeCallInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="82d8f-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="82d8f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="82d8f-104">id</span><span class="sxs-lookup"><span data-stu-id="82d8f-104">ID</span></span>|<span data-ttu-id="82d8f-105">204</span><span class="sxs-lookup"><span data-stu-id="82d8f-105">204</span></span>|  
|<span data-ttu-id="82d8f-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="82d8f-106">Keywords</span></span>|<span data-ttu-id="82d8f-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="82d8f-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="82d8f-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="82d8f-108">Level</span></span>|<span data-ttu-id="82d8f-109">Information</span><span class="sxs-lookup"><span data-stu-id="82d8f-109">Information</span></span>|  
|<span data-ttu-id="82d8f-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="82d8f-110">Channel</span></span>|<span data-ttu-id="82d8f-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="82d8f-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="82d8f-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="82d8f-112">Description</span></span>  

 <span data-ttu-id="82d8f-113">Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `BeforeCall`-Methode auf einem Clientparameterinspektor aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="82d8f-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a client parameter inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="82d8f-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="82d8f-114">Message</span></span>  

 <span data-ttu-id="82d8f-115">Der Verteiler hat 'BeforeCall' auf einem ClientParameterInspector vom Typ '%1' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="82d8f-115">The Dispatcher invoked 'BeforeCall' on a ClientParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="82d8f-116">Details</span><span class="sxs-lookup"><span data-stu-id="82d8f-116">Details</span></span>  
  
|<span data-ttu-id="82d8f-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="82d8f-117">Data Item Name</span></span>|<span data-ttu-id="82d8f-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="82d8f-118">Data Item Type</span></span>|<span data-ttu-id="82d8f-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="82d8f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="82d8f-120">TypName</span><span class="sxs-lookup"><span data-stu-id="82d8f-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="82d8f-121">Der CLR-FullName für den Typ des aufgerufenen Inspektors.</span><span class="sxs-lookup"><span data-stu-id="82d8f-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="82d8f-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="82d8f-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="82d8f-123">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="82d8f-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="82d8f-124">Sein Format ist als "Website Name Anwendungspfad für virtuelle Computer&#124;virtuellen Dienst Pfad&#124;Dienst Name '" definiert.</span><span class="sxs-lookup"><span data-stu-id="82d8f-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="82d8f-125">Beispiel: "Default Web Site/calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="82d8f-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="82d8f-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="82d8f-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="82d8f-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="82d8f-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
