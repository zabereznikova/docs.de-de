---
title: 206 - ErrorHandlerInvoked
ms.date: 03/30/2017
ms.assetid: 97340f4d-4e09-4e42-a17a-982b3868dbcf
ms.openlocfilehash: 40a92d77c57728249569a854eab8767ff371bca2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458818"
---
# <a name="206---errorhandlerinvoked"></a><span data-ttu-id="02e2c-102">206 - ErrorHandlerInvoked</span><span class="sxs-lookup"><span data-stu-id="02e2c-102">206 - ErrorHandlerInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="02e2c-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="02e2c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="02e2c-104">Id</span><span class="sxs-lookup"><span data-stu-id="02e2c-104">ID</span></span>|<span data-ttu-id="02e2c-105">206</span><span class="sxs-lookup"><span data-stu-id="02e2c-105">206</span></span>|  
|<span data-ttu-id="02e2c-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="02e2c-106">Keywords</span></span>|<span data-ttu-id="02e2c-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="02e2c-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="02e2c-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="02e2c-108">Level</span></span>|<span data-ttu-id="02e2c-109">Information</span><span class="sxs-lookup"><span data-stu-id="02e2c-109">Information</span></span>|  
|<span data-ttu-id="02e2c-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="02e2c-110">Channel</span></span>|<span data-ttu-id="02e2c-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="02e2c-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="02e2c-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="02e2c-112">Description</span></span>  
 <span data-ttu-id="02e2c-113">Dieses Ereignis wird ausgegeben, nachdem ein `ErrorHandler` die Gelegenheit hatte, eine Ausnahme zu behandeln, die während eines Dienstvorgangs aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="02e2c-113">This event is emitted after an `ErrorHandler` has had an opportunity to handle an exception that occurred in a service operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="02e2c-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="02e2c-114">Message</span></span>  
 <span data-ttu-id="02e2c-115">Der Verteiler hat einen ErrorHandler vom Typ "%1" mit einer Ausnahme vom Typ "%3" aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="02e2c-115">The Dispatcher invoked an ErrorHandler of type '%1' with an exception of type '%3'.</span></span> <span data-ttu-id="02e2c-116">ErrorHandled == '%2'.</span><span class="sxs-lookup"><span data-stu-id="02e2c-116">ErrorHandled == '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="02e2c-117">Details</span><span class="sxs-lookup"><span data-stu-id="02e2c-117">Details</span></span>  
  
|<span data-ttu-id="02e2c-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="02e2c-118">Data Item Name</span></span>|<span data-ttu-id="02e2c-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="02e2c-119">Data Item Type</span></span>|<span data-ttu-id="02e2c-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="02e2c-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="02e2c-121">TypeName</span><span class="sxs-lookup"><span data-stu-id="02e2c-121">TypeName</span></span>|`xs:string`|<span data-ttu-id="02e2c-122">Der CLR-FullName des aufgerufenen `ErrorHandler`-Typs.</span><span class="sxs-lookup"><span data-stu-id="02e2c-122">The CLR FullName of the type of the invoked `ErrorHandler`.</span></span>|  
|<span data-ttu-id="02e2c-123">Handled</span><span class="sxs-lookup"><span data-stu-id="02e2c-123">Handled</span></span>|`xs:unsignedByte`|<span data-ttu-id="02e2c-124">`true`, wenn der Fehlerhandler den Fehler behandelt hat, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="02e2c-124">`true` if the error handler handled the error, otherwise `false`.</span></span>|  
|<span data-ttu-id="02e2c-125">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="02e2c-125">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="02e2c-126">Der CLR-FullName der Ausnahme, die behandelt wurde.</span><span class="sxs-lookup"><span data-stu-id="02e2c-126">The CLR FullName of the exception that was being handled.</span></span>|  
|<span data-ttu-id="02e2c-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="02e2c-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="02e2c-128">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="02e2c-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="02e2c-129">Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="02e2c-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="02e2c-130">Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="02e2c-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="02e2c-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="02e2c-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="02e2c-132">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="02e2c-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
