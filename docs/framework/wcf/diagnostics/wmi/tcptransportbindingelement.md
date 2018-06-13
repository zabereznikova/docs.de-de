---
title: TcpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
ms.openlocfilehash: e64f689923d95546c8cecdf47c247faf79242ebf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485789"
---
# <a name="tcptransportbindingelement"></a><span data-ttu-id="93608-102">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="93608-102">TcpTransportBindingElement</span></span>
<span data-ttu-id="93608-103">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="93608-103">TcpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93608-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="93608-104">Syntax</span></span>  
  
```  
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="93608-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="93608-105">Methods</span></span>  
 <span data-ttu-id="93608-106">Von der TcpTransportBindingElement-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="93608-106">The TcpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="93608-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="93608-107">Properties</span></span>  
 <span data-ttu-id="93608-108">Die TcpTransportBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="93608-108">The TcpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="connectionpoolsettings"></a><span data-ttu-id="93608-109">ConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="93608-109">ConnectionPoolSettings</span></span>  
 <span data-ttu-id="93608-110">Datentyp: TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="93608-110">Data type: TcpConnectionPoolSettings</span></span>  
  
 <span data-ttu-id="93608-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="93608-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="93608-112">Die Verbindungspooleinstellungen.</span><span class="sxs-lookup"><span data-stu-id="93608-112">The connection pool settings.</span></span>  
  
### <a name="listenbacklog"></a><span data-ttu-id="93608-113">ListenBacklog</span><span class="sxs-lookup"><span data-stu-id="93608-113">ListenBacklog</span></span>  
 <span data-ttu-id="93608-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="93608-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="93608-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="93608-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="93608-116">Maximal mögliche Anzahl der ausstehenden Verbindungsanforderungen in der Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="93608-116">The maximum number of queued connection requests that can be pending.</span></span>  
  
### <a name="portsharingenabled"></a><span data-ttu-id="93608-117">PortSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="93608-117">PortSharingEnabled</span></span>  
 <span data-ttu-id="93608-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="93608-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="93608-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="93608-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="93608-120">Boolescher Wert, der angibt, ob die TCP-Portfreigabe für diese Verbindung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="93608-120">A boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span>  
  
### <a name="teredoenabled"></a><span data-ttu-id="93608-121">TeredoEnabled</span><span class="sxs-lookup"><span data-stu-id="93608-121">TeredoEnabled</span></span>  
 <span data-ttu-id="93608-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="93608-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="93608-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="93608-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="93608-124">Boolescher Wert, der angibt, ob das Teredo-Protokoll aktiviert ist, das zur Adressierung von Clients hinter einer Firewall verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="93608-124">A boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93608-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="93608-125">Requirements</span></span>  
  
|<span data-ttu-id="93608-126">MOF</span><span class="sxs-lookup"><span data-stu-id="93608-126">MOF</span></span>|<span data-ttu-id="93608-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="93608-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="93608-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="93608-128">Namespace</span></span>|<span data-ttu-id="93608-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="93608-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="93608-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93608-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
