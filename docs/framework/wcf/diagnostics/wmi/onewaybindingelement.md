---
title: OneWayBindingElement
ms.date: 03/30/2017
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
ms.openlocfilehash: ee7cfed20234175ba54dd25dbbbab4615c1ed7af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485744"
---
# <a name="onewaybindingelement"></a><span data-ttu-id="63835-102">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="63835-102">OneWayBindingElement</span></span>
<span data-ttu-id="63835-103">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="63835-103">OneWayBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63835-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="63835-104">Syntax</span></span>  
  
```  
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="63835-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="63835-105">Methods</span></span>  
 <span data-ttu-id="63835-106">Die Klasse OneWayBindingElement definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="63835-106">The OneWayBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="63835-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="63835-107">Properties</span></span>  
 <span data-ttu-id="63835-108">Die Klasse OneWayBindingElement verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="63835-108">The OneWayBindingElement class has the following properties:</span></span>  
  
### <a name="channelpoolsettings"></a><span data-ttu-id="63835-109">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="63835-109">ChannelPoolSettings</span></span>  
 <span data-ttu-id="63835-110">Datentyp: ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="63835-110">Data type: ChannelPoolSettings</span></span>  
  
 <span data-ttu-id="63835-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="63835-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="63835-112">Die Kanalpool-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="63835-112">The channel pool settings.</span></span>  
  
### <a name="maxacceptedchannels"></a><span data-ttu-id="63835-113">MaxAcceptedChannels</span><span class="sxs-lookup"><span data-stu-id="63835-113">MaxAcceptedChannels</span></span>  
 <span data-ttu-id="63835-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="63835-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="63835-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="63835-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="63835-116">Die maximale Anzahl von akzeptierten Kanälen.</span><span class="sxs-lookup"><span data-stu-id="63835-116">The maximum number of accepted channels.</span></span>  
  
### <a name="packetroutable"></a><span data-ttu-id="63835-117">PacketRoutable</span><span class="sxs-lookup"><span data-stu-id="63835-117">PacketRoutable</span></span>  
 <span data-ttu-id="63835-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="63835-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="63835-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="63835-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="63835-120">Ein Wert, der angibt, ob das Paket geroutet werden kann.</span><span class="sxs-lookup"><span data-stu-id="63835-120">A value that indicates whether the packet is routable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63835-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="63835-121">Requirements</span></span>  
  
|<span data-ttu-id="63835-122">MOF</span><span class="sxs-lookup"><span data-stu-id="63835-122">MOF</span></span>|<span data-ttu-id="63835-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="63835-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="63835-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="63835-124">Namespace</span></span>|<span data-ttu-id="63835-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="63835-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="63835-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63835-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>
