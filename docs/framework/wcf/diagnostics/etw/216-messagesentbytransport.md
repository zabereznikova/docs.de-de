---
title: 216 - MessageSentByTransport
ms.date: 03/30/2017
ms.assetid: 150c3167-4154-4225-8d94-57cc94341233
ms.openlocfilehash: b3e9e1a48951ad5a2e5e7820dc1828c20e310635
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278907"
---
# <a name="216---messagesentbytransport"></a><span data-ttu-id="366b2-102">216 - MessageSentByTransport</span><span class="sxs-lookup"><span data-stu-id="366b2-102">216 - MessageSentByTransport</span></span>

## <a name="properties"></a><span data-ttu-id="366b2-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="366b2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="366b2-104">id</span><span class="sxs-lookup"><span data-stu-id="366b2-104">ID</span></span>|<span data-ttu-id="366b2-105">216</span><span class="sxs-lookup"><span data-stu-id="366b2-105">216</span></span>|  
|<span data-ttu-id="366b2-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="366b2-106">Keywords</span></span>|<span data-ttu-id="366b2-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="366b2-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="366b2-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="366b2-108">Level</span></span>|<span data-ttu-id="366b2-109">Information</span><span class="sxs-lookup"><span data-stu-id="366b2-109">Information</span></span>|  
|<span data-ttu-id="366b2-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="366b2-110">Channel</span></span>|<span data-ttu-id="366b2-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="366b2-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="366b2-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="366b2-112">Description</span></span>  

 <span data-ttu-id="366b2-113">Dieses Ereignis tritt auf, wenn ein TCP-basierter Transport eine Nachricht sendet.</span><span class="sxs-lookup"><span data-stu-id="366b2-113">This event occurs when a TCP-based transport sends a message.</span></span> <span data-ttu-id="366b2-114">Beachten Sie, dass auf Transportebene zwischen Clients und Diensten für einen einzelnen Vorgang mehrere Nachrichten ausgetauscht werden können.</span><span class="sxs-lookup"><span data-stu-id="366b2-114">Note that at the transport level multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="366b2-115">Der Grund dafür kann das Infrastrukturverhalten sein, beispielsweise in Verbindung mit Sicherheitsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="366b2-115">This may be due to infrastructure behavior, security being a good example.</span></span> <span data-ttu-id="366b2-116">Daher variiert die Anzahl der ausgegebenen **messagesentbytransport** -Ereignisse abhängig von der Bindung Ihres Dieners und seiner Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="366b2-116">Therefore, the number of **MessageSentByTransport** events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
## <a name="message"></a><span data-ttu-id="366b2-117">`Message`</span><span class="sxs-lookup"><span data-stu-id="366b2-117">Message</span></span>  

 <span data-ttu-id="366b2-118">Der Transport hat eine Nachricht an '%1' gesendet.</span><span class="sxs-lookup"><span data-stu-id="366b2-118">The transport sent a message to '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="366b2-119">Details</span><span class="sxs-lookup"><span data-stu-id="366b2-119">Details</span></span>  
  
|<span data-ttu-id="366b2-120">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="366b2-120">Data Item Name</span></span>|<span data-ttu-id="366b2-121">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="366b2-121">Data Item Type</span></span>|<span data-ttu-id="366b2-122">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="366b2-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="366b2-123">DestinationAddress</span><span class="sxs-lookup"><span data-stu-id="366b2-123">DestinationAddress</span></span>|`xs:string`|<span data-ttu-id="366b2-124">Die Adresse, an die die Anforderungsnachricht gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="366b2-124">The address that the request message was sent to.</span></span>|  
|<span data-ttu-id="366b2-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="366b2-125">HostReference</span></span>|<span data-ttu-id="366b2-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="366b2-126">xs:string</span></span>|<span data-ttu-id="366b2-127">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="366b2-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="366b2-128">Sein Format ist als "Website Name Anwendungspfad für virtuelle Computer&#124;virtuellen Dienst Pfad&#124;Dienst Name '" definiert.</span><span class="sxs-lookup"><span data-stu-id="366b2-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="366b2-129">Beispiel: "Default Web Site/calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="366b2-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="366b2-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="366b2-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="366b2-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="366b2-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
