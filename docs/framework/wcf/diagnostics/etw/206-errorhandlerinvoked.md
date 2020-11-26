---
title: 206 - ErrorHandlerInvoked
ms.date: 03/30/2017
ms.assetid: 97340f4d-4e09-4e42-a17a-982b3868dbcf
ms.openlocfilehash: 99415733624752217d32f6f026a419b2b32bfa7b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244612"
---
# <a name="206---errorhandlerinvoked"></a><span data-ttu-id="9fdfc-102">206 - ErrorHandlerInvoked</span><span class="sxs-lookup"><span data-stu-id="9fdfc-102">206 - ErrorHandlerInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="9fdfc-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9fdfc-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9fdfc-104">id</span><span class="sxs-lookup"><span data-stu-id="9fdfc-104">ID</span></span>|<span data-ttu-id="9fdfc-105">206</span><span class="sxs-lookup"><span data-stu-id="9fdfc-105">206</span></span>|  
|<span data-ttu-id="9fdfc-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="9fdfc-106">Keywords</span></span>|<span data-ttu-id="9fdfc-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9fdfc-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="9fdfc-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="9fdfc-108">Level</span></span>|<span data-ttu-id="9fdfc-109">Information</span><span class="sxs-lookup"><span data-stu-id="9fdfc-109">Information</span></span>|  
|<span data-ttu-id="9fdfc-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="9fdfc-110">Channel</span></span>|<span data-ttu-id="9fdfc-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="9fdfc-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9fdfc-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9fdfc-112">Description</span></span>  

 <span data-ttu-id="9fdfc-113">Dieses Ereignis wird ausgegeben, nachdem ein `ErrorHandler` die Gelegenheit hatte, eine Ausnahme zu behandeln, die während eines Dienstvorgangs aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="9fdfc-113">This event is emitted after an `ErrorHandler` has had an opportunity to handle an exception that occurred in a service operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9fdfc-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="9fdfc-114">Message</span></span>  

 <span data-ttu-id="9fdfc-115">Der Verteiler hat einen Errorhandler vom Typ ' %1 ' mit einer Ausnahme vom Typ ' %3 ' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="9fdfc-115">The Dispatcher invoked an ErrorHandler of type '%1' with an exception of type '%3'.</span></span> <span data-ttu-id="9fdfc-116">ErrorHandled == '%2'.</span><span class="sxs-lookup"><span data-stu-id="9fdfc-116">ErrorHandled == '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9fdfc-117">Details</span><span class="sxs-lookup"><span data-stu-id="9fdfc-117">Details</span></span>  
  
|<span data-ttu-id="9fdfc-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="9fdfc-118">Data Item Name</span></span>|<span data-ttu-id="9fdfc-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="9fdfc-119">Data Item Type</span></span>|<span data-ttu-id="9fdfc-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9fdfc-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9fdfc-121">TypName</span><span class="sxs-lookup"><span data-stu-id="9fdfc-121">TypeName</span></span>|`xs:string`|<span data-ttu-id="9fdfc-122">Der CLR-FullName des aufgerufenen `ErrorHandler`-Typs.</span><span class="sxs-lookup"><span data-stu-id="9fdfc-122">The CLR FullName of the type of the invoked `ErrorHandler`.</span></span>|  
|<span data-ttu-id="9fdfc-123">Verarbeitete</span><span class="sxs-lookup"><span data-stu-id="9fdfc-123">Handled</span></span>|`xs:unsignedByte`|<span data-ttu-id="9fdfc-124">`true`, wenn der Fehlerhandler den Fehler behandelt hat, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="9fdfc-124">`true` if the error handler handled the error, otherwise `false`.</span></span>|  
|<span data-ttu-id="9fdfc-125">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="9fdfc-125">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="9fdfc-126">Der CLR-FullName der Ausnahme, die behandelt wurde.</span><span class="sxs-lookup"><span data-stu-id="9fdfc-126">The CLR FullName of the exception that was being handled.</span></span>|  
|<span data-ttu-id="9fdfc-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="9fdfc-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="9fdfc-128">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="9fdfc-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="9fdfc-129">Sein Format ist als "Website Name Anwendungspfad für virtuelle Computer&#124;virtuellen Dienst Pfad&#124;Dienst Name '" definiert.</span><span class="sxs-lookup"><span data-stu-id="9fdfc-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="9fdfc-130">Beispiel: "Default Web Site/calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="9fdfc-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="9fdfc-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9fdfc-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="9fdfc-132">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="9fdfc-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
