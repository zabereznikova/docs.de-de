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
ms.openlocfilehash: 93632d6a178c0f58143fc148a0e1eb51be94ed17
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="channel-class"></a><span data-ttu-id="a000d-102">Kanalklasse</span><span class="sxs-lookup"><span data-stu-id="a000d-102">Channel class</span></span>
<span data-ttu-id="a000d-103">Kanal</span><span class="sxs-lookup"><span data-stu-id="a000d-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a000d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a000d-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="a000d-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="a000d-105">Methods</span></span>  
 <span data-ttu-id="a000d-106">Die Kanalklasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="a000d-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a000d-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a000d-107">Properties</span></span>  
 <span data-ttu-id="a000d-108">Die Kanalklasse verfügt über die folgenden Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="a000d-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="a000d-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="a000d-109">LocalAddress</span></span>  
 <span data-ttu-id="a000d-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="a000d-110">Data type: string</span></span>  
  
 <span data-ttu-id="a000d-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a000d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a000d-112">Der lokale Endpunkt für den Kanal.</span><span class="sxs-lookup"><span data-stu-id="a000d-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="a000d-113">ref</span><span class="sxs-lookup"><span data-stu-id="a000d-113">ref</span></span>  
 <span data-ttu-id="a000d-114">Datentyp: Endpunkt</span><span class="sxs-lookup"><span data-stu-id="a000d-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="a000d-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a000d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a000d-116">Ein Verweis auf den Endpunkt, mit dem der Kanal verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="a000d-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="a000d-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="a000d-117">RemoteAddress</span></span>  
 <span data-ttu-id="a000d-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="a000d-118">Data type: string</span></span>  
  
 <span data-ttu-id="a000d-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a000d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a000d-120">Die dem Kanal zugeordnete Remoteadresse.</span><span class="sxs-lookup"><span data-stu-id="a000d-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="a000d-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="a000d-121">SessionId</span></span>  
 <span data-ttu-id="a000d-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="a000d-122">Data type: string</span></span>  
  
 <span data-ttu-id="a000d-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a000d-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a000d-124">Die aktuelle Sitzungs-ID (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="a000d-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="a000d-125">Typ</span><span class="sxs-lookup"><span data-stu-id="a000d-125">Type</span></span>  
 <span data-ttu-id="a000d-126">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="a000d-126">Data type: string</span></span>  
  
 <span data-ttu-id="a000d-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a000d-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a000d-128">Der Kanaltyp.</span><span class="sxs-lookup"><span data-stu-id="a000d-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a000d-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a000d-129">Requirements</span></span>  
  
|<span data-ttu-id="a000d-130">MOF</span><span class="sxs-lookup"><span data-stu-id="a000d-130">MOF</span></span>|<span data-ttu-id="a000d-131">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="a000d-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a000d-132">Namespace</span><span class="sxs-lookup"><span data-stu-id="a000d-132">Namespace</span></span>|<span data-ttu-id="a000d-133">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a000d-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a000d-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a000d-134">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelBase>
