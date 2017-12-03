---
title: 302 - UserDefinedWarningOccurred
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8d1f0bf1-0151-45e6-be92-573d397b54de
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 61ec1e341d5220000b928409e006553c71ab379a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="302---userdefinedwarningoccurred"></a><span data-ttu-id="cc4d9-102">302 - UserDefinedWarningOccurred</span><span class="sxs-lookup"><span data-stu-id="cc4d9-102">302 - UserDefinedWarningOccurred</span></span>
## <a name="properties"></a><span data-ttu-id="cc4d9-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="cc4d9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cc4d9-104">ID</span><span class="sxs-lookup"><span data-stu-id="cc4d9-104">ID</span></span>|<span data-ttu-id="cc4d9-105">302</span><span class="sxs-lookup"><span data-stu-id="cc4d9-105">302</span></span>|  
|<span data-ttu-id="cc4d9-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="cc4d9-106">Keywords</span></span>|<span data-ttu-id="cc4d9-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="cc4d9-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="cc4d9-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="cc4d9-108">Level</span></span>|<span data-ttu-id="cc4d9-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="cc4d9-109">Warning</span></span>|  
|<span data-ttu-id="cc4d9-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="cc4d9-110">Channel</span></span>|<span data-ttu-id="cc4d9-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="cc4d9-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="cc4d9-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cc4d9-112">Description</span></span>  
 <span data-ttu-id="cc4d9-113">Dieses Ereignis wird vom Benutzercode ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="cc4d9-113">This event is emitted from user code.</span></span> <span data-ttu-id="cc4d9-114">Entwickler können dieses Ereignis ausgeben, wenn ein benutzerdefiniertes Warnungsereignis im Dienst auftritt.</span><span class="sxs-lookup"><span data-stu-id="cc4d9-114">Developers can emit this event when a custom-defined warning event occurs in their service.</span></span> <span data-ttu-id="cc4d9-115">Sie können dafür die <xref:System.Diagnostics.Eventing>-APIs verwenden.</span><span class="sxs-lookup"><span data-stu-id="cc4d9-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="cc4d9-116">Zusätzlich ist ein WCF-Beispiel vorhanden, das als Wrapper dieser API fungiert und veranschaulicht, wie Sie dieses Ereignis ordnungsgemäß ausgeben.</span><span class="sxs-lookup"><span data-stu-id="cc4d9-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="cc4d9-117">Meldung</span><span class="sxs-lookup"><span data-stu-id="cc4d9-117">Message</span></span>  
 <span data-ttu-id="cc4d9-118">Name:'%1', Verweis:'%2', Nutzlast:%3</span><span class="sxs-lookup"><span data-stu-id="cc4d9-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="cc4d9-119">Details</span><span class="sxs-lookup"><span data-stu-id="cc4d9-119">Details</span></span>  
  
|<span data-ttu-id="cc4d9-120">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="cc4d9-120">Data Item Name</span></span>|<span data-ttu-id="cc4d9-121">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="cc4d9-121">Data Item Type</span></span>|<span data-ttu-id="cc4d9-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cc4d9-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="cc4d9-123">Name</span><span class="sxs-lookup"><span data-stu-id="cc4d9-123">Name</span></span>|`xs:string`|<span data-ttu-id="cc4d9-124">Der benutzerdefinierte Name des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="cc4d9-124">The user-defined name of the event.</span></span>|  
|<span data-ttu-id="cc4d9-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="cc4d9-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="cc4d9-126">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="cc4d9-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="cc4d9-127">Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="cc4d9-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="cc4d9-128">Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="cc4d9-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="cc4d9-129">Payload</span><span class="sxs-lookup"><span data-stu-id="cc4d9-129">Payload</span></span>|`xs:string`|<span data-ttu-id="cc4d9-130">Die benutzerdefinierte Nutzlast des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="cc4d9-130">The user-defined payload of the event.</span></span>|
