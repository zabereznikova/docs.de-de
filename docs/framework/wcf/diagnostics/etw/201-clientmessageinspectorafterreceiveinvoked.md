---
title: 201 - ClientMessageInspectorAfterReceiveInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9ff637f1-cc26-4400-ab9b-546f70e5057d
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 213808824051c812717e1e5b1f379be63824e255
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="201---clientmessageinspectorafterreceiveinvoked"></a><span data-ttu-id="f845d-102">201 - ClientMessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="f845d-102">201 - ClientMessageInspectorAfterReceiveInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="f845d-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f845d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f845d-104">Id</span><span class="sxs-lookup"><span data-stu-id="f845d-104">ID</span></span>|<span data-ttu-id="f845d-105">201</span><span class="sxs-lookup"><span data-stu-id="f845d-105">201</span></span>|  
|<span data-ttu-id="f845d-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="f845d-106">Keywords</span></span>|<span data-ttu-id="f845d-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f845d-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="f845d-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="f845d-108">Level</span></span>|<span data-ttu-id="f845d-109">Information</span><span class="sxs-lookup"><span data-stu-id="f845d-109">Information</span></span>|  
|<span data-ttu-id="f845d-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="f845d-110">Channel</span></span>|<span data-ttu-id="f845d-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="f845d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f845d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f845d-112">Description</span></span>  
 <span data-ttu-id="f845d-113">Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `AfterReceiveReply`-Methode auf einem Clientmeldungsinspektor aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="f845d-113">This event is emitted after the Service Model has invoked the `AfterReceiveReply` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f845d-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="f845d-114">Message</span></span>  
 <span data-ttu-id="f845d-115">Der Verteiler hat 'AfterReceiveReply' auf einem ClientMessageInspector vom Typ '%1' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="f845d-115">The Dispatcher invoked 'AfterReceiveReply' on a ClientMessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f845d-116">Details</span><span class="sxs-lookup"><span data-stu-id="f845d-116">Details</span></span>  
  
|<span data-ttu-id="f845d-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="f845d-117">Data Item Name</span></span>|<span data-ttu-id="f845d-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="f845d-118">Data Item Type</span></span>|<span data-ttu-id="f845d-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f845d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f845d-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="f845d-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="f845d-121">Der CLR-FullName für den Typ des aufgerufenen Inspektors.</span><span class="sxs-lookup"><span data-stu-id="f845d-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="f845d-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="f845d-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="f845d-123">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="f845d-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="f845d-124">Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="f845d-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="f845d-125">Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="f845d-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="f845d-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f845d-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f845d-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f845d-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
