---
title: 203 - ClientParameterInspectorAfterCallInvoked
ms.date: 03/30/2017
ms.assetid: b9592212-07e2-43e0-8b00-affd195cf55a
ms.openlocfilehash: 57192b44a0c3babc77fcca13ad4a1433b85bfdd7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781939"
---
# <a name="203---clientparameterinspectoraftercallinvoked"></a><span data-ttu-id="9c04a-102">203 - ClientParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="9c04a-102">203 - ClientParameterInspectorAfterCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="9c04a-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9c04a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9c04a-104">ID</span><span class="sxs-lookup"><span data-stu-id="9c04a-104">ID</span></span>|<span data-ttu-id="9c04a-105">203</span><span class="sxs-lookup"><span data-stu-id="9c04a-105">203</span></span>|  
|<span data-ttu-id="9c04a-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="9c04a-106">Keywords</span></span>|<span data-ttu-id="9c04a-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9c04a-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="9c04a-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="9c04a-108">Level</span></span>|<span data-ttu-id="9c04a-109">Information</span><span class="sxs-lookup"><span data-stu-id="9c04a-109">Information</span></span>|  
|<span data-ttu-id="9c04a-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="9c04a-110">Channel</span></span>|<span data-ttu-id="9c04a-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="9c04a-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9c04a-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c04a-112">Description</span></span>  
 <span data-ttu-id="9c04a-113">Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `AfterCall`-Methode auf einem Clientparameterinspektor aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="9c04a-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a client parameter inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9c04a-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="9c04a-114">Message</span></span>  
 <span data-ttu-id="9c04a-115">Der Verteiler hat 'AfterCall' auf einem ClientParameterInspector vom Typ '%1' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="9c04a-115">The Dispatcher invoked 'AfterCall' on a ClientParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9c04a-116">Details</span><span class="sxs-lookup"><span data-stu-id="9c04a-116">Details</span></span>  
  
|<span data-ttu-id="9c04a-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="9c04a-117">Data Item Name</span></span>|<span data-ttu-id="9c04a-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="9c04a-118">Data Item Type</span></span>|<span data-ttu-id="9c04a-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c04a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9c04a-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="9c04a-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="9c04a-121">Der CLR-FullName für den Typ des aufgerufenen Inspektors.</span><span class="sxs-lookup"><span data-stu-id="9c04a-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="9c04a-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="9c04a-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="9c04a-123">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="9c04a-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="9c04a-124">Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="9c04a-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="9c04a-125">Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="9c04a-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="9c04a-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9c04a-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="9c04a-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="9c04a-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
