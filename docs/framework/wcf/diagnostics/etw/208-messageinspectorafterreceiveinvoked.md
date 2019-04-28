---
title: 208 - MessageInspectorAfterReceiveInvoked
ms.date: 03/30/2017
ms.assetid: dfb5f7b0-4346-4949-8104-351726b1f502
ms.openlocfilehash: 3499131fcb52f0a0ab6d0e78e165522b7092612f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781900"
---
# <a name="208---messageinspectorafterreceiveinvoked"></a><span data-ttu-id="b15a2-102">208 - MessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="b15a2-102">208 - MessageInspectorAfterReceiveInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="b15a2-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b15a2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b15a2-104">ID</span><span class="sxs-lookup"><span data-stu-id="b15a2-104">ID</span></span>|<span data-ttu-id="b15a2-105">208</span><span class="sxs-lookup"><span data-stu-id="b15a2-105">208</span></span>|  
|<span data-ttu-id="b15a2-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="b15a2-106">Keywords</span></span>|<span data-ttu-id="b15a2-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b15a2-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="b15a2-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="b15a2-108">Level</span></span>|<span data-ttu-id="b15a2-109">Information</span><span class="sxs-lookup"><span data-stu-id="b15a2-109">Information</span></span>|  
|<span data-ttu-id="b15a2-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="b15a2-110">Channel</span></span>|<span data-ttu-id="b15a2-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="b15a2-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b15a2-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b15a2-112">Description</span></span>  
 <span data-ttu-id="b15a2-113">Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `AfterReceive`-Methode auf einem Nachrichteninspektor aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="b15a2-113">This event is emitted after the Service Model has invoked the `AfterReceive` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b15a2-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="b15a2-114">Message</span></span>  
 <span data-ttu-id="b15a2-115">Der Verteiler hat 'AfterReceiveReply' auf einem MessageInspector vom Typ '%1' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="b15a2-115">The Dispatcher invoked 'AfterReceiveReply' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b15a2-116">Details</span><span class="sxs-lookup"><span data-stu-id="b15a2-116">Details</span></span>  
  
|<span data-ttu-id="b15a2-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="b15a2-117">Data Item Name</span></span>|<span data-ttu-id="b15a2-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="b15a2-118">Data Item Type</span></span>|<span data-ttu-id="b15a2-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b15a2-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b15a2-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="b15a2-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="b15a2-121">Der CLR-FullName des aufgerufenen `MessageInspector`-Typs.</span><span class="sxs-lookup"><span data-stu-id="b15a2-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="b15a2-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="b15a2-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="b15a2-123">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="b15a2-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="b15a2-124">Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="b15a2-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="b15a2-125">Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="b15a2-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="b15a2-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b15a2-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="b15a2-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="b15a2-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
