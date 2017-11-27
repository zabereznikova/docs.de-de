---
title: 221 - MessageReceivedFromTransport
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4995f0d5-c182-4d97-981f-6951da6df1fb
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4f977f938844f48182be6662f489506e8119fe67
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="221---messagereceivedfromtransport"></a><span data-ttu-id="2aede-102">221 - MessageReceivedFromTransport</span><span class="sxs-lookup"><span data-stu-id="2aede-102">221 - MessageReceivedFromTransport</span></span>
## <a name="properties"></a><span data-ttu-id="2aede-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2aede-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2aede-104">ID</span><span class="sxs-lookup"><span data-stu-id="2aede-104">ID</span></span>|<span data-ttu-id="2aede-105">221</span><span class="sxs-lookup"><span data-stu-id="2aede-105">221</span></span>|  
|<span data-ttu-id="2aede-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="2aede-106">Keywords</span></span>|<span data-ttu-id="2aede-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2aede-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="2aede-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="2aede-108">Level</span></span>|<span data-ttu-id="2aede-109">Information</span><span class="sxs-lookup"><span data-stu-id="2aede-109">Information</span></span>|  
|<span data-ttu-id="2aede-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="2aede-110">Channel</span></span>|<span data-ttu-id="2aede-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="2aede-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2aede-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2aede-112">Description</span></span>  
 <span data-ttu-id="2aede-113">Dieses Ereignis wird ausgegeben, wenn das Dienstmodell eine Nachricht vom Transport empfängt.</span><span class="sxs-lookup"><span data-stu-id="2aede-113">This event is emitted when the Service Model receives a message from the transport.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2aede-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="2aede-114">Message</span></span>  
 <span data-ttu-id="2aede-115">Der Verteiler hat eine Nachricht vom Transport empfangen.</span><span class="sxs-lookup"><span data-stu-id="2aede-115">The Dispatcher received a message from the transport.</span></span> <span data-ttu-id="2aede-116">Korrelations-ID == '%1'.</span><span class="sxs-lookup"><span data-stu-id="2aede-116">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2aede-117">Details</span><span class="sxs-lookup"><span data-stu-id="2aede-117">Details</span></span>  
  
|<span data-ttu-id="2aede-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="2aede-118">Data Item Name</span></span>|<span data-ttu-id="2aede-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="2aede-119">Data Item Type</span></span>|<span data-ttu-id="2aede-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2aede-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2aede-121">Correlation ID</span><span class="sxs-lookup"><span data-stu-id="2aede-121">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="2aede-122">Die Aktivitäts-ID, die verwendet wurde, um für ein `MessageSentToTransport`-Ereignis eine Korrelation zum entsprechenden `MessageReceivedFromTransport`-Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2aede-122">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="2aede-123">HostReference</span><span class="sxs-lookup"><span data-stu-id="2aede-123">HostReference</span></span>|`xs:string`|<span data-ttu-id="2aede-124">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="2aede-124">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="2aede-125">Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="2aede-125">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="2aede-126">Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="2aede-126">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="2aede-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2aede-127">AppDomain</span></span>|`xs:string`|<span data-ttu-id="2aede-128">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2aede-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
