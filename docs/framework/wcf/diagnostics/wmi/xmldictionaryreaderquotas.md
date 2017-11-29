---
title: XmlDictionaryReaderQuotas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 980a7eacd095dc1b601d63f5a807f2e287c09885
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="4e76b-102">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="4e76b-102">XmlDictionaryReaderQuotas</span></span>
<span data-ttu-id="4e76b-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="4e76b-103">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e76b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e76b-104">Syntax</span></span>  
  
```  
class XmlDictionaryReaderQuotas  
{  
  sint32 MaxArrayLength;  
  sint32 MaxBytesPerRead;  
  sint32 MaxDepth;  
  sint32 MaxNameTableCharCount;  
  sint32 MaxStringContentLength;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4e76b-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="4e76b-105">Methods</span></span>  
 <span data-ttu-id="4e76b-106">Von der XmlDictionaryReaderQuotas-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="4e76b-106">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4e76b-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="4e76b-107">Properties</span></span>  
 <span data-ttu-id="4e76b-108">Die XmlDictionaryReaderQuotas-Klasse weist die folgenden Eigenschaften auf:</span><span class="sxs-lookup"><span data-stu-id="4e76b-108">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="4e76b-109">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="4e76b-109">MaxArrayLength</span></span>  
 <span data-ttu-id="4e76b-110">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="4e76b-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="4e76b-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="4e76b-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4e76b-112">Die maximal zulässige Arraylänge.</span><span class="sxs-lookup"><span data-stu-id="4e76b-112">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="4e76b-113">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="4e76b-113">MaxBytesPerRead</span></span>  
 <span data-ttu-id="4e76b-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="4e76b-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="4e76b-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="4e76b-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4e76b-116">Die maximal zulässigen Bytes, die bei jedem Lesevorgang zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4e76b-116">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="4e76b-117">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="4e76b-117">MaxDepth</span></span>  
 <span data-ttu-id="4e76b-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="4e76b-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="4e76b-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="4e76b-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4e76b-120">Die maximale geschachtelte Knotentiefe für jeden Lesevorgang.</span><span class="sxs-lookup"><span data-stu-id="4e76b-120">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="4e76b-121">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="4e76b-121">MaxNameTableCharCount</span></span>  
 <span data-ttu-id="4e76b-122">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="4e76b-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="4e76b-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="4e76b-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4e76b-124">Die maximal zulässigen Zeichen in einem Tabellennamen.</span><span class="sxs-lookup"><span data-stu-id="4e76b-124">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="4e76b-125">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="4e76b-125">MaxStringContentLength</span></span>  
 <span data-ttu-id="4e76b-126">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="4e76b-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="4e76b-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="4e76b-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4e76b-128">Die maximale Zeichenanzahl, die in XML-Elementinhalten zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="4e76b-128">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e76b-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4e76b-129">Requirements</span></span>  
  
|<span data-ttu-id="4e76b-130">MOF</span><span class="sxs-lookup"><span data-stu-id="4e76b-130">MOF</span></span>|<span data-ttu-id="4e76b-131">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="4e76b-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4e76b-132">Namespace</span><span class="sxs-lookup"><span data-stu-id="4e76b-132">Namespace</span></span>|<span data-ttu-id="4e76b-133">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4e76b-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4e76b-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e76b-134">See Also</span></span>  
 <xref:System.Xml.XmlDictionaryReaderQuotas>  
 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
