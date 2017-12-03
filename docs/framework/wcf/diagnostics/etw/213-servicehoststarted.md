---
title: 213 - ServiceHostStarted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6f7facc-342f-46bb-9d52-a470178ba6bb
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cc12626263e21f5fd7310157dcdafe327e6d17a8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="213---servicehoststarted"></a><span data-ttu-id="39f95-102">213 - ServiceHostStarted</span><span class="sxs-lookup"><span data-stu-id="39f95-102">213 - ServiceHostStarted</span></span>
## <a name="properties"></a><span data-ttu-id="39f95-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="39f95-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="39f95-104">ID</span><span class="sxs-lookup"><span data-stu-id="39f95-104">ID</span></span>|<span data-ttu-id="39f95-105">213</span><span class="sxs-lookup"><span data-stu-id="39f95-105">213</span></span>|  
|<span data-ttu-id="39f95-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="39f95-106">Keywords</span></span>|<span data-ttu-id="39f95-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceHost</span><span class="sxs-lookup"><span data-stu-id="39f95-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceHost</span></span>|  
|<span data-ttu-id="39f95-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="39f95-108">Level</span></span>|<span data-ttu-id="39f95-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="39f95-109">LogAlways</span></span>|  
|<span data-ttu-id="39f95-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="39f95-110">Channel</span></span>|<span data-ttu-id="39f95-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="39f95-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="39f95-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39f95-112">Description</span></span>  
 <span data-ttu-id="39f95-113">Dieses Ereignis wird ausgegeben, wenn ein im Web gehosteter Diensthost gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="39f95-113">This event is emitted when a Web-hosted service host is started.</span></span> <span data-ttu-id="39f95-114">Dies kommt in der Regel vor, wenn der Dienst von einer Nachricht aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="39f95-114">This typically happens when the service is activated by a message.</span></span> <span data-ttu-id="39f95-115">Es kann auch vorkommen, wenn für den Dienst das automatische Starten konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="39f95-115">It may also happen if the service is configured to be automatically started.</span></span>  
  
## <a name="message"></a><span data-ttu-id="39f95-116">Meldung</span><span class="sxs-lookup"><span data-stu-id="39f95-116">Message</span></span>  
 <span data-ttu-id="39f95-117">ServiceHost wurde gestartet: '%1'.</span><span class="sxs-lookup"><span data-stu-id="39f95-117">ServiceHost started: '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="39f95-118">Details</span><span class="sxs-lookup"><span data-stu-id="39f95-118">Details</span></span>  
  
|<span data-ttu-id="39f95-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="39f95-119">Data Item Name</span></span>|<span data-ttu-id="39f95-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="39f95-120">Data Item Type</span></span>|<span data-ttu-id="39f95-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39f95-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="39f95-122">Service Type Name</span><span class="sxs-lookup"><span data-stu-id="39f95-122">Service Type Name</span></span>|`xs:string`|<span data-ttu-id="39f95-123">Der CLR-FullName des Typs der Dienstimplementierung.</span><span class="sxs-lookup"><span data-stu-id="39f95-123">The CLR FullName of the type of the service implementation.</span></span>|  
|<span data-ttu-id="39f95-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="39f95-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="39f95-125">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="39f95-125">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="39f95-126">Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="39f95-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="39f95-127">Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="39f95-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="39f95-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="39f95-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="39f95-129">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="39f95-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
