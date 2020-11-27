---
title: 209 - MessageInspectorBeforeSendInvoked
ms.date: 03/30/2017
ms.assetid: 7d710875-fb77-4463-978b-bc86d59d84cd
ms.openlocfilehash: 50a9424f445781cac70d7d7fde58beea10231cfa
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267753"
---
# <a name="209---messageinspectorbeforesendinvoked"></a><span data-ttu-id="eb9cc-102">209 - MessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="eb9cc-102">209 - MessageInspectorBeforeSendInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="eb9cc-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="eb9cc-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eb9cc-104">id</span><span class="sxs-lookup"><span data-stu-id="eb9cc-104">ID</span></span>|<span data-ttu-id="eb9cc-105">209</span><span class="sxs-lookup"><span data-stu-id="eb9cc-105">209</span></span>|  
|<span data-ttu-id="eb9cc-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="eb9cc-106">Keywords</span></span>|<span data-ttu-id="eb9cc-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="eb9cc-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="eb9cc-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="eb9cc-108">Level</span></span>|<span data-ttu-id="eb9cc-109">Information</span><span class="sxs-lookup"><span data-stu-id="eb9cc-109">Information</span></span>|  
|<span data-ttu-id="eb9cc-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="eb9cc-110">Channel</span></span>|<span data-ttu-id="eb9cc-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="eb9cc-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="eb9cc-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="eb9cc-112">Description</span></span>  

 <span data-ttu-id="eb9cc-113">Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `BeforeSend`-Methode auf einem Nachrichteninspektor aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="eb9cc-113">This event is emitted after the Service Model has invoked the `BeforeSend` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="eb9cc-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="eb9cc-114">Message</span></span>  

 <span data-ttu-id="eb9cc-115">Der Verteiler hat 'BeforeSendRequest' auf einem MessageInspector vom Typ '%1' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="eb9cc-115">The Dispatcher invoked 'BeforeSendRequest' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="eb9cc-116">Details</span><span class="sxs-lookup"><span data-stu-id="eb9cc-116">Details</span></span>  
  
|<span data-ttu-id="eb9cc-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="eb9cc-117">Data Item Name</span></span>|<span data-ttu-id="eb9cc-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="eb9cc-118">Data Item Type</span></span>|<span data-ttu-id="eb9cc-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="eb9cc-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="eb9cc-120">TypName</span><span class="sxs-lookup"><span data-stu-id="eb9cc-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="eb9cc-121">Der CLR-FullName des aufgerufenen `MessageInspector`-Typs.</span><span class="sxs-lookup"><span data-stu-id="eb9cc-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="eb9cc-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="eb9cc-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="eb9cc-123">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="eb9cc-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="eb9cc-124">Sein Format ist als "Website Name Anwendungspfad für virtuelle Computer&#124;virtuellen Dienst Pfad&#124;Dienst Name '" definiert.</span><span class="sxs-lookup"><span data-stu-id="eb9cc-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="eb9cc-125">Beispiel: "Default Web Site/calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="eb9cc-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="eb9cc-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="eb9cc-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="eb9cc-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="eb9cc-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
