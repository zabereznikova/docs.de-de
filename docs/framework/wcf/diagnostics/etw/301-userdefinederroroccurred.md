---
title: 301 - UserDefinedErrorOccurred
ms.date: 03/30/2017
ms.assetid: a0285d1c-550f-4c14-9c36-a96e97f1c4e4
ms.openlocfilehash: 2c3ff1905a1d17413211246f5b3cc156bcbb7320
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243455"
---
# <a name="301---userdefinederroroccurred"></a><span data-ttu-id="ae528-102">301 - UserDefinedErrorOccurred</span><span class="sxs-lookup"><span data-stu-id="ae528-102">301 - UserDefinedErrorOccurred</span></span>

## <a name="properties"></a><span data-ttu-id="ae528-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ae528-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ae528-104">id</span><span class="sxs-lookup"><span data-stu-id="ae528-104">ID</span></span>|<span data-ttu-id="ae528-105">301</span><span class="sxs-lookup"><span data-stu-id="ae528-105">301</span></span>|  
|<span data-ttu-id="ae528-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="ae528-106">Keywords</span></span>|<span data-ttu-id="ae528-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="ae528-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="ae528-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="ae528-108">Level</span></span>|<span data-ttu-id="ae528-109">Fehler</span><span class="sxs-lookup"><span data-stu-id="ae528-109">Error</span></span>|  
|<span data-ttu-id="ae528-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="ae528-110">Channel</span></span>|<span data-ttu-id="ae528-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="ae528-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ae528-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ae528-112">Description</span></span>  

 <span data-ttu-id="ae528-113">Dieses Ereignis wird vom Benutzercode ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="ae528-113">This event is emitted from user code.</span></span> <span data-ttu-id="ae528-114">Entwickler können dieses Ereignis ausgeben, wenn ein benutzerdefinierter Fehler im Dienst auftritt.</span><span class="sxs-lookup"><span data-stu-id="ae528-114">Developers can emit this event when a custom-defined error occurs in their service.</span></span> <span data-ttu-id="ae528-115">Sie können dafür die <xref:System.Diagnostics.Eventing>-APIs verwenden.</span><span class="sxs-lookup"><span data-stu-id="ae528-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="ae528-116">Zusätzlich ist ein WCF-Beispiel vorhanden, das als Wrapper dieser API fungiert und veranschaulicht, wie Sie dieses Ereignis ordnungsgemäß ausgeben.</span><span class="sxs-lookup"><span data-stu-id="ae528-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ae528-117">`Message`</span><span class="sxs-lookup"><span data-stu-id="ae528-117">Message</span></span>  

 <span data-ttu-id="ae528-118">Name:'%1', Verweis:'%2', Nutzlast:%3</span><span class="sxs-lookup"><span data-stu-id="ae528-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="ae528-119">Details</span><span class="sxs-lookup"><span data-stu-id="ae528-119">Details</span></span>  
  
|<span data-ttu-id="ae528-120">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="ae528-120">Data Item Name</span></span>|<span data-ttu-id="ae528-121">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="ae528-121">Data Item Type</span></span>|<span data-ttu-id="ae528-122">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ae528-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ae528-123">Name</span><span class="sxs-lookup"><span data-stu-id="ae528-123">Name</span></span>|`xs:string`|<span data-ttu-id="ae528-124">Der benutzerdefinierte Name des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="ae528-124">The user-defined name of the event.</span></span>|  
|<span data-ttu-id="ae528-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="ae528-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="ae528-126">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="ae528-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="ae528-127">Sein Format ist als "Website Name Anwendungspfad für virtuelle Computer&#124;virtuellen Dienst Pfad&#124;Dienst Name '" definiert.</span><span class="sxs-lookup"><span data-stu-id="ae528-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="ae528-128">Beispiel: "Default Web Site/calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="ae528-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="ae528-129">Nutzlast</span><span class="sxs-lookup"><span data-stu-id="ae528-129">Payload</span></span>|`xs:string`|<span data-ttu-id="ae528-130">Die benutzerdefinierte Nutzlast des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="ae528-130">The user-defined payload of the event.</span></span>|
