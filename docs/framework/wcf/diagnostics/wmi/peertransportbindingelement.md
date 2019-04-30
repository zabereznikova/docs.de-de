---
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: ba9031dad96f12c7c48b03f1da4af1b3adc6dd4f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962955"
---
# <a name="peertransportbindingelement"></a><span data-ttu-id="f3a4a-102">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="f3a4a-102">PeerTransportBindingElement</span></span>
<span data-ttu-id="f3a4a-103">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="f3a4a-103">PeerTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3a4a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f3a4a-104">Syntax</span></span>  
  
```csharp
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f3a4a-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="f3a4a-105">Methods</span></span>  
 <span data-ttu-id="f3a4a-106">Von der Klasse PeerTransportBindingElement werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="f3a4a-106">The PeerTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f3a4a-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f3a4a-107">Properties</span></span>  
 <span data-ttu-id="f3a4a-108">Die Klasse PeerTransportBindingElement verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="f3a4a-108">The PeerTransportBindingElement class has the following properties:</span></span>  
  
### <a name="listenipaddress"></a><span data-ttu-id="f3a4a-109">ListenIPAddress</span><span class="sxs-lookup"><span data-stu-id="f3a4a-109">ListenIPAddress</span></span>  
 <span data-ttu-id="f3a4a-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="f3a4a-110">Data type: string</span></span>  
  
 <span data-ttu-id="f3a4a-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f3a4a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f3a4a-112">Die IP-Adresse, auf der der Peerknoten Meldungen abhört.</span><span class="sxs-lookup"><span data-stu-id="f3a4a-112">The IP address on which the peer node listens for messages.</span></span>  
  
### <a name="port"></a><span data-ttu-id="f3a4a-113">Port</span><span class="sxs-lookup"><span data-stu-id="f3a4a-113">Port</span></span>  
 <span data-ttu-id="f3a4a-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="f3a4a-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="f3a4a-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f3a4a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f3a4a-116">Der Netzwerkschnittstellenanschluss, auf dem diese Bindung Peerkanalnachrichten verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="f3a4a-116">The network interface port on which this binding processes peer channel messages.</span></span>  
  
### <a name="security"></a><span data-ttu-id="f3a4a-117">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="f3a4a-117">Security</span></span>  
 <span data-ttu-id="f3a4a-118">Datentyp: PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="f3a4a-118">Data type: PeerSecuritySettings</span></span>  
  
 <span data-ttu-id="f3a4a-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f3a4a-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f3a4a-120">Peertransportsicherheitseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="f3a4a-120">Peer transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3a4a-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f3a4a-121">Requirements</span></span>  
  
|<span data-ttu-id="f3a4a-122">MOF</span><span class="sxs-lookup"><span data-stu-id="f3a4a-122">MOF</span></span>|<span data-ttu-id="f3a4a-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f3a4a-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f3a4a-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="f3a4a-124">Namespace</span></span>|<span data-ttu-id="f3a4a-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f3a4a-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f3a4a-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3a4a-126">See also</span></span>

- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
