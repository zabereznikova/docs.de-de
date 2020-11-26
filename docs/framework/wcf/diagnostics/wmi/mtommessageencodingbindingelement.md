---
title: MtomMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
ms.openlocfilehash: b4d8503543c93d0112fc39e4b2dba5434bc56472
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96237403"
---
# <a name="mtommessageencodingbindingelement"></a><span data-ttu-id="52be2-102">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="52be2-102">MtomMessageEncodingBindingElement</span></span>

<span data-ttu-id="52be2-103">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="52be2-103">MtomMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52be2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="52be2-104">Syntax</span></span>  
  
```csharp
class MtomMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="52be2-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="52be2-105">Methods</span></span>  

 <span data-ttu-id="52be2-106">Die Klasse MtomMessageEncodingBindingElement definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="52be2-106">The MtomMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="52be2-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="52be2-107">Properties</span></span>  

 <span data-ttu-id="52be2-108">Die Klasse MtomMessageEncodingBindingElement verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="52be2-108">The MtomMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="52be2-109">Codierung</span><span class="sxs-lookup"><span data-stu-id="52be2-109">Encoding</span></span>  

 <span data-ttu-id="52be2-110">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="52be2-110">Data type: string</span></span>  
  
 <span data-ttu-id="52be2-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="52be2-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="52be2-112">Die Zeichensatzcodierung, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="52be2-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="52be2-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="52be2-113">MaxReadPoolSize</span></span>  

 <span data-ttu-id="52be2-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="52be2-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="52be2-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="52be2-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="52be2-116">Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gelesen werden können, ohne neue Leser zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="52be2-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="52be2-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="52be2-117">MaxWritePoolSize</span></span>  

 <span data-ttu-id="52be2-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="52be2-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="52be2-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="52be2-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="52be2-120">Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gesendet werden können, ohne neue Schreiber zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="52be2-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="52be2-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="52be2-121">ReaderQuotas</span></span>  

 <span data-ttu-id="52be2-122">Datentyp: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="52be2-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="52be2-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="52be2-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="52be2-124">Die Kontingente der Leser.</span><span class="sxs-lookup"><span data-stu-id="52be2-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52be2-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="52be2-125">Requirements</span></span>  
  
|<span data-ttu-id="52be2-126">MOF</span><span class="sxs-lookup"><span data-stu-id="52be2-126">MOF</span></span>|<span data-ttu-id="52be2-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="52be2-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="52be2-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="52be2-128">Namespace</span></span>|<span data-ttu-id="52be2-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="52be2-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="52be2-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="52be2-130">See also</span></span>

- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
