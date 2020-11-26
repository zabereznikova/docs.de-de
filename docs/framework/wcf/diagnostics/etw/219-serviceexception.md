---
title: 219 - ServiceException
ms.date: 03/30/2017
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
ms.openlocfilehash: 832ced406b6079fad8f4b9bea512a6d390bdcc0f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96241940"
---
# <a name="219---serviceexception"></a><span data-ttu-id="11e80-102">219 - ServiceException</span><span class="sxs-lookup"><span data-stu-id="11e80-102">219 - ServiceException</span></span>

## <a name="properties"></a><span data-ttu-id="11e80-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="11e80-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="11e80-104">id</span><span class="sxs-lookup"><span data-stu-id="11e80-104">ID</span></span>|<span data-ttu-id="11e80-105">219</span><span class="sxs-lookup"><span data-stu-id="11e80-105">219</span></span>|  
|<span data-ttu-id="11e80-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="11e80-106">Keywords</span></span>|<span data-ttu-id="11e80-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="11e80-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="11e80-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="11e80-108">Level</span></span>|<span data-ttu-id="11e80-109">Fehler</span><span class="sxs-lookup"><span data-stu-id="11e80-109">Error</span></span>|  
|<span data-ttu-id="11e80-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="11e80-110">Channel</span></span>|<span data-ttu-id="11e80-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="11e80-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="11e80-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="11e80-112">Description</span></span>  

 <span data-ttu-id="11e80-113">Dieses Ereignis wird ausgegeben, wenn in einem WCF-Dienst eine nicht behandelte Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="11e80-113">This event is emitted when a WCF service encounters an unhandled exception.</span></span> <span data-ttu-id="11e80-114">Dies schließt nicht behandelte Ausnahmen während der Aktivierung, während der Meldungsverarbeitung und im Benutzercode ein.</span><span class="sxs-lookup"><span data-stu-id="11e80-114">This includes unhandled exceptions during activation, during message processing, and in user code.</span></span>  
  
## <a name="message"></a><span data-ttu-id="11e80-115">`Message`</span><span class="sxs-lookup"><span data-stu-id="11e80-115">Message</span></span>  

 <span data-ttu-id="11e80-116">Während der Meldungsverarbeitung ist eine nicht behandelte Ausnahme vom Typ '%2' aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="11e80-116">There was an unhandled exception of type '%2' during message processing.</span></span> <span data-ttu-id="11e80-117">Vollständige Ausnahme ToString: %1.</span><span class="sxs-lookup"><span data-stu-id="11e80-117">Full Exception ToString: %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="11e80-118">Details</span><span class="sxs-lookup"><span data-stu-id="11e80-118">Details</span></span>  
  
|<span data-ttu-id="11e80-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="11e80-119">Data Item Name</span></span>|<span data-ttu-id="11e80-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="11e80-120">Data Item Type</span></span>|<span data-ttu-id="11e80-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="11e80-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="11e80-122">ExceptionToString</span><span class="sxs-lookup"><span data-stu-id="11e80-122">ExceptionToString</span></span>|`xs:string`|<span data-ttu-id="11e80-123">Das Ergebnis des Aufrufens von `ToString`() für die CLR-Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="11e80-123">The result of calling `ToString`() on the CLR exception.</span></span>|  
|<span data-ttu-id="11e80-124">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="11e80-124">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="11e80-125">Der CLR-FullName des Ausnahmetyps.</span><span class="sxs-lookup"><span data-stu-id="11e80-125">The CLR FullName of the exception's type.</span></span>|  
|<span data-ttu-id="11e80-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="11e80-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="11e80-127">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="11e80-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="11e80-128">Sein Format ist als "Website Name Anwendungspfad für virtuelle Computer&#124;virtuellen Dienst Pfad&#124;Dienst Name '" definiert.</span><span class="sxs-lookup"><span data-stu-id="11e80-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="11e80-129">Beispiel: "Default Web Site/calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="11e80-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="11e80-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="11e80-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="11e80-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="11e80-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
