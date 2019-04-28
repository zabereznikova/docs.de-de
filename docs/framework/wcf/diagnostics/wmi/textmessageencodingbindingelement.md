---
title: TextMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 885e2d7a-3436-4093-bc5f-0a404c62acdc
ms.openlocfilehash: 67c1083daa9acfd204d4de50d4e9178b25aafcf0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61858389"
---
# <a name="textmessageencodingbindingelement"></a><span data-ttu-id="8af22-102">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="8af22-102">TextMessageEncodingBindingElement</span></span>
<span data-ttu-id="8af22-103">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="8af22-103">TextMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8af22-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8af22-104">Syntax</span></span>  
  
```csharp
class TextMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="8af22-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="8af22-105">Methods</span></span>  
 <span data-ttu-id="8af22-106">Die TextMessageEncodingBindingElement-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="8af22-106">The TextMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="8af22-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8af22-107">Properties</span></span>  
 <span data-ttu-id="8af22-108">Die TextMessageEncodingBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="8af22-108">The TextMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="8af22-109">Codierung</span><span class="sxs-lookup"><span data-stu-id="8af22-109">Encoding</span></span>  
 <span data-ttu-id="8af22-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="8af22-110">Data type: string</span></span>  
  
 <span data-ttu-id="8af22-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="8af22-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8af22-112">Die Zeichensatzcodierung, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8af22-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="8af22-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="8af22-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="8af22-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="8af22-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="8af22-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="8af22-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8af22-116">Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gelesen werden können, ohne neue Leser zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="8af22-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="8af22-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="8af22-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="8af22-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="8af22-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="8af22-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="8af22-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8af22-120">Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gesendet werden können, ohne neue Schreiber zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="8af22-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="8af22-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="8af22-121">ReaderQuotas</span></span>  
 <span data-ttu-id="8af22-122">Datentyp: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="8af22-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="8af22-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="8af22-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8af22-124">Die Kontingente der Leser.</span><span class="sxs-lookup"><span data-stu-id="8af22-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8af22-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8af22-125">Requirements</span></span>  
  
|<span data-ttu-id="8af22-126">MOF</span><span class="sxs-lookup"><span data-stu-id="8af22-126">MOF</span></span>|<span data-ttu-id="8af22-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="8af22-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="8af22-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="8af22-128">Namespace</span></span>|<span data-ttu-id="8af22-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="8af22-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8af22-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8af22-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
