---
title: Kanalklasse
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: 3fbf398cca7ae9adbbecb9439bf3cbd32eb03969
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668391"
---
# <a name="channel-class"></a><span data-ttu-id="0676e-102">Kanalklasse</span><span class="sxs-lookup"><span data-stu-id="0676e-102">Channel class</span></span>
<span data-ttu-id="0676e-103">Kanal</span><span class="sxs-lookup"><span data-stu-id="0676e-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0676e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0676e-104">Syntax</span></span>  
  
```csharp
class Channel  
{  
  string LocalAddress;  
  Endpoint ref;  
  string RemoteAddress;  
  string SessionId;  
  string Type;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="0676e-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="0676e-105">Methods</span></span>  
 <span data-ttu-id="0676e-106">Die Kanalklasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="0676e-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="0676e-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="0676e-107">Properties</span></span>  
 <span data-ttu-id="0676e-108">Die Kanalklasse verfügt über die folgenden Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="0676e-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="0676e-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="0676e-109">LocalAddress</span></span>  
 <span data-ttu-id="0676e-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="0676e-110">Data type: string</span></span>  
  
 <span data-ttu-id="0676e-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0676e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0676e-112">Der lokale Endpunkt für den Kanal.</span><span class="sxs-lookup"><span data-stu-id="0676e-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="0676e-113">ref</span><span class="sxs-lookup"><span data-stu-id="0676e-113">ref</span></span>  
 <span data-ttu-id="0676e-114">Datentyp: Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0676e-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="0676e-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0676e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0676e-116">Ein Verweis auf den Endpunkt, mit dem der Kanal verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="0676e-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="0676e-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="0676e-117">RemoteAddress</span></span>  
 <span data-ttu-id="0676e-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="0676e-118">Data type: string</span></span>  
  
 <span data-ttu-id="0676e-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0676e-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0676e-120">Die dem Kanal zugeordnete Remoteadresse.</span><span class="sxs-lookup"><span data-stu-id="0676e-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="0676e-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="0676e-121">SessionId</span></span>  
 <span data-ttu-id="0676e-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="0676e-122">Data type: string</span></span>  
  
 <span data-ttu-id="0676e-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0676e-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0676e-124">Die aktuelle Sitzungs-ID (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="0676e-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="0676e-125">Typ</span><span class="sxs-lookup"><span data-stu-id="0676e-125">Type</span></span>  
 <span data-ttu-id="0676e-126">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="0676e-126">Data type: string</span></span>  
  
 <span data-ttu-id="0676e-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0676e-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0676e-128">Der Kanaltyp.</span><span class="sxs-lookup"><span data-stu-id="0676e-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0676e-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0676e-129">Requirements</span></span>  
  
|<span data-ttu-id="0676e-130">MOF</span><span class="sxs-lookup"><span data-stu-id="0676e-130">MOF</span></span>|<span data-ttu-id="0676e-131">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="0676e-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="0676e-132">Namespace</span><span class="sxs-lookup"><span data-stu-id="0676e-132">Namespace</span></span>|<span data-ttu-id="0676e-133">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0676e-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0676e-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0676e-134">See also</span></span>
- <xref:System.ServiceModel.Channels.ChannelBase>
