---
title: 206 - ErrorHandlerInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97340f4d-4e09-4e42-a17a-982b3868dbcf
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 43acd7ae7bbfc84e1d1ffb1bf4fa49a3dd3f191a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="206---errorhandlerinvoked"></a><span data-ttu-id="4aaca-102">206 - ErrorHandlerInvoked</span><span class="sxs-lookup"><span data-stu-id="4aaca-102">206 - ErrorHandlerInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="4aaca-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="4aaca-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4aaca-104">Id</span><span class="sxs-lookup"><span data-stu-id="4aaca-104">ID</span></span>|<span data-ttu-id="4aaca-105">206</span><span class="sxs-lookup"><span data-stu-id="4aaca-105">206</span></span>|  
|<span data-ttu-id="4aaca-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="4aaca-106">Keywords</span></span>|<span data-ttu-id="4aaca-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4aaca-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="4aaca-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="4aaca-108">Level</span></span>|<span data-ttu-id="4aaca-109">Information</span><span class="sxs-lookup"><span data-stu-id="4aaca-109">Information</span></span>|  
|<span data-ttu-id="4aaca-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="4aaca-110">Channel</span></span>|<span data-ttu-id="4aaca-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="4aaca-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4aaca-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4aaca-112">Description</span></span>  
 <span data-ttu-id="4aaca-113">Dieses Ereignis wird ausgegeben, nachdem ein `ErrorHandler` die Gelegenheit hatte, eine Ausnahme zu behandeln, die während eines Dienstvorgangs aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="4aaca-113">This event is emitted after an `ErrorHandler` has had an opportunity to handle an exception that occurred in a service operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4aaca-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="4aaca-114">Message</span></span>  
 <span data-ttu-id="4aaca-115">Der Verteiler hat einen ErrorHandler vom Typ "%1" mit einer Ausnahme vom Typ "%3" aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="4aaca-115">The Dispatcher invoked an ErrorHandler of type '%1' with an exception of type '%3'.</span></span> <span data-ttu-id="4aaca-116">ErrorHandled == '%2'.</span><span class="sxs-lookup"><span data-stu-id="4aaca-116">ErrorHandled == '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4aaca-117">Details</span><span class="sxs-lookup"><span data-stu-id="4aaca-117">Details</span></span>  
  
|<span data-ttu-id="4aaca-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="4aaca-118">Data Item Name</span></span>|<span data-ttu-id="4aaca-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="4aaca-119">Data Item Type</span></span>|<span data-ttu-id="4aaca-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4aaca-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4aaca-121">TypeName</span><span class="sxs-lookup"><span data-stu-id="4aaca-121">TypeName</span></span>|`xs:string`|<span data-ttu-id="4aaca-122">Der CLR-FullName des aufgerufenen `ErrorHandler`-Typs.</span><span class="sxs-lookup"><span data-stu-id="4aaca-122">The CLR FullName of the type of the invoked `ErrorHandler`.</span></span>|  
|<span data-ttu-id="4aaca-123">Handled</span><span class="sxs-lookup"><span data-stu-id="4aaca-123">Handled</span></span>|`xs:unsignedByte`|<span data-ttu-id="4aaca-124">`true`, wenn der Fehlerhandler den Fehler behandelt hat, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="4aaca-124">`true` if the error handler handled the error, otherwise `false`.</span></span>|  
|<span data-ttu-id="4aaca-125">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="4aaca-125">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="4aaca-126">Der CLR-FullName der Ausnahme, die behandelt wurde.</span><span class="sxs-lookup"><span data-stu-id="4aaca-126">The CLR FullName of the exception that was being handled.</span></span>|  
|<span data-ttu-id="4aaca-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="4aaca-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="4aaca-128">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="4aaca-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="4aaca-129">Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="4aaca-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="4aaca-130">Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="4aaca-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="4aaca-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4aaca-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="4aaca-132">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="4aaca-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
