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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cf9c39334289cb30d1a01917c0be37da02fcdc5b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="namedpipeconnectionpoolsettings"></a><span data-ttu-id="66cb8-102">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="66cb8-102">NamedPipeConnectionPoolSettings</span></span>
<span data-ttu-id="66cb8-103">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="66cb8-103">NamedPipeConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66cb8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="66cb8-104">Syntax</span></span>  
  
```  
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="66cb8-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="66cb8-105">Methods</span></span>  
 <span data-ttu-id="66cb8-106">Die NamedPipeConnectionPoolSettings-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="66cb8-106">The NamedPipeConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="66cb8-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="66cb8-107">Properties</span></span>  
 <span data-ttu-id="66cb8-108">Die NamedPipeConnectionPoolSettings-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="66cb8-108">The NamedPipeConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="66cb8-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="66cb8-109">GroupName</span></span>  
 <span data-ttu-id="66cb8-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="66cb8-110">Data type: string</span></span>  
  
 <span data-ttu-id="66cb8-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="66cb8-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="66cb8-112">Der Gruppenname des vom Bindungselement verwendeten Verbindungspools.</span><span class="sxs-lookup"><span data-stu-id="66cb8-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="66cb8-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="66cb8-113">IdleTimeout</span></span>  
 <span data-ttu-id="66cb8-114">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="66cb8-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="66cb8-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="66cb8-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="66cb8-116">Die maximale Zeit, während der sich die Verbindung im Leerlauf befinden darf, bevor sie getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="66cb8-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="66cb8-117">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="66cb8-117">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="66cb8-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="66cb8-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="66cb8-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="66cb8-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="66cb8-120">Die maximale Anzahl von ausgehenden Verbindungen pro Endpunkt auf dem Client.</span><span class="sxs-lookup"><span data-stu-id="66cb8-120">The maximum number of outbound connections for each endpoint on the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66cb8-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="66cb8-121">Requirements</span></span>  
  
|<span data-ttu-id="66cb8-122">MOF</span><span class="sxs-lookup"><span data-stu-id="66cb8-122">MOF</span></span>|<span data-ttu-id="66cb8-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="66cb8-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="66cb8-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="66cb8-124">Namespace</span></span>|<span data-ttu-id="66cb8-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="66cb8-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="66cb8-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66cb8-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
