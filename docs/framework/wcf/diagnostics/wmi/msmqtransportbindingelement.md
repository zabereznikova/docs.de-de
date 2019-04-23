---
title: MsmqTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
ms.openlocfilehash: 706cec5c414197ebabda7939728b95be32582e0f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59770749"
---
# <a name="msmqtransportbindingelement"></a><span data-ttu-id="9c2b3-102">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="9c2b3-102">MsmqTransportBindingElement</span></span>
<span data-ttu-id="9c2b3-103">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="9c2b3-103">MsmqTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c2b3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9c2b3-104">Syntax</span></span>  
  
```csharp
class MsmqTransportBindingElement : MsmqBindingElementBase  
{  
  sint32 MaxPoolSize;  
  string QueueTransferProtocol;  
  boolean UseActiveDirectory;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9c2b3-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="9c2b3-105">Methods</span></span>  
 <span data-ttu-id="9c2b3-106">Von der MsmqTransportBindingElement-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="9c2b3-106">The MsmqTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9c2b3-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9c2b3-107">Properties</span></span>  
 <span data-ttu-id="9c2b3-108">Die MsmqTransportBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="9c2b3-108">The MsmqTransportBindingElement class has the following properties:</span></span>  
  
### <a name="maxpoolsize"></a><span data-ttu-id="9c2b3-109">MaxPoolSize</span><span class="sxs-lookup"><span data-stu-id="9c2b3-109">MaxPoolSize</span></span>  
 <span data-ttu-id="9c2b3-110">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="9c2b3-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="9c2b3-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9c2b3-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9c2b3-112">Maximale Größe des Pools, der interne MSMQ-Nachrichtenobjekte enthält.</span><span class="sxs-lookup"><span data-stu-id="9c2b3-112">The maximum size of the pool that contains internal MSMQ message objects.</span></span>  
  
### <a name="queuetransferprotocol"></a><span data-ttu-id="9c2b3-113">QueueTransferProtocol</span><span class="sxs-lookup"><span data-stu-id="9c2b3-113">QueueTransferProtocol</span></span>  
 <span data-ttu-id="9c2b3-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="9c2b3-114">Data type: string</span></span>  
  
 <span data-ttu-id="9c2b3-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9c2b3-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9c2b3-116">Enumerationswert, der den Wartenschlangentransport für den Kommunikationskanal angibt, der von der Bindung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9c2b3-116">An enumeration value that indicates the queued communication channel transport that this binding uses.</span></span>  
  
### <a name="useactivedirectory"></a><span data-ttu-id="9c2b3-117">UseActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="9c2b3-117">UseActiveDirectory</span></span>  
 <span data-ttu-id="9c2b3-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="9c2b3-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="9c2b3-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9c2b3-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9c2b3-120">Gibt einen booleschen Wert zurück, der angibt, ob Warteschlangenadressen mit Active Directory konvertiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9c2b3-120">Returns a Boolean value that indicates whether queue addresses should be converted using Active Directory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c2b3-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9c2b3-121">Requirements</span></span>  
  
|<span data-ttu-id="9c2b3-122">MOF</span><span class="sxs-lookup"><span data-stu-id="9c2b3-122">MOF</span></span>|<span data-ttu-id="9c2b3-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="9c2b3-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9c2b3-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="9c2b3-124">Namespace</span></span>|<span data-ttu-id="9c2b3-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9c2b3-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9c2b3-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c2b3-126">See also</span></span>

- <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>
