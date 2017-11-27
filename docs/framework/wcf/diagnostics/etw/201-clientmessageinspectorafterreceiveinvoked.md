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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 907f4404e234ada2cf084f531a4de8fcfc84d6c0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="201---clientmessageinspectorafterreceiveinvoked"></a><span data-ttu-id="4293b-102">201 - ClientMessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="4293b-102">201 - ClientMessageInspectorAfterReceiveInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="4293b-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="4293b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4293b-104">ID</span><span class="sxs-lookup"><span data-stu-id="4293b-104">ID</span></span>|<span data-ttu-id="4293b-105">201</span><span class="sxs-lookup"><span data-stu-id="4293b-105">201</span></span>|  
|<span data-ttu-id="4293b-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="4293b-106">Keywords</span></span>|<span data-ttu-id="4293b-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4293b-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="4293b-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="4293b-108">Level</span></span>|<span data-ttu-id="4293b-109">Information</span><span class="sxs-lookup"><span data-stu-id="4293b-109">Information</span></span>|  
|<span data-ttu-id="4293b-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="4293b-110">Channel</span></span>|<span data-ttu-id="4293b-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="4293b-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4293b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4293b-112">Description</span></span>  
 <span data-ttu-id="4293b-113">Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `AfterReceiveReply`-Methode auf einem Clientmeldungsinspektor aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="4293b-113">This event is emitted after the Service Model has invoked the `AfterReceiveReply` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4293b-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="4293b-114">Message</span></span>  
 <span data-ttu-id="4293b-115">Der Verteiler hat 'AfterReceiveReply' auf einem ClientMessageInspector vom Typ '%1' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="4293b-115">The Dispatcher invoked 'AfterReceiveReply' on a ClientMessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4293b-116">Details</span><span class="sxs-lookup"><span data-stu-id="4293b-116">Details</span></span>  
  
|<span data-ttu-id="4293b-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="4293b-117">Data Item Name</span></span>|<span data-ttu-id="4293b-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="4293b-118">Data Item Type</span></span>|<span data-ttu-id="4293b-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4293b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4293b-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="4293b-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="4293b-121">Der CLR-FullName für den Typ des aufgerufenen Inspektors.</span><span class="sxs-lookup"><span data-stu-id="4293b-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="4293b-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="4293b-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="4293b-123">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="4293b-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="4293b-124">Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="4293b-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="4293b-125">Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="4293b-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="4293b-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4293b-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="4293b-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="4293b-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
