---
title: BinaryMessageEncodingBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e2bb3cdd-3bbd-4bb5-85fe-570457500a66
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: adac65808853ec75e37245c8c9fa031a533c22a6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="binarymessageencodingbindingelement"></a><span data-ttu-id="40a6e-102">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="40a6e-102">BinaryMessageEncodingBindingElement</span></span>
<span data-ttu-id="40a6e-103">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="40a6e-103">BinaryMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40a6e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="40a6e-104">Syntax</span></span>  
  
```  
class BinaryMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  sint32 MaxReadPoolSize;  
  sint32 MaxSessionSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="40a6e-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="40a6e-105">Methods</span></span>  
 <span data-ttu-id="40a6e-106">Die BinaryMessageEncodingBindingElement-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="40a6e-106">The BinaryMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="40a6e-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="40a6e-107">Properties</span></span>  
 <span data-ttu-id="40a6e-108">Die BinaryMessageEncodingBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="40a6e-108">The BinaryMessageEncodingBindingElement class has the following properties.</span></span>  
  
## <a name="maxreadpoolsize"></a><span data-ttu-id="40a6e-109">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="40a6e-109">MaxReadPoolSize</span></span>  
 <span data-ttu-id="40a6e-110">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="40a6e-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="40a6e-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="40a6e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="40a6e-112">Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gelesen werden können, ohne neue Leser zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="40a6e-112">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
## <a name="maxsessionsize"></a><span data-ttu-id="40a6e-113">MaxSessionSize</span><span class="sxs-lookup"><span data-stu-id="40a6e-113">MaxSessionSize</span></span>  
 <span data-ttu-id="40a6e-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="40a6e-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="40a6e-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="40a6e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="40a6e-116">Dieser Wert gibt die Größe des für die Codierung verwendeten Puffers an (in Byte).</span><span class="sxs-lookup"><span data-stu-id="40a6e-116">A value that specifies the size, in bytes, of the buffer used for encoding.</span></span>  
  
## <a name="maxwritepoolsize"></a><span data-ttu-id="40a6e-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="40a6e-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="40a6e-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="40a6e-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="40a6e-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="40a6e-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="40a6e-120">Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gesendet werden können, ohne neue Schreiber zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="40a6e-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
## <a name="readerquotas"></a><span data-ttu-id="40a6e-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="40a6e-121">ReaderQuotas</span></span>  
 <span data-ttu-id="40a6e-122">Datentyp: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="40a6e-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="40a6e-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="40a6e-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="40a6e-124">Die Kontingente der Leser.</span><span class="sxs-lookup"><span data-stu-id="40a6e-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40a6e-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="40a6e-125">Requirements</span></span>  
  
|<span data-ttu-id="40a6e-126">MOF</span><span class="sxs-lookup"><span data-stu-id="40a6e-126">MOF</span></span>|<span data-ttu-id="40a6e-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="40a6e-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="40a6e-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="40a6e-128">Namespace</span></span>|<span data-ttu-id="40a6e-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="40a6e-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="40a6e-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40a6e-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
