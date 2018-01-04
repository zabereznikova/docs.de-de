---
title: Kanalklasse
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 073f0a2a2731a08acd914a7dd85cb2b419d98128
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="channel-class"></a><span data-ttu-id="7d968-102">Kanalklasse</span><span class="sxs-lookup"><span data-stu-id="7d968-102">Channel class</span></span>
<span data-ttu-id="7d968-103">Kanal</span><span class="sxs-lookup"><span data-stu-id="7d968-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d968-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7d968-104">Syntax</span></span>  
  
```  
class Channel  
{  
  string LocalAddress;  
  Endpoint ref;  
  string RemoteAddress;  
  string SessionId;  
  string Type;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="7d968-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="7d968-105">Methods</span></span>  
 <span data-ttu-id="7d968-106">Die Kanalklasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="7d968-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7d968-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7d968-107">Properties</span></span>  
 <span data-ttu-id="7d968-108">Die Kanalklasse verfügt über die folgenden Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="7d968-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="7d968-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="7d968-109">LocalAddress</span></span>  
 <span data-ttu-id="7d968-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="7d968-110">Data type: string</span></span>  
  
 <span data-ttu-id="7d968-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7d968-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7d968-112">Der lokale Endpunkt für den Kanal.</span><span class="sxs-lookup"><span data-stu-id="7d968-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="7d968-113">ref</span><span class="sxs-lookup"><span data-stu-id="7d968-113">ref</span></span>  
 <span data-ttu-id="7d968-114">Datentyp: Endpunkt</span><span class="sxs-lookup"><span data-stu-id="7d968-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="7d968-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7d968-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7d968-116">Ein Verweis auf den Endpunkt, mit dem der Kanal verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="7d968-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="7d968-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="7d968-117">RemoteAddress</span></span>  
 <span data-ttu-id="7d968-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="7d968-118">Data type: string</span></span>  
  
 <span data-ttu-id="7d968-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7d968-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7d968-120">Die dem Kanal zugeordnete Remoteadresse.</span><span class="sxs-lookup"><span data-stu-id="7d968-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="7d968-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="7d968-121">SessionId</span></span>  
 <span data-ttu-id="7d968-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="7d968-122">Data type: string</span></span>  
  
 <span data-ttu-id="7d968-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7d968-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7d968-124">Die aktuelle Sitzungs-ID (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="7d968-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="7d968-125">Typ</span><span class="sxs-lookup"><span data-stu-id="7d968-125">Type</span></span>  
 <span data-ttu-id="7d968-126">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="7d968-126">Data type: string</span></span>  
  
 <span data-ttu-id="7d968-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7d968-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7d968-128">Der Kanaltyp.</span><span class="sxs-lookup"><span data-stu-id="7d968-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d968-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7d968-129">Requirements</span></span>  
  
|<span data-ttu-id="7d968-130">MOF</span><span class="sxs-lookup"><span data-stu-id="7d968-130">MOF</span></span>|<span data-ttu-id="7d968-131">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="7d968-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7d968-132">Namespace</span><span class="sxs-lookup"><span data-stu-id="7d968-132">Namespace</span></span>|<span data-ttu-id="7d968-133">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7d968-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7d968-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d968-134">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelBase>
