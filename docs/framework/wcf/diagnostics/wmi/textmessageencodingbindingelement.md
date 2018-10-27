---
title: TextMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 885e2d7a-3436-4093-bc5f-0a404c62acdc
ms.openlocfilehash: 2371c38aebe2bd8d6da93d702801556fad986ef9
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452572"
---
# <a name="textmessageencodingbindingelement"></a><span data-ttu-id="f0ef0-102">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="f0ef0-102">TextMessageEncodingBindingElement</span></span>
<span data-ttu-id="f0ef0-103">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="f0ef0-103">TextMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0ef0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0ef0-104">Syntax</span></span>  
  
```csharp
class TextMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f0ef0-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="f0ef0-105">Methods</span></span>  
 <span data-ttu-id="f0ef0-106">Die TextMessageEncodingBindingElement-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="f0ef0-106">The TextMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f0ef0-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f0ef0-107">Properties</span></span>  
 <span data-ttu-id="f0ef0-108">Die TextMessageEncodingBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="f0ef0-108">The TextMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="f0ef0-109">Codierung</span><span class="sxs-lookup"><span data-stu-id="f0ef0-109">Encoding</span></span>  
 <span data-ttu-id="f0ef0-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="f0ef0-110">Data type: string</span></span>  
  
 <span data-ttu-id="f0ef0-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f0ef0-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f0ef0-112">Die Zeichensatzcodierung, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f0ef0-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="f0ef0-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="f0ef0-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="f0ef0-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="f0ef0-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="f0ef0-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f0ef0-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f0ef0-116">Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gelesen werden können, ohne neue Leser zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="f0ef0-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="f0ef0-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="f0ef0-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="f0ef0-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="f0ef0-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="f0ef0-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f0ef0-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f0ef0-120">Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gesendet werden können, ohne neue Schreiber zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="f0ef0-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="f0ef0-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="f0ef0-121">ReaderQuotas</span></span>  
 <span data-ttu-id="f0ef0-122">Datentyp: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="f0ef0-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="f0ef0-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f0ef0-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f0ef0-124">Die Kontingente der Leser.</span><span class="sxs-lookup"><span data-stu-id="f0ef0-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0ef0-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f0ef0-125">Requirements</span></span>  
  
|<span data-ttu-id="f0ef0-126">MOF</span><span class="sxs-lookup"><span data-stu-id="f0ef0-126">MOF</span></span>|<span data-ttu-id="f0ef0-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f0ef0-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f0ef0-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="f0ef0-128">Namespace</span></span>|<span data-ttu-id="f0ef0-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f0ef0-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f0ef0-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0ef0-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
