---
title: OneWayBindingElement
ms.date: 03/30/2017
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
ms.openlocfilehash: 34220a3651819978f5f597fdc67d54630ec5e059
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50195813"
---
# <a name="onewaybindingelement"></a><span data-ttu-id="c514d-102">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="c514d-102">OneWayBindingElement</span></span>
<span data-ttu-id="c514d-103">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="c514d-103">OneWayBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c514d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c514d-104">Syntax</span></span>  
  
```csharp
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c514d-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="c514d-105">Methods</span></span>  
 <span data-ttu-id="c514d-106">Die Klasse OneWayBindingElement definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="c514d-106">The OneWayBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c514d-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="c514d-107">Properties</span></span>  
 <span data-ttu-id="c514d-108">Die Klasse OneWayBindingElement verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="c514d-108">The OneWayBindingElement class has the following properties:</span></span>  
  
### <a name="channelpoolsettings"></a><span data-ttu-id="c514d-109">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="c514d-109">ChannelPoolSettings</span></span>  
 <span data-ttu-id="c514d-110">Datentyp: ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="c514d-110">Data type: ChannelPoolSettings</span></span>  
  
 <span data-ttu-id="c514d-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="c514d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c514d-112">Die Kanalpool-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="c514d-112">The channel pool settings.</span></span>  
  
### <a name="maxacceptedchannels"></a><span data-ttu-id="c514d-113">MaxAcceptedChannels</span><span class="sxs-lookup"><span data-stu-id="c514d-113">MaxAcceptedChannels</span></span>  
 <span data-ttu-id="c514d-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="c514d-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="c514d-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="c514d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c514d-116">Die maximale Anzahl von akzeptierten Kanälen.</span><span class="sxs-lookup"><span data-stu-id="c514d-116">The maximum number of accepted channels.</span></span>  
  
### <a name="packetroutable"></a><span data-ttu-id="c514d-117">PacketRoutable</span><span class="sxs-lookup"><span data-stu-id="c514d-117">PacketRoutable</span></span>  
 <span data-ttu-id="c514d-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="c514d-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="c514d-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="c514d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c514d-120">Ein Wert, der angibt, ob das Paket geroutet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c514d-120">A value that indicates whether the packet is routable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c514d-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c514d-121">Requirements</span></span>  
  
|<span data-ttu-id="c514d-122">MOF</span><span class="sxs-lookup"><span data-stu-id="c514d-122">MOF</span></span>|<span data-ttu-id="c514d-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="c514d-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c514d-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="c514d-124">Namespace</span></span>|<span data-ttu-id="c514d-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c514d-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c514d-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c514d-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>
