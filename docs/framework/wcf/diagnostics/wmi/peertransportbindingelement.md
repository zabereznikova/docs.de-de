---
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: 437ccc0446e3cc05596ab12b7908177b7f78e431
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54670653"
---
# <a name="peertransportbindingelement"></a><span data-ttu-id="b989d-102">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="b989d-102">PeerTransportBindingElement</span></span>
<span data-ttu-id="b989d-103">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="b989d-103">PeerTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b989d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b989d-104">Syntax</span></span>  
  
```csharp
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b989d-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="b989d-105">Methods</span></span>  
 <span data-ttu-id="b989d-106">Von der Klasse PeerTransportBindingElement werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="b989d-106">The PeerTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b989d-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b989d-107">Properties</span></span>  
 <span data-ttu-id="b989d-108">Die Klasse PeerTransportBindingElement verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="b989d-108">The PeerTransportBindingElement class has the following properties:</span></span>  
  
### <a name="listenipaddress"></a><span data-ttu-id="b989d-109">ListenIPAddress</span><span class="sxs-lookup"><span data-stu-id="b989d-109">ListenIPAddress</span></span>  
 <span data-ttu-id="b989d-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="b989d-110">Data type: string</span></span>  
  
 <span data-ttu-id="b989d-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b989d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b989d-112">Die IP-Adresse, auf der der Peerknoten Meldungen abhört.</span><span class="sxs-lookup"><span data-stu-id="b989d-112">The IP address on which the peer node listens for messages.</span></span>  
  
### <a name="port"></a><span data-ttu-id="b989d-113">Port</span><span class="sxs-lookup"><span data-stu-id="b989d-113">Port</span></span>  
 <span data-ttu-id="b989d-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="b989d-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="b989d-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b989d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b989d-116">Der Netzwerkschnittstellenanschluss, auf dem diese Bindung Peerkanalnachrichten verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="b989d-116">The network interface port on which this binding processes peer channel messages.</span></span>  
  
### <a name="security"></a><span data-ttu-id="b989d-117">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b989d-117">Security</span></span>  
 <span data-ttu-id="b989d-118">Datentyp: PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="b989d-118">Data type: PeerSecuritySettings</span></span>  
  
 <span data-ttu-id="b989d-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b989d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b989d-120">Peertransportsicherheitseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="b989d-120">Peer transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b989d-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b989d-121">Requirements</span></span>  
  
|<span data-ttu-id="b989d-122">MOF</span><span class="sxs-lookup"><span data-stu-id="b989d-122">MOF</span></span>|<span data-ttu-id="b989d-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="b989d-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b989d-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="b989d-124">Namespace</span></span>|<span data-ttu-id="b989d-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b989d-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b989d-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b989d-126">See also</span></span>
- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
