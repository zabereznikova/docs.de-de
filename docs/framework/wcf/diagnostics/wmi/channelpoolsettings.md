---
title: ChannelPoolSettings
ms.date: 03/30/2017
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
ms.openlocfilehash: 8900af77d0d385bb68b4b85e1d15be57bb7a8d14
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59131910"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="0e35e-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="0e35e-102">ChannelPoolSettings</span></span>
<span data-ttu-id="0e35e-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="0e35e-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e35e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0e35e-104">Syntax</span></span>  
  
```csharp
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="0e35e-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="0e35e-105">Methods</span></span>  
 <span data-ttu-id="0e35e-106">Die ChannelPoolSettings-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="0e35e-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="0e35e-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="0e35e-107">Properties</span></span>  
 <span data-ttu-id="0e35e-108">Die ChannelPoolSettings-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="0e35e-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="0e35e-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="0e35e-109">IdleTimeout</span></span>  
 <span data-ttu-id="0e35e-110">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="0e35e-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="0e35e-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0e35e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0e35e-112">Die maximale Zeit, während der sich die Verbindung im Leerlauf befinden darf, bevor sie getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="0e35e-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="0e35e-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="0e35e-113">LeaseTimeout</span></span>  
 <span data-ttu-id="0e35e-114">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="0e35e-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="0e35e-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0e35e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0e35e-116">Die maximale Zeit für die Ausführung eines Leasevorgangs, bevor ein Timeout auftritt.</span><span class="sxs-lookup"><span data-stu-id="0e35e-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="0e35e-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="0e35e-117">MaxOutboundChannelsPerEndpoint</span></span>  
 <span data-ttu-id="0e35e-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="0e35e-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="0e35e-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0e35e-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0e35e-120">Die maximale Anzahl von ausgehenden Kanälen pro Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="0e35e-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e35e-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0e35e-121">Requirements</span></span>  
  
|<span data-ttu-id="0e35e-122">MOF</span><span class="sxs-lookup"><span data-stu-id="0e35e-122">MOF</span></span>|<span data-ttu-id="0e35e-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="0e35e-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="0e35e-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="0e35e-124">Namespace</span></span>|<span data-ttu-id="0e35e-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0e35e-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0e35e-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e35e-126">See also</span></span>

- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
