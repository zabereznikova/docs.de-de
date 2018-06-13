---
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: 78914d52a9e57fe2e48adcfc0d7b6f911a0d8b3a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33487827"
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="9d4de-102">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="9d4de-102">XmlDictionaryReaderQuotas</span></span>
<span data-ttu-id="9d4de-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="9d4de-103">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d4de-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9d4de-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="9d4de-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="9d4de-105">Methods</span></span>  
 <span data-ttu-id="9d4de-106">Von der XmlDictionaryReaderQuotas-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="9d4de-106">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9d4de-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9d4de-107">Properties</span></span>  
 <span data-ttu-id="9d4de-108">Die XmlDictionaryReaderQuotas-Klasse weist die folgenden Eigenschaften auf:</span><span class="sxs-lookup"><span data-stu-id="9d4de-108">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="9d4de-109">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="9d4de-109">MaxArrayLength</span></span>  
 <span data-ttu-id="9d4de-110">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="9d4de-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="9d4de-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9d4de-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d4de-112">Die maximal zulässige Arraylänge.</span><span class="sxs-lookup"><span data-stu-id="9d4de-112">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="9d4de-113">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="9d4de-113">MaxBytesPerRead</span></span>  
 <span data-ttu-id="9d4de-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="9d4de-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="9d4de-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9d4de-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d4de-116">Die maximal zulässigen Bytes, die bei jedem Lesevorgang zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9d4de-116">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="9d4de-117">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="9d4de-117">MaxDepth</span></span>  
 <span data-ttu-id="9d4de-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="9d4de-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="9d4de-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9d4de-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d4de-120">Die maximale geschachtelte Knotentiefe für jeden Lesevorgang.</span><span class="sxs-lookup"><span data-stu-id="9d4de-120">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="9d4de-121">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="9d4de-121">MaxNameTableCharCount</span></span>  
 <span data-ttu-id="9d4de-122">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="9d4de-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="9d4de-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9d4de-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d4de-124">Die maximal zulässigen Zeichen in einem Tabellennamen.</span><span class="sxs-lookup"><span data-stu-id="9d4de-124">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="9d4de-125">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="9d4de-125">MaxStringContentLength</span></span>  
 <span data-ttu-id="9d4de-126">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="9d4de-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="9d4de-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9d4de-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d4de-128">Die maximale Zeichenanzahl, die in XML-Elementinhalten zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="9d4de-128">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d4de-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9d4de-129">Requirements</span></span>  
  
|<span data-ttu-id="9d4de-130">MOF</span><span class="sxs-lookup"><span data-stu-id="9d4de-130">MOF</span></span>|<span data-ttu-id="9d4de-131">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="9d4de-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9d4de-132">Namespace</span><span class="sxs-lookup"><span data-stu-id="9d4de-132">Namespace</span></span>|<span data-ttu-id="9d4de-133">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9d4de-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9d4de-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d4de-134">See Also</span></span>  
 <xref:System.Xml.XmlDictionaryReaderQuotas>  
 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
