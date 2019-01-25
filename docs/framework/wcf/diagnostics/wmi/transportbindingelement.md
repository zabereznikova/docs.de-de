---
title: TransportBindingElement
ms.date: 03/30/2017
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
ms.openlocfilehash: 303e5523befb68c65bc50ee3933af58897929363
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668452"
---
# <a name="transportbindingelement"></a><span data-ttu-id="bc54e-102">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="bc54e-102">TransportBindingElement</span></span>
<span data-ttu-id="bc54e-103">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="bc54e-103">TransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc54e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bc54e-104">Syntax</span></span>  
  
```csharp
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="bc54e-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="bc54e-105">Methods</span></span>  
 <span data-ttu-id="bc54e-106">Von der Klasse TransportBindingElement werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="bc54e-106">The TransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="bc54e-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="bc54e-107">Properties</span></span>  
 <span data-ttu-id="bc54e-108">Die Klasse TransportBindingElement verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="bc54e-108">The TransportBindingElement class has the following properties:</span></span>  
  
### <a name="manualaddressing"></a><span data-ttu-id="bc54e-109">ManualAddressing</span><span class="sxs-lookup"><span data-stu-id="bc54e-109">ManualAddressing</span></span>  
 <span data-ttu-id="bc54e-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="bc54e-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="bc54e-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="bc54e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bc54e-112">Ein boolescher Wert, der angibt, ob der Benutzer die Kontrolle über die Nachrichtenadressierung übernehmen möchte.</span><span class="sxs-lookup"><span data-stu-id="bc54e-112">A boolean value that specifies whether the user wants to take control of message addressing.</span></span>  
  
### <a name="maxbufferpoolsize"></a><span data-ttu-id="bc54e-113">MaxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="bc54e-113">MaxBufferPoolSize</span></span>  
 <span data-ttu-id="bc54e-114">Datentyp: sint64</span><span class="sxs-lookup"><span data-stu-id="bc54e-114">Data type: sint64</span></span>  
  
 <span data-ttu-id="bc54e-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="bc54e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bc54e-116">Die maximale Pufferpoolgröße der Bindung.</span><span class="sxs-lookup"><span data-stu-id="bc54e-116">The maximum buffer pool size for the binding.</span></span>  
  
### <a name="maxreceivedmessagesize"></a><span data-ttu-id="bc54e-117">MaxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="bc54e-117">MaxReceivedMessageSize</span></span>  
 <span data-ttu-id="bc54e-118">Datentyp: sint64</span><span class="sxs-lookup"><span data-stu-id="bc54e-118">Data type: sint64</span></span>  
  
 <span data-ttu-id="bc54e-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="bc54e-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bc54e-120">Die maximale Größe einer Nachricht, die von dieser Bindung verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="bc54e-120">The maximum size for a message that is processed by this binding.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="bc54e-121">Schema</span><span class="sxs-lookup"><span data-stu-id="bc54e-121">Scheme</span></span>  
 <span data-ttu-id="bc54e-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="bc54e-122">Data type: string</span></span>  
  
 <span data-ttu-id="bc54e-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="bc54e-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bc54e-124">Das URI-Schema für den Transport.</span><span class="sxs-lookup"><span data-stu-id="bc54e-124">The URI scheme for the transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc54e-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bc54e-125">Requirements</span></span>  
  
|<span data-ttu-id="bc54e-126">MOF</span><span class="sxs-lookup"><span data-stu-id="bc54e-126">MOF</span></span>|<span data-ttu-id="bc54e-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="bc54e-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="bc54e-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="bc54e-128">Namespace</span></span>|<span data-ttu-id="bc54e-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="bc54e-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bc54e-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc54e-130">See also</span></span>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
