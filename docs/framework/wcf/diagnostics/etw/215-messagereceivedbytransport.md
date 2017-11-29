---
title: 215 - MessageReceivedByTransport
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb32aa60-5207-4711-9f08-110e8ac327e5
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 92880fd01f8f61a06c9b2c7d51ecc4a1671c6c85
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="215---messagereceivedbytransport"></a><span data-ttu-id="b6415-102">215 - MessageReceivedByTransport</span><span class="sxs-lookup"><span data-stu-id="b6415-102">215 - MessageReceivedByTransport</span></span>
## <a name="properties"></a><span data-ttu-id="b6415-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b6415-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b6415-104">ID</span><span class="sxs-lookup"><span data-stu-id="b6415-104">ID</span></span>|<span data-ttu-id="b6415-105">215</span><span class="sxs-lookup"><span data-stu-id="b6415-105">215</span></span>|  
|<span data-ttu-id="b6415-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="b6415-106">Keywords</span></span>|<span data-ttu-id="b6415-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b6415-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="b6415-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="b6415-108">Level</span></span>|<span data-ttu-id="b6415-109">Information</span><span class="sxs-lookup"><span data-stu-id="b6415-109">Information</span></span>|  
|<span data-ttu-id="b6415-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="b6415-110">Channel</span></span>|<span data-ttu-id="b6415-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="b6415-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b6415-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b6415-112">Description</span></span>  
 <span data-ttu-id="b6415-113">Dieses Ereignis tritt auf, wenn ein TCP-basierter Transport eine Nachricht empfängt.</span><span class="sxs-lookup"><span data-stu-id="b6415-113">This event occurs when a TCP-based transport receives a message.</span></span> <span data-ttu-id="b6415-114">Beachten Sie, dass auf Transportebene zwischen Clients und Diensten für einen einzelnen Vorgang mehrere Nachrichten ausgetauscht werden können.</span><span class="sxs-lookup"><span data-stu-id="b6415-114">Note that at the transport level, multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="b6415-115">Der Grund dafür kann das Infrastrukturverhalten sein, beispielsweise in Verbindung mit Sicherheitsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="b6415-115">This can be due to infrastructure behavior, security is a good example.</span></span> <span data-ttu-id="b6415-116">Daher kann die Anzahl von ausgegebenen `MessageReceivedByTransport`-Ereignissen je nach Bindung des Diensts und seiner Konfiguration variieren.</span><span class="sxs-lookup"><span data-stu-id="b6415-116">Therefore, the number of `MessageReceivedByTransport` events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b6415-117">Dieses Ereignis wird nicht bei unidirektionalen Transporten ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="b6415-117">This event is not emitted for one-way transports.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b6415-118">Meldung</span><span class="sxs-lookup"><span data-stu-id="b6415-118">Message</span></span>  
 <span data-ttu-id="b6415-119">Der Transport hat eine Nachricht von '%1' empfangen.</span><span class="sxs-lookup"><span data-stu-id="b6415-119">The transport received a message from '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b6415-120">Details</span><span class="sxs-lookup"><span data-stu-id="b6415-120">Details</span></span>  
  
|<span data-ttu-id="b6415-121">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="b6415-121">Data Item Name</span></span>|<span data-ttu-id="b6415-122">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="b6415-122">Data Item Type</span></span>|<span data-ttu-id="b6415-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b6415-123">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b6415-124">Listen Address</span><span class="sxs-lookup"><span data-stu-id="b6415-124">Listen Address</span></span>|`xs:string`|<span data-ttu-id="b6415-125">Die Adresse, die die Nachricht empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="b6415-125">The address that received the message.</span></span>|  
|<span data-ttu-id="b6415-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="b6415-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="b6415-127">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="b6415-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="b6415-128">Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="b6415-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="b6415-129">Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="b6415-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="b6415-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b6415-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="b6415-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="b6415-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
