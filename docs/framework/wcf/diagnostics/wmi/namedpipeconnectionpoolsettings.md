---
title: NamedPipeConnectionPoolSettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 079bccb8-54b5-4436-a43d-5567763f72ce
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 601ccd5589da759606365570538e0df902e4fbe2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="namedpipeconnectionpoolsettings"></a><span data-ttu-id="10737-102">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="10737-102">NamedPipeConnectionPoolSettings</span></span>
<span data-ttu-id="10737-103">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="10737-103">NamedPipeConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10737-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="10737-104">Syntax</span></span>  
  
```  
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="10737-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="10737-105">Methods</span></span>  
 <span data-ttu-id="10737-106">Die NamedPipeConnectionPoolSettings-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="10737-106">The NamedPipeConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="10737-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="10737-107">Properties</span></span>  
 <span data-ttu-id="10737-108">Die NamedPipeConnectionPoolSettings-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="10737-108">The NamedPipeConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="10737-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="10737-109">GroupName</span></span>  
 <span data-ttu-id="10737-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="10737-110">Data type: string</span></span>  
  
 <span data-ttu-id="10737-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="10737-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="10737-112">Der Gruppenname des vom Bindungselement verwendeten Verbindungspools.</span><span class="sxs-lookup"><span data-stu-id="10737-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="10737-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="10737-113">IdleTimeout</span></span>  
 <span data-ttu-id="10737-114">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="10737-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="10737-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="10737-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="10737-116">Die maximale Zeit, während der sich die Verbindung im Leerlauf befinden darf, bevor sie getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="10737-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="10737-117">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="10737-117">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="10737-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="10737-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="10737-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="10737-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="10737-120">Die maximale Anzahl von ausgehenden Verbindungen pro Endpunkt auf dem Client.</span><span class="sxs-lookup"><span data-stu-id="10737-120">The maximum number of outbound connections for each endpoint on the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10737-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="10737-121">Requirements</span></span>  
  
|<span data-ttu-id="10737-122">MOF</span><span class="sxs-lookup"><span data-stu-id="10737-122">MOF</span></span>|<span data-ttu-id="10737-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="10737-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="10737-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="10737-124">Namespace</span></span>|<span data-ttu-id="10737-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="10737-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="10737-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10737-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
