---
title: 218 - ClientOperationCompleted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b069bced-7bb2-4e01-8227-e5dbda17af09
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ea826aa99e847f74c5a44113f2ae16d7322873f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="218---clientoperationcompleted"></a><span data-ttu-id="fdac7-102">218 - ClientOperationCompleted</span><span class="sxs-lookup"><span data-stu-id="fdac7-102">218 - ClientOperationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="fdac7-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="fdac7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fdac7-104">ID</span><span class="sxs-lookup"><span data-stu-id="fdac7-104">ID</span></span>|<span data-ttu-id="fdac7-105">218</span><span class="sxs-lookup"><span data-stu-id="fdac7-105">218</span></span>|  
|<span data-ttu-id="fdac7-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="fdac7-106">Keywords</span></span>|<span data-ttu-id="fdac7-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fdac7-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="fdac7-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="fdac7-108">Level</span></span>|<span data-ttu-id="fdac7-109">Information</span><span class="sxs-lookup"><span data-stu-id="fdac7-109">Information</span></span>|  
|<span data-ttu-id="fdac7-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="fdac7-110">Channel</span></span>|<span data-ttu-id="fdac7-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="fdac7-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fdac7-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fdac7-112">Description</span></span>  
 <span data-ttu-id="fdac7-113">Dieses Ereignis wird von Clients direkt nach Abschluss eines Vorgangs ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="fdac7-113">This event is emitted by clients just after an operation completes.</span></span> <span data-ttu-id="fdac7-114">Bei unidirektionalen Vorgänge wird dies direkt nach dem erfolgreichen Senden der Nachricht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fdac7-114">For one-way operations, this is just after the message is sent successfully.</span></span> <span data-ttu-id="fdac7-115">Für Anforderung-Antwort-Vorgänge wird dies ausgeführt, nachdem die Antwort empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="fdac7-115">For request-response operations this is after the response is received.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fdac7-116">Meldung</span><span class="sxs-lookup"><span data-stu-id="fdac7-116">Message</span></span>  
 <span data-ttu-id="fdac7-117">Der Client hat das Ausführen der Aktion '%1' abgeschlossen, die dem Vertrag '%2' zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="fdac7-117">The Client completed executing Action '%1' associated with the '%2' contract.</span></span> <span data-ttu-id="fdac7-118">Die Nachricht wurde an '%3' gesendet.</span><span class="sxs-lookup"><span data-stu-id="fdac7-118">The message was sent to '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fdac7-119">Details</span><span class="sxs-lookup"><span data-stu-id="fdac7-119">Details</span></span>  
  
|<span data-ttu-id="fdac7-120">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="fdac7-120">Data Item Name</span></span>|<span data-ttu-id="fdac7-121">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="fdac7-121">Data Item Type</span></span>|<span data-ttu-id="fdac7-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fdac7-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fdac7-123">Aktion</span><span class="sxs-lookup"><span data-stu-id="fdac7-123">Action</span></span>|<span data-ttu-id="fdac7-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="fdac7-124">xs:string</span></span>|<span data-ttu-id="fdac7-125">Der SOAP-Aktionsheader der ausgehenden Nachricht.</span><span class="sxs-lookup"><span data-stu-id="fdac7-125">The SOAP action header of the outgoing message.</span></span>|  
|<span data-ttu-id="fdac7-126">Contract Name</span><span class="sxs-lookup"><span data-stu-id="fdac7-126">Contract Name</span></span>|`xs:string`|<span data-ttu-id="fdac7-127">Der Name des Vertrags.</span><span class="sxs-lookup"><span data-stu-id="fdac7-127">The name of the contract.</span></span> <span data-ttu-id="fdac7-128">Beispiel: ICalculator.</span><span class="sxs-lookup"><span data-stu-id="fdac7-128">Example: ICalculator.</span></span>|  
|<span data-ttu-id="fdac7-129">Ziel</span><span class="sxs-lookup"><span data-stu-id="fdac7-129">Destination</span></span>|`xs:string`|<span data-ttu-id="fdac7-130">Die Adresse des Dienstendpunkts, an den die Nachricht gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="fdac7-130">The address of the service endpoint that the message was sent to.</span></span>|  
|<span data-ttu-id="fdac7-131">HostReference</span><span class="sxs-lookup"><span data-stu-id="fdac7-131">HostReference</span></span>|`xs:string`|<span data-ttu-id="fdac7-132">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="fdac7-132">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="fdac7-133">Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="fdac7-133">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="fdac7-134">Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="fdac7-134">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="fdac7-135">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fdac7-135">AppDomain</span></span>|`xs:string`|<span data-ttu-id="fdac7-136">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="fdac7-136">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
