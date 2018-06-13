---
title: 217 - ClientOperationPrepared
ms.date: 03/30/2017
ms.assetid: ad207f04-b038-4f33-95e9-27a361df8ecd
ms.openlocfilehash: 5979cd8ffe0e05b61af01d2aa98c4a2c63fd432c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461064"
---
# <a name="217---clientoperationprepared"></a><span data-ttu-id="969cb-102">217 - ClientOperationPrepared</span><span class="sxs-lookup"><span data-stu-id="969cb-102">217 - ClientOperationPrepared</span></span>
## <a name="properties"></a><span data-ttu-id="969cb-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="969cb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="969cb-104">Id</span><span class="sxs-lookup"><span data-stu-id="969cb-104">ID</span></span>|<span data-ttu-id="969cb-105">217</span><span class="sxs-lookup"><span data-stu-id="969cb-105">217</span></span>|  
|<span data-ttu-id="969cb-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="969cb-106">Keywords</span></span>|<span data-ttu-id="969cb-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="969cb-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="969cb-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="969cb-108">Level</span></span>|<span data-ttu-id="969cb-109">Information</span><span class="sxs-lookup"><span data-stu-id="969cb-109">Information</span></span>|  
|<span data-ttu-id="969cb-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="969cb-110">Channel</span></span>|<span data-ttu-id="969cb-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="969cb-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="969cb-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="969cb-112">Description</span></span>  
 <span data-ttu-id="969cb-113">Dieses Ereignis wird von Clients direkt vor dem Senden eines Vorgangs an einen Dienst ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="969cb-113">This event is emitted by clients just before an operation is sent to the service.</span></span>  
  
## <a name="message"></a><span data-ttu-id="969cb-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="969cb-114">Message</span></span>  
 <span data-ttu-id="969cb-115">Der Client führt die Aktion aus '%1' aus, die dem Vertrag '%2' zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="969cb-115">The Client is executing Action '%1' associated with the '%2' contract.</span></span> <span data-ttu-id="969cb-116">Die Nachricht wird an '%3' gesendet.</span><span class="sxs-lookup"><span data-stu-id="969cb-116">The message will be sent to '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="969cb-117">Details</span><span class="sxs-lookup"><span data-stu-id="969cb-117">Details</span></span>  
  
|<span data-ttu-id="969cb-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="969cb-118">Data Item Name</span></span>|<span data-ttu-id="969cb-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="969cb-119">Data Item Type</span></span>|<span data-ttu-id="969cb-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="969cb-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="969cb-121">Aktion</span><span class="sxs-lookup"><span data-stu-id="969cb-121">Action</span></span>|`xs:string`|<span data-ttu-id="969cb-122">Der SOAP-Aktionsheader der ausgehenden Nachricht.</span><span class="sxs-lookup"><span data-stu-id="969cb-122">The SOAP action header of the outgoing message.</span></span>|  
|<span data-ttu-id="969cb-123">Contract Name</span><span class="sxs-lookup"><span data-stu-id="969cb-123">Contract Name</span></span>|`xs:string`|<span data-ttu-id="969cb-124">Der Name des Vertrags.</span><span class="sxs-lookup"><span data-stu-id="969cb-124">The name of the contract.</span></span> <span data-ttu-id="969cb-125">Beispiel: ICalculator.</span><span class="sxs-lookup"><span data-stu-id="969cb-125">Example: ICalculator.</span></span>|  
|<span data-ttu-id="969cb-126">Ziel</span><span class="sxs-lookup"><span data-stu-id="969cb-126">Destination</span></span>|`xs:string`|<span data-ttu-id="969cb-127">Die Adresse des Dienstendpunkts, an den die Nachricht gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="969cb-127">The address of the service endpoint that the message is sent to.</span></span>|  
|<span data-ttu-id="969cb-128">HostReference</span><span class="sxs-lookup"><span data-stu-id="969cb-128">HostReference</span></span>|`xs:string`|<span data-ttu-id="969cb-129">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="969cb-129">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="969cb-130">Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="969cb-130">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="969cb-131">Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="969cb-131">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="969cb-132">AppDomain</span><span class="sxs-lookup"><span data-stu-id="969cb-132">AppDomain</span></span>|`xs:string`|<span data-ttu-id="969cb-133">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="969cb-133">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
