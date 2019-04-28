---
title: 303 - UserDefinedInformationEventOccured
ms.date: 03/30/2017
ms.assetid: 5ed5acaf-3755-4417-92c4-4ebc8e854ca1
ms.openlocfilehash: 0b782b5ac0527b5acb3ebf0bf11c117563042495
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61595776"
---
# <a name="303---userdefinedinformationeventoccured"></a><span data-ttu-id="49ce7-102">303 - UserDefinedInformationEventOccured</span><span class="sxs-lookup"><span data-stu-id="49ce7-102">303 - UserDefinedInformationEventOccured</span></span>
## <a name="properties"></a><span data-ttu-id="49ce7-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="49ce7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="49ce7-104">ID</span><span class="sxs-lookup"><span data-stu-id="49ce7-104">ID</span></span>|<span data-ttu-id="49ce7-105">303</span><span class="sxs-lookup"><span data-stu-id="49ce7-105">303</span></span>|  
|<span data-ttu-id="49ce7-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="49ce7-106">Keywords</span></span>|<span data-ttu-id="49ce7-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="49ce7-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="49ce7-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="49ce7-108">Level</span></span>|<span data-ttu-id="49ce7-109">Information</span><span class="sxs-lookup"><span data-stu-id="49ce7-109">Information</span></span>|  
|<span data-ttu-id="49ce7-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="49ce7-110">Channel</span></span>|<span data-ttu-id="49ce7-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="49ce7-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="49ce7-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="49ce7-112">Description</span></span>  
 <span data-ttu-id="49ce7-113">Dieses Ereignis wird vom Benutzercode ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="49ce7-113">This event is emitted from user code.</span></span> <span data-ttu-id="49ce7-114">Entwickler können dieses Ereignis ausgeben, wenn ein benutzerdefiniertes Informationsereignis im Dienst auftritt.</span><span class="sxs-lookup"><span data-stu-id="49ce7-114">Developers can emit this event when a custom-defined informational event occurs in their service.</span></span> <span data-ttu-id="49ce7-115">Sie können dafür die <xref:System.Diagnostics.Eventing>-APIs verwenden.</span><span class="sxs-lookup"><span data-stu-id="49ce7-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="49ce7-116">Zusätzlich ist ein WCF-Beispiel vorhanden, das als Wrapper dieser API fungiert und veranschaulicht, wie Sie dieses Ereignis ordnungsgemäß ausgeben.</span><span class="sxs-lookup"><span data-stu-id="49ce7-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="49ce7-117">Meldung</span><span class="sxs-lookup"><span data-stu-id="49ce7-117">Message</span></span>  
 <span data-ttu-id="49ce7-118">Name:'%1', Verweis:'%2', Nutzlast:%3</span><span class="sxs-lookup"><span data-stu-id="49ce7-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="49ce7-119">Details</span><span class="sxs-lookup"><span data-stu-id="49ce7-119">Details</span></span>  
  
|<span data-ttu-id="49ce7-120">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="49ce7-120">Data Item Name</span></span>|<span data-ttu-id="49ce7-121">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="49ce7-121">Data Item Type</span></span>|<span data-ttu-id="49ce7-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="49ce7-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="49ce7-123">Name</span><span class="sxs-lookup"><span data-stu-id="49ce7-123">Name</span></span>|`xs:string`|<span data-ttu-id="49ce7-124">Der benutzerdefinierte Name des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="49ce7-124">The user-defined name of the event</span></span>|  
|<span data-ttu-id="49ce7-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="49ce7-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="49ce7-126">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="49ce7-126">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="49ce7-127">Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="49ce7-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="49ce7-128">Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="49ce7-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="49ce7-129">Payload</span><span class="sxs-lookup"><span data-stu-id="49ce7-129">Payload</span></span>|`xs:string`|<span data-ttu-id="49ce7-130">Die benutzerdefinierte Nutzlast des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="49ce7-130">The user-defined payload of the event.</span></span>|
