---
title: Kanalklasse
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: a920636e7df9609b12834366b1488c80122f9fca
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274230"
---
# <a name="channel-class"></a><span data-ttu-id="848a4-102">Kanalklasse</span><span class="sxs-lookup"><span data-stu-id="848a4-102">Channel class</span></span>

<span data-ttu-id="848a4-103">Kanal</span><span class="sxs-lookup"><span data-stu-id="848a4-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="848a4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="848a4-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="848a4-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="848a4-105">Methods</span></span>  

 <span data-ttu-id="848a4-106">Die Kanalklasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="848a4-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="848a4-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="848a4-107">Properties</span></span>  

 <span data-ttu-id="848a4-108">Die Kanalklasse verfügt über die folgenden Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="848a4-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="848a4-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="848a4-109">LocalAddress</span></span>  

 <span data-ttu-id="848a4-110">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="848a4-110">Data type: string</span></span>  
  
 <span data-ttu-id="848a4-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="848a4-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="848a4-112">Der lokale Endpunkt für den Kanal.</span><span class="sxs-lookup"><span data-stu-id="848a4-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="848a4-113">ref</span><span class="sxs-lookup"><span data-stu-id="848a4-113">ref</span></span>  

 <span data-ttu-id="848a4-114">Datentyp: Endpunkt</span><span class="sxs-lookup"><span data-stu-id="848a4-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="848a4-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="848a4-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="848a4-116">Ein Verweis auf den Endpunkt, mit dem der Kanal verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="848a4-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="848a4-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="848a4-117">RemoteAddress</span></span>  

 <span data-ttu-id="848a4-118">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="848a4-118">Data type: string</span></span>  
  
 <span data-ttu-id="848a4-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="848a4-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="848a4-120">Die dem Kanal zugeordnete Remoteadresse.</span><span class="sxs-lookup"><span data-stu-id="848a4-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="848a4-121">SessionID</span><span class="sxs-lookup"><span data-stu-id="848a4-121">SessionId</span></span>  

 <span data-ttu-id="848a4-122">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="848a4-122">Data type: string</span></span>  
  
 <span data-ttu-id="848a4-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="848a4-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="848a4-124">Die aktuelle Sitzungs-ID (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="848a4-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="848a4-125">type</span><span class="sxs-lookup"><span data-stu-id="848a4-125">Type</span></span>  

 <span data-ttu-id="848a4-126">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="848a4-126">Data type: string</span></span>  
  
 <span data-ttu-id="848a4-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="848a4-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="848a4-128">Der Kanaltyp.</span><span class="sxs-lookup"><span data-stu-id="848a4-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="848a4-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="848a4-129">Requirements</span></span>  
  
|<span data-ttu-id="848a4-130">MOF</span><span class="sxs-lookup"><span data-stu-id="848a4-130">MOF</span></span>|<span data-ttu-id="848a4-131">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="848a4-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="848a4-132">Namespace</span><span class="sxs-lookup"><span data-stu-id="848a4-132">Namespace</span></span>|<span data-ttu-id="848a4-133">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="848a4-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="848a4-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="848a4-134">See also</span></span>

- <xref:System.ServiceModel.Channels.ChannelBase>
