---
title: 216 - MessageSentByTransport
ms.date: 03/30/2017
ms.assetid: 150c3167-4154-4225-8d94-57cc94341233
ms.openlocfilehash: fa21568e4c8c38eefe359c417d47ec0a9d30a7c4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458682"
---
# <a name="216---messagesentbytransport"></a><span data-ttu-id="32fed-102">216 - MessageSentByTransport</span><span class="sxs-lookup"><span data-stu-id="32fed-102">216 - MessageSentByTransport</span></span>
## <a name="properties"></a><span data-ttu-id="32fed-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="32fed-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="32fed-104">Id</span><span class="sxs-lookup"><span data-stu-id="32fed-104">ID</span></span>|<span data-ttu-id="32fed-105">216</span><span class="sxs-lookup"><span data-stu-id="32fed-105">216</span></span>|  
|<span data-ttu-id="32fed-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="32fed-106">Keywords</span></span>|<span data-ttu-id="32fed-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="32fed-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="32fed-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="32fed-108">Level</span></span>|<span data-ttu-id="32fed-109">Information</span><span class="sxs-lookup"><span data-stu-id="32fed-109">Information</span></span>|  
|<span data-ttu-id="32fed-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="32fed-110">Channel</span></span>|<span data-ttu-id="32fed-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="32fed-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="32fed-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32fed-112">Description</span></span>  
 <span data-ttu-id="32fed-113">Dieses Ereignis tritt auf, wenn ein TCP-basierter Transport eine Nachricht sendet.</span><span class="sxs-lookup"><span data-stu-id="32fed-113">This event occurs when a TCP-based transport sends a message.</span></span> <span data-ttu-id="32fed-114">Beachten Sie, dass auf Transportebene zwischen Clients und Diensten für einen einzelnen Vorgang mehrere Nachrichten ausgetauscht werden können.</span><span class="sxs-lookup"><span data-stu-id="32fed-114">Note that at the transport level multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="32fed-115">Der Grund dafür kann das Infrastrukturverhalten sein, beispielsweise in Verbindung mit Sicherheitsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="32fed-115">This may be due to infrastructure behavior, security being a good example.</span></span> <span data-ttu-id="32fed-116">Aus diesem Grund wird die Anzahl der **MessageSentByTransport** Ereignisse, die ausgegeben werden basierend auf der Bindung des Diensts und seiner Konfiguration variieren.</span><span class="sxs-lookup"><span data-stu-id="32fed-116">Therefore, the number of **MessageSentByTransport** events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
## <a name="message"></a><span data-ttu-id="32fed-117">Meldung</span><span class="sxs-lookup"><span data-stu-id="32fed-117">Message</span></span>  
 <span data-ttu-id="32fed-118">Der Transport hat eine Nachricht an '%1' gesendet.</span><span class="sxs-lookup"><span data-stu-id="32fed-118">The transport sent a message to '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="32fed-119">Details</span><span class="sxs-lookup"><span data-stu-id="32fed-119">Details</span></span>  
  
|<span data-ttu-id="32fed-120">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="32fed-120">Data Item Name</span></span>|<span data-ttu-id="32fed-121">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="32fed-121">Data Item Type</span></span>|<span data-ttu-id="32fed-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32fed-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="32fed-123">DestinationAddress</span><span class="sxs-lookup"><span data-stu-id="32fed-123">DestinationAddress</span></span>|`xs:string`|<span data-ttu-id="32fed-124">Die Adresse, an die die Anforderungsnachricht gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="32fed-124">The address that the request message was sent to.</span></span>|  
|<span data-ttu-id="32fed-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="32fed-125">HostReference</span></span>|<span data-ttu-id="32fed-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="32fed-126">xs:string</span></span>|<span data-ttu-id="32fed-127">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="32fed-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="32fed-128">Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="32fed-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="32fed-129">Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="32fed-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="32fed-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="32fed-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="32fed-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="32fed-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
