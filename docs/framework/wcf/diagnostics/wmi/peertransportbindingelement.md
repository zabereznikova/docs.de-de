---
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: ba9031dad96f12c7c48b03f1da4af1b3adc6dd4f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59194063"
---
# <a name="peertransportbindingelement"></a><span data-ttu-id="a20ba-102">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="a20ba-102">PeerTransportBindingElement</span></span>
<span data-ttu-id="a20ba-103">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="a20ba-103">PeerTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a20ba-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a20ba-104">Syntax</span></span>  
  
```csharp
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a20ba-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="a20ba-105">Methods</span></span>  
 <span data-ttu-id="a20ba-106">Von der Klasse PeerTransportBindingElement werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="a20ba-106">The PeerTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a20ba-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a20ba-107">Properties</span></span>  
 <span data-ttu-id="a20ba-108">Die Klasse PeerTransportBindingElement verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="a20ba-108">The PeerTransportBindingElement class has the following properties:</span></span>  
  
### <a name="listenipaddress"></a><span data-ttu-id="a20ba-109">ListenIPAddress</span><span class="sxs-lookup"><span data-stu-id="a20ba-109">ListenIPAddress</span></span>  
 <span data-ttu-id="a20ba-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="a20ba-110">Data type: string</span></span>  
  
 <span data-ttu-id="a20ba-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a20ba-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a20ba-112">Die IP-Adresse, auf der der Peerknoten Meldungen abhört.</span><span class="sxs-lookup"><span data-stu-id="a20ba-112">The IP address on which the peer node listens for messages.</span></span>  
  
### <a name="port"></a><span data-ttu-id="a20ba-113">Port</span><span class="sxs-lookup"><span data-stu-id="a20ba-113">Port</span></span>  
 <span data-ttu-id="a20ba-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="a20ba-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="a20ba-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a20ba-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a20ba-116">Der Netzwerkschnittstellenanschluss, auf dem diese Bindung Peerkanalnachrichten verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="a20ba-116">The network interface port on which this binding processes peer channel messages.</span></span>  
  
### <a name="security"></a><span data-ttu-id="a20ba-117">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="a20ba-117">Security</span></span>  
 <span data-ttu-id="a20ba-118">Datentyp: PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="a20ba-118">Data type: PeerSecuritySettings</span></span>  
  
 <span data-ttu-id="a20ba-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a20ba-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a20ba-120">Peertransportsicherheitseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="a20ba-120">Peer transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a20ba-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a20ba-121">Requirements</span></span>  
  
|<span data-ttu-id="a20ba-122">MOF</span><span class="sxs-lookup"><span data-stu-id="a20ba-122">MOF</span></span>|<span data-ttu-id="a20ba-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="a20ba-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a20ba-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="a20ba-124">Namespace</span></span>|<span data-ttu-id="a20ba-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a20ba-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a20ba-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a20ba-126">See also</span></span>

- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
