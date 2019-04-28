---
title: 201 - ClientMessageInspectorAfterReceiveInvoked
ms.date: 03/30/2017
ms.assetid: 9ff637f1-cc26-4400-ab9b-546f70e5057d
ms.openlocfilehash: 96ca318c141d49e2ac5594d5ee101658a2aa8f21
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782033"
---
# <a name="201---clientmessageinspectorafterreceiveinvoked"></a><span data-ttu-id="cd622-102">201 - ClientMessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="cd622-102">201 - ClientMessageInspectorAfterReceiveInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="cd622-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="cd622-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cd622-104">ID</span><span class="sxs-lookup"><span data-stu-id="cd622-104">ID</span></span>|<span data-ttu-id="cd622-105">201</span><span class="sxs-lookup"><span data-stu-id="cd622-105">201</span></span>|  
|<span data-ttu-id="cd622-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="cd622-106">Keywords</span></span>|<span data-ttu-id="cd622-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="cd622-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="cd622-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="cd622-108">Level</span></span>|<span data-ttu-id="cd622-109">Information</span><span class="sxs-lookup"><span data-stu-id="cd622-109">Information</span></span>|  
|<span data-ttu-id="cd622-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="cd622-110">Channel</span></span>|<span data-ttu-id="cd622-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="cd622-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="cd622-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd622-112">Description</span></span>  
 <span data-ttu-id="cd622-113">Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `AfterReceiveReply`-Methode auf einem Clientmeldungsinspektor aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="cd622-113">This event is emitted after the Service Model has invoked the `AfterReceiveReply` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="cd622-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="cd622-114">Message</span></span>  
 <span data-ttu-id="cd622-115">Der Verteiler hat 'AfterReceiveReply' auf einem ClientMessageInspector vom Typ '%1' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="cd622-115">The Dispatcher invoked 'AfterReceiveReply' on a ClientMessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="cd622-116">Details</span><span class="sxs-lookup"><span data-stu-id="cd622-116">Details</span></span>  
  
|<span data-ttu-id="cd622-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="cd622-117">Data Item Name</span></span>|<span data-ttu-id="cd622-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="cd622-118">Data Item Type</span></span>|<span data-ttu-id="cd622-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd622-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="cd622-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="cd622-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="cd622-121">Der CLR-FullName für den Typ des aufgerufenen Inspektors.</span><span class="sxs-lookup"><span data-stu-id="cd622-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="cd622-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="cd622-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="cd622-123">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="cd622-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="cd622-124">Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="cd622-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="cd622-125">Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="cd622-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="cd622-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="cd622-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="cd622-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="cd622-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
