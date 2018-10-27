---
title: TcpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
ms.openlocfilehash: 04326484bbf1f07c66ad8fb401642880f9ba8c6e
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/26/2018
ms.locfileid: "50033713"
---
# <a name="tcptransportbindingelement"></a><span data-ttu-id="9a441-102">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="9a441-102">TcpTransportBindingElement</span></span>
<span data-ttu-id="9a441-103">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="9a441-103">TcpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a441-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a441-104">Syntax</span></span>  
  
```csharp
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9a441-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="9a441-105">Methods</span></span>  
 <span data-ttu-id="9a441-106">Von der TcpTransportBindingElement-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="9a441-106">The TcpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9a441-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9a441-107">Properties</span></span>  
 <span data-ttu-id="9a441-108">Die TcpTransportBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="9a441-108">The TcpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="connectionpoolsettings"></a><span data-ttu-id="9a441-109">ConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="9a441-109">ConnectionPoolSettings</span></span>  
 <span data-ttu-id="9a441-110">Datentyp: TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="9a441-110">Data type: TcpConnectionPoolSettings</span></span>  
  
 <span data-ttu-id="9a441-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9a441-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9a441-112">Die Verbindungspooleinstellungen.</span><span class="sxs-lookup"><span data-stu-id="9a441-112">The connection pool settings.</span></span>  
  
### <a name="listenbacklog"></a><span data-ttu-id="9a441-113">ListenBacklog</span><span class="sxs-lookup"><span data-stu-id="9a441-113">ListenBacklog</span></span>  
 <span data-ttu-id="9a441-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="9a441-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="9a441-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9a441-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9a441-116">Maximal mögliche Anzahl der ausstehenden Verbindungsanforderungen in der Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="9a441-116">The maximum number of queued connection requests that can be pending.</span></span>  
  
### <a name="portsharingenabled"></a><span data-ttu-id="9a441-117">PortSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="9a441-117">PortSharingEnabled</span></span>  
 <span data-ttu-id="9a441-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="9a441-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="9a441-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9a441-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9a441-120">Boolescher Wert, der angibt, ob die TCP-Portfreigabe für diese Verbindung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9a441-120">A boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span>  
  
### <a name="teredoenabled"></a><span data-ttu-id="9a441-121">TeredoEnabled</span><span class="sxs-lookup"><span data-stu-id="9a441-121">TeredoEnabled</span></span>  
 <span data-ttu-id="9a441-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="9a441-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="9a441-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9a441-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9a441-124">Boolescher Wert, der angibt, ob das Teredo-Protokoll aktiviert ist, das zur Adressierung von Clients hinter einer Firewall verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9a441-124">A boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a441-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9a441-125">Requirements</span></span>  
  
|<span data-ttu-id="9a441-126">MOF</span><span class="sxs-lookup"><span data-stu-id="9a441-126">MOF</span></span>|<span data-ttu-id="9a441-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="9a441-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9a441-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="9a441-128">Namespace</span></span>|<span data-ttu-id="9a441-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9a441-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9a441-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a441-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
