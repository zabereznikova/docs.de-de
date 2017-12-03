---
title: 205 - OperationInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c8d6c90-dfa5-4ae0-a589-96679a8fb3ba
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b4e101c4e9e5812c32b85029e9c24d983cb5e5d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="205---operationinvoked"></a><span data-ttu-id="1ec7f-102">205 - OperationInvoked</span><span class="sxs-lookup"><span data-stu-id="1ec7f-102">205 - OperationInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="1ec7f-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1ec7f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1ec7f-104">ID</span><span class="sxs-lookup"><span data-stu-id="1ec7f-104">ID</span></span>|<span data-ttu-id="1ec7f-105">205</span><span class="sxs-lookup"><span data-stu-id="1ec7f-105">205</span></span>|  
|<span data-ttu-id="1ec7f-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="1ec7f-106">Keywords</span></span>|<span data-ttu-id="1ec7f-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1ec7f-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="1ec7f-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="1ec7f-108">Level</span></span>|<span data-ttu-id="1ec7f-109">Information</span><span class="sxs-lookup"><span data-stu-id="1ec7f-109">Information</span></span>|  
|<span data-ttu-id="1ec7f-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="1ec7f-110">Channel</span></span>|<span data-ttu-id="1ec7f-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="1ec7f-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1ec7f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ec7f-112">Description</span></span>  
 <span data-ttu-id="1ec7f-113">Dieses Ereignis wird unmittelbar vor dem Vorgang ausgegeben, bei dem der standardmäßige `OperationInvoker` des Dienstmodells mit dem Aufrufen einer Methode beginnt.</span><span class="sxs-lookup"><span data-stu-id="1ec7f-113">This event is emitted just before the Service Model's default `OperationInvoker` begins a call to a method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1ec7f-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="1ec7f-114">Message</span></span>  
 <span data-ttu-id="1ec7f-115">Ein OperationInvoker hat die '%1'-Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="1ec7f-115">An OperationInvoker invoked the '%1' method.</span></span> <span data-ttu-id="1ec7f-116">Aufruferdaten: '%2'.</span><span class="sxs-lookup"><span data-stu-id="1ec7f-116">Caller information: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1ec7f-117">Details</span><span class="sxs-lookup"><span data-stu-id="1ec7f-117">Details</span></span>  
  
|<span data-ttu-id="1ec7f-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="1ec7f-118">Data Item Name</span></span>|<span data-ttu-id="1ec7f-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="1ec7f-119">Data Item Type</span></span>|<span data-ttu-id="1ec7f-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ec7f-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1ec7f-121">Methodenname</span><span class="sxs-lookup"><span data-stu-id="1ec7f-121">Method Name</span></span>|`xs:string`|<span data-ttu-id="1ec7f-122">Der CLR-Name der Methode, die vom `OperationInvoker` aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="1ec7f-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="1ec7f-123">Aufruferinformationen</span><span class="sxs-lookup"><span data-stu-id="1ec7f-123">Caller Information</span></span>|`xs:string`|<span data-ttu-id="1ec7f-124">Die IP-Adresse und die Portnummer des Clients im Format 'IPAddress:PortNumber'.</span><span class="sxs-lookup"><span data-stu-id="1ec7f-124">The IP address and port number of the client in the format 'IPAddress:PortNumber'.</span></span> <span data-ttu-id="1ec7f-125">Diese beiden Werte werden aus der 'System.ServiceModel.Channels.RemoteEndpointMessageProperty'-Meldungseigenschaft im Vorgangskontext abgerufen.</span><span class="sxs-lookup"><span data-stu-id="1ec7f-125">The two values are retrieved from the 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' message property within the operation context.</span></span> <span data-ttu-id="1ec7f-126">Beachten Sie, dass dieser Wert für Nicht-TCP-Bindungen `null` ist.</span><span class="sxs-lookup"><span data-stu-id="1ec7f-126">Note that for non-TCP bindings this value `null`.</span></span>|  
|<span data-ttu-id="1ec7f-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="1ec7f-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="1ec7f-128">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="1ec7f-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="1ec7f-129">Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="1ec7f-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="1ec7f-130">Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="1ec7f-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="1ec7f-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1ec7f-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="1ec7f-132">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1ec7f-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
