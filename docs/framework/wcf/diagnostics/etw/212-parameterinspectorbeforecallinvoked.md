---
title: 212 - ParameterInspectorBeforeCallInvoked
ms.date: 03/30/2017
ms.assetid: 063fc8d2-ceac-4c18-8368-de84f2c78035
ms.openlocfilehash: 28c2aca4555d2e4ff498e450deae55ad6a87743c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279037"
---
# <a name="212---parameterinspectorbeforecallinvoked"></a><span data-ttu-id="420b3-102">212 - ParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="420b3-102">212 - ParameterInspectorBeforeCallInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="420b3-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="420b3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="420b3-104">id</span><span class="sxs-lookup"><span data-stu-id="420b3-104">ID</span></span>|<span data-ttu-id="420b3-105">212</span><span class="sxs-lookup"><span data-stu-id="420b3-105">212</span></span>|  
|<span data-ttu-id="420b3-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="420b3-106">Keywords</span></span>|<span data-ttu-id="420b3-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="420b3-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="420b3-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="420b3-108">Level</span></span>|<span data-ttu-id="420b3-109">Information</span><span class="sxs-lookup"><span data-stu-id="420b3-109">Information</span></span>|  
|<span data-ttu-id="420b3-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="420b3-110">Channel</span></span>|<span data-ttu-id="420b3-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="420b3-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="420b3-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="420b3-112">Description</span></span>  

 <span data-ttu-id="420b3-113">Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `BeforeCall`-Methode auf einem `ParameterInspector` aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="420b3-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="420b3-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="420b3-114">Message</span></span>  

 <span data-ttu-id="420b3-115">Der Verteiler hat 'BeforeCall' auf einem ParameterInspector vom Typ '%1' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="420b3-115">The Dispatcher invoked 'BeforeCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="420b3-116">Details</span><span class="sxs-lookup"><span data-stu-id="420b3-116">Details</span></span>  
  
|<span data-ttu-id="420b3-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="420b3-117">Data Item Name</span></span>|<span data-ttu-id="420b3-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="420b3-118">Data Item Type</span></span>|<span data-ttu-id="420b3-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="420b3-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="420b3-120">TypName</span><span class="sxs-lookup"><span data-stu-id="420b3-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="420b3-121">Der CLR-FullName für den Typ des aufgerufenen Inspektors.</span><span class="sxs-lookup"><span data-stu-id="420b3-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="420b3-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="420b3-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="420b3-123">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="420b3-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="420b3-124">Sein Format ist als "Website Name Anwendungspfad für virtuelle Computer&#124;virtuellen Dienst Pfad&#124;Dienst Name '" definiert.</span><span class="sxs-lookup"><span data-stu-id="420b3-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="420b3-125">Beispiel: "Default Web Site/calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="420b3-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="420b3-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="420b3-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="420b3-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="420b3-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
