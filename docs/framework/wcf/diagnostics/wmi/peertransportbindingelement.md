---
title: PeerTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 193000acf2f3c8a0eddb2552559ee40a0f5fced9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="peertransportbindingelement"></a><span data-ttu-id="133d2-102">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="133d2-102">PeerTransportBindingElement</span></span>
<span data-ttu-id="133d2-103">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="133d2-103">PeerTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="133d2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="133d2-104">Syntax</span></span>  
  
```  
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="133d2-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="133d2-105">Methods</span></span>  
 <span data-ttu-id="133d2-106">Von der Klasse PeerTransportBindingElement werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="133d2-106">The PeerTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="133d2-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="133d2-107">Properties</span></span>  
 <span data-ttu-id="133d2-108">Die Klasse PeerTransportBindingElement verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="133d2-108">The PeerTransportBindingElement class has the following properties:</span></span>  
  
### <a name="listenipaddress"></a><span data-ttu-id="133d2-109">ListenIPAddress</span><span class="sxs-lookup"><span data-stu-id="133d2-109">ListenIPAddress</span></span>  
 <span data-ttu-id="133d2-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="133d2-110">Data type: string</span></span>  
  
 <span data-ttu-id="133d2-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="133d2-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="133d2-112">Die IP-Adresse, auf der der Peerknoten Meldungen abhört.</span><span class="sxs-lookup"><span data-stu-id="133d2-112">The IP address on which the peer node listens for messages.</span></span>  
  
### <a name="port"></a><span data-ttu-id="133d2-113">Port</span><span class="sxs-lookup"><span data-stu-id="133d2-113">Port</span></span>  
 <span data-ttu-id="133d2-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="133d2-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="133d2-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="133d2-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="133d2-116">Der Netzwerkschnittstellenanschluss, auf dem diese Bindung Peerchannel-Meldungen verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="133d2-116">The network interface port on which this binding processes peer channel messages.</span></span>  
  
### <a name="security"></a><span data-ttu-id="133d2-117">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="133d2-117">Security</span></span>  
 <span data-ttu-id="133d2-118">Datentyp: PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="133d2-118">Data type: PeerSecuritySettings</span></span>  
  
 <span data-ttu-id="133d2-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="133d2-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="133d2-120">Peertransportsicherheitseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="133d2-120">Peer transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="133d2-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="133d2-121">Requirements</span></span>  
  
|<span data-ttu-id="133d2-122">MOF</span><span class="sxs-lookup"><span data-stu-id="133d2-122">MOF</span></span>|<span data-ttu-id="133d2-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="133d2-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="133d2-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="133d2-124">Namespace</span></span>|<span data-ttu-id="133d2-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="133d2-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="133d2-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="133d2-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
