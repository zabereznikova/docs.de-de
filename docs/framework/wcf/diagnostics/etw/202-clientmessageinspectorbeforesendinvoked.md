---
title: 202 - ClientMessageInspectorBeforeSendInvoked
ms.date: 03/30/2017
ms.assetid: 0b02ca82-8a55-45e3-b2e2-ddfe28a7269c
ms.openlocfilehash: 98de1d7e8e5e87ec7fbd783092f7fbc212fec65d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781991"
---
# <a name="202---clientmessageinspectorbeforesendinvoked"></a><span data-ttu-id="5fe67-102">202 - ClientMessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="5fe67-102">202 - ClientMessageInspectorBeforeSendInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="5fe67-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="5fe67-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5fe67-104">ID</span><span class="sxs-lookup"><span data-stu-id="5fe67-104">ID</span></span>|<span data-ttu-id="5fe67-105">202</span><span class="sxs-lookup"><span data-stu-id="5fe67-105">202</span></span>|  
|<span data-ttu-id="5fe67-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5fe67-106">Keywords</span></span>|<span data-ttu-id="5fe67-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="5fe67-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="5fe67-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="5fe67-108">Level</span></span>|<span data-ttu-id="5fe67-109">Information</span><span class="sxs-lookup"><span data-stu-id="5fe67-109">Information</span></span>|  
|<span data-ttu-id="5fe67-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="5fe67-110">Channel</span></span>|<span data-ttu-id="5fe67-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="5fe67-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5fe67-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5fe67-112">Description</span></span>  
 <span data-ttu-id="5fe67-113">Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `BeforeSendRequest`-Methode auf einem Clientmeldungsinspektor aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="5fe67-113">This event is emitted after the Service Model has invoked the `BeforeSendRequest` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5fe67-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="5fe67-114">Message</span></span>  
 <span data-ttu-id="5fe67-115">Der Verteiler hat 'BeforeSendRequest' auf einem ClientMessageInspector des Typs '%1' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="5fe67-115">The Dispatcher invoked 'BeforeSendRequest' on a ClientMessageInspector of type  '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5fe67-116">Details</span><span class="sxs-lookup"><span data-stu-id="5fe67-116">Details</span></span>  
  
|<span data-ttu-id="5fe67-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="5fe67-117">Data Item Name</span></span>|<span data-ttu-id="5fe67-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="5fe67-118">Data Item Type</span></span>|<span data-ttu-id="5fe67-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5fe67-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5fe67-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="5fe67-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="5fe67-121">Der CLR-FullName für den Typ des aufgerufenen Inspektors.</span><span class="sxs-lookup"><span data-stu-id="5fe67-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="5fe67-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="5fe67-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="5fe67-123">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="5fe67-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="5fe67-124">Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="5fe67-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="5fe67-125">Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="5fe67-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="5fe67-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5fe67-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="5fe67-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="5fe67-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
