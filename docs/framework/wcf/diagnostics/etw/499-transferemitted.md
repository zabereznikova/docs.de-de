---
title: 499 - TransferEmitted
ms.date: 03/30/2017
ms.assetid: 07a26434-a7a0-40fc-b5d0-3520a04328ae
ms.openlocfilehash: b1ade828ee6519288165e272e7d9f36fd6aca9ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774932"
---
# <a name="499---transferemitted"></a><span data-ttu-id="55290-102">499 - TransferEmitted</span><span class="sxs-lookup"><span data-stu-id="55290-102">499 - TransferEmitted</span></span>
## <a name="properties"></a><span data-ttu-id="55290-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="55290-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="55290-104">ID</span><span class="sxs-lookup"><span data-stu-id="55290-104">ID</span></span>|<span data-ttu-id="55290-105">499</span><span class="sxs-lookup"><span data-stu-id="55290-105">499</span></span>|  
|<span data-ttu-id="55290-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="55290-106">Keywords</span></span>|<span data-ttu-id="55290-107">Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span><span class="sxs-lookup"><span data-stu-id="55290-107">Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span></span>|  
|<span data-ttu-id="55290-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="55290-108">Level</span></span>|<span data-ttu-id="55290-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="55290-109">LogAlways</span></span>|  
|<span data-ttu-id="55290-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="55290-110">Channel</span></span>|<span data-ttu-id="55290-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="55290-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="55290-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55290-112">Description</span></span>  
 <span data-ttu-id="55290-113">Dieses Ereignis wird ausgegeben, wenn das Übertragungsereignis stattfindet.</span><span class="sxs-lookup"><span data-stu-id="55290-113">This event is emitted when the transfer event takes place.</span></span>  
  
## <a name="message"></a><span data-ttu-id="55290-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="55290-114">Message</span></span>  
 <span data-ttu-id="55290-115">Übertragungsereignis ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="55290-115">Transfer event emitted.</span></span>  
  
## <a name="details"></a><span data-ttu-id="55290-116">Details</span><span class="sxs-lookup"><span data-stu-id="55290-116">Details</span></span>  
  
|<span data-ttu-id="55290-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="55290-117">Data Item Name</span></span>|<span data-ttu-id="55290-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="55290-118">Data Item Type</span></span>|<span data-ttu-id="55290-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55290-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="55290-120">HostReference</span><span class="sxs-lookup"><span data-stu-id="55290-120">HostReference</span></span>|`xs:string`|<span data-ttu-id="55290-121">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="55290-121">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="55290-122">Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="55290-122">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="55290-123">Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="55290-123">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="55290-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="55290-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="55290-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="55290-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
