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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 06c0ff11752ae1030e574182cfb825fb87ddc8c7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="6fed5-102">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="6fed5-102">XmlDictionaryReaderQuotas</span></span>
<span data-ttu-id="6fed5-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="6fed5-103">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fed5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6fed5-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="6fed5-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="6fed5-105">Methods</span></span>  
 <span data-ttu-id="6fed5-106">Von der XmlDictionaryReaderQuotas-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="6fed5-106">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6fed5-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="6fed5-107">Properties</span></span>  
 <span data-ttu-id="6fed5-108">Die XmlDictionaryReaderQuotas-Klasse weist die folgenden Eigenschaften auf:</span><span class="sxs-lookup"><span data-stu-id="6fed5-108">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="6fed5-109">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="6fed5-109">MaxArrayLength</span></span>  
 <span data-ttu-id="6fed5-110">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="6fed5-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="6fed5-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6fed5-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6fed5-112">Die maximal zulässige Arraylänge.</span><span class="sxs-lookup"><span data-stu-id="6fed5-112">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="6fed5-113">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="6fed5-113">MaxBytesPerRead</span></span>  
 <span data-ttu-id="6fed5-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="6fed5-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="6fed5-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6fed5-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6fed5-116">Die maximal zulässigen Bytes, die bei jedem Lesevorgang zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6fed5-116">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="6fed5-117">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="6fed5-117">MaxDepth</span></span>  
 <span data-ttu-id="6fed5-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="6fed5-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="6fed5-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6fed5-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6fed5-120">Die maximale geschachtelte Knotentiefe für jeden Lesevorgang.</span><span class="sxs-lookup"><span data-stu-id="6fed5-120">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="6fed5-121">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="6fed5-121">MaxNameTableCharCount</span></span>  
 <span data-ttu-id="6fed5-122">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="6fed5-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="6fed5-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6fed5-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6fed5-124">Die maximal zulässigen Zeichen in einem Tabellennamen.</span><span class="sxs-lookup"><span data-stu-id="6fed5-124">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="6fed5-125">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="6fed5-125">MaxStringContentLength</span></span>  
 <span data-ttu-id="6fed5-126">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="6fed5-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="6fed5-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6fed5-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6fed5-128">Die maximale Zeichenanzahl, die in XML-Elementinhalten zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="6fed5-128">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fed5-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6fed5-129">Requirements</span></span>  
  
|<span data-ttu-id="6fed5-130">MOF</span><span class="sxs-lookup"><span data-stu-id="6fed5-130">MOF</span></span>|<span data-ttu-id="6fed5-131">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="6fed5-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6fed5-132">Namespace</span><span class="sxs-lookup"><span data-stu-id="6fed5-132">Namespace</span></span>|<span data-ttu-id="6fed5-133">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6fed5-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6fed5-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6fed5-134">See Also</span></span>  
 <xref:System.Xml.XmlDictionaryReaderQuotas>  
 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
