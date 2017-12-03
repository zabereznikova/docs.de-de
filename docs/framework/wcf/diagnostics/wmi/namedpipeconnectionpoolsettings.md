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
ms.openlocfilehash: 18740c4c87aaeafcd0a28991376e0c45fe688223
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="namedpipeconnectionpoolsettings"></a><span data-ttu-id="dbb0b-102">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="dbb0b-102">NamedPipeConnectionPoolSettings</span></span>
<span data-ttu-id="dbb0b-103">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="dbb0b-103">NamedPipeConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbb0b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dbb0b-104">Syntax</span></span>  
  
```  
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="dbb0b-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="dbb0b-105">Methods</span></span>  
 <span data-ttu-id="dbb0b-106">Die NamedPipeConnectionPoolSettings-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="dbb0b-106">The NamedPipeConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="dbb0b-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="dbb0b-107">Properties</span></span>  
 <span data-ttu-id="dbb0b-108">Die NamedPipeConnectionPoolSettings-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="dbb0b-108">The NamedPipeConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="dbb0b-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="dbb0b-109">GroupName</span></span>  
 <span data-ttu-id="dbb0b-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="dbb0b-110">Data type: string</span></span>  
  
 <span data-ttu-id="dbb0b-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="dbb0b-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dbb0b-112">Der Gruppenname des vom Bindungselement verwendeten Verbindungspools.</span><span class="sxs-lookup"><span data-stu-id="dbb0b-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="dbb0b-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="dbb0b-113">IdleTimeout</span></span>  
 <span data-ttu-id="dbb0b-114">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="dbb0b-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="dbb0b-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="dbb0b-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dbb0b-116">Die maximale Zeit, während der sich die Verbindung im Leerlauf befinden darf, bevor sie getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="dbb0b-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="dbb0b-117">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="dbb0b-117">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="dbb0b-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="dbb0b-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="dbb0b-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="dbb0b-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dbb0b-120">Die maximale Anzahl von ausgehenden Verbindungen pro Endpunkt auf dem Client.</span><span class="sxs-lookup"><span data-stu-id="dbb0b-120">The maximum number of outbound connections for each endpoint on the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbb0b-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dbb0b-121">Requirements</span></span>  
  
|<span data-ttu-id="dbb0b-122">MOF</span><span class="sxs-lookup"><span data-stu-id="dbb0b-122">MOF</span></span>|<span data-ttu-id="dbb0b-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="dbb0b-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="dbb0b-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="dbb0b-124">Namespace</span></span>|<span data-ttu-id="dbb0b-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="dbb0b-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dbb0b-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dbb0b-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
