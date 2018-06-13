---
title: 212 - ParameterInspectorBeforeCallInvoked
ms.date: 03/30/2017
ms.assetid: 063fc8d2-ceac-4c18-8368-de84f2c78035
ms.openlocfilehash: 02d4a4ed1e96983e132a1943dd39f9f885e5596a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458805"
---
# <a name="212---parameterinspectorbeforecallinvoked"></a><span data-ttu-id="ecce1-102">212 - ParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="ecce1-102">212 - ParameterInspectorBeforeCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="ecce1-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ecce1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ecce1-104">Id</span><span class="sxs-lookup"><span data-stu-id="ecce1-104">ID</span></span>|<span data-ttu-id="ecce1-105">212</span><span class="sxs-lookup"><span data-stu-id="ecce1-105">212</span></span>|  
|<span data-ttu-id="ecce1-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="ecce1-106">Keywords</span></span>|<span data-ttu-id="ecce1-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ecce1-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="ecce1-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="ecce1-108">Level</span></span>|<span data-ttu-id="ecce1-109">Information</span><span class="sxs-lookup"><span data-stu-id="ecce1-109">Information</span></span>|  
|<span data-ttu-id="ecce1-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="ecce1-110">Channel</span></span>|<span data-ttu-id="ecce1-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="ecce1-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ecce1-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ecce1-112">Description</span></span>  
 <span data-ttu-id="ecce1-113">Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `BeforeCall`-Methode auf einem `ParameterInspector` aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="ecce1-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ecce1-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="ecce1-114">Message</span></span>  
 <span data-ttu-id="ecce1-115">Der Verteiler hat 'BeforeCall' auf einem ParameterInspector vom Typ '%1' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ecce1-115">The Dispatcher invoked 'BeforeCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ecce1-116">Details</span><span class="sxs-lookup"><span data-stu-id="ecce1-116">Details</span></span>  
  
|<span data-ttu-id="ecce1-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="ecce1-117">Data Item Name</span></span>|<span data-ttu-id="ecce1-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="ecce1-118">Data Item Type</span></span>|<span data-ttu-id="ecce1-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ecce1-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ecce1-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="ecce1-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="ecce1-121">Der CLR-FullName für den Typ des aufgerufenen Inspektors.</span><span class="sxs-lookup"><span data-stu-id="ecce1-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="ecce1-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="ecce1-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="ecce1-123">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="ecce1-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="ecce1-124">Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="ecce1-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="ecce1-125">Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="ecce1-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="ecce1-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ecce1-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="ecce1-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ecce1-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
