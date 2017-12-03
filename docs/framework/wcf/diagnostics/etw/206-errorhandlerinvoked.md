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
ms.openlocfilehash: 4ff48217b1430002e1590ec3fdb1707d65075ffe
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="206---errorhandlerinvoked"></a><span data-ttu-id="904ef-102">206 - ErrorHandlerInvoked</span><span class="sxs-lookup"><span data-stu-id="904ef-102">206 - ErrorHandlerInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="904ef-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="904ef-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="904ef-104">ID</span><span class="sxs-lookup"><span data-stu-id="904ef-104">ID</span></span>|<span data-ttu-id="904ef-105">206</span><span class="sxs-lookup"><span data-stu-id="904ef-105">206</span></span>|  
|<span data-ttu-id="904ef-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="904ef-106">Keywords</span></span>|<span data-ttu-id="904ef-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="904ef-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="904ef-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="904ef-108">Level</span></span>|<span data-ttu-id="904ef-109">Information</span><span class="sxs-lookup"><span data-stu-id="904ef-109">Information</span></span>|  
|<span data-ttu-id="904ef-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="904ef-110">Channel</span></span>|<span data-ttu-id="904ef-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="904ef-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="904ef-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="904ef-112">Description</span></span>  
 <span data-ttu-id="904ef-113">Dieses Ereignis wird ausgegeben, nachdem ein `ErrorHandler` die Gelegenheit hatte, eine Ausnahme zu behandeln, die während eines Dienstvorgangs aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="904ef-113">This event is emitted after an `ErrorHandler` has had an opportunity to handle an exception that occurred in a service operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="904ef-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="904ef-114">Message</span></span>  
 <span data-ttu-id="904ef-115">Der Verteiler hat einen ErrorHandler vom Typ "%1" mit einer Ausnahme vom Typ "%3" aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="904ef-115">The Dispatcher invoked an ErrorHandler of type '%1' with an exception of type '%3'.</span></span> <span data-ttu-id="904ef-116">ErrorHandled == '%2'.</span><span class="sxs-lookup"><span data-stu-id="904ef-116">ErrorHandled == '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="904ef-117">Details</span><span class="sxs-lookup"><span data-stu-id="904ef-117">Details</span></span>  
  
|<span data-ttu-id="904ef-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="904ef-118">Data Item Name</span></span>|<span data-ttu-id="904ef-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="904ef-119">Data Item Type</span></span>|<span data-ttu-id="904ef-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="904ef-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="904ef-121">TypeName</span><span class="sxs-lookup"><span data-stu-id="904ef-121">TypeName</span></span>|`xs:string`|<span data-ttu-id="904ef-122">Der CLR-FullName des aufgerufenen `ErrorHandler`-Typs.</span><span class="sxs-lookup"><span data-stu-id="904ef-122">The CLR FullName of the type of the invoked `ErrorHandler`.</span></span>|  
|<span data-ttu-id="904ef-123">Handled</span><span class="sxs-lookup"><span data-stu-id="904ef-123">Handled</span></span>|`xs:unsignedByte`|<span data-ttu-id="904ef-124">`true`, wenn der Fehlerhandler den Fehler behandelt hat, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="904ef-124">`true` if the error handler handled the error, otherwise `false`.</span></span>|  
|<span data-ttu-id="904ef-125">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="904ef-125">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="904ef-126">Der CLR-FullName der Ausnahme, die behandelt wurde.</span><span class="sxs-lookup"><span data-stu-id="904ef-126">The CLR FullName of the exception that was being handled.</span></span>|  
|<span data-ttu-id="904ef-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="904ef-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="904ef-128">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="904ef-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="904ef-129">Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="904ef-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="904ef-130">Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="904ef-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="904ef-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="904ef-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="904ef-132">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="904ef-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
