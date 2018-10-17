---
title: MtomMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
ms.openlocfilehash: 49a640a666131491366646d6d486d25a515e35bf
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2018
ms.locfileid: "49373431"
---
# <a name="mtommessageencodingbindingelement"></a><span data-ttu-id="3ebfc-102">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="3ebfc-102">MtomMessageEncodingBindingElement</span></span>
<span data-ttu-id="3ebfc-103">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="3ebfc-103">MtomMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ebfc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3ebfc-104">Syntax</span></span>  
  
```csharp
class MtomMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3ebfc-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="3ebfc-105">Methods</span></span>  
 <span data-ttu-id="3ebfc-106">Die Klasse MtomMessageEncodingBindingElement definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="3ebfc-106">The MtomMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3ebfc-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="3ebfc-107">Properties</span></span>  
 <span data-ttu-id="3ebfc-108">Die Klasse MtomMessageEncodingBindingElement verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="3ebfc-108">The MtomMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="3ebfc-109">Codierung</span><span class="sxs-lookup"><span data-stu-id="3ebfc-109">Encoding</span></span>  
 <span data-ttu-id="3ebfc-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="3ebfc-110">Data type: string</span></span>  
  
 <span data-ttu-id="3ebfc-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="3ebfc-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3ebfc-112">Die Zeichensatzcodierung, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3ebfc-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="3ebfc-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="3ebfc-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="3ebfc-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="3ebfc-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="3ebfc-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="3ebfc-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3ebfc-116">Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gelesen werden können, ohne neue Leser zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="3ebfc-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="3ebfc-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="3ebfc-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="3ebfc-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="3ebfc-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="3ebfc-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="3ebfc-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3ebfc-120">Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gesendet werden können, ohne neue Schreiber zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="3ebfc-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="3ebfc-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="3ebfc-121">ReaderQuotas</span></span>  
 <span data-ttu-id="3ebfc-122">Datentyp: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="3ebfc-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="3ebfc-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="3ebfc-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3ebfc-124">Die Kontingente der Leser.</span><span class="sxs-lookup"><span data-stu-id="3ebfc-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ebfc-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3ebfc-125">Requirements</span></span>  
  
|<span data-ttu-id="3ebfc-126">MOF</span><span class="sxs-lookup"><span data-stu-id="3ebfc-126">MOF</span></span>|<span data-ttu-id="3ebfc-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="3ebfc-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3ebfc-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="3ebfc-128">Namespace</span></span>|<span data-ttu-id="3ebfc-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3ebfc-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3ebfc-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ebfc-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
