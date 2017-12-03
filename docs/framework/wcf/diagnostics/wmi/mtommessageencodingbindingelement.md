---
title: MtomMessageEncodingBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 867b4a2b84a28dff4e3b9e4fc9d3c52065de212f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="mtommessageencodingbindingelement"></a><span data-ttu-id="93c1d-102">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="93c1d-102">MtomMessageEncodingBindingElement</span></span>
<span data-ttu-id="93c1d-103">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="93c1d-103">MtomMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93c1d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="93c1d-104">Syntax</span></span>  
  
```  
class MtomMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="93c1d-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="93c1d-105">Methods</span></span>  
 <span data-ttu-id="93c1d-106">Die Klasse MtomMessageEncodingBindingElement definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="93c1d-106">The MtomMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="93c1d-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="93c1d-107">Properties</span></span>  
 <span data-ttu-id="93c1d-108">Die Klasse MtomMessageEncodingBindingElement verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="93c1d-108">The MtomMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="93c1d-109">Codierung</span><span class="sxs-lookup"><span data-stu-id="93c1d-109">Encoding</span></span>  
 <span data-ttu-id="93c1d-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="93c1d-110">Data type: string</span></span>  
  
 <span data-ttu-id="93c1d-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="93c1d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="93c1d-112">Die Zeichensatzcodierung, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="93c1d-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="93c1d-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="93c1d-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="93c1d-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="93c1d-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="93c1d-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="93c1d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="93c1d-116">Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gelesen werden können, ohne neue Leser zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="93c1d-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="93c1d-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="93c1d-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="93c1d-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="93c1d-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="93c1d-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="93c1d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="93c1d-120">Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gesendet werden können, ohne neue Schreiber zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="93c1d-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="93c1d-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="93c1d-121">ReaderQuotas</span></span>  
 <span data-ttu-id="93c1d-122">Datentyp: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="93c1d-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="93c1d-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="93c1d-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="93c1d-124">Die Kontingente der Leser.</span><span class="sxs-lookup"><span data-stu-id="93c1d-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93c1d-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="93c1d-125">Requirements</span></span>  
  
|<span data-ttu-id="93c1d-126">MOF</span><span class="sxs-lookup"><span data-stu-id="93c1d-126">MOF</span></span>|<span data-ttu-id="93c1d-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="93c1d-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="93c1d-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="93c1d-128">Namespace</span></span>|<span data-ttu-id="93c1d-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="93c1d-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="93c1d-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93c1d-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
