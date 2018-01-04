---
title: 219 - ServiceException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fceff5c748076c75c942f515e2621edff5106f4e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="219---serviceexception"></a><span data-ttu-id="2278a-102">219 - ServiceException</span><span class="sxs-lookup"><span data-stu-id="2278a-102">219 - ServiceException</span></span>
## <a name="properties"></a><span data-ttu-id="2278a-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2278a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2278a-104">Id</span><span class="sxs-lookup"><span data-stu-id="2278a-104">ID</span></span>|<span data-ttu-id="2278a-105">219</span><span class="sxs-lookup"><span data-stu-id="2278a-105">219</span></span>|  
|<span data-ttu-id="2278a-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="2278a-106">Keywords</span></span>|<span data-ttu-id="2278a-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2278a-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="2278a-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="2278a-108">Level</span></span>|<span data-ttu-id="2278a-109">Fehler</span><span class="sxs-lookup"><span data-stu-id="2278a-109">Error</span></span>|  
|<span data-ttu-id="2278a-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="2278a-110">Channel</span></span>|<span data-ttu-id="2278a-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="2278a-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2278a-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2278a-112">Description</span></span>  
 <span data-ttu-id="2278a-113">Dieses Ereignis wird ausgegeben, wenn in einem WCF-Dienst eine nicht behandelte Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="2278a-113">This event is emitted when a WCF service encounters an unhandled exception.</span></span> <span data-ttu-id="2278a-114">Dies schließt nicht behandelte Ausnahmen während der Aktivierung, während der Meldungsverarbeitung und im Benutzercode ein.</span><span class="sxs-lookup"><span data-stu-id="2278a-114">This includes unhandled exceptions during activation, during message processing, and in user code.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2278a-115">Meldung</span><span class="sxs-lookup"><span data-stu-id="2278a-115">Message</span></span>  
 <span data-ttu-id="2278a-116">Während der Meldungsverarbeitung ist eine nicht behandelte Ausnahme vom Typ '%2' aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="2278a-116">There was an unhandled exception of type '%2' during message processing.</span></span> <span data-ttu-id="2278a-117">Vollständige Ausnahme ToString: %1.</span><span class="sxs-lookup"><span data-stu-id="2278a-117">Full Exception ToString: %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2278a-118">Details</span><span class="sxs-lookup"><span data-stu-id="2278a-118">Details</span></span>  
  
|<span data-ttu-id="2278a-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="2278a-119">Data Item Name</span></span>|<span data-ttu-id="2278a-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="2278a-120">Data Item Type</span></span>|<span data-ttu-id="2278a-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2278a-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2278a-122">ExceptionToString</span><span class="sxs-lookup"><span data-stu-id="2278a-122">ExceptionToString</span></span>|`xs:string`|<span data-ttu-id="2278a-123">Das Ergebnis des Aufrufens von `ToString`() für die CLR-Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="2278a-123">The result of calling `ToString`() on the CLR exception.</span></span>|  
|<span data-ttu-id="2278a-124">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="2278a-124">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="2278a-125">Der CLR-FullName des Ausnahmetyps.</span><span class="sxs-lookup"><span data-stu-id="2278a-125">The CLR FullName of the exception's type.</span></span>|  
|<span data-ttu-id="2278a-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="2278a-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="2278a-127">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="2278a-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="2278a-128">Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="2278a-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="2278a-129">Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="2278a-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="2278a-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2278a-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="2278a-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2278a-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
