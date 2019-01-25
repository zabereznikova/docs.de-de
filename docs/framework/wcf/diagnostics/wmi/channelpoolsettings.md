---
title: ChannelPoolSettings
ms.date: 03/30/2017
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
ms.openlocfilehash: 4a3e45140765f99f4a30b77fc9d02b167601b50b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54591477"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="19c9d-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="19c9d-102">ChannelPoolSettings</span></span>
<span data-ttu-id="19c9d-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="19c9d-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19c9d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="19c9d-104">Syntax</span></span>  
  
```csharp
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="19c9d-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="19c9d-105">Methods</span></span>  
 <span data-ttu-id="19c9d-106">Die ChannelPoolSettings-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="19c9d-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="19c9d-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="19c9d-107">Properties</span></span>  
 <span data-ttu-id="19c9d-108">Die ChannelPoolSettings-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="19c9d-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="19c9d-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="19c9d-109">IdleTimeout</span></span>  
 <span data-ttu-id="19c9d-110">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="19c9d-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="19c9d-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19c9d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19c9d-112">Die maximale Zeit, während der sich die Verbindung im Leerlauf befinden darf, bevor sie getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="19c9d-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="19c9d-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="19c9d-113">LeaseTimeout</span></span>  
 <span data-ttu-id="19c9d-114">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="19c9d-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="19c9d-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19c9d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19c9d-116">Die maximale Zeit für die Ausführung eines Leasevorgangs, bevor ein Timeout auftritt.</span><span class="sxs-lookup"><span data-stu-id="19c9d-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="19c9d-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="19c9d-117">MaxOutboundChannelsPerEndpoint</span></span>  
 <span data-ttu-id="19c9d-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="19c9d-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="19c9d-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19c9d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19c9d-120">Die maximale Anzahl von ausgehenden Kanälen pro Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="19c9d-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19c9d-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="19c9d-121">Requirements</span></span>  
  
|<span data-ttu-id="19c9d-122">MOF</span><span class="sxs-lookup"><span data-stu-id="19c9d-122">MOF</span></span>|<span data-ttu-id="19c9d-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="19c9d-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="19c9d-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="19c9d-124">Namespace</span></span>|<span data-ttu-id="19c9d-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="19c9d-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="19c9d-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="19c9d-126">See also</span></span>
- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
