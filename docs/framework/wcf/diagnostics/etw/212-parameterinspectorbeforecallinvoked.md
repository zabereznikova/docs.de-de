---
title: 212 - ParameterInspectorBeforeCallInvoked
ms.date: 03/30/2017
ms.assetid: 063fc8d2-ceac-4c18-8368-de84f2c78035
ms.openlocfilehash: 02d4a4ed1e96983e132a1943dd39f9f885e5596a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781848"
---
# <a name="212---parameterinspectorbeforecallinvoked"></a><span data-ttu-id="cfff5-102">212 - ParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="cfff5-102">212 - ParameterInspectorBeforeCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="cfff5-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="cfff5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cfff5-104">ID</span><span class="sxs-lookup"><span data-stu-id="cfff5-104">ID</span></span>|<span data-ttu-id="cfff5-105">212</span><span class="sxs-lookup"><span data-stu-id="cfff5-105">212</span></span>|  
|<span data-ttu-id="cfff5-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="cfff5-106">Keywords</span></span>|<span data-ttu-id="cfff5-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="cfff5-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="cfff5-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="cfff5-108">Level</span></span>|<span data-ttu-id="cfff5-109">Information</span><span class="sxs-lookup"><span data-stu-id="cfff5-109">Information</span></span>|  
|<span data-ttu-id="cfff5-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="cfff5-110">Channel</span></span>|<span data-ttu-id="cfff5-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="cfff5-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="cfff5-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cfff5-112">Description</span></span>  
 <span data-ttu-id="cfff5-113">Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `BeforeCall`-Methode auf einem `ParameterInspector` aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="cfff5-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="cfff5-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="cfff5-114">Message</span></span>  
 <span data-ttu-id="cfff5-115">Der Verteiler hat 'BeforeCall' auf einem ParameterInspector vom Typ '%1' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="cfff5-115">The Dispatcher invoked 'BeforeCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="cfff5-116">Details</span><span class="sxs-lookup"><span data-stu-id="cfff5-116">Details</span></span>  
  
|<span data-ttu-id="cfff5-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="cfff5-117">Data Item Name</span></span>|<span data-ttu-id="cfff5-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="cfff5-118">Data Item Type</span></span>|<span data-ttu-id="cfff5-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cfff5-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="cfff5-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="cfff5-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="cfff5-121">Der CLR-FullName für den Typ des aufgerufenen Inspektors.</span><span class="sxs-lookup"><span data-stu-id="cfff5-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="cfff5-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="cfff5-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="cfff5-123">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="cfff5-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="cfff5-124">Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="cfff5-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="cfff5-125">Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="cfff5-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="cfff5-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="cfff5-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="cfff5-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="cfff5-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
