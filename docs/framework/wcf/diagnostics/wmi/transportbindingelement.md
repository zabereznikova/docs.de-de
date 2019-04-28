---
title: TransportBindingElement
ms.date: 03/30/2017
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
ms.openlocfilehash: bdb5ca7400a41dd724c2ad7fc76695a82874ded6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61641618"
---
# <a name="transportbindingelement"></a><span data-ttu-id="f13fb-102">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="f13fb-102">TransportBindingElement</span></span>
<span data-ttu-id="f13fb-103">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="f13fb-103">TransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f13fb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f13fb-104">Syntax</span></span>  
  
```csharp
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f13fb-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="f13fb-105">Methods</span></span>  
 <span data-ttu-id="f13fb-106">Von der Klasse TransportBindingElement werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="f13fb-106">The TransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f13fb-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f13fb-107">Properties</span></span>  
 <span data-ttu-id="f13fb-108">Die Klasse TransportBindingElement verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="f13fb-108">The TransportBindingElement class has the following properties:</span></span>  
  
### <a name="manualaddressing"></a><span data-ttu-id="f13fb-109">ManualAddressing</span><span class="sxs-lookup"><span data-stu-id="f13fb-109">ManualAddressing</span></span>  
 <span data-ttu-id="f13fb-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="f13fb-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="f13fb-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f13fb-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f13fb-112">Ein boolescher Wert, der angibt, ob der Benutzer die Kontrolle über die Nachrichtenadressierung übernehmen möchte.</span><span class="sxs-lookup"><span data-stu-id="f13fb-112">A boolean value that specifies whether the user wants to take control of message addressing.</span></span>  
  
### <a name="maxbufferpoolsize"></a><span data-ttu-id="f13fb-113">MaxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="f13fb-113">MaxBufferPoolSize</span></span>  
 <span data-ttu-id="f13fb-114">Datentyp: sint64</span><span class="sxs-lookup"><span data-stu-id="f13fb-114">Data type: sint64</span></span>  
  
 <span data-ttu-id="f13fb-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f13fb-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f13fb-116">Die maximale Pufferpoolgröße der Bindung.</span><span class="sxs-lookup"><span data-stu-id="f13fb-116">The maximum buffer pool size for the binding.</span></span>  
  
### <a name="maxreceivedmessagesize"></a><span data-ttu-id="f13fb-117">MaxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="f13fb-117">MaxReceivedMessageSize</span></span>  
 <span data-ttu-id="f13fb-118">Datentyp: sint64</span><span class="sxs-lookup"><span data-stu-id="f13fb-118">Data type: sint64</span></span>  
  
 <span data-ttu-id="f13fb-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f13fb-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f13fb-120">Die maximale Größe einer Nachricht, die von dieser Bindung verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="f13fb-120">The maximum size for a message that is processed by this binding.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="f13fb-121">Schema</span><span class="sxs-lookup"><span data-stu-id="f13fb-121">Scheme</span></span>  
 <span data-ttu-id="f13fb-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="f13fb-122">Data type: string</span></span>  
  
 <span data-ttu-id="f13fb-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f13fb-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f13fb-124">Das URI-Schema für den Transport.</span><span class="sxs-lookup"><span data-stu-id="f13fb-124">The URI scheme for the transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f13fb-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f13fb-125">Requirements</span></span>  
  
|<span data-ttu-id="f13fb-126">MOF</span><span class="sxs-lookup"><span data-stu-id="f13fb-126">MOF</span></span>|<span data-ttu-id="f13fb-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f13fb-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f13fb-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="f13fb-128">Namespace</span></span>|<span data-ttu-id="f13fb-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f13fb-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f13fb-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f13fb-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TransportBindingElement>
