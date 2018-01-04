---
title: TextMessageEncodingBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 885e2d7a-3436-4093-bc5f-0a404c62acdc
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3f1e026296745f6fc40171866c81f91818789e01
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="textmessageencodingbindingelement"></a><span data-ttu-id="82e68-102">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="82e68-102">TextMessageEncodingBindingElement</span></span>
<span data-ttu-id="82e68-103">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="82e68-103">TextMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82e68-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="82e68-104">Syntax</span></span>  
  
```  
class TextMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="82e68-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="82e68-105">Methods</span></span>  
 <span data-ttu-id="82e68-106">Die TextMessageEncodingBindingElement-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="82e68-106">The TextMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="82e68-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="82e68-107">Properties</span></span>  
 <span data-ttu-id="82e68-108">Die TextMessageEncodingBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="82e68-108">The TextMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="82e68-109">Codierung</span><span class="sxs-lookup"><span data-stu-id="82e68-109">Encoding</span></span>  
 <span data-ttu-id="82e68-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="82e68-110">Data type: string</span></span>  
  
 <span data-ttu-id="82e68-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="82e68-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="82e68-112">Die Zeichensatzcodierung, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="82e68-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="82e68-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="82e68-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="82e68-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="82e68-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="82e68-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="82e68-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="82e68-116">Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gelesen werden können, ohne neue Leser zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="82e68-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="82e68-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="82e68-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="82e68-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="82e68-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="82e68-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="82e68-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="82e68-120">Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gesendet werden können, ohne neue Schreiber zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="82e68-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="82e68-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="82e68-121">ReaderQuotas</span></span>  
 <span data-ttu-id="82e68-122">Datentyp: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="82e68-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="82e68-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="82e68-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="82e68-124">Die Kontingente der Leser.</span><span class="sxs-lookup"><span data-stu-id="82e68-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82e68-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="82e68-125">Requirements</span></span>  
  
|<span data-ttu-id="82e68-126">MOF</span><span class="sxs-lookup"><span data-stu-id="82e68-126">MOF</span></span>|<span data-ttu-id="82e68-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="82e68-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="82e68-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="82e68-128">Namespace</span></span>|<span data-ttu-id="82e68-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="82e68-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="82e68-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82e68-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
