---
title: 499 - TransferEmitted
ms.date: 03/30/2017
ms.assetid: 07a26434-a7a0-40fc-b5d0-3520a04328ae
ms.openlocfilehash: dc47aa36b5a409c89aaf7963ce51f11cdf84b0fc
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96247576"
---
# <a name="499---transferemitted"></a><span data-ttu-id="9e946-102">499 - TransferEmitted</span><span class="sxs-lookup"><span data-stu-id="9e946-102">499 - TransferEmitted</span></span>

## <a name="properties"></a><span data-ttu-id="9e946-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9e946-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9e946-104">id</span><span class="sxs-lookup"><span data-stu-id="9e946-104">ID</span></span>|<span data-ttu-id="9e946-105">499</span><span class="sxs-lookup"><span data-stu-id="9e946-105">499</span></span>|  
|<span data-ttu-id="9e946-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="9e946-106">Keywords</span></span>|<span data-ttu-id="9e946-107">Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span><span class="sxs-lookup"><span data-stu-id="9e946-107">Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span></span>|  
|<span data-ttu-id="9e946-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="9e946-108">Level</span></span>|<span data-ttu-id="9e946-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="9e946-109">LogAlways</span></span>|  
|<span data-ttu-id="9e946-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="9e946-110">Channel</span></span>|<span data-ttu-id="9e946-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="9e946-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9e946-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9e946-112">Description</span></span>  

 <span data-ttu-id="9e946-113">Dieses Ereignis wird ausgegeben, wenn das Übertragungsereignis stattfindet.</span><span class="sxs-lookup"><span data-stu-id="9e946-113">This event is emitted when the transfer event takes place.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9e946-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="9e946-114">Message</span></span>  

 <span data-ttu-id="9e946-115">Übertragungsereignis ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="9e946-115">Transfer event emitted.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9e946-116">Details</span><span class="sxs-lookup"><span data-stu-id="9e946-116">Details</span></span>  
  
|<span data-ttu-id="9e946-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="9e946-117">Data Item Name</span></span>|<span data-ttu-id="9e946-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="9e946-118">Data Item Type</span></span>|<span data-ttu-id="9e946-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9e946-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9e946-120">HostReference</span><span class="sxs-lookup"><span data-stu-id="9e946-120">HostReference</span></span>|`xs:string`|<span data-ttu-id="9e946-121">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="9e946-121">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="9e946-122">Sein Format ist als "Website Name Anwendungspfad für virtuelle Computer&#124;virtuellen Dienst Pfad&#124;Dienst Name '" definiert.</span><span class="sxs-lookup"><span data-stu-id="9e946-122">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="9e946-123">Beispiel: "Default Web Site/calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="9e946-123">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="9e946-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9e946-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="9e946-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="9e946-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
