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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8de4338fd9d1d18ab1f689df39b2247a29d2dcf5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="209---messageinspectorbeforesendinvoked"></a><span data-ttu-id="f38ea-102">209 - MessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="f38ea-102">209 - MessageInspectorBeforeSendInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="f38ea-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f38ea-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f38ea-104">ID</span><span class="sxs-lookup"><span data-stu-id="f38ea-104">ID</span></span>|<span data-ttu-id="f38ea-105">209</span><span class="sxs-lookup"><span data-stu-id="f38ea-105">209</span></span>|  
|<span data-ttu-id="f38ea-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="f38ea-106">Keywords</span></span>|<span data-ttu-id="f38ea-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f38ea-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="f38ea-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="f38ea-108">Level</span></span>|<span data-ttu-id="f38ea-109">Information</span><span class="sxs-lookup"><span data-stu-id="f38ea-109">Information</span></span>|  
|<span data-ttu-id="f38ea-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="f38ea-110">Channel</span></span>|<span data-ttu-id="f38ea-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="f38ea-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f38ea-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f38ea-112">Description</span></span>  
 <span data-ttu-id="f38ea-113">Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `BeforeSend`-Methode auf einem Nachrichteninspektor aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="f38ea-113">This event is emitted after the Service Model has invoked the `BeforeSend` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f38ea-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="f38ea-114">Message</span></span>  
 <span data-ttu-id="f38ea-115">Der Verteiler hat 'BeforeSendRequest' auf einem MessageInspector vom Typ '%1' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="f38ea-115">The Dispatcher invoked 'BeforeSendRequest' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f38ea-116">Details</span><span class="sxs-lookup"><span data-stu-id="f38ea-116">Details</span></span>  
  
|<span data-ttu-id="f38ea-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="f38ea-117">Data Item Name</span></span>|<span data-ttu-id="f38ea-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="f38ea-118">Data Item Type</span></span>|<span data-ttu-id="f38ea-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f38ea-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f38ea-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="f38ea-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="f38ea-121">Der CLR-FullName des aufgerufenen `MessageInspector`-Typs.</span><span class="sxs-lookup"><span data-stu-id="f38ea-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="f38ea-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="f38ea-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="f38ea-123">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="f38ea-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="f38ea-124">Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="f38ea-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="f38ea-125">Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="f38ea-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="f38ea-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f38ea-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f38ea-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f38ea-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
