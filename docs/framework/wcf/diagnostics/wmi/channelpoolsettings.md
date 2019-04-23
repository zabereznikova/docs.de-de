---
title: ChannelPoolSettings
ms.date: 03/30/2017
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
ms.openlocfilehash: 8900af77d0d385bb68b4b85e1d15be57bb7a8d14
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "59972861"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="b08f7-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="b08f7-102">ChannelPoolSettings</span></span>
<span data-ttu-id="b08f7-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="b08f7-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b08f7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b08f7-104">Syntax</span></span>  
  
```csharp
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b08f7-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="b08f7-105">Methods</span></span>  
 <span data-ttu-id="b08f7-106">Die ChannelPoolSettings-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="b08f7-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b08f7-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b08f7-107">Properties</span></span>  
 <span data-ttu-id="b08f7-108">Die ChannelPoolSettings-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="b08f7-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="b08f7-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="b08f7-109">IdleTimeout</span></span>  
 <span data-ttu-id="b08f7-110">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="b08f7-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="b08f7-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b08f7-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b08f7-112">Die maximale Zeit, während der sich die Verbindung im Leerlauf befinden darf, bevor sie getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="b08f7-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="b08f7-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="b08f7-113">LeaseTimeout</span></span>  
 <span data-ttu-id="b08f7-114">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="b08f7-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="b08f7-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b08f7-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b08f7-116">Die maximale Zeit für die Ausführung eines Leasevorgangs, bevor ein Timeout auftritt.</span><span class="sxs-lookup"><span data-stu-id="b08f7-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="b08f7-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="b08f7-117">MaxOutboundChannelsPerEndpoint</span></span>  
 <span data-ttu-id="b08f7-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="b08f7-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="b08f7-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b08f7-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b08f7-120">Die maximale Anzahl von ausgehenden Kanälen pro Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="b08f7-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b08f7-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b08f7-121">Requirements</span></span>  
  
|<span data-ttu-id="b08f7-122">MOF</span><span class="sxs-lookup"><span data-stu-id="b08f7-122">MOF</span></span>|<span data-ttu-id="b08f7-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="b08f7-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b08f7-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="b08f7-124">Namespace</span></span>|<span data-ttu-id="b08f7-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b08f7-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b08f7-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b08f7-126">See also</span></span>

- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
