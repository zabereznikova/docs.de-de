---
title: ChannelPoolSettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e97e934673efbc6d0f72751c7cb1de6fba84a141
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="channelpoolsettings"></a><span data-ttu-id="f18bc-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="f18bc-102">ChannelPoolSettings</span></span>
<span data-ttu-id="f18bc-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="f18bc-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f18bc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f18bc-104">Syntax</span></span>  
  
```  
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f18bc-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="f18bc-105">Methods</span></span>  
 <span data-ttu-id="f18bc-106">Die ChannelPoolSettings-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="f18bc-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f18bc-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f18bc-107">Properties</span></span>  
 <span data-ttu-id="f18bc-108">Die ChannelPoolSettings-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="f18bc-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="f18bc-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="f18bc-109">IdleTimeout</span></span>  
 <span data-ttu-id="f18bc-110">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="f18bc-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="f18bc-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f18bc-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f18bc-112">Die maximale Zeit, während der sich die Verbindung im Leerlauf befinden darf, bevor sie getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="f18bc-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="f18bc-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="f18bc-113">LeaseTimeout</span></span>  
 <span data-ttu-id="f18bc-114">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="f18bc-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="f18bc-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f18bc-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f18bc-116">Die maximale Zeit für die Ausführung eines Leasevorgangs, bevor ein Timeout auftritt.</span><span class="sxs-lookup"><span data-stu-id="f18bc-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="f18bc-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="f18bc-117">MaxOutboundChannelsPerEndpoint</span></span>  
 <span data-ttu-id="f18bc-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="f18bc-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="f18bc-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f18bc-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f18bc-120">Die maximale Anzahl von ausgehenden Kanälen pro Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="f18bc-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f18bc-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f18bc-121">Requirements</span></span>  
  
|<span data-ttu-id="f18bc-122">MOF</span><span class="sxs-lookup"><span data-stu-id="f18bc-122">MOF</span></span>|<span data-ttu-id="f18bc-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f18bc-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f18bc-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="f18bc-124">Namespace</span></span>|<span data-ttu-id="f18bc-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f18bc-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f18bc-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f18bc-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelPoolSettings>
