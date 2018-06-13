---
title: 218 - ClientOperationCompleted
ms.date: 03/30/2017
ms.assetid: b069bced-7bb2-4e01-8227-e5dbda17af09
ms.openlocfilehash: 83f39be84a8d62962b85652b0e39b537c92e612c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457973"
---
# <a name="218---clientoperationcompleted"></a><span data-ttu-id="4db3d-102">218 - ClientOperationCompleted</span><span class="sxs-lookup"><span data-stu-id="4db3d-102">218 - ClientOperationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="4db3d-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="4db3d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4db3d-104">Id</span><span class="sxs-lookup"><span data-stu-id="4db3d-104">ID</span></span>|<span data-ttu-id="4db3d-105">218</span><span class="sxs-lookup"><span data-stu-id="4db3d-105">218</span></span>|  
|<span data-ttu-id="4db3d-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="4db3d-106">Keywords</span></span>|<span data-ttu-id="4db3d-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4db3d-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="4db3d-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="4db3d-108">Level</span></span>|<span data-ttu-id="4db3d-109">Information</span><span class="sxs-lookup"><span data-stu-id="4db3d-109">Information</span></span>|  
|<span data-ttu-id="4db3d-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="4db3d-110">Channel</span></span>|<span data-ttu-id="4db3d-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="4db3d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4db3d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4db3d-112">Description</span></span>  
 <span data-ttu-id="4db3d-113">Dieses Ereignis wird von Clients direkt nach Abschluss eines Vorgangs ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="4db3d-113">This event is emitted by clients just after an operation completes.</span></span> <span data-ttu-id="4db3d-114">Bei unidirektionalen Vorgänge wird dies direkt nach dem erfolgreichen Senden der Nachricht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4db3d-114">For one-way operations, this is just after the message is sent successfully.</span></span> <span data-ttu-id="4db3d-115">Für Anforderung-Antwort-Vorgänge wird dies ausgeführt, nachdem die Antwort empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="4db3d-115">For request-response operations this is after the response is received.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4db3d-116">Meldung</span><span class="sxs-lookup"><span data-stu-id="4db3d-116">Message</span></span>  
 <span data-ttu-id="4db3d-117">Der Client hat das Ausführen der Aktion '%1' abgeschlossen, die dem Vertrag '%2' zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="4db3d-117">The Client completed executing Action '%1' associated with the '%2' contract.</span></span> <span data-ttu-id="4db3d-118">Die Nachricht wurde an '%3' gesendet.</span><span class="sxs-lookup"><span data-stu-id="4db3d-118">The message was sent to '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4db3d-119">Details</span><span class="sxs-lookup"><span data-stu-id="4db3d-119">Details</span></span>  
  
|<span data-ttu-id="4db3d-120">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="4db3d-120">Data Item Name</span></span>|<span data-ttu-id="4db3d-121">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="4db3d-121">Data Item Type</span></span>|<span data-ttu-id="4db3d-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4db3d-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4db3d-123">Aktion</span><span class="sxs-lookup"><span data-stu-id="4db3d-123">Action</span></span>|<span data-ttu-id="4db3d-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="4db3d-124">xs:string</span></span>|<span data-ttu-id="4db3d-125">Der SOAP-Aktionsheader der ausgehenden Nachricht.</span><span class="sxs-lookup"><span data-stu-id="4db3d-125">The SOAP action header of the outgoing message.</span></span>|  
|<span data-ttu-id="4db3d-126">Contract Name</span><span class="sxs-lookup"><span data-stu-id="4db3d-126">Contract Name</span></span>|`xs:string`|<span data-ttu-id="4db3d-127">Der Name des Vertrags.</span><span class="sxs-lookup"><span data-stu-id="4db3d-127">The name of the contract.</span></span> <span data-ttu-id="4db3d-128">Beispiel: ICalculator.</span><span class="sxs-lookup"><span data-stu-id="4db3d-128">Example: ICalculator.</span></span>|  
|<span data-ttu-id="4db3d-129">Ziel</span><span class="sxs-lookup"><span data-stu-id="4db3d-129">Destination</span></span>|`xs:string`|<span data-ttu-id="4db3d-130">Die Adresse des Dienstendpunkts, an den die Nachricht gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="4db3d-130">The address of the service endpoint that the message was sent to.</span></span>|  
|<span data-ttu-id="4db3d-131">HostReference</span><span class="sxs-lookup"><span data-stu-id="4db3d-131">HostReference</span></span>|`xs:string`|<span data-ttu-id="4db3d-132">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="4db3d-132">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="4db3d-133">Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="4db3d-133">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="4db3d-134">Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="4db3d-134">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="4db3d-135">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4db3d-135">AppDomain</span></span>|`xs:string`|<span data-ttu-id="4db3d-136">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="4db3d-136">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
