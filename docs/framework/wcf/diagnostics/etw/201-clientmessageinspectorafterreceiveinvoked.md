---
title: 201 - ClientMessageInspectorAfterReceiveInvoked
ms.date: 03/30/2017
ms.assetid: 9ff637f1-cc26-4400-ab9b-546f70e5057d
ms.openlocfilehash: 96ca318c141d49e2ac5594d5ee101658a2aa8f21
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459023"
---
# <a name="201---clientmessageinspectorafterreceiveinvoked"></a><span data-ttu-id="fada4-102">201 - ClientMessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="fada4-102">201 - ClientMessageInspectorAfterReceiveInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="fada4-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="fada4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fada4-104">Id</span><span class="sxs-lookup"><span data-stu-id="fada4-104">ID</span></span>|<span data-ttu-id="fada4-105">201</span><span class="sxs-lookup"><span data-stu-id="fada4-105">201</span></span>|  
|<span data-ttu-id="fada4-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="fada4-106">Keywords</span></span>|<span data-ttu-id="fada4-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fada4-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="fada4-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="fada4-108">Level</span></span>|<span data-ttu-id="fada4-109">Information</span><span class="sxs-lookup"><span data-stu-id="fada4-109">Information</span></span>|  
|<span data-ttu-id="fada4-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="fada4-110">Channel</span></span>|<span data-ttu-id="fada4-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="fada4-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fada4-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fada4-112">Description</span></span>  
 <span data-ttu-id="fada4-113">Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `AfterReceiveReply`-Methode auf einem Clientmeldungsinspektor aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="fada4-113">This event is emitted after the Service Model has invoked the `AfterReceiveReply` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fada4-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="fada4-114">Message</span></span>  
 <span data-ttu-id="fada4-115">Der Verteiler hat 'AfterReceiveReply' auf einem ClientMessageInspector vom Typ '%1' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="fada4-115">The Dispatcher invoked 'AfterReceiveReply' on a ClientMessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fada4-116">Details</span><span class="sxs-lookup"><span data-stu-id="fada4-116">Details</span></span>  
  
|<span data-ttu-id="fada4-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="fada4-117">Data Item Name</span></span>|<span data-ttu-id="fada4-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="fada4-118">Data Item Type</span></span>|<span data-ttu-id="fada4-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fada4-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fada4-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="fada4-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="fada4-121">Der CLR-FullName für den Typ des aufgerufenen Inspektors.</span><span class="sxs-lookup"><span data-stu-id="fada4-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="fada4-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="fada4-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="fada4-123">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="fada4-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="fada4-124">Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="fada4-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="fada4-125">Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="fada4-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="fada4-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fada4-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="fada4-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="fada4-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
