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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c130093b9600c324e7179febce6857341b8a7d3c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="transportbindingelement"></a><span data-ttu-id="ab9de-102">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="ab9de-102">TransportBindingElement</span></span>
<span data-ttu-id="ab9de-103">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="ab9de-103">TransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab9de-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ab9de-104">Syntax</span></span>  
  
```  
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ab9de-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="ab9de-105">Methods</span></span>  
 <span data-ttu-id="ab9de-106">Von der Klasse TransportBindingElement werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="ab9de-106">The TransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ab9de-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ab9de-107">Properties</span></span>  
 <span data-ttu-id="ab9de-108">Die Klasse TransportBindingElement verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="ab9de-108">The TransportBindingElement class has the following properties:</span></span>  
  
### <a name="manualaddressing"></a><span data-ttu-id="ab9de-109">ManualAddressing</span><span class="sxs-lookup"><span data-stu-id="ab9de-109">ManualAddressing</span></span>  
 <span data-ttu-id="ab9de-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="ab9de-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="ab9de-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ab9de-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ab9de-112">Ein boolescher Wert, der angibt, ob der Benutzer die Kontrolle über die Nachrichtenadressierung übernehmen möchte.</span><span class="sxs-lookup"><span data-stu-id="ab9de-112">A boolean value that specifies whether the user wants to take control of message addressing.</span></span>  
  
### <a name="maxbufferpoolsize"></a><span data-ttu-id="ab9de-113">MaxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="ab9de-113">MaxBufferPoolSize</span></span>  
 <span data-ttu-id="ab9de-114">Datentyp: sint64</span><span class="sxs-lookup"><span data-stu-id="ab9de-114">Data type: sint64</span></span>  
  
 <span data-ttu-id="ab9de-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ab9de-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ab9de-116">Die maximale Pufferpoolgröße der Bindung.</span><span class="sxs-lookup"><span data-stu-id="ab9de-116">The maximum buffer pool size for the binding.</span></span>  
  
### <a name="maxreceivedmessagesize"></a><span data-ttu-id="ab9de-117">MaxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="ab9de-117">MaxReceivedMessageSize</span></span>  
 <span data-ttu-id="ab9de-118">Datentyp: sint64</span><span class="sxs-lookup"><span data-stu-id="ab9de-118">Data type: sint64</span></span>  
  
 <span data-ttu-id="ab9de-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ab9de-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ab9de-120">Die maximale Größe einer Nachricht, die von dieser Bindung verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="ab9de-120">The maximum size for a message that is processed by this binding.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="ab9de-121">Schema</span><span class="sxs-lookup"><span data-stu-id="ab9de-121">Scheme</span></span>  
 <span data-ttu-id="ab9de-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="ab9de-122">Data type: string</span></span>  
  
 <span data-ttu-id="ab9de-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ab9de-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ab9de-124">Das URI-Schema für den Transport.</span><span class="sxs-lookup"><span data-stu-id="ab9de-124">The URI scheme for the transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab9de-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ab9de-125">Requirements</span></span>  
  
|<span data-ttu-id="ab9de-126">MOF</span><span class="sxs-lookup"><span data-stu-id="ab9de-126">MOF</span></span>|<span data-ttu-id="ab9de-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ab9de-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ab9de-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="ab9de-128">Namespace</span></span>|<span data-ttu-id="ab9de-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ab9de-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ab9de-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab9de-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TransportBindingElement>
