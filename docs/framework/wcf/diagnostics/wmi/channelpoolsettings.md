---
title: ChannelPoolSettings
ms.date: 03/30/2017
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
ms.openlocfilehash: 3dcc1f3b27d93d5641a4bb2d8082aa3fa88882dc
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274217"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="6de86-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="6de86-102">ChannelPoolSettings</span></span>

<span data-ttu-id="6de86-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="6de86-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6de86-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6de86-104">Syntax</span></span>  
  
```csharp
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="6de86-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="6de86-105">Methods</span></span>  

 <span data-ttu-id="6de86-106">Die ChannelPoolSettings-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="6de86-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6de86-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="6de86-107">Properties</span></span>  

 <span data-ttu-id="6de86-108">Die ChannelPoolSettings-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="6de86-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="6de86-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="6de86-109">IdleTimeout</span></span>  

 <span data-ttu-id="6de86-110">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="6de86-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="6de86-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6de86-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6de86-112">Die maximale Zeit, während der sich die Verbindung im Leerlauf befinden darf, bevor sie getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="6de86-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="6de86-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="6de86-113">LeaseTimeout</span></span>  

 <span data-ttu-id="6de86-114">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="6de86-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="6de86-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6de86-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6de86-116">Die maximale Zeit für die Ausführung eines Leasevorgangs, bevor ein Timeout auftritt.</span><span class="sxs-lookup"><span data-stu-id="6de86-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="6de86-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="6de86-117">MaxOutboundChannelsPerEndpoint</span></span>  

 <span data-ttu-id="6de86-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="6de86-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="6de86-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6de86-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6de86-120">Die maximale Anzahl von ausgehenden Kanälen pro Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="6de86-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6de86-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6de86-121">Requirements</span></span>  
  
|<span data-ttu-id="6de86-122">MOF</span><span class="sxs-lookup"><span data-stu-id="6de86-122">MOF</span></span>|<span data-ttu-id="6de86-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="6de86-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6de86-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="6de86-124">Namespace</span></span>|<span data-ttu-id="6de86-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6de86-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6de86-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6de86-126">See also</span></span>

- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
