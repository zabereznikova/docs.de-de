---
title: 202 - ClientMessageInspectorBeforeSendInvoked
ms.date: 03/30/2017
ms.assetid: 0b02ca82-8a55-45e3-b2e2-ddfe28a7269c
ms.openlocfilehash: 98de1d7e8e5e87ec7fbd783092f7fbc212fec65d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459354"
---
# <a name="202---clientmessageinspectorbeforesendinvoked"></a><span data-ttu-id="8f5cf-102">202 - ClientMessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="8f5cf-102">202 - ClientMessageInspectorBeforeSendInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="8f5cf-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8f5cf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8f5cf-104">Id</span><span class="sxs-lookup"><span data-stu-id="8f5cf-104">ID</span></span>|<span data-ttu-id="8f5cf-105">202</span><span class="sxs-lookup"><span data-stu-id="8f5cf-105">202</span></span>|  
|<span data-ttu-id="8f5cf-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="8f5cf-106">Keywords</span></span>|<span data-ttu-id="8f5cf-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="8f5cf-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="8f5cf-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="8f5cf-108">Level</span></span>|<span data-ttu-id="8f5cf-109">Information</span><span class="sxs-lookup"><span data-stu-id="8f5cf-109">Information</span></span>|  
|<span data-ttu-id="8f5cf-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="8f5cf-110">Channel</span></span>|<span data-ttu-id="8f5cf-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="8f5cf-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8f5cf-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f5cf-112">Description</span></span>  
 <span data-ttu-id="8f5cf-113">Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `BeforeSendRequest`-Methode auf einem Clientmeldungsinspektor aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="8f5cf-113">This event is emitted after the Service Model has invoked the `BeforeSendRequest` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8f5cf-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="8f5cf-114">Message</span></span>  
 <span data-ttu-id="8f5cf-115">Der Verteiler hat 'BeforeSendRequest' auf einem ClientMessageInspector des Typs '%1' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="8f5cf-115">The Dispatcher invoked 'BeforeSendRequest' on a ClientMessageInspector of type  '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8f5cf-116">Details</span><span class="sxs-lookup"><span data-stu-id="8f5cf-116">Details</span></span>  
  
|<span data-ttu-id="8f5cf-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="8f5cf-117">Data Item Name</span></span>|<span data-ttu-id="8f5cf-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="8f5cf-118">Data Item Type</span></span>|<span data-ttu-id="8f5cf-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f5cf-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8f5cf-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="8f5cf-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="8f5cf-121">Der CLR-FullName für den Typ des aufgerufenen Inspektors.</span><span class="sxs-lookup"><span data-stu-id="8f5cf-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="8f5cf-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="8f5cf-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="8f5cf-123">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="8f5cf-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="8f5cf-124">Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="8f5cf-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="8f5cf-125">Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="8f5cf-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="8f5cf-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8f5cf-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="8f5cf-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8f5cf-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
