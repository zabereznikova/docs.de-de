---
title: 211 - ParameterInspectorAfterCallInvoked
ms.date: 03/30/2017
ms.assetid: c0e21297-10b8-4456-a0e1-e019145cd5ac
ms.openlocfilehash: ada3ced31def2bb821b975e09f50ad83f28d56bf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459716"
---
# <a name="211---parameterinspectoraftercallinvoked"></a><span data-ttu-id="fae57-102">211 - ParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="fae57-102">211 - ParameterInspectorAfterCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="fae57-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="fae57-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fae57-104">ID</span><span class="sxs-lookup"><span data-stu-id="fae57-104">ID</span></span>|<span data-ttu-id="fae57-105">211</span><span class="sxs-lookup"><span data-stu-id="fae57-105">211</span></span>|  
|<span data-ttu-id="fae57-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="fae57-106">Keywords</span></span>|<span data-ttu-id="fae57-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fae57-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="fae57-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="fae57-108">Level</span></span>|<span data-ttu-id="fae57-109">Information</span><span class="sxs-lookup"><span data-stu-id="fae57-109">Information</span></span>|  
|<span data-ttu-id="fae57-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="fae57-110">Channel</span></span>|<span data-ttu-id="fae57-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="fae57-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fae57-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fae57-112">Description</span></span>  
 <span data-ttu-id="fae57-113">Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `AfterCall`-Methode auf einem `ParameterInspector` aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="fae57-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fae57-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="fae57-114">Message</span></span>  
 <span data-ttu-id="fae57-115">Der Verteiler hat 'AfterCall' auf einem ParameterInspector vom Typ '%1' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="fae57-115">The Dispatcher invoked 'AfterCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fae57-116">Details</span><span class="sxs-lookup"><span data-stu-id="fae57-116">Details</span></span>  
  
|<span data-ttu-id="fae57-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="fae57-117">Data Item Name</span></span>|<span data-ttu-id="fae57-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="fae57-118">Data Item Type</span></span>|<span data-ttu-id="fae57-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fae57-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fae57-120">Typname</span><span class="sxs-lookup"><span data-stu-id="fae57-120">Type Name</span></span>|`xs:string`|<span data-ttu-id="fae57-121">Der CLR-FullName des aufgerufenen `ParameterInspector`-Typs.</span><span class="sxs-lookup"><span data-stu-id="fae57-121">The CLR FullName of the type of the invoked `ParameterInspector`.</span></span>|  
|<span data-ttu-id="fae57-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="fae57-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="fae57-123">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="fae57-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="fae57-124">Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="fae57-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="fae57-125">Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="fae57-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="fae57-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fae57-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="fae57-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="fae57-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
