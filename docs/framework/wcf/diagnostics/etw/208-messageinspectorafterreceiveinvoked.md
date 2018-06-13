---
title: 208 - MessageInspectorAfterReceiveInvoked
ms.date: 03/30/2017
ms.assetid: dfb5f7b0-4346-4949-8104-351726b1f502
ms.openlocfilehash: 3499131fcb52f0a0ab6d0e78e165522b7092612f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458897"
---
# <a name="208---messageinspectorafterreceiveinvoked"></a><span data-ttu-id="f4009-102">208 - MessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="f4009-102">208 - MessageInspectorAfterReceiveInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="f4009-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f4009-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f4009-104">ID</span><span class="sxs-lookup"><span data-stu-id="f4009-104">ID</span></span>|<span data-ttu-id="f4009-105">208</span><span class="sxs-lookup"><span data-stu-id="f4009-105">208</span></span>|  
|<span data-ttu-id="f4009-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f4009-106">Keywords</span></span>|<span data-ttu-id="f4009-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f4009-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="f4009-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="f4009-108">Level</span></span>|<span data-ttu-id="f4009-109">Information</span><span class="sxs-lookup"><span data-stu-id="f4009-109">Information</span></span>|  
|<span data-ttu-id="f4009-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="f4009-110">Channel</span></span>|<span data-ttu-id="f4009-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="f4009-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f4009-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4009-112">Description</span></span>  
 <span data-ttu-id="f4009-113">Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `AfterReceive`-Methode auf einem Nachrichteninspektor aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="f4009-113">This event is emitted after the Service Model has invoked the `AfterReceive` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f4009-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="f4009-114">Message</span></span>  
 <span data-ttu-id="f4009-115">Der Verteiler hat 'AfterReceiveReply' auf einem MessageInspector vom Typ '%1' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="f4009-115">The Dispatcher invoked 'AfterReceiveReply' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f4009-116">Details</span><span class="sxs-lookup"><span data-stu-id="f4009-116">Details</span></span>  
  
|<span data-ttu-id="f4009-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="f4009-117">Data Item Name</span></span>|<span data-ttu-id="f4009-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="f4009-118">Data Item Type</span></span>|<span data-ttu-id="f4009-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4009-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f4009-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="f4009-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="f4009-121">Der CLR-FullName des aufgerufenen `MessageInspector`-Typs.</span><span class="sxs-lookup"><span data-stu-id="f4009-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="f4009-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="f4009-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="f4009-123">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="f4009-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="f4009-124">Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="f4009-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="f4009-125">Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="f4009-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="f4009-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f4009-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f4009-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f4009-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
