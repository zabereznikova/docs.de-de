---
title: 221 - MessageReceivedFromTransport
ms.date: 03/30/2017
ms.assetid: 4995f0d5-c182-4d97-981f-6951da6df1fb
ms.openlocfilehash: 47e871b70e3ef2419543b4710c2988736665cb46
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263099"
---
# <a name="221---messagereceivedfromtransport"></a><span data-ttu-id="8c327-102">221 - MessageReceivedFromTransport</span><span class="sxs-lookup"><span data-stu-id="8c327-102">221 - MessageReceivedFromTransport</span></span>

## <a name="properties"></a><span data-ttu-id="8c327-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8c327-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8c327-104">id</span><span class="sxs-lookup"><span data-stu-id="8c327-104">ID</span></span>|<span data-ttu-id="8c327-105">221</span><span class="sxs-lookup"><span data-stu-id="8c327-105">221</span></span>|  
|<span data-ttu-id="8c327-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="8c327-106">Keywords</span></span>|<span data-ttu-id="8c327-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="8c327-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="8c327-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="8c327-108">Level</span></span>|<span data-ttu-id="8c327-109">Information</span><span class="sxs-lookup"><span data-stu-id="8c327-109">Information</span></span>|  
|<span data-ttu-id="8c327-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="8c327-110">Channel</span></span>|<span data-ttu-id="8c327-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="8c327-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8c327-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8c327-112">Description</span></span>  

 <span data-ttu-id="8c327-113">Dieses Ereignis wird ausgegeben, wenn das Dienstmodell eine Nachricht vom Transport empfängt.</span><span class="sxs-lookup"><span data-stu-id="8c327-113">This event is emitted when the Service Model receives a message from the transport.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8c327-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="8c327-114">Message</span></span>  

 <span data-ttu-id="8c327-115">Der Verteiler hat eine Nachricht vom Transport empfangen.</span><span class="sxs-lookup"><span data-stu-id="8c327-115">The Dispatcher received a message from the transport.</span></span> <span data-ttu-id="8c327-116">Korrelations-ID == '%1'.</span><span class="sxs-lookup"><span data-stu-id="8c327-116">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8c327-117">Details</span><span class="sxs-lookup"><span data-stu-id="8c327-117">Details</span></span>  
  
|<span data-ttu-id="8c327-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="8c327-118">Data Item Name</span></span>|<span data-ttu-id="8c327-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="8c327-119">Data Item Type</span></span>|<span data-ttu-id="8c327-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8c327-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8c327-121">Korrelations-ID</span><span class="sxs-lookup"><span data-stu-id="8c327-121">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="8c327-122">Die Aktivitäts-ID, die verwendet wurde, um für ein `MessageSentToTransport`-Ereignis eine Korrelation zum entsprechenden `MessageReceivedFromTransport`-Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8c327-122">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="8c327-123">HostReference</span><span class="sxs-lookup"><span data-stu-id="8c327-123">HostReference</span></span>|`xs:string`|<span data-ttu-id="8c327-124">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="8c327-124">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="8c327-125">Sein Format ist als "Website Name Anwendungspfad für virtuelle Computer&#124;virtuellen Dienst Pfad&#124;Dienst Name '" definiert.</span><span class="sxs-lookup"><span data-stu-id="8c327-125">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="8c327-126">Beispiel: "Default Web Site/calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="8c327-126">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="8c327-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8c327-127">AppDomain</span></span>|`xs:string`|<span data-ttu-id="8c327-128">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8c327-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
