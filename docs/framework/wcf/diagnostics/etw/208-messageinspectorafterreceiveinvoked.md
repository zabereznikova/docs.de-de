---
title: 208 - MessageInspectorAfterReceiveInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dfb5f7b0-4346-4949-8104-351726b1f502
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cdb89eb9f2a50db20f6da53a2b3f527aef8c0ed1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="208---messageinspectorafterreceiveinvoked"></a><span data-ttu-id="de9ae-102">208 - MessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="de9ae-102">208 - MessageInspectorAfterReceiveInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="de9ae-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="de9ae-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="de9ae-104">ID</span><span class="sxs-lookup"><span data-stu-id="de9ae-104">ID</span></span>|<span data-ttu-id="de9ae-105">208</span><span class="sxs-lookup"><span data-stu-id="de9ae-105">208</span></span>|  
|<span data-ttu-id="de9ae-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="de9ae-106">Keywords</span></span>|<span data-ttu-id="de9ae-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="de9ae-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="de9ae-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="de9ae-108">Level</span></span>|<span data-ttu-id="de9ae-109">Information</span><span class="sxs-lookup"><span data-stu-id="de9ae-109">Information</span></span>|  
|<span data-ttu-id="de9ae-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="de9ae-110">Channel</span></span>|<span data-ttu-id="de9ae-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="de9ae-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="de9ae-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="de9ae-112">Description</span></span>  
 <span data-ttu-id="de9ae-113">Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `AfterReceive`-Methode auf einem Nachrichteninspektor aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="de9ae-113">This event is emitted after the Service Model has invoked the `AfterReceive` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="de9ae-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="de9ae-114">Message</span></span>  
 <span data-ttu-id="de9ae-115">Der Verteiler hat 'AfterReceiveReply' auf einem MessageInspector vom Typ '%1' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="de9ae-115">The Dispatcher invoked 'AfterReceiveReply' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="de9ae-116">Details</span><span class="sxs-lookup"><span data-stu-id="de9ae-116">Details</span></span>  
  
|<span data-ttu-id="de9ae-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="de9ae-117">Data Item Name</span></span>|<span data-ttu-id="de9ae-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="de9ae-118">Data Item Type</span></span>|<span data-ttu-id="de9ae-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="de9ae-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="de9ae-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="de9ae-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="de9ae-121">Der CLR-FullName des aufgerufenen `MessageInspector`-Typs.</span><span class="sxs-lookup"><span data-stu-id="de9ae-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="de9ae-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="de9ae-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="de9ae-123">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="de9ae-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="de9ae-124">Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="de9ae-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="de9ae-125">Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="de9ae-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="de9ae-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="de9ae-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="de9ae-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="de9ae-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
