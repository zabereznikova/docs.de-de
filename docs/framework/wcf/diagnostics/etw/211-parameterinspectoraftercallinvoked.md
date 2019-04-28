---
title: 211 - ParameterInspectorAfterCallInvoked
ms.date: 03/30/2017
ms.assetid: c0e21297-10b8-4456-a0e1-e019145cd5ac
ms.openlocfilehash: ada3ced31def2bb821b975e09f50ad83f28d56bf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781861"
---
# <a name="211---parameterinspectoraftercallinvoked"></a><span data-ttu-id="9fa33-102">211 - ParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="9fa33-102">211 - ParameterInspectorAfterCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="9fa33-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9fa33-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9fa33-104">ID</span><span class="sxs-lookup"><span data-stu-id="9fa33-104">ID</span></span>|<span data-ttu-id="9fa33-105">211</span><span class="sxs-lookup"><span data-stu-id="9fa33-105">211</span></span>|  
|<span data-ttu-id="9fa33-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="9fa33-106">Keywords</span></span>|<span data-ttu-id="9fa33-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9fa33-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="9fa33-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="9fa33-108">Level</span></span>|<span data-ttu-id="9fa33-109">Information</span><span class="sxs-lookup"><span data-stu-id="9fa33-109">Information</span></span>|  
|<span data-ttu-id="9fa33-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="9fa33-110">Channel</span></span>|<span data-ttu-id="9fa33-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="9fa33-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9fa33-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9fa33-112">Description</span></span>  
 <span data-ttu-id="9fa33-113">Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `AfterCall`-Methode auf einem `ParameterInspector` aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="9fa33-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9fa33-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="9fa33-114">Message</span></span>  
 <span data-ttu-id="9fa33-115">Der Verteiler hat 'AfterCall' auf einem ParameterInspector vom Typ '%1' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="9fa33-115">The Dispatcher invoked 'AfterCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9fa33-116">Details</span><span class="sxs-lookup"><span data-stu-id="9fa33-116">Details</span></span>  
  
|<span data-ttu-id="9fa33-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="9fa33-117">Data Item Name</span></span>|<span data-ttu-id="9fa33-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="9fa33-118">Data Item Type</span></span>|<span data-ttu-id="9fa33-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9fa33-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9fa33-120">Typname</span><span class="sxs-lookup"><span data-stu-id="9fa33-120">Type Name</span></span>|`xs:string`|<span data-ttu-id="9fa33-121">Der CLR-FullName des aufgerufenen `ParameterInspector`-Typs.</span><span class="sxs-lookup"><span data-stu-id="9fa33-121">The CLR FullName of the type of the invoked `ParameterInspector`.</span></span>|  
|<span data-ttu-id="9fa33-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="9fa33-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="9fa33-123">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="9fa33-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="9fa33-124">Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="9fa33-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="9fa33-125">Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="9fa33-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="9fa33-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9fa33-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="9fa33-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="9fa33-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
