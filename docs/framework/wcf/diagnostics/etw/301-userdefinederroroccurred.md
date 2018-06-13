---
title: 301 - UserDefinedErrorOccurred
ms.date: 03/30/2017
ms.assetid: a0285d1c-550f-4c14-9c36-a96e97f1c4e4
ms.openlocfilehash: 6eb80d6f0b20af9aae6e7de5248323088e352b26
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459478"
---
# <a name="301---userdefinederroroccurred"></a><span data-ttu-id="00853-102">301 - UserDefinedErrorOccurred</span><span class="sxs-lookup"><span data-stu-id="00853-102">301 - UserDefinedErrorOccurred</span></span>
## <a name="properties"></a><span data-ttu-id="00853-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="00853-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="00853-104">Id</span><span class="sxs-lookup"><span data-stu-id="00853-104">ID</span></span>|<span data-ttu-id="00853-105">301</span><span class="sxs-lookup"><span data-stu-id="00853-105">301</span></span>|  
|<span data-ttu-id="00853-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="00853-106">Keywords</span></span>|<span data-ttu-id="00853-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="00853-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="00853-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="00853-108">Level</span></span>|<span data-ttu-id="00853-109">Fehler</span><span class="sxs-lookup"><span data-stu-id="00853-109">Error</span></span>|  
|<span data-ttu-id="00853-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="00853-110">Channel</span></span>|<span data-ttu-id="00853-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="00853-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="00853-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00853-112">Description</span></span>  
 <span data-ttu-id="00853-113">Dieses Ereignis wird vom Benutzercode ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="00853-113">This event is emitted from user code.</span></span> <span data-ttu-id="00853-114">Entwickler können dieses Ereignis ausgeben, wenn ein benutzerdefinierter Fehler im Dienst auftritt.</span><span class="sxs-lookup"><span data-stu-id="00853-114">Developers can emit this event when a custom-defined error occurs in their service.</span></span> <span data-ttu-id="00853-115">Sie können dafür die <xref:System.Diagnostics.Eventing>-APIs verwenden.</span><span class="sxs-lookup"><span data-stu-id="00853-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="00853-116">Zusätzlich ist ein WCF-Beispiel vorhanden, das als Wrapper dieser API fungiert und veranschaulicht, wie Sie dieses Ereignis ordnungsgemäß ausgeben.</span><span class="sxs-lookup"><span data-stu-id="00853-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="00853-117">Meldung</span><span class="sxs-lookup"><span data-stu-id="00853-117">Message</span></span>  
 <span data-ttu-id="00853-118">Name:'%1', Verweis:'%2', Nutzlast:%3</span><span class="sxs-lookup"><span data-stu-id="00853-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="00853-119">Details</span><span class="sxs-lookup"><span data-stu-id="00853-119">Details</span></span>  
  
|<span data-ttu-id="00853-120">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="00853-120">Data Item Name</span></span>|<span data-ttu-id="00853-121">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="00853-121">Data Item Type</span></span>|<span data-ttu-id="00853-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00853-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="00853-123">name</span><span class="sxs-lookup"><span data-stu-id="00853-123">Name</span></span>|`xs:string`|<span data-ttu-id="00853-124">Der benutzerdefinierte Name des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="00853-124">The user-defined name of the event.</span></span>|  
|<span data-ttu-id="00853-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="00853-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="00853-126">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="00853-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="00853-127">Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="00853-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="00853-128">Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="00853-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="00853-129">Payload</span><span class="sxs-lookup"><span data-stu-id="00853-129">Payload</span></span>|`xs:string`|<span data-ttu-id="00853-130">Die benutzerdefinierte Nutzlast des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="00853-130">The user-defined payload of the event.</span></span>|
