---
title: MsmqTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
ms.openlocfilehash: 33cd9c427ed5ad04eaf9e9889f60f091f335d1e7
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2018
ms.locfileid: "50198106"
---
# <a name="msmqtransportbindingelement"></a><span data-ttu-id="3ea52-102">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="3ea52-102">MsmqTransportBindingElement</span></span>
<span data-ttu-id="3ea52-103">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="3ea52-103">MsmqTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ea52-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3ea52-104">Syntax</span></span>  
  
```csharp
class MsmqTransportBindingElement : MsmqBindingElementBase  
{  
  sint32 MaxPoolSize;  
  string QueueTransferProtocol;  
  boolean UseActiveDirectory;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3ea52-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="3ea52-105">Methods</span></span>  
 <span data-ttu-id="3ea52-106">Von der MsmqTransportBindingElement-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="3ea52-106">The MsmqTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3ea52-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="3ea52-107">Properties</span></span>  
 <span data-ttu-id="3ea52-108">Die MsmqTransportBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="3ea52-108">The MsmqTransportBindingElement class has the following properties:</span></span>  
  
### <a name="maxpoolsize"></a><span data-ttu-id="3ea52-109">MaxPoolSize</span><span class="sxs-lookup"><span data-stu-id="3ea52-109">MaxPoolSize</span></span>  
 <span data-ttu-id="3ea52-110">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="3ea52-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="3ea52-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="3ea52-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3ea52-112">Maximale Größe des Pools, der interne MSMQ-Nachrichtenobjekte enthält.</span><span class="sxs-lookup"><span data-stu-id="3ea52-112">The maximum size of the pool that contains internal MSMQ message objects.</span></span>  
  
### <a name="queuetransferprotocol"></a><span data-ttu-id="3ea52-113">QueueTransferProtocol</span><span class="sxs-lookup"><span data-stu-id="3ea52-113">QueueTransferProtocol</span></span>  
 <span data-ttu-id="3ea52-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="3ea52-114">Data type: string</span></span>  
  
 <span data-ttu-id="3ea52-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="3ea52-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3ea52-116">Enumerationswert, der den Wartenschlangentransport für den Kommunikationskanal angibt, der von der Bindung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3ea52-116">An enumeration value that indicates the queued communication channel transport that this binding uses.</span></span>  
  
### <a name="useactivedirectory"></a><span data-ttu-id="3ea52-117">UseActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="3ea52-117">UseActiveDirectory</span></span>  
 <span data-ttu-id="3ea52-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="3ea52-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="3ea52-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="3ea52-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3ea52-120">Gibt einen booleschen Wert zurück, der angibt, ob Warteschlangenadressen mit Active Directory konvertiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3ea52-120">Returns a Boolean value that indicates whether queue addresses should be converted using Active Directory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ea52-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3ea52-121">Requirements</span></span>  
  
|<span data-ttu-id="3ea52-122">MOF</span><span class="sxs-lookup"><span data-stu-id="3ea52-122">MOF</span></span>|<span data-ttu-id="3ea52-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="3ea52-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3ea52-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="3ea52-124">Namespace</span></span>|<span data-ttu-id="3ea52-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3ea52-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3ea52-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ea52-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>
