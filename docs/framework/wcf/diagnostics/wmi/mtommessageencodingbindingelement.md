---
title: MtomMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
ms.openlocfilehash: aed65311d2b36a5dc764511de04e34c4bfb69d7b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963244"
---
# <a name="mtommessageencodingbindingelement"></a><span data-ttu-id="d4920-102">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="d4920-102">MtomMessageEncodingBindingElement</span></span>
<span data-ttu-id="d4920-103">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="d4920-103">MtomMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4920-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d4920-104">Syntax</span></span>  
  
```csharp
class MtomMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d4920-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="d4920-105">Methods</span></span>  
 <span data-ttu-id="d4920-106">Die Klasse MtomMessageEncodingBindingElement definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="d4920-106">The MtomMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d4920-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d4920-107">Properties</span></span>  
 <span data-ttu-id="d4920-108">Die Klasse MtomMessageEncodingBindingElement verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="d4920-108">The MtomMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="d4920-109">Codierung</span><span class="sxs-lookup"><span data-stu-id="d4920-109">Encoding</span></span>  
 <span data-ttu-id="d4920-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="d4920-110">Data type: string</span></span>  
  
 <span data-ttu-id="d4920-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d4920-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4920-112">Die Zeichensatzcodierung, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d4920-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="d4920-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="d4920-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="d4920-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="d4920-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="d4920-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d4920-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4920-116">Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gelesen werden können, ohne neue Leser zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="d4920-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="d4920-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="d4920-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="d4920-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="d4920-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="d4920-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d4920-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4920-120">Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gesendet werden können, ohne neue Schreiber zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="d4920-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="d4920-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="d4920-121">ReaderQuotas</span></span>  
 <span data-ttu-id="d4920-122">Datentyp: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="d4920-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="d4920-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d4920-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4920-124">Die Kontingente der Leser.</span><span class="sxs-lookup"><span data-stu-id="d4920-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4920-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d4920-125">Requirements</span></span>  
  
|<span data-ttu-id="d4920-126">MOF</span><span class="sxs-lookup"><span data-stu-id="d4920-126">MOF</span></span>|<span data-ttu-id="d4920-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="d4920-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d4920-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="d4920-128">Namespace</span></span>|<span data-ttu-id="d4920-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d4920-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d4920-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4920-130">See also</span></span>

- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
