---
title: MsmqTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
ms.openlocfilehash: 6590c5188e4e1758987a75fbd007099703ea6bc5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250423"
---
# <a name="msmqtransportbindingelement"></a><span data-ttu-id="a3dc4-102">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="a3dc4-102">MsmqTransportBindingElement</span></span>

<span data-ttu-id="a3dc4-103">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="a3dc4-103">MsmqTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3dc4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a3dc4-104">Syntax</span></span>  
  
```csharp
class MsmqTransportBindingElement : MsmqBindingElementBase  
{  
  sint32 MaxPoolSize;  
  string QueueTransferProtocol;  
  boolean UseActiveDirectory;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a3dc4-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="a3dc4-105">Methods</span></span>  

 <span data-ttu-id="a3dc4-106">Von der MsmqTransportBindingElement-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="a3dc4-106">The MsmqTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a3dc4-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a3dc4-107">Properties</span></span>  

 <span data-ttu-id="a3dc4-108">Die MsmqTransportBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="a3dc4-108">The MsmqTransportBindingElement class has the following properties:</span></span>  
  
### <a name="maxpoolsize"></a><span data-ttu-id="a3dc4-109">MaxPoolSize</span><span class="sxs-lookup"><span data-stu-id="a3dc4-109">MaxPoolSize</span></span>  

 <span data-ttu-id="a3dc4-110">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="a3dc4-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="a3dc4-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a3dc4-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a3dc4-112">Maximale Größe des Pools, der interne MSMQ-Nachrichtenobjekte enthält.</span><span class="sxs-lookup"><span data-stu-id="a3dc4-112">The maximum size of the pool that contains internal MSMQ message objects.</span></span>  
  
### <a name="queuetransferprotocol"></a><span data-ttu-id="a3dc4-113">QueueTransferProtocol</span><span class="sxs-lookup"><span data-stu-id="a3dc4-113">QueueTransferProtocol</span></span>  

 <span data-ttu-id="a3dc4-114">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="a3dc4-114">Data type: string</span></span>  
  
 <span data-ttu-id="a3dc4-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a3dc4-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a3dc4-116">Enumerationswert, der den Wartenschlangentransport für den Kommunikationskanal angibt, der von der Bindung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a3dc4-116">An enumeration value that indicates the queued communication channel transport that this binding uses.</span></span>  
  
### <a name="useactivedirectory"></a><span data-ttu-id="a3dc4-117">UseActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="a3dc4-117">UseActiveDirectory</span></span>  

 <span data-ttu-id="a3dc4-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="a3dc4-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="a3dc4-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a3dc4-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a3dc4-120">Gibt einen booleschen Wert zurück, der angibt, ob Warteschlangenadressen mit Active Directory konvertiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a3dc4-120">Returns a Boolean value that indicates whether queue addresses should be converted using Active Directory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3dc4-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a3dc4-121">Requirements</span></span>  
  
|<span data-ttu-id="a3dc4-122">MOF</span><span class="sxs-lookup"><span data-stu-id="a3dc4-122">MOF</span></span>|<span data-ttu-id="a3dc4-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="a3dc4-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a3dc4-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="a3dc4-124">Namespace</span></span>|<span data-ttu-id="a3dc4-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a3dc4-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a3dc4-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a3dc4-126">See also</span></span>

- <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>
