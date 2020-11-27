---
title: 201 - ClientMessageInspectorAfterReceiveInvoked
ms.date: 03/30/2017
ms.assetid: 9ff637f1-cc26-4400-ab9b-546f70e5057d
ms.openlocfilehash: d84f6c6f38868f7915caaaf87e15885099b65456
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266674"
---
# <a name="201---clientmessageinspectorafterreceiveinvoked"></a><span data-ttu-id="2e86a-102">201 - ClientMessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="2e86a-102">201 - ClientMessageInspectorAfterReceiveInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="2e86a-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2e86a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2e86a-104">id</span><span class="sxs-lookup"><span data-stu-id="2e86a-104">ID</span></span>|<span data-ttu-id="2e86a-105">201</span><span class="sxs-lookup"><span data-stu-id="2e86a-105">201</span></span>|  
|<span data-ttu-id="2e86a-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="2e86a-106">Keywords</span></span>|<span data-ttu-id="2e86a-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2e86a-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="2e86a-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="2e86a-108">Level</span></span>|<span data-ttu-id="2e86a-109">Information</span><span class="sxs-lookup"><span data-stu-id="2e86a-109">Information</span></span>|  
|<span data-ttu-id="2e86a-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="2e86a-110">Channel</span></span>|<span data-ttu-id="2e86a-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="2e86a-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2e86a-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2e86a-112">Description</span></span>  

 <span data-ttu-id="2e86a-113">Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `AfterReceiveReply`-Methode auf einem Clientmeldungsinspektor aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="2e86a-113">This event is emitted after the Service Model has invoked the `AfterReceiveReply` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2e86a-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="2e86a-114">Message</span></span>  

 <span data-ttu-id="2e86a-115">Der Verteiler hat 'AfterReceiveReply' auf einem ClientMessageInspector vom Typ '%1' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="2e86a-115">The Dispatcher invoked 'AfterReceiveReply' on a ClientMessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2e86a-116">Details</span><span class="sxs-lookup"><span data-stu-id="2e86a-116">Details</span></span>  
  
|<span data-ttu-id="2e86a-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="2e86a-117">Data Item Name</span></span>|<span data-ttu-id="2e86a-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="2e86a-118">Data Item Type</span></span>|<span data-ttu-id="2e86a-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2e86a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2e86a-120">TypName</span><span class="sxs-lookup"><span data-stu-id="2e86a-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="2e86a-121">Der CLR-FullName für den Typ des aufgerufenen Inspektors.</span><span class="sxs-lookup"><span data-stu-id="2e86a-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="2e86a-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="2e86a-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="2e86a-123">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="2e86a-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="2e86a-124">Sein Format ist als "Website Name Anwendungspfad für virtuelle Computer&#124;virtuellen Dienst Pfad&#124;Dienst Name '" definiert.</span><span class="sxs-lookup"><span data-stu-id="2e86a-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="2e86a-125">Beispiel: "Default Web Site/calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="2e86a-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="2e86a-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2e86a-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="2e86a-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2e86a-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
