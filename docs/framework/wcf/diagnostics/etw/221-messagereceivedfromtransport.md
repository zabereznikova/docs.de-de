---
title: 221 - MessageReceivedFromTransport
ms.date: 03/30/2017
ms.assetid: 4995f0d5-c182-4d97-981f-6951da6df1fb
ms.openlocfilehash: 98dbf2728242fa73b3e54b7cf32f9e227e5251b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458776"
---
# <a name="221---messagereceivedfromtransport"></a><span data-ttu-id="318fb-102">221 - MessageReceivedFromTransport</span><span class="sxs-lookup"><span data-stu-id="318fb-102">221 - MessageReceivedFromTransport</span></span>
## <a name="properties"></a><span data-ttu-id="318fb-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="318fb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="318fb-104">Id</span><span class="sxs-lookup"><span data-stu-id="318fb-104">ID</span></span>|<span data-ttu-id="318fb-105">221</span><span class="sxs-lookup"><span data-stu-id="318fb-105">221</span></span>|  
|<span data-ttu-id="318fb-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="318fb-106">Keywords</span></span>|<span data-ttu-id="318fb-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="318fb-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="318fb-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="318fb-108">Level</span></span>|<span data-ttu-id="318fb-109">Information</span><span class="sxs-lookup"><span data-stu-id="318fb-109">Information</span></span>|  
|<span data-ttu-id="318fb-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="318fb-110">Channel</span></span>|<span data-ttu-id="318fb-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="318fb-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="318fb-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="318fb-112">Description</span></span>  
 <span data-ttu-id="318fb-113">Dieses Ereignis wird ausgegeben, wenn das Dienstmodell eine Nachricht vom Transport empfängt.</span><span class="sxs-lookup"><span data-stu-id="318fb-113">This event is emitted when the Service Model receives a message from the transport.</span></span>  
  
## <a name="message"></a><span data-ttu-id="318fb-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="318fb-114">Message</span></span>  
 <span data-ttu-id="318fb-115">Der Verteiler hat eine Nachricht vom Transport empfangen.</span><span class="sxs-lookup"><span data-stu-id="318fb-115">The Dispatcher received a message from the transport.</span></span> <span data-ttu-id="318fb-116">Korrelations-ID == '%1'.</span><span class="sxs-lookup"><span data-stu-id="318fb-116">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="318fb-117">Details</span><span class="sxs-lookup"><span data-stu-id="318fb-117">Details</span></span>  
  
|<span data-ttu-id="318fb-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="318fb-118">Data Item Name</span></span>|<span data-ttu-id="318fb-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="318fb-119">Data Item Type</span></span>|<span data-ttu-id="318fb-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="318fb-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="318fb-121">Correlation ID</span><span class="sxs-lookup"><span data-stu-id="318fb-121">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="318fb-122">Die Aktivitäts-ID, die verwendet wurde, um für ein `MessageSentToTransport`-Ereignis eine Korrelation zum entsprechenden `MessageReceivedFromTransport`-Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="318fb-122">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="318fb-123">HostReference</span><span class="sxs-lookup"><span data-stu-id="318fb-123">HostReference</span></span>|`xs:string`|<span data-ttu-id="318fb-124">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="318fb-124">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="318fb-125">Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="318fb-125">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="318fb-126">Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="318fb-126">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="318fb-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="318fb-127">AppDomain</span></span>|`xs:string`|<span data-ttu-id="318fb-128">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="318fb-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
