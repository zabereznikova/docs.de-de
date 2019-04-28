---
title: 219 - ServiceException
ms.date: 03/30/2017
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
ms.openlocfilehash: eb4289c0346c9e1d9481347d69db8c5f007e4325
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781731"
---
# <a name="219---serviceexception"></a><span data-ttu-id="0166c-102">219 - ServiceException</span><span class="sxs-lookup"><span data-stu-id="0166c-102">219 - ServiceException</span></span>
## <a name="properties"></a><span data-ttu-id="0166c-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="0166c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0166c-104">ID</span><span class="sxs-lookup"><span data-stu-id="0166c-104">ID</span></span>|<span data-ttu-id="0166c-105">219</span><span class="sxs-lookup"><span data-stu-id="0166c-105">219</span></span>|  
|<span data-ttu-id="0166c-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="0166c-106">Keywords</span></span>|<span data-ttu-id="0166c-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0166c-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="0166c-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="0166c-108">Level</span></span>|<span data-ttu-id="0166c-109">Fehler</span><span class="sxs-lookup"><span data-stu-id="0166c-109">Error</span></span>|  
|<span data-ttu-id="0166c-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="0166c-110">Channel</span></span>|<span data-ttu-id="0166c-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="0166c-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0166c-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0166c-112">Description</span></span>  
 <span data-ttu-id="0166c-113">Dieses Ereignis wird ausgegeben, wenn in einem WCF-Dienst eine nicht behandelte Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="0166c-113">This event is emitted when a WCF service encounters an unhandled exception.</span></span> <span data-ttu-id="0166c-114">Dies schließt nicht behandelte Ausnahmen während der Aktivierung, während der Meldungsverarbeitung und im Benutzercode ein.</span><span class="sxs-lookup"><span data-stu-id="0166c-114">This includes unhandled exceptions during activation, during message processing, and in user code.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0166c-115">Meldung</span><span class="sxs-lookup"><span data-stu-id="0166c-115">Message</span></span>  
 <span data-ttu-id="0166c-116">Während der Meldungsverarbeitung ist eine nicht behandelte Ausnahme vom Typ '%2' aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0166c-116">There was an unhandled exception of type '%2' during message processing.</span></span> <span data-ttu-id="0166c-117">Vollständige Ausnahme ToString: %1.</span><span class="sxs-lookup"><span data-stu-id="0166c-117">Full Exception ToString: %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0166c-118">Details</span><span class="sxs-lookup"><span data-stu-id="0166c-118">Details</span></span>  
  
|<span data-ttu-id="0166c-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="0166c-119">Data Item Name</span></span>|<span data-ttu-id="0166c-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="0166c-120">Data Item Type</span></span>|<span data-ttu-id="0166c-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0166c-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0166c-122">ExceptionToString</span><span class="sxs-lookup"><span data-stu-id="0166c-122">ExceptionToString</span></span>|`xs:string`|<span data-ttu-id="0166c-123">Das Ergebnis des Aufrufens von `ToString`() für die CLR-Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="0166c-123">The result of calling `ToString`() on the CLR exception.</span></span>|  
|<span data-ttu-id="0166c-124">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="0166c-124">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="0166c-125">Der CLR-FullName des Ausnahmetyps.</span><span class="sxs-lookup"><span data-stu-id="0166c-125">The CLR FullName of the exception's type.</span></span>|  
|<span data-ttu-id="0166c-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="0166c-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="0166c-127">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="0166c-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="0166c-128">Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="0166c-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="0166c-129">Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="0166c-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="0166c-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0166c-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="0166c-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="0166c-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
