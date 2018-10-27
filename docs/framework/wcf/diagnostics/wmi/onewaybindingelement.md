---
title: OneWayBindingElement
ms.date: 03/30/2017
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
ms.openlocfilehash: 34220a3651819978f5f597fdc67d54630ec5e059
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50049294"
---
# <a name="onewaybindingelement"></a><span data-ttu-id="b12ad-102">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="b12ad-102">OneWayBindingElement</span></span>
<span data-ttu-id="b12ad-103">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="b12ad-103">OneWayBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b12ad-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b12ad-104">Syntax</span></span>  
  
```csharp
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b12ad-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="b12ad-105">Methods</span></span>  
 <span data-ttu-id="b12ad-106">Die Klasse OneWayBindingElement definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="b12ad-106">The OneWayBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b12ad-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b12ad-107">Properties</span></span>  
 <span data-ttu-id="b12ad-108">Die Klasse OneWayBindingElement verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="b12ad-108">The OneWayBindingElement class has the following properties:</span></span>  
  
### <a name="channelpoolsettings"></a><span data-ttu-id="b12ad-109">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="b12ad-109">ChannelPoolSettings</span></span>  
 <span data-ttu-id="b12ad-110">Datentyp: ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="b12ad-110">Data type: ChannelPoolSettings</span></span>  
  
 <span data-ttu-id="b12ad-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b12ad-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b12ad-112">Die Kanalpool-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="b12ad-112">The channel pool settings.</span></span>  
  
### <a name="maxacceptedchannels"></a><span data-ttu-id="b12ad-113">MaxAcceptedChannels</span><span class="sxs-lookup"><span data-stu-id="b12ad-113">MaxAcceptedChannels</span></span>  
 <span data-ttu-id="b12ad-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="b12ad-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="b12ad-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b12ad-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b12ad-116">Die maximale Anzahl von akzeptierten Kanälen.</span><span class="sxs-lookup"><span data-stu-id="b12ad-116">The maximum number of accepted channels.</span></span>  
  
### <a name="packetroutable"></a><span data-ttu-id="b12ad-117">PacketRoutable</span><span class="sxs-lookup"><span data-stu-id="b12ad-117">PacketRoutable</span></span>  
 <span data-ttu-id="b12ad-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="b12ad-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="b12ad-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b12ad-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b12ad-120">Ein Wert, der angibt, ob das Paket geroutet werden kann.</span><span class="sxs-lookup"><span data-stu-id="b12ad-120">A value that indicates whether the packet is routable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b12ad-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b12ad-121">Requirements</span></span>  
  
|<span data-ttu-id="b12ad-122">MOF</span><span class="sxs-lookup"><span data-stu-id="b12ad-122">MOF</span></span>|<span data-ttu-id="b12ad-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="b12ad-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b12ad-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="b12ad-124">Namespace</span></span>|<span data-ttu-id="b12ad-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b12ad-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b12ad-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b12ad-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>
