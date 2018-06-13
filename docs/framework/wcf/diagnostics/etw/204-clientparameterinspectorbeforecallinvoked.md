---
title: 204 - ClientParameterInspectorBeforeCallInvoked
ms.date: 03/30/2017
ms.assetid: 8253555a-9002-4565-8ede-33d7a33a895f
ms.openlocfilehash: eb060cfa79b75452deae67705126a24b7ca9ffef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458584"
---
# <a name="204---clientparameterinspectorbeforecallinvoked"></a><span data-ttu-id="6d8b7-102">204 - ClientParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="6d8b7-102">204 - ClientParameterInspectorBeforeCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="6d8b7-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="6d8b7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6d8b7-104">Id</span><span class="sxs-lookup"><span data-stu-id="6d8b7-104">ID</span></span>|<span data-ttu-id="6d8b7-105">204</span><span class="sxs-lookup"><span data-stu-id="6d8b7-105">204</span></span>|  
|<span data-ttu-id="6d8b7-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="6d8b7-106">Keywords</span></span>|<span data-ttu-id="6d8b7-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6d8b7-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="6d8b7-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="6d8b7-108">Level</span></span>|<span data-ttu-id="6d8b7-109">Information</span><span class="sxs-lookup"><span data-stu-id="6d8b7-109">Information</span></span>|  
|<span data-ttu-id="6d8b7-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="6d8b7-110">Channel</span></span>|<span data-ttu-id="6d8b7-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="6d8b7-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6d8b7-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6d8b7-112">Description</span></span>  
 <span data-ttu-id="6d8b7-113">Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `BeforeCall`-Methode auf einem Clientparameterinspektor aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="6d8b7-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a client parameter inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6d8b7-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="6d8b7-114">Message</span></span>  
 <span data-ttu-id="6d8b7-115">Der Verteiler hat 'BeforeCall' auf einem ClientParameterInspector vom Typ '%1' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="6d8b7-115">The Dispatcher invoked 'BeforeCall' on a ClientParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6d8b7-116">Details</span><span class="sxs-lookup"><span data-stu-id="6d8b7-116">Details</span></span>  
  
|<span data-ttu-id="6d8b7-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="6d8b7-117">Data Item Name</span></span>|<span data-ttu-id="6d8b7-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="6d8b7-118">Data Item Type</span></span>|<span data-ttu-id="6d8b7-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6d8b7-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6d8b7-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="6d8b7-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="6d8b7-121">Der CLR-FullName für den Typ des aufgerufenen Inspektors.</span><span class="sxs-lookup"><span data-stu-id="6d8b7-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="6d8b7-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="6d8b7-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="6d8b7-123">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="6d8b7-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="6d8b7-124">Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="6d8b7-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="6d8b7-125">Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="6d8b7-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="6d8b7-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6d8b7-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="6d8b7-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="6d8b7-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
