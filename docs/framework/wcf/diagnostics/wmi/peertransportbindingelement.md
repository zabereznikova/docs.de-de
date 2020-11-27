---
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: ae6a3448896cb206bce8867daf7104c3e484ecc8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269014"
---
# <a name="peertransportbindingelement"></a><span data-ttu-id="3e660-102">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="3e660-102">PeerTransportBindingElement</span></span>

<span data-ttu-id="3e660-103">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="3e660-103">PeerTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e660-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3e660-104">Syntax</span></span>  
  
```csharp
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3e660-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="3e660-105">Methods</span></span>  

 <span data-ttu-id="3e660-106">Von der Klasse PeerTransportBindingElement werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="3e660-106">The PeerTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3e660-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="3e660-107">Properties</span></span>  

 <span data-ttu-id="3e660-108">Die Klasse PeerTransportBindingElement verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="3e660-108">The PeerTransportBindingElement class has the following properties:</span></span>  
  
### <a name="listenipaddress"></a><span data-ttu-id="3e660-109">ListenIPAddress</span><span class="sxs-lookup"><span data-stu-id="3e660-109">ListenIPAddress</span></span>  

 <span data-ttu-id="3e660-110">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="3e660-110">Data type: string</span></span>  
  
 <span data-ttu-id="3e660-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="3e660-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3e660-112">Die IP-Adresse, auf der der Peerknoten Meldungen abhört.</span><span class="sxs-lookup"><span data-stu-id="3e660-112">The IP address on which the peer node listens for messages.</span></span>  
  
### <a name="port"></a><span data-ttu-id="3e660-113">Port</span><span class="sxs-lookup"><span data-stu-id="3e660-113">Port</span></span>  

 <span data-ttu-id="3e660-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="3e660-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="3e660-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="3e660-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3e660-116">Der Netzwerkschnittstellenanschluss, auf dem diese Bindung Peerkanalnachrichten verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="3e660-116">The network interface port on which this binding processes peer channel messages.</span></span>  
  
### <a name="security"></a><span data-ttu-id="3e660-117">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="3e660-117">Security</span></span>  

 <span data-ttu-id="3e660-118">Datentyp: PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="3e660-118">Data type: PeerSecuritySettings</span></span>  
  
 <span data-ttu-id="3e660-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="3e660-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3e660-120">Peertransportsicherheitseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="3e660-120">Peer transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e660-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3e660-121">Requirements</span></span>  
  
|<span data-ttu-id="3e660-122">MOF</span><span class="sxs-lookup"><span data-stu-id="3e660-122">MOF</span></span>|<span data-ttu-id="3e660-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="3e660-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3e660-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="3e660-124">Namespace</span></span>|<span data-ttu-id="3e660-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3e660-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3e660-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3e660-126">See also</span></span>

- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
