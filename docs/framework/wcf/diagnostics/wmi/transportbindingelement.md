---
title: TransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 062b45eb5d627903142ca1a5fd4db6df0855384b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="transportbindingelement"></a><span data-ttu-id="56317-102">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="56317-102">TransportBindingElement</span></span>
<span data-ttu-id="56317-103">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="56317-103">TransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56317-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="56317-104">Syntax</span></span>  
  
```  
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="56317-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="56317-105">Methods</span></span>  
 <span data-ttu-id="56317-106">Von der Klasse TransportBindingElement werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="56317-106">The TransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="56317-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="56317-107">Properties</span></span>  
 <span data-ttu-id="56317-108">Die Klasse TransportBindingElement verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="56317-108">The TransportBindingElement class has the following properties:</span></span>  
  
### <a name="manualaddressing"></a><span data-ttu-id="56317-109">ManualAddressing</span><span class="sxs-lookup"><span data-stu-id="56317-109">ManualAddressing</span></span>  
 <span data-ttu-id="56317-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="56317-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="56317-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="56317-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="56317-112">Ein boolescher Wert, der angibt, ob der Benutzer die Kontrolle über die Nachrichtenadressierung übernehmen möchte.</span><span class="sxs-lookup"><span data-stu-id="56317-112">A boolean value that specifies whether the user wants to take control of message addressing.</span></span>  
  
### <a name="maxbufferpoolsize"></a><span data-ttu-id="56317-113">MaxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="56317-113">MaxBufferPoolSize</span></span>  
 <span data-ttu-id="56317-114">Datentyp: sint64</span><span class="sxs-lookup"><span data-stu-id="56317-114">Data type: sint64</span></span>  
  
 <span data-ttu-id="56317-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="56317-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="56317-116">Die maximale Pufferpoolgröße der Bindung.</span><span class="sxs-lookup"><span data-stu-id="56317-116">The maximum buffer pool size for the binding.</span></span>  
  
### <a name="maxreceivedmessagesize"></a><span data-ttu-id="56317-117">MaxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="56317-117">MaxReceivedMessageSize</span></span>  
 <span data-ttu-id="56317-118">Datentyp: sint64</span><span class="sxs-lookup"><span data-stu-id="56317-118">Data type: sint64</span></span>  
  
 <span data-ttu-id="56317-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="56317-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="56317-120">Die maximale Größe einer Nachricht, die von dieser Bindung verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="56317-120">The maximum size for a message that is processed by this binding.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="56317-121">Schema</span><span class="sxs-lookup"><span data-stu-id="56317-121">Scheme</span></span>  
 <span data-ttu-id="56317-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="56317-122">Data type: string</span></span>  
  
 <span data-ttu-id="56317-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="56317-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="56317-124">Das URI-Schema für den Transport.</span><span class="sxs-lookup"><span data-stu-id="56317-124">The URI scheme for the transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56317-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="56317-125">Requirements</span></span>  
  
|<span data-ttu-id="56317-126">MOF</span><span class="sxs-lookup"><span data-stu-id="56317-126">MOF</span></span>|<span data-ttu-id="56317-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="56317-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="56317-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="56317-128">Namespace</span></span>|<span data-ttu-id="56317-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="56317-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="56317-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="56317-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TransportBindingElement>
