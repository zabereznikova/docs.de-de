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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: abaacfb6541d41019a8d0cd6df53913c6b7911f2
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="onewaybindingelement"></a><span data-ttu-id="c23f6-102">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="c23f6-102">OneWayBindingElement</span></span>
<span data-ttu-id="c23f6-103">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="c23f6-103">OneWayBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c23f6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c23f6-104">Syntax</span></span>  
  
```  
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c23f6-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="c23f6-105">Methods</span></span>  
 <span data-ttu-id="c23f6-106">Die Klasse OneWayBindingElement definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="c23f6-106">The OneWayBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c23f6-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="c23f6-107">Properties</span></span>  
 <span data-ttu-id="c23f6-108">Die Klasse OneWayBindingElement verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="c23f6-108">The OneWayBindingElement class has the following properties:</span></span>  
  
### <a name="channelpoolsettings"></a><span data-ttu-id="c23f6-109">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="c23f6-109">ChannelPoolSettings</span></span>  
 <span data-ttu-id="c23f6-110">Datentyp: ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="c23f6-110">Data type: ChannelPoolSettings</span></span>  
  
 <span data-ttu-id="c23f6-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="c23f6-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c23f6-112">Die Kanalpool-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="c23f6-112">The channel pool settings.</span></span>  
  
### <a name="maxacceptedchannels"></a><span data-ttu-id="c23f6-113">MaxAcceptedChannels</span><span class="sxs-lookup"><span data-stu-id="c23f6-113">MaxAcceptedChannels</span></span>  
 <span data-ttu-id="c23f6-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="c23f6-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="c23f6-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="c23f6-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c23f6-116">Die maximale Anzahl von akzeptierten Kanälen.</span><span class="sxs-lookup"><span data-stu-id="c23f6-116">The maximum number of accepted channels.</span></span>  
  
### <a name="packetroutable"></a><span data-ttu-id="c23f6-117">PacketRoutable</span><span class="sxs-lookup"><span data-stu-id="c23f6-117">PacketRoutable</span></span>  
 <span data-ttu-id="c23f6-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="c23f6-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="c23f6-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="c23f6-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c23f6-120">Ein Wert, der angibt, ob das Paket geroutet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c23f6-120">A value that indicates whether the packet is routable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c23f6-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c23f6-121">Requirements</span></span>  
  
|<span data-ttu-id="c23f6-122">MOF</span><span class="sxs-lookup"><span data-stu-id="c23f6-122">MOF</span></span>|<span data-ttu-id="c23f6-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="c23f6-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c23f6-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="c23f6-124">Namespace</span></span>|<span data-ttu-id="c23f6-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c23f6-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c23f6-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c23f6-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>
