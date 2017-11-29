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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0a56616e97526b2d410d18d97dc1391c6fc32cc3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="channelpoolsettings"></a><span data-ttu-id="1eaa3-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="1eaa3-102">ChannelPoolSettings</span></span>
<span data-ttu-id="1eaa3-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="1eaa3-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1eaa3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1eaa3-104">Syntax</span></span>  
  
```  
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="1eaa3-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="1eaa3-105">Methods</span></span>  
 <span data-ttu-id="1eaa3-106">Die ChannelPoolSettings-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="1eaa3-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1eaa3-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1eaa3-107">Properties</span></span>  
 <span data-ttu-id="1eaa3-108">Die ChannelPoolSettings-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="1eaa3-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="1eaa3-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="1eaa3-109">IdleTimeout</span></span>  
 <span data-ttu-id="1eaa3-110">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="1eaa3-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="1eaa3-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="1eaa3-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1eaa3-112">Die maximale Zeit, während der sich die Verbindung im Leerlauf befinden darf, bevor sie getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="1eaa3-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="1eaa3-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="1eaa3-113">LeaseTimeout</span></span>  
 <span data-ttu-id="1eaa3-114">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="1eaa3-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="1eaa3-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="1eaa3-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1eaa3-116">Die maximale Zeit für die Ausführung eines Leasevorgangs, bevor ein Timeout auftritt.</span><span class="sxs-lookup"><span data-stu-id="1eaa3-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="1eaa3-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="1eaa3-117">MaxOutboundChannelsPerEndpoint</span></span>  
 <span data-ttu-id="1eaa3-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="1eaa3-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="1eaa3-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="1eaa3-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1eaa3-120">Die maximale Anzahl von ausgehenden Kanälen pro Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="1eaa3-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1eaa3-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1eaa3-121">Requirements</span></span>  
  
|<span data-ttu-id="1eaa3-122">MOF</span><span class="sxs-lookup"><span data-stu-id="1eaa3-122">MOF</span></span>|<span data-ttu-id="1eaa3-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="1eaa3-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1eaa3-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="1eaa3-124">Namespace</span></span>|<span data-ttu-id="1eaa3-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1eaa3-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1eaa3-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1eaa3-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelPoolSettings>
