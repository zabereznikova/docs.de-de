---
title: OneWayBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a43707f25a9ee1beb1ce7adac36a2c4a55cab6d6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="onewaybindingelement"></a><span data-ttu-id="77e2d-102">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="77e2d-102">OneWayBindingElement</span></span>
<span data-ttu-id="77e2d-103">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="77e2d-103">OneWayBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77e2d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="77e2d-104">Syntax</span></span>  
  
```  
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="77e2d-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="77e2d-105">Methods</span></span>  
 <span data-ttu-id="77e2d-106">Die Klasse OneWayBindingElement definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="77e2d-106">The OneWayBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="77e2d-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="77e2d-107">Properties</span></span>  
 <span data-ttu-id="77e2d-108">Die Klasse OneWayBindingElement verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="77e2d-108">The OneWayBindingElement class has the following properties:</span></span>  
  
### <a name="channelpoolsettings"></a><span data-ttu-id="77e2d-109">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="77e2d-109">ChannelPoolSettings</span></span>  
 <span data-ttu-id="77e2d-110">Datentyp: ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="77e2d-110">Data type: ChannelPoolSettings</span></span>  
  
 <span data-ttu-id="77e2d-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="77e2d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="77e2d-112">Die Kanalpool-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="77e2d-112">The channel pool settings.</span></span>  
  
### <a name="maxacceptedchannels"></a><span data-ttu-id="77e2d-113">MaxAcceptedChannels</span><span class="sxs-lookup"><span data-stu-id="77e2d-113">MaxAcceptedChannels</span></span>  
 <span data-ttu-id="77e2d-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="77e2d-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="77e2d-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="77e2d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="77e2d-116">Die maximale Anzahl von akzeptierten Kanälen.</span><span class="sxs-lookup"><span data-stu-id="77e2d-116">The maximum number of accepted channels.</span></span>  
  
### <a name="packetroutable"></a><span data-ttu-id="77e2d-117">PacketRoutable</span><span class="sxs-lookup"><span data-stu-id="77e2d-117">PacketRoutable</span></span>  
 <span data-ttu-id="77e2d-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="77e2d-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="77e2d-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="77e2d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="77e2d-120">Ein Wert, der angibt, ob das Paket geroutet werden kann.</span><span class="sxs-lookup"><span data-stu-id="77e2d-120">A value that indicates whether the packet is routable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77e2d-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="77e2d-121">Requirements</span></span>  
  
|<span data-ttu-id="77e2d-122">MOF</span><span class="sxs-lookup"><span data-stu-id="77e2d-122">MOF</span></span>|<span data-ttu-id="77e2d-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="77e2d-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="77e2d-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="77e2d-124">Namespace</span></span>|<span data-ttu-id="77e2d-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="77e2d-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="77e2d-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77e2d-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>
