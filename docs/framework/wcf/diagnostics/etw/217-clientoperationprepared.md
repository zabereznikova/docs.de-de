---
title: 217 - ClientOperationPrepared
ms.date: 03/30/2017
ms.assetid: ad207f04-b038-4f33-95e9-27a361df8ecd
ms.openlocfilehash: e8aaf65bdff0718e932d07937e052541b7134f11
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278881"
---
# <a name="217---clientoperationprepared"></a><span data-ttu-id="5af76-102">217 - ClientOperationPrepared</span><span class="sxs-lookup"><span data-stu-id="5af76-102">217 - ClientOperationPrepared</span></span>

## <a name="properties"></a><span data-ttu-id="5af76-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="5af76-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5af76-104">id</span><span class="sxs-lookup"><span data-stu-id="5af76-104">ID</span></span>|<span data-ttu-id="5af76-105">217</span><span class="sxs-lookup"><span data-stu-id="5af76-105">217</span></span>|  
|<span data-ttu-id="5af76-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="5af76-106">Keywords</span></span>|<span data-ttu-id="5af76-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="5af76-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="5af76-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="5af76-108">Level</span></span>|<span data-ttu-id="5af76-109">Information</span><span class="sxs-lookup"><span data-stu-id="5af76-109">Information</span></span>|  
|<span data-ttu-id="5af76-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="5af76-110">Channel</span></span>|<span data-ttu-id="5af76-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="5af76-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5af76-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5af76-112">Description</span></span>  

 <span data-ttu-id="5af76-113">Dieses Ereignis wird von Clients direkt vor dem Senden eines Vorgangs an einen Dienst ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="5af76-113">This event is emitted by clients just before an operation is sent to the service.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5af76-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="5af76-114">Message</span></span>  

 <span data-ttu-id="5af76-115">Der Client führt die Aktion aus '%1' aus, die dem Vertrag '%2' zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="5af76-115">The Client is executing Action '%1' associated with the '%2' contract.</span></span> <span data-ttu-id="5af76-116">Die Nachricht wird an '%3' gesendet.</span><span class="sxs-lookup"><span data-stu-id="5af76-116">The message will be sent to '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5af76-117">Details</span><span class="sxs-lookup"><span data-stu-id="5af76-117">Details</span></span>  
  
|<span data-ttu-id="5af76-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="5af76-118">Data Item Name</span></span>|<span data-ttu-id="5af76-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="5af76-119">Data Item Type</span></span>|<span data-ttu-id="5af76-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5af76-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5af76-121">Aktion</span><span class="sxs-lookup"><span data-stu-id="5af76-121">Action</span></span>|`xs:string`|<span data-ttu-id="5af76-122">Der SOAP-Aktionsheader der ausgehenden Nachricht.</span><span class="sxs-lookup"><span data-stu-id="5af76-122">The SOAP action header of the outgoing message.</span></span>|  
|<span data-ttu-id="5af76-123">Contract Name</span><span class="sxs-lookup"><span data-stu-id="5af76-123">Contract Name</span></span>|`xs:string`|<span data-ttu-id="5af76-124">Der Name des Vertrags.</span><span class="sxs-lookup"><span data-stu-id="5af76-124">The name of the contract.</span></span> <span data-ttu-id="5af76-125">Beispiel: ICalculator.</span><span class="sxs-lookup"><span data-stu-id="5af76-125">Example: ICalculator.</span></span>|  
|<span data-ttu-id="5af76-126">Destination</span><span class="sxs-lookup"><span data-stu-id="5af76-126">Destination</span></span>|`xs:string`|<span data-ttu-id="5af76-127">Die Adresse des Dienstendpunkts, an den die Nachricht gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="5af76-127">The address of the service endpoint that the message is sent to.</span></span>|  
|<span data-ttu-id="5af76-128">HostReference</span><span class="sxs-lookup"><span data-stu-id="5af76-128">HostReference</span></span>|`xs:string`|<span data-ttu-id="5af76-129">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="5af76-129">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="5af76-130">Sein Format ist als "Website Name Anwendungspfad für virtuelle Computer&#124;virtuellen Dienst Pfad&#124;Dienst Name '" definiert.</span><span class="sxs-lookup"><span data-stu-id="5af76-130">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="5af76-131">Beispiel: "Default Web Site/calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="5af76-131">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="5af76-132">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5af76-132">AppDomain</span></span>|`xs:string`|<span data-ttu-id="5af76-133">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="5af76-133">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
