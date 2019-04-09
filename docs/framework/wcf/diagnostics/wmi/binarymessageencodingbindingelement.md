---
title: BinaryMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: e2bb3cdd-3bbd-4bb5-85fe-570457500a66
ms.openlocfilehash: e0551e7b4b05151490625912742aa6b26ef0216e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145677"
---
# <a name="binarymessageencodingbindingelement"></a><span data-ttu-id="932cf-102">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="932cf-102">BinaryMessageEncodingBindingElement</span></span>
<span data-ttu-id="932cf-103">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="932cf-103">BinaryMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="932cf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="932cf-104">Syntax</span></span>  
  
```csharp  
class BinaryMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  sint32 MaxReadPoolSize;  
  sint32 MaxSessionSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="932cf-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="932cf-105">Methods</span></span>  
 <span data-ttu-id="932cf-106">Die BinaryMessageEncodingBindingElement-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="932cf-106">The BinaryMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="932cf-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="932cf-107">Properties</span></span>  
 <span data-ttu-id="932cf-108">Die BinaryMessageEncodingBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="932cf-108">The BinaryMessageEncodingBindingElement class has the following properties.</span></span>  
  
## <a name="maxreadpoolsize"></a><span data-ttu-id="932cf-109">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="932cf-109">MaxReadPoolSize</span></span>  
 <span data-ttu-id="932cf-110">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="932cf-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="932cf-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="932cf-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="932cf-112">Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gelesen werden können, ohne neue Leser zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="932cf-112">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
## <a name="maxsessionsize"></a><span data-ttu-id="932cf-113">MaxSessionSize</span><span class="sxs-lookup"><span data-stu-id="932cf-113">MaxSessionSize</span></span>  
 <span data-ttu-id="932cf-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="932cf-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="932cf-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="932cf-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="932cf-116">Dieser Wert gibt die Größe des für die Codierung verwendeten Puffers an (in Byte).</span><span class="sxs-lookup"><span data-stu-id="932cf-116">A value that specifies the size, in bytes, of the buffer used for encoding.</span></span>  
  
## <a name="maxwritepoolsize"></a><span data-ttu-id="932cf-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="932cf-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="932cf-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="932cf-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="932cf-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="932cf-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="932cf-120">Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gesendet werden können, ohne neue Schreiber zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="932cf-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
## <a name="readerquotas"></a><span data-ttu-id="932cf-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="932cf-121">ReaderQuotas</span></span>  
 <span data-ttu-id="932cf-122">Datentyp: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="932cf-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="932cf-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="932cf-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="932cf-124">Die Kontingente der Leser.</span><span class="sxs-lookup"><span data-stu-id="932cf-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="932cf-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="932cf-125">Requirements</span></span>  
  
|<span data-ttu-id="932cf-126">MOF</span><span class="sxs-lookup"><span data-stu-id="932cf-126">MOF</span></span>|<span data-ttu-id="932cf-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="932cf-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="932cf-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="932cf-128">Namespace</span></span>|<span data-ttu-id="932cf-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="932cf-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="932cf-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="932cf-130">See also</span></span>

- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
