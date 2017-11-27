---
title: 301 - UserDefinedErrorOccurred
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0285d1c-550f-4c14-9c36-a96e97f1c4e4
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: df75fdfa68e11a4a017dffa54e1bb4d628940968
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="301---userdefinederroroccurred"></a><span data-ttu-id="a7fae-102">301 - UserDefinedErrorOccurred</span><span class="sxs-lookup"><span data-stu-id="a7fae-102">301 - UserDefinedErrorOccurred</span></span>
## <a name="properties"></a><span data-ttu-id="a7fae-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a7fae-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a7fae-104">ID</span><span class="sxs-lookup"><span data-stu-id="a7fae-104">ID</span></span>|<span data-ttu-id="a7fae-105">301</span><span class="sxs-lookup"><span data-stu-id="a7fae-105">301</span></span>|  
|<span data-ttu-id="a7fae-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="a7fae-106">Keywords</span></span>|<span data-ttu-id="a7fae-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="a7fae-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="a7fae-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="a7fae-108">Level</span></span>|<span data-ttu-id="a7fae-109">Fehler</span><span class="sxs-lookup"><span data-stu-id="a7fae-109">Error</span></span>|  
|<span data-ttu-id="a7fae-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="a7fae-110">Channel</span></span>|<span data-ttu-id="a7fae-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="a7fae-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a7fae-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7fae-112">Description</span></span>  
 <span data-ttu-id="a7fae-113">Dieses Ereignis wird vom Benutzercode ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="a7fae-113">This event is emitted from user code.</span></span> <span data-ttu-id="a7fae-114">Entwickler können dieses Ereignis ausgeben, wenn ein benutzerdefinierter Fehler im Dienst auftritt.</span><span class="sxs-lookup"><span data-stu-id="a7fae-114">Developers can emit this event when a custom-defined error occurs in their service.</span></span> <span data-ttu-id="a7fae-115">Sie können dafür die <xref:System.Diagnostics.Eventing>-APIs verwenden.</span><span class="sxs-lookup"><span data-stu-id="a7fae-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="a7fae-116">Zusätzlich ist ein WCF-Beispiel vorhanden, das als Wrapper dieser API fungiert und veranschaulicht, wie Sie dieses Ereignis ordnungsgemäß ausgeben.</span><span class="sxs-lookup"><span data-stu-id="a7fae-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a7fae-117">Meldung</span><span class="sxs-lookup"><span data-stu-id="a7fae-117">Message</span></span>  
 <span data-ttu-id="a7fae-118">Name:'%1', Verweis:'%2', Nutzlast:%3</span><span class="sxs-lookup"><span data-stu-id="a7fae-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="a7fae-119">Details</span><span class="sxs-lookup"><span data-stu-id="a7fae-119">Details</span></span>  
  
|<span data-ttu-id="a7fae-120">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="a7fae-120">Data Item Name</span></span>|<span data-ttu-id="a7fae-121">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="a7fae-121">Data Item Type</span></span>|<span data-ttu-id="a7fae-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7fae-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a7fae-123">Name</span><span class="sxs-lookup"><span data-stu-id="a7fae-123">Name</span></span>|`xs:string`|<span data-ttu-id="a7fae-124">Der benutzerdefinierte Name des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="a7fae-124">The user-defined name of the event.</span></span>|  
|<span data-ttu-id="a7fae-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="a7fae-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="a7fae-126">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="a7fae-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="a7fae-127">Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="a7fae-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="a7fae-128">Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="a7fae-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="a7fae-129">Payload</span><span class="sxs-lookup"><span data-stu-id="a7fae-129">Payload</span></span>|`xs:string`|<span data-ttu-id="a7fae-130">Die benutzerdefinierte Nutzlast des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="a7fae-130">The user-defined payload of the event.</span></span>|
