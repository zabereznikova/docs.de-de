---
title: 206 - ErrorHandlerInvoked
ms.date: 03/30/2017
ms.assetid: 97340f4d-4e09-4e42-a17a-982b3868dbcf
ms.openlocfilehash: 40a92d77c57728249569a854eab8767ff371bca2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781926"
---
# <a name="206---errorhandlerinvoked"></a><span data-ttu-id="9ca19-102">206 - ErrorHandlerInvoked</span><span class="sxs-lookup"><span data-stu-id="9ca19-102">206 - ErrorHandlerInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="9ca19-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9ca19-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9ca19-104">ID</span><span class="sxs-lookup"><span data-stu-id="9ca19-104">ID</span></span>|<span data-ttu-id="9ca19-105">206</span><span class="sxs-lookup"><span data-stu-id="9ca19-105">206</span></span>|  
|<span data-ttu-id="9ca19-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="9ca19-106">Keywords</span></span>|<span data-ttu-id="9ca19-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9ca19-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="9ca19-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="9ca19-108">Level</span></span>|<span data-ttu-id="9ca19-109">Information</span><span class="sxs-lookup"><span data-stu-id="9ca19-109">Information</span></span>|  
|<span data-ttu-id="9ca19-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="9ca19-110">Channel</span></span>|<span data-ttu-id="9ca19-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="9ca19-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9ca19-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9ca19-112">Description</span></span>  
 <span data-ttu-id="9ca19-113">Dieses Ereignis wird ausgegeben, nachdem ein `ErrorHandler` die Gelegenheit hatte, eine Ausnahme zu behandeln, die während eines Dienstvorgangs aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="9ca19-113">This event is emitted after an `ErrorHandler` has had an opportunity to handle an exception that occurred in a service operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9ca19-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="9ca19-114">Message</span></span>  
 <span data-ttu-id="9ca19-115">Der Verteiler hat einen ErrorHandler vom Typ "%1" mit einer Ausnahme vom Typ "%3" aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="9ca19-115">The Dispatcher invoked an ErrorHandler of type '%1' with an exception of type '%3'.</span></span> <span data-ttu-id="9ca19-116">ErrorHandled == '%2'.</span><span class="sxs-lookup"><span data-stu-id="9ca19-116">ErrorHandled == '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9ca19-117">Details</span><span class="sxs-lookup"><span data-stu-id="9ca19-117">Details</span></span>  
  
|<span data-ttu-id="9ca19-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="9ca19-118">Data Item Name</span></span>|<span data-ttu-id="9ca19-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="9ca19-119">Data Item Type</span></span>|<span data-ttu-id="9ca19-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9ca19-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9ca19-121">TypeName</span><span class="sxs-lookup"><span data-stu-id="9ca19-121">TypeName</span></span>|`xs:string`|<span data-ttu-id="9ca19-122">Der CLR-FullName des aufgerufenen `ErrorHandler`-Typs.</span><span class="sxs-lookup"><span data-stu-id="9ca19-122">The CLR FullName of the type of the invoked `ErrorHandler`.</span></span>|  
|<span data-ttu-id="9ca19-123">Handled</span><span class="sxs-lookup"><span data-stu-id="9ca19-123">Handled</span></span>|`xs:unsignedByte`|<span data-ttu-id="9ca19-124">`true`, wenn der Fehlerhandler den Fehler behandelt hat, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="9ca19-124">`true` if the error handler handled the error, otherwise `false`.</span></span>|  
|<span data-ttu-id="9ca19-125">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="9ca19-125">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="9ca19-126">Der CLR-FullName der Ausnahme, die behandelt wurde.</span><span class="sxs-lookup"><span data-stu-id="9ca19-126">The CLR FullName of the exception that was being handled.</span></span>|  
|<span data-ttu-id="9ca19-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="9ca19-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="9ca19-128">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="9ca19-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="9ca19-129">Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="9ca19-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="9ca19-130">Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="9ca19-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="9ca19-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9ca19-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="9ca19-132">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="9ca19-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
