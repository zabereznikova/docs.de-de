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
ms.workload: dotnet
ms.openlocfilehash: 3995b517b27a5565f7fcb9c11da27c9e1bb40887
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="channelpoolsettings"></a><span data-ttu-id="32acc-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="32acc-102">ChannelPoolSettings</span></span>
<span data-ttu-id="32acc-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="32acc-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32acc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="32acc-104">Syntax</span></span>  
  
```  
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="32acc-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="32acc-105">Methods</span></span>  
 <span data-ttu-id="32acc-106">Die ChannelPoolSettings-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="32acc-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="32acc-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="32acc-107">Properties</span></span>  
 <span data-ttu-id="32acc-108">Die ChannelPoolSettings-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="32acc-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="32acc-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="32acc-109">IdleTimeout</span></span>  
 <span data-ttu-id="32acc-110">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="32acc-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="32acc-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="32acc-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="32acc-112">Die maximale Zeit, während der sich die Verbindung im Leerlauf befinden darf, bevor sie getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="32acc-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="32acc-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="32acc-113">LeaseTimeout</span></span>  
 <span data-ttu-id="32acc-114">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="32acc-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="32acc-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="32acc-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="32acc-116">Die maximale Zeit für die Ausführung eines Leasevorgangs, bevor ein Timeout auftritt.</span><span class="sxs-lookup"><span data-stu-id="32acc-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="32acc-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="32acc-117">MaxOutboundChannelsPerEndpoint</span></span>  
 <span data-ttu-id="32acc-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="32acc-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="32acc-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="32acc-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="32acc-120">Die maximale Anzahl von ausgehenden Kanälen pro Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="32acc-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32acc-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="32acc-121">Requirements</span></span>  
  
|<span data-ttu-id="32acc-122">MOF</span><span class="sxs-lookup"><span data-stu-id="32acc-122">MOF</span></span>|<span data-ttu-id="32acc-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="32acc-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="32acc-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="32acc-124">Namespace</span></span>|<span data-ttu-id="32acc-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="32acc-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="32acc-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32acc-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelPoolSettings>
