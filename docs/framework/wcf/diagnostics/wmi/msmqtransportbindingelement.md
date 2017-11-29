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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c0c2c5d54050216c91a318a407341c4ffb9cb687
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="msmqtransportbindingelement"></a><span data-ttu-id="a5369-102">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="a5369-102">MsmqTransportBindingElement</span></span>
<span data-ttu-id="a5369-103">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="a5369-103">MsmqTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5369-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a5369-104">Syntax</span></span>  
  
```  
class MsmqTransportBindingElement : MsmqBindingElementBase  
{  
  sint32 MaxPoolSize;  
  string QueueTransferProtocol;  
  boolean UseActiveDirectory;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a5369-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="a5369-105">Methods</span></span>  
 <span data-ttu-id="a5369-106">Von der MsmqTransportBindingElement-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="a5369-106">The MsmqTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a5369-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a5369-107">Properties</span></span>  
 <span data-ttu-id="a5369-108">Die MsmqTransportBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="a5369-108">The MsmqTransportBindingElement class has the following properties:</span></span>  
  
### <a name="maxpoolsize"></a><span data-ttu-id="a5369-109">MaxPoolSize</span><span class="sxs-lookup"><span data-stu-id="a5369-109">MaxPoolSize</span></span>  
 <span data-ttu-id="a5369-110">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="a5369-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="a5369-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a5369-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a5369-112">Maximale Größe des Pools, der interne MSMQ-Nachrichtenobjekte enthält.</span><span class="sxs-lookup"><span data-stu-id="a5369-112">The maximum size of the pool that contains internal MSMQ message objects.</span></span>  
  
### <a name="queuetransferprotocol"></a><span data-ttu-id="a5369-113">QueueTransferProtocol</span><span class="sxs-lookup"><span data-stu-id="a5369-113">QueueTransferProtocol</span></span>  
 <span data-ttu-id="a5369-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="a5369-114">Data type: string</span></span>  
  
 <span data-ttu-id="a5369-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a5369-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a5369-116">Enumerationswert, der den Wartenschlangentransport für den Kommunikationskanal angibt, der von der Bindung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a5369-116">An enumeration value that indicates the queued communication channel transport that this binding uses.</span></span>  
  
### <a name="useactivedirectory"></a><span data-ttu-id="a5369-117">UseActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="a5369-117">UseActiveDirectory</span></span>  
 <span data-ttu-id="a5369-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="a5369-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="a5369-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a5369-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a5369-120">Gibt einen booleschen Wert zurück, der angibt, ob Warteschlangenadressen mit Active Directory konvertiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a5369-120">Returns a Boolean value that indicates whether queue addresses should be converted using Active Directory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5369-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a5369-121">Requirements</span></span>  
  
|<span data-ttu-id="a5369-122">MOF</span><span class="sxs-lookup"><span data-stu-id="a5369-122">MOF</span></span>|<span data-ttu-id="a5369-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="a5369-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a5369-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="a5369-124">Namespace</span></span>|<span data-ttu-id="a5369-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a5369-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a5369-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5369-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>
