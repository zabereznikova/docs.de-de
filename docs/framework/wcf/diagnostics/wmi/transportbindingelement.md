---
title: TransportBindingElement
ms.date: 03/30/2017
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
ms.openlocfilehash: 45bfcd069391156bc85cc4c26f2b172770197a9e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96234842"
---
# <a name="transportbindingelement"></a><span data-ttu-id="46663-102">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="46663-102">TransportBindingElement</span></span>

<span data-ttu-id="46663-103">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="46663-103">TransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46663-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="46663-104">Syntax</span></span>  
  
```csharp
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="46663-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="46663-105">Methods</span></span>  

 <span data-ttu-id="46663-106">Von der Klasse TransportBindingElement werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="46663-106">The TransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="46663-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="46663-107">Properties</span></span>  

 <span data-ttu-id="46663-108">Die Klasse TransportBindingElement verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="46663-108">The TransportBindingElement class has the following properties:</span></span>  
  
### <a name="manualaddressing"></a><span data-ttu-id="46663-109">ManualAddressing</span><span class="sxs-lookup"><span data-stu-id="46663-109">ManualAddressing</span></span>  

 <span data-ttu-id="46663-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="46663-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="46663-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="46663-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="46663-112">Ein boolescher Wert, der angibt, ob der Benutzer die Kontrolle über die Nachrichtenadressierung übernehmen möchte.</span><span class="sxs-lookup"><span data-stu-id="46663-112">A boolean value that specifies whether the user wants to take control of message addressing.</span></span>  
  
### <a name="maxbufferpoolsize"></a><span data-ttu-id="46663-113">MaxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="46663-113">MaxBufferPoolSize</span></span>  

 <span data-ttu-id="46663-114">Datentyp: sint64</span><span class="sxs-lookup"><span data-stu-id="46663-114">Data type: sint64</span></span>  
  
 <span data-ttu-id="46663-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="46663-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="46663-116">Die maximale Pufferpoolgröße der Bindung.</span><span class="sxs-lookup"><span data-stu-id="46663-116">The maximum buffer pool size for the binding.</span></span>  
  
### <a name="maxreceivedmessagesize"></a><span data-ttu-id="46663-117">MaxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="46663-117">MaxReceivedMessageSize</span></span>  

 <span data-ttu-id="46663-118">Datentyp: sint64</span><span class="sxs-lookup"><span data-stu-id="46663-118">Data type: sint64</span></span>  
  
 <span data-ttu-id="46663-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="46663-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="46663-120">Die maximale Größe einer Nachricht, die von dieser Bindung verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="46663-120">The maximum size for a message that is processed by this binding.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="46663-121">Schema</span><span class="sxs-lookup"><span data-stu-id="46663-121">Scheme</span></span>  

 <span data-ttu-id="46663-122">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="46663-122">Data type: string</span></span>  
  
 <span data-ttu-id="46663-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="46663-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="46663-124">Das URI-Schema für den Transport.</span><span class="sxs-lookup"><span data-stu-id="46663-124">The URI scheme for the transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46663-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="46663-125">Requirements</span></span>  
  
|<span data-ttu-id="46663-126">MOF</span><span class="sxs-lookup"><span data-stu-id="46663-126">MOF</span></span>|<span data-ttu-id="46663-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="46663-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="46663-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="46663-128">Namespace</span></span>|<span data-ttu-id="46663-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="46663-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="46663-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="46663-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TransportBindingElement>
