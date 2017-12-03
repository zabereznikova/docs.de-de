---
title: 499 - TransferEmitted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 07a26434-a7a0-40fc-b5d0-3520a04328ae
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1a0bbe31095a59be4b091de6974ae0173753e240
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="499---transferemitted"></a><span data-ttu-id="3ac18-102">499 - TransferEmitted</span><span class="sxs-lookup"><span data-stu-id="3ac18-102">499 - TransferEmitted</span></span>
## <a name="properties"></a><span data-ttu-id="3ac18-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="3ac18-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3ac18-104">ID</span><span class="sxs-lookup"><span data-stu-id="3ac18-104">ID</span></span>|<span data-ttu-id="3ac18-105">499</span><span class="sxs-lookup"><span data-stu-id="3ac18-105">499</span></span>|  
|<span data-ttu-id="3ac18-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="3ac18-106">Keywords</span></span>|<span data-ttu-id="3ac18-107">Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span><span class="sxs-lookup"><span data-stu-id="3ac18-107">Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span></span>|  
|<span data-ttu-id="3ac18-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="3ac18-108">Level</span></span>|<span data-ttu-id="3ac18-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="3ac18-109">LogAlways</span></span>|  
|<span data-ttu-id="3ac18-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="3ac18-110">Channel</span></span>|<span data-ttu-id="3ac18-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="3ac18-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3ac18-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3ac18-112">Description</span></span>  
 <span data-ttu-id="3ac18-113">Dieses Ereignis wird ausgegeben, wenn das Übertragungsereignis stattfindet.</span><span class="sxs-lookup"><span data-stu-id="3ac18-113">This event is emitted when the transfer event takes place.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3ac18-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="3ac18-114">Message</span></span>  
 <span data-ttu-id="3ac18-115">Übertragungsereignis ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="3ac18-115">Transfer event emitted.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3ac18-116">Details</span><span class="sxs-lookup"><span data-stu-id="3ac18-116">Details</span></span>  
  
|<span data-ttu-id="3ac18-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="3ac18-117">Data Item Name</span></span>|<span data-ttu-id="3ac18-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="3ac18-118">Data Item Type</span></span>|<span data-ttu-id="3ac18-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3ac18-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3ac18-120">HostReference</span><span class="sxs-lookup"><span data-stu-id="3ac18-120">HostReference</span></span>|`xs:string`|<span data-ttu-id="3ac18-121">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="3ac18-121">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="3ac18-122">Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="3ac18-122">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="3ac18-123">Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="3ac18-123">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="3ac18-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3ac18-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="3ac18-125">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="3ac18-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
