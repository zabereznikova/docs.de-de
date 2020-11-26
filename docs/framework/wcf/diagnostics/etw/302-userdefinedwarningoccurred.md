---
title: 302 - UserDefinedWarningOccurred
ms.date: 03/30/2017
ms.assetid: 8d1f0bf1-0151-45e6-be92-573d397b54de
ms.openlocfilehash: b942b2e9716713371b8679fc9df9b9634dfc7283
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243442"
---
# <a name="302---userdefinedwarningoccurred"></a><span data-ttu-id="82272-102">302 - UserDefinedWarningOccurred</span><span class="sxs-lookup"><span data-stu-id="82272-102">302 - UserDefinedWarningOccurred</span></span>

## <a name="properties"></a><span data-ttu-id="82272-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="82272-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="82272-104">id</span><span class="sxs-lookup"><span data-stu-id="82272-104">ID</span></span>|<span data-ttu-id="82272-105">302</span><span class="sxs-lookup"><span data-stu-id="82272-105">302</span></span>|  
|<span data-ttu-id="82272-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="82272-106">Keywords</span></span>|<span data-ttu-id="82272-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="82272-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="82272-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="82272-108">Level</span></span>|<span data-ttu-id="82272-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="82272-109">Warning</span></span>|  
|<span data-ttu-id="82272-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="82272-110">Channel</span></span>|<span data-ttu-id="82272-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="82272-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="82272-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="82272-112">Description</span></span>  

 <span data-ttu-id="82272-113">Dieses Ereignis wird vom Benutzercode ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="82272-113">This event is emitted from user code.</span></span> <span data-ttu-id="82272-114">Entwickler können dieses Ereignis ausgeben, wenn ein benutzerdefiniertes Warnungsereignis im Dienst auftritt.</span><span class="sxs-lookup"><span data-stu-id="82272-114">Developers can emit this event when a custom-defined warning event occurs in their service.</span></span> <span data-ttu-id="82272-115">Sie können dafür die <xref:System.Diagnostics.Eventing>-APIs verwenden.</span><span class="sxs-lookup"><span data-stu-id="82272-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="82272-116">Zusätzlich ist ein WCF-Beispiel vorhanden, das als Wrapper dieser API fungiert und veranschaulicht, wie Sie dieses Ereignis ordnungsgemäß ausgeben.</span><span class="sxs-lookup"><span data-stu-id="82272-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="82272-117">`Message`</span><span class="sxs-lookup"><span data-stu-id="82272-117">Message</span></span>  

 <span data-ttu-id="82272-118">Name:'%1', Verweis:'%2', Nutzlast:%3</span><span class="sxs-lookup"><span data-stu-id="82272-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="82272-119">Details</span><span class="sxs-lookup"><span data-stu-id="82272-119">Details</span></span>  
  
|<span data-ttu-id="82272-120">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="82272-120">Data Item Name</span></span>|<span data-ttu-id="82272-121">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="82272-121">Data Item Type</span></span>|<span data-ttu-id="82272-122">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="82272-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="82272-123">Name</span><span class="sxs-lookup"><span data-stu-id="82272-123">Name</span></span>|`xs:string`|<span data-ttu-id="82272-124">Der benutzerdefinierte Name des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="82272-124">The user-defined name of the event.</span></span>|  
|<span data-ttu-id="82272-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="82272-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="82272-126">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="82272-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="82272-127">Sein Format ist als "Website Name Anwendungspfad für virtuelle Computer&#124;virtuellen Dienst Pfad&#124;Dienst Name '" definiert.</span><span class="sxs-lookup"><span data-stu-id="82272-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="82272-128">Beispiel: "Default Web Site/calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="82272-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="82272-129">Nutzlast</span><span class="sxs-lookup"><span data-stu-id="82272-129">Payload</span></span>|`xs:string`|<span data-ttu-id="82272-130">Die benutzerdefinierte Nutzlast des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="82272-130">The user-defined payload of the event.</span></span>|
