---
title: 209 - MessageInspectorBeforeSendInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d710875-fb77-4463-978b-bc86d59d84cd
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3341f9ae5600536a7d824034582bf232f5be90ad
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="209---messageinspectorbeforesendinvoked"></a><span data-ttu-id="f76b4-102">209 - MessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="f76b4-102">209 - MessageInspectorBeforeSendInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="f76b4-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f76b4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f76b4-104">ID</span><span class="sxs-lookup"><span data-stu-id="f76b4-104">ID</span></span>|<span data-ttu-id="f76b4-105">209</span><span class="sxs-lookup"><span data-stu-id="f76b4-105">209</span></span>|  
|<span data-ttu-id="f76b4-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="f76b4-106">Keywords</span></span>|<span data-ttu-id="f76b4-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f76b4-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="f76b4-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="f76b4-108">Level</span></span>|<span data-ttu-id="f76b4-109">Information</span><span class="sxs-lookup"><span data-stu-id="f76b4-109">Information</span></span>|  
|<span data-ttu-id="f76b4-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="f76b4-110">Channel</span></span>|<span data-ttu-id="f76b4-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="f76b4-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f76b4-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f76b4-112">Description</span></span>  
 <span data-ttu-id="f76b4-113">Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `BeforeSend`-Methode auf einem Nachrichteninspektor aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="f76b4-113">This event is emitted after the Service Model has invoked the `BeforeSend` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f76b4-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="f76b4-114">Message</span></span>  
 <span data-ttu-id="f76b4-115">Der Verteiler hat 'BeforeSendRequest' auf einem MessageInspector vom Typ '%1' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="f76b4-115">The Dispatcher invoked 'BeforeSendRequest' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f76b4-116">Details</span><span class="sxs-lookup"><span data-stu-id="f76b4-116">Details</span></span>  
  
|<span data-ttu-id="f76b4-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="f76b4-117">Data Item Name</span></span>|<span data-ttu-id="f76b4-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="f76b4-118">Data Item Type</span></span>|<span data-ttu-id="f76b4-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f76b4-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f76b4-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="f76b4-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="f76b4-121">Der CLR-FullName des aufgerufenen `MessageInspector`-Typs.</span><span class="sxs-lookup"><span data-stu-id="f76b4-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="f76b4-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="f76b4-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="f76b4-123">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="f76b4-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="f76b4-124">Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="f76b4-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="f76b4-125">Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="f76b4-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="f76b4-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f76b4-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f76b4-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f76b4-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
