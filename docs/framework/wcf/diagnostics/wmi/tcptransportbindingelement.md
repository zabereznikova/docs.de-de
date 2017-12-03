---
title: TcpTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4b9aa7e0d9eaba0181b17b44da1bf871c10af814
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="tcptransportbindingelement"></a><span data-ttu-id="eeaca-102">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="eeaca-102">TcpTransportBindingElement</span></span>
<span data-ttu-id="eeaca-103">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="eeaca-103">TcpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eeaca-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eeaca-104">Syntax</span></span>  
  
```  
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="eeaca-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="eeaca-105">Methods</span></span>  
 <span data-ttu-id="eeaca-106">Von der TcpTransportBindingElement-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="eeaca-106">The TcpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="eeaca-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="eeaca-107">Properties</span></span>  
 <span data-ttu-id="eeaca-108">Die TcpTransportBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="eeaca-108">The TcpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="connectionpoolsettings"></a><span data-ttu-id="eeaca-109">ConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="eeaca-109">ConnectionPoolSettings</span></span>  
 <span data-ttu-id="eeaca-110">Datentyp: TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="eeaca-110">Data type: TcpConnectionPoolSettings</span></span>  
  
 <span data-ttu-id="eeaca-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="eeaca-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eeaca-112">Die Verbindungspooleinstellungen.</span><span class="sxs-lookup"><span data-stu-id="eeaca-112">The connection pool settings.</span></span>  
  
### <a name="listenbacklog"></a><span data-ttu-id="eeaca-113">ListenBacklog</span><span class="sxs-lookup"><span data-stu-id="eeaca-113">ListenBacklog</span></span>  
 <span data-ttu-id="eeaca-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="eeaca-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="eeaca-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="eeaca-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eeaca-116">Maximal mögliche Anzahl der ausstehenden Verbindungsanforderungen in der Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="eeaca-116">The maximum number of queued connection requests that can be pending.</span></span>  
  
### <a name="portsharingenabled"></a><span data-ttu-id="eeaca-117">PortSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="eeaca-117">PortSharingEnabled</span></span>  
 <span data-ttu-id="eeaca-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="eeaca-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="eeaca-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="eeaca-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eeaca-120">Boolescher Wert, der angibt, ob die TCP-Portfreigabe für diese Verbindung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="eeaca-120">A boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span>  
  
### <a name="teredoenabled"></a><span data-ttu-id="eeaca-121">TeredoEnabled</span><span class="sxs-lookup"><span data-stu-id="eeaca-121">TeredoEnabled</span></span>  
 <span data-ttu-id="eeaca-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="eeaca-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="eeaca-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="eeaca-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eeaca-124">Boolescher Wert, der angibt, ob das Teredo-Protokoll aktiviert ist, das zur Adressierung von Clients hinter einer Firewall verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="eeaca-124">A boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eeaca-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eeaca-125">Requirements</span></span>  
  
|<span data-ttu-id="eeaca-126">MOF</span><span class="sxs-lookup"><span data-stu-id="eeaca-126">MOF</span></span>|<span data-ttu-id="eeaca-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="eeaca-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="eeaca-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="eeaca-128">Namespace</span></span>|<span data-ttu-id="eeaca-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="eeaca-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eeaca-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eeaca-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
