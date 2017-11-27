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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6e1eccbaae35a16fe4fb133296698d347c190e94
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="textmessageencodingbindingelement"></a><span data-ttu-id="ed2e6-102">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="ed2e6-102">TextMessageEncodingBindingElement</span></span>
<span data-ttu-id="ed2e6-103">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="ed2e6-103">TextMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed2e6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ed2e6-104">Syntax</span></span>  
  
```  
class TextMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ed2e6-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="ed2e6-105">Methods</span></span>  
 <span data-ttu-id="ed2e6-106">Die TextMessageEncodingBindingElement-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="ed2e6-106">The TextMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ed2e6-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ed2e6-107">Properties</span></span>  
 <span data-ttu-id="ed2e6-108">Die TextMessageEncodingBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="ed2e6-108">The TextMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="ed2e6-109">Codierung</span><span class="sxs-lookup"><span data-stu-id="ed2e6-109">Encoding</span></span>  
 <span data-ttu-id="ed2e6-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="ed2e6-110">Data type: string</span></span>  
  
 <span data-ttu-id="ed2e6-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ed2e6-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ed2e6-112">Die Zeichensatzcodierung, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ed2e6-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="ed2e6-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="ed2e6-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="ed2e6-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="ed2e6-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="ed2e6-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ed2e6-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ed2e6-116">Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gelesen werden können, ohne neue Leser zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="ed2e6-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="ed2e6-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="ed2e6-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="ed2e6-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="ed2e6-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="ed2e6-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ed2e6-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ed2e6-120">Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gesendet werden können, ohne neue Schreiber zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="ed2e6-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="ed2e6-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="ed2e6-121">ReaderQuotas</span></span>  
 <span data-ttu-id="ed2e6-122">Datentyp: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="ed2e6-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="ed2e6-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ed2e6-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ed2e6-124">Die Kontingente der Leser.</span><span class="sxs-lookup"><span data-stu-id="ed2e6-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed2e6-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ed2e6-125">Requirements</span></span>  
  
|<span data-ttu-id="ed2e6-126">MOF</span><span class="sxs-lookup"><span data-stu-id="ed2e6-126">MOF</span></span>|<span data-ttu-id="ed2e6-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ed2e6-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ed2e6-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="ed2e6-128">Namespace</span></span>|<span data-ttu-id="ed2e6-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ed2e6-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ed2e6-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed2e6-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
