---
title: MsmqTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c4cfa3d58127fa560f39ce0dcfe51b97ded6223a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="msmqtransportbindingelement"></a><span data-ttu-id="2d532-102">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="2d532-102">MsmqTransportBindingElement</span></span>
<span data-ttu-id="2d532-103">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="2d532-103">MsmqTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d532-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d532-104">Syntax</span></span>  
  
```  
class MsmqTransportBindingElement : MsmqBindingElementBase  
{  
  sint32 MaxPoolSize;  
  string QueueTransferProtocol;  
  boolean UseActiveDirectory;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="2d532-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="2d532-105">Methods</span></span>  
 <span data-ttu-id="2d532-106">Von der MsmqTransportBindingElement-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="2d532-106">The MsmqTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="2d532-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2d532-107">Properties</span></span>  
 <span data-ttu-id="2d532-108">Die MsmqTransportBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="2d532-108">The MsmqTransportBindingElement class has the following properties:</span></span>  
  
### <a name="maxpoolsize"></a><span data-ttu-id="2d532-109">MaxPoolSize</span><span class="sxs-lookup"><span data-stu-id="2d532-109">MaxPoolSize</span></span>  
 <span data-ttu-id="2d532-110">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="2d532-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="2d532-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="2d532-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2d532-112">Maximale Größe des Pools, der interne MSMQ-Nachrichtenobjekte enthält.</span><span class="sxs-lookup"><span data-stu-id="2d532-112">The maximum size of the pool that contains internal MSMQ message objects.</span></span>  
  
### <a name="queuetransferprotocol"></a><span data-ttu-id="2d532-113">QueueTransferProtocol</span><span class="sxs-lookup"><span data-stu-id="2d532-113">QueueTransferProtocol</span></span>  
 <span data-ttu-id="2d532-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="2d532-114">Data type: string</span></span>  
  
 <span data-ttu-id="2d532-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="2d532-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2d532-116">Enumerationswert, der den Wartenschlangentransport für den Kommunikationskanal angibt, der von der Bindung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2d532-116">An enumeration value that indicates the queued communication channel transport that this binding uses.</span></span>  
  
### <a name="useactivedirectory"></a><span data-ttu-id="2d532-117">UseActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="2d532-117">UseActiveDirectory</span></span>  
 <span data-ttu-id="2d532-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="2d532-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="2d532-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="2d532-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2d532-120">Gibt einen booleschen Wert zurück, der angibt, ob Warteschlangenadressen mit Active Directory konvertiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2d532-120">Returns a Boolean value that indicates whether queue addresses should be converted using Active Directory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d532-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2d532-121">Requirements</span></span>  
  
|<span data-ttu-id="2d532-122">MOF</span><span class="sxs-lookup"><span data-stu-id="2d532-122">MOF</span></span>|<span data-ttu-id="2d532-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="2d532-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="2d532-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="2d532-124">Namespace</span></span>|<span data-ttu-id="2d532-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2d532-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2d532-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d532-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>
