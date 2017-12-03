---
title: 220 - MessageSentToTransport
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aef4e781-240b-45bc-bff8-400053037e71
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7bc3b784dca090ed768711728a054782e06c7b10
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="220---messagesenttotransport"></a><span data-ttu-id="45471-102">220 - MessageSentToTransport</span><span class="sxs-lookup"><span data-stu-id="45471-102">220 - MessageSentToTransport</span></span>
## <a name="properties"></a><span data-ttu-id="45471-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="45471-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="45471-104">ID</span><span class="sxs-lookup"><span data-stu-id="45471-104">Id</span></span>|<span data-ttu-id="45471-105">220</span><span class="sxs-lookup"><span data-stu-id="45471-105">220</span></span>|  
|<span data-ttu-id="45471-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="45471-106">Keywords</span></span>|<span data-ttu-id="45471-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="45471-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="45471-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="45471-108">Level</span></span>|<span data-ttu-id="45471-109">Information</span><span class="sxs-lookup"><span data-stu-id="45471-109">Information</span></span>|  
|<span data-ttu-id="45471-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="45471-110">Channel</span></span>|<span data-ttu-id="45471-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="45471-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="45471-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="45471-112">Description</span></span>  
 <span data-ttu-id="45471-113">Dieses Ereignis wird ausgegeben, wenn das Dienstmodell eine Nachricht an den Transport sendet.</span><span class="sxs-lookup"><span data-stu-id="45471-113">This event is emitted when the Service Model sends a message to the transport.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="45471-114">Dieses Ereignis wird nicht für unidirektionale Transporte ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="45471-114">This event will not be emitted for one-way transports.</span></span>  
  
## <a name="message"></a><span data-ttu-id="45471-115">Meldung</span><span class="sxs-lookup"><span data-stu-id="45471-115">Message</span></span>  
 <span data-ttu-id="45471-116">Der Verteiler hat eine Nachricht an den Transport gesendet.</span><span class="sxs-lookup"><span data-stu-id="45471-116">The Dispatcher sent a message to the transport.</span></span> <span data-ttu-id="45471-117">Korrelations-ID == '%1'.</span><span class="sxs-lookup"><span data-stu-id="45471-117">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="45471-118">Details</span><span class="sxs-lookup"><span data-stu-id="45471-118">Details</span></span>  
  
|<span data-ttu-id="45471-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="45471-119">Data Item Name</span></span>|<span data-ttu-id="45471-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="45471-120">Data Item Type</span></span>|<span data-ttu-id="45471-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="45471-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="45471-122">Correlation ID</span><span class="sxs-lookup"><span data-stu-id="45471-122">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="45471-123">Die Aktivitäts-ID, die verwendet wurde, um für ein `MessageSentToTransport`-Ereignis eine Korrelation zum entsprechenden `MessageReceivedFromTransport`-Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="45471-123">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="45471-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="45471-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="45471-125">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="45471-125">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="45471-126">Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="45471-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="45471-127">Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="45471-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="45471-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="45471-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="45471-129">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="45471-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
