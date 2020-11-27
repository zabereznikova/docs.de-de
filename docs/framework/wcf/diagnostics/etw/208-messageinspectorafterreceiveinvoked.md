---
title: 208 - MessageInspectorAfterReceiveInvoked
ms.date: 03/30/2017
ms.assetid: dfb5f7b0-4346-4949-8104-351726b1f502
ms.openlocfilehash: 4aa0f41b0b772551d9257920e5c15051961b7332
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267818"
---
# <a name="208---messageinspectorafterreceiveinvoked"></a><span data-ttu-id="d4b62-102">208 - MessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="d4b62-102">208 - MessageInspectorAfterReceiveInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="d4b62-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d4b62-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d4b62-104">id</span><span class="sxs-lookup"><span data-stu-id="d4b62-104">ID</span></span>|<span data-ttu-id="d4b62-105">208</span><span class="sxs-lookup"><span data-stu-id="d4b62-105">208</span></span>|  
|<span data-ttu-id="d4b62-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="d4b62-106">Keywords</span></span>|<span data-ttu-id="d4b62-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d4b62-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="d4b62-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="d4b62-108">Level</span></span>|<span data-ttu-id="d4b62-109">Information</span><span class="sxs-lookup"><span data-stu-id="d4b62-109">Information</span></span>|  
|<span data-ttu-id="d4b62-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="d4b62-110">Channel</span></span>|<span data-ttu-id="d4b62-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="d4b62-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d4b62-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d4b62-112">Description</span></span>  

 <span data-ttu-id="d4b62-113">Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `AfterReceive`-Methode auf einem Nachrichteninspektor aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="d4b62-113">This event is emitted after the Service Model has invoked the `AfterReceive` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d4b62-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="d4b62-114">Message</span></span>  

 <span data-ttu-id="d4b62-115">Der Verteiler hat 'AfterReceiveReply' auf einem MessageInspector vom Typ '%1' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="d4b62-115">The Dispatcher invoked 'AfterReceiveReply' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d4b62-116">Details</span><span class="sxs-lookup"><span data-stu-id="d4b62-116">Details</span></span>  
  
|<span data-ttu-id="d4b62-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="d4b62-117">Data Item Name</span></span>|<span data-ttu-id="d4b62-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="d4b62-118">Data Item Type</span></span>|<span data-ttu-id="d4b62-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d4b62-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d4b62-120">TypName</span><span class="sxs-lookup"><span data-stu-id="d4b62-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="d4b62-121">Der CLR-FullName des aufgerufenen `MessageInspector`-Typs.</span><span class="sxs-lookup"><span data-stu-id="d4b62-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="d4b62-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="d4b62-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="d4b62-123">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="d4b62-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="d4b62-124">Sein Format ist als "Website Name Anwendungspfad für virtuelle Computer&#124;virtuellen Dienst Pfad&#124;Dienst Name '" definiert.</span><span class="sxs-lookup"><span data-stu-id="d4b62-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="d4b62-125">Beispiel: "Default Web Site/calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="d4b62-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="d4b62-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d4b62-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="d4b62-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="d4b62-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
