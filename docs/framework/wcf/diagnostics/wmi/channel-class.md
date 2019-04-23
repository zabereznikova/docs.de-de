---
title: Kanalklasse
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: f60a3946617b0994db1ba9e9ddf43be863be81f9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59767447"
---
# <a name="channel-class"></a><span data-ttu-id="407c6-102">Kanalklasse</span><span class="sxs-lookup"><span data-stu-id="407c6-102">Channel class</span></span>
<span data-ttu-id="407c6-103">Kanal</span><span class="sxs-lookup"><span data-stu-id="407c6-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="407c6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="407c6-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="407c6-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="407c6-105">Methods</span></span>  
 <span data-ttu-id="407c6-106">Die Kanalklasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="407c6-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="407c6-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="407c6-107">Properties</span></span>  
 <span data-ttu-id="407c6-108">Die Kanalklasse verfügt über die folgenden Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="407c6-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="407c6-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="407c6-109">LocalAddress</span></span>  
 <span data-ttu-id="407c6-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="407c6-110">Data type: string</span></span>  
  
 <span data-ttu-id="407c6-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="407c6-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="407c6-112">Der lokale Endpunkt für den Kanal.</span><span class="sxs-lookup"><span data-stu-id="407c6-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="407c6-113">ref</span><span class="sxs-lookup"><span data-stu-id="407c6-113">ref</span></span>  
 <span data-ttu-id="407c6-114">Datentyp: Endpunkt</span><span class="sxs-lookup"><span data-stu-id="407c6-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="407c6-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="407c6-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="407c6-116">Ein Verweis auf den Endpunkt, mit dem der Kanal verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="407c6-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="407c6-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="407c6-117">RemoteAddress</span></span>  
 <span data-ttu-id="407c6-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="407c6-118">Data type: string</span></span>  
  
 <span data-ttu-id="407c6-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="407c6-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="407c6-120">Die dem Kanal zugeordnete Remoteadresse.</span><span class="sxs-lookup"><span data-stu-id="407c6-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="407c6-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="407c6-121">SessionId</span></span>  
 <span data-ttu-id="407c6-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="407c6-122">Data type: string</span></span>  
  
 <span data-ttu-id="407c6-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="407c6-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="407c6-124">Die aktuelle Sitzungs-ID (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="407c6-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="407c6-125">Typ</span><span class="sxs-lookup"><span data-stu-id="407c6-125">Type</span></span>  
 <span data-ttu-id="407c6-126">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="407c6-126">Data type: string</span></span>  
  
 <span data-ttu-id="407c6-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="407c6-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="407c6-128">Der Kanaltyp.</span><span class="sxs-lookup"><span data-stu-id="407c6-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="407c6-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="407c6-129">Requirements</span></span>  
  
|<span data-ttu-id="407c6-130">MOF</span><span class="sxs-lookup"><span data-stu-id="407c6-130">MOF</span></span>|<span data-ttu-id="407c6-131">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="407c6-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="407c6-132">Namespace</span><span class="sxs-lookup"><span data-stu-id="407c6-132">Namespace</span></span>|<span data-ttu-id="407c6-133">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="407c6-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="407c6-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="407c6-134">See also</span></span>

- <xref:System.ServiceModel.Channels.ChannelBase>
