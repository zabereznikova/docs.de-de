---
title: 209 - MessageInspectorBeforeSendInvoked
ms.date: 03/30/2017
ms.assetid: 7d710875-fb77-4463-978b-bc86d59d84cd
ms.openlocfilehash: 24184c24b9affdf3a56d7968c02cf5354d690749
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458834"
---
# <a name="209---messageinspectorbeforesendinvoked"></a><span data-ttu-id="15870-102">209 - MessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="15870-102">209 - MessageInspectorBeforeSendInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="15870-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="15870-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="15870-104">Id</span><span class="sxs-lookup"><span data-stu-id="15870-104">ID</span></span>|<span data-ttu-id="15870-105">209</span><span class="sxs-lookup"><span data-stu-id="15870-105">209</span></span>|  
|<span data-ttu-id="15870-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="15870-106">Keywords</span></span>|<span data-ttu-id="15870-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="15870-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="15870-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="15870-108">Level</span></span>|<span data-ttu-id="15870-109">Information</span><span class="sxs-lookup"><span data-stu-id="15870-109">Information</span></span>|  
|<span data-ttu-id="15870-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="15870-110">Channel</span></span>|<span data-ttu-id="15870-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="15870-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="15870-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15870-112">Description</span></span>  
 <span data-ttu-id="15870-113">Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `BeforeSend`-Methode auf einem Nachrichteninspektor aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="15870-113">This event is emitted after the Service Model has invoked the `BeforeSend` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="15870-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="15870-114">Message</span></span>  
 <span data-ttu-id="15870-115">Der Verteiler hat 'BeforeSendRequest' auf einem MessageInspector vom Typ '%1' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="15870-115">The Dispatcher invoked 'BeforeSendRequest' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="15870-116">Details</span><span class="sxs-lookup"><span data-stu-id="15870-116">Details</span></span>  
  
|<span data-ttu-id="15870-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="15870-117">Data Item Name</span></span>|<span data-ttu-id="15870-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="15870-118">Data Item Type</span></span>|<span data-ttu-id="15870-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15870-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="15870-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="15870-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="15870-121">Der CLR-FullName des aufgerufenen `MessageInspector`-Typs.</span><span class="sxs-lookup"><span data-stu-id="15870-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="15870-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="15870-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="15870-123">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="15870-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="15870-124">Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="15870-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="15870-125">Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="15870-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="15870-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="15870-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="15870-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="15870-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
