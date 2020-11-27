---
title: 202 - ClientMessageInspectorBeforeSendInvoked
ms.date: 03/30/2017
ms.assetid: 0b02ca82-8a55-45e3-b2e2-ddfe28a7269c
ms.openlocfilehash: f05a0f817b8cb4857a4fa50eada15d3ff9e06855
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266622"
---
# <a name="202---clientmessageinspectorbeforesendinvoked"></a><span data-ttu-id="06ddd-102">202 - ClientMessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="06ddd-102">202 - ClientMessageInspectorBeforeSendInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="06ddd-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="06ddd-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="06ddd-104">id</span><span class="sxs-lookup"><span data-stu-id="06ddd-104">ID</span></span>|<span data-ttu-id="06ddd-105">202</span><span class="sxs-lookup"><span data-stu-id="06ddd-105">202</span></span>|  
|<span data-ttu-id="06ddd-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="06ddd-106">Keywords</span></span>|<span data-ttu-id="06ddd-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="06ddd-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="06ddd-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="06ddd-108">Level</span></span>|<span data-ttu-id="06ddd-109">Information</span><span class="sxs-lookup"><span data-stu-id="06ddd-109">Information</span></span>|  
|<span data-ttu-id="06ddd-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="06ddd-110">Channel</span></span>|<span data-ttu-id="06ddd-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="06ddd-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="06ddd-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="06ddd-112">Description</span></span>  

 <span data-ttu-id="06ddd-113">Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `BeforeSendRequest`-Methode auf einem Clientmeldungsinspektor aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="06ddd-113">This event is emitted after the Service Model has invoked the `BeforeSendRequest` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="06ddd-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="06ddd-114">Message</span></span>  

 <span data-ttu-id="06ddd-115">Der Verteiler hat 'BeforeSendRequest' auf einem ClientMessageInspector des Typs '%1' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="06ddd-115">The Dispatcher invoked 'BeforeSendRequest' on a ClientMessageInspector of type  '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="06ddd-116">Details</span><span class="sxs-lookup"><span data-stu-id="06ddd-116">Details</span></span>  
  
|<span data-ttu-id="06ddd-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="06ddd-117">Data Item Name</span></span>|<span data-ttu-id="06ddd-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="06ddd-118">Data Item Type</span></span>|<span data-ttu-id="06ddd-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="06ddd-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="06ddd-120">TypName</span><span class="sxs-lookup"><span data-stu-id="06ddd-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="06ddd-121">Der CLR-FullName für den Typ des aufgerufenen Inspektors.</span><span class="sxs-lookup"><span data-stu-id="06ddd-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="06ddd-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="06ddd-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="06ddd-123">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="06ddd-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="06ddd-124">Sein Format ist als "Website Name Anwendungspfad für virtuelle Computer&#124;virtuellen Dienst Pfad&#124;Dienst Name '" definiert.</span><span class="sxs-lookup"><span data-stu-id="06ddd-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="06ddd-125">Beispiel: "Default Web Site/calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="06ddd-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="06ddd-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="06ddd-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="06ddd-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="06ddd-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
