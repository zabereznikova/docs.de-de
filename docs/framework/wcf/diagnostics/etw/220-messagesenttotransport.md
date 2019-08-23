---
title: 220 - MessageSentToTransport
ms.date: 03/30/2017
ms.assetid: aef4e781-240b-45bc-bff8-400053037e71
ms.openlocfilehash: 9f95edf42e0b1ec19d2019773def282fc279871b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69948282"
---
# <a name="220---messagesenttotransport"></a><span data-ttu-id="076a8-102">220 - MessageSentToTransport</span><span class="sxs-lookup"><span data-stu-id="076a8-102">220 - MessageSentToTransport</span></span>
## <a name="properties"></a><span data-ttu-id="076a8-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="076a8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="076a8-104">Id</span><span class="sxs-lookup"><span data-stu-id="076a8-104">Id</span></span>|<span data-ttu-id="076a8-105">220</span><span class="sxs-lookup"><span data-stu-id="076a8-105">220</span></span>|  
|<span data-ttu-id="076a8-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="076a8-106">Keywords</span></span>|<span data-ttu-id="076a8-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="076a8-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="076a8-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="076a8-108">Level</span></span>|<span data-ttu-id="076a8-109">Information</span><span class="sxs-lookup"><span data-stu-id="076a8-109">Information</span></span>|  
|<span data-ttu-id="076a8-110">Channel</span><span class="sxs-lookup"><span data-stu-id="076a8-110">Channel</span></span>|<span data-ttu-id="076a8-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="076a8-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="076a8-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="076a8-112">Description</span></span>  
 <span data-ttu-id="076a8-113">Dieses Ereignis wird ausgegeben, wenn das Dienstmodell eine Nachricht an den Transport sendet.</span><span class="sxs-lookup"><span data-stu-id="076a8-113">This event is emitted when the Service Model sends a message to the transport.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="076a8-114">Dieses Ereignis wird nicht für unidirektionale Transporte ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="076a8-114">This event will not be emitted for one-way transports.</span></span>  
  
## <a name="message"></a><span data-ttu-id="076a8-115">Meldung</span><span class="sxs-lookup"><span data-stu-id="076a8-115">Message</span></span>  
 <span data-ttu-id="076a8-116">Der Verteiler hat eine Nachricht an den Transport gesendet.</span><span class="sxs-lookup"><span data-stu-id="076a8-116">The Dispatcher sent a message to the transport.</span></span> <span data-ttu-id="076a8-117">Korrelations-ID == '%1'.</span><span class="sxs-lookup"><span data-stu-id="076a8-117">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="076a8-118">Details</span><span class="sxs-lookup"><span data-stu-id="076a8-118">Details</span></span>  
  
|<span data-ttu-id="076a8-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="076a8-119">Data Item Name</span></span>|<span data-ttu-id="076a8-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="076a8-120">Data Item Type</span></span>|<span data-ttu-id="076a8-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="076a8-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="076a8-122">Correlation ID</span><span class="sxs-lookup"><span data-stu-id="076a8-122">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="076a8-123">Die Aktivitäts-ID, die verwendet wurde, um für ein `MessageSentToTransport`-Ereignis eine Korrelation zum entsprechenden `MessageReceivedFromTransport`-Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="076a8-123">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="076a8-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="076a8-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="076a8-125">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="076a8-125">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="076a8-126">Sein Format ist als "Website Name Anwendungspfad des virtuellen Pfads&#124;Dienst&#124;Name" definiert.</span><span class="sxs-lookup"><span data-stu-id="076a8-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="076a8-127">Beispiel: "Default Web Site/calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="076a8-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="076a8-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="076a8-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="076a8-129">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="076a8-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
