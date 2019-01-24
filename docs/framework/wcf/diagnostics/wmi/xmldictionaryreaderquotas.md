---
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: f24865fb0affa7b4516a14fc05b905995826e82e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597670"
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="a1ccd-102">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="a1ccd-102">XmlDictionaryReaderQuotas</span></span>
<span data-ttu-id="a1ccd-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="a1ccd-103">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1ccd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1ccd-104">Syntax</span></span>  
  
```csharp
class XmlDictionaryReaderQuotas  
{  
  sint32 MaxArrayLength;  
  sint32 MaxBytesPerRead;  
  sint32 MaxDepth;  
  sint32 MaxNameTableCharCount;  
  sint32 MaxStringContentLength;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a1ccd-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="a1ccd-105">Methods</span></span>  
 <span data-ttu-id="a1ccd-106">Von der XmlDictionaryReaderQuotas-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="a1ccd-106">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a1ccd-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a1ccd-107">Properties</span></span>  
 <span data-ttu-id="a1ccd-108">Die XmlDictionaryReaderQuotas-Klasse weist die folgenden Eigenschaften auf:</span><span class="sxs-lookup"><span data-stu-id="a1ccd-108">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="a1ccd-109">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="a1ccd-109">MaxArrayLength</span></span>  
 <span data-ttu-id="a1ccd-110">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="a1ccd-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="a1ccd-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a1ccd-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a1ccd-112">Die maximal zulässige Arraylänge.</span><span class="sxs-lookup"><span data-stu-id="a1ccd-112">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="a1ccd-113">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="a1ccd-113">MaxBytesPerRead</span></span>  
 <span data-ttu-id="a1ccd-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="a1ccd-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="a1ccd-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a1ccd-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a1ccd-116">Die maximal zulässigen Bytes, die bei jedem Lesevorgang zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a1ccd-116">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="a1ccd-117">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="a1ccd-117">MaxDepth</span></span>  
 <span data-ttu-id="a1ccd-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="a1ccd-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="a1ccd-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a1ccd-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a1ccd-120">Die maximale geschachtelte Knotentiefe für jeden Lesevorgang.</span><span class="sxs-lookup"><span data-stu-id="a1ccd-120">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="a1ccd-121">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="a1ccd-121">MaxNameTableCharCount</span></span>  
 <span data-ttu-id="a1ccd-122">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="a1ccd-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="a1ccd-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a1ccd-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a1ccd-124">Die maximal zulässigen Zeichen in einem Tabellennamen.</span><span class="sxs-lookup"><span data-stu-id="a1ccd-124">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="a1ccd-125">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="a1ccd-125">MaxStringContentLength</span></span>  
 <span data-ttu-id="a1ccd-126">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="a1ccd-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="a1ccd-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a1ccd-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a1ccd-128">Die maximale Zeichenanzahl, die in XML-Elementinhalten zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="a1ccd-128">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1ccd-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a1ccd-129">Requirements</span></span>  
  
|<span data-ttu-id="a1ccd-130">MOF</span><span class="sxs-lookup"><span data-stu-id="a1ccd-130">MOF</span></span>|<span data-ttu-id="a1ccd-131">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="a1ccd-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a1ccd-132">Namespace</span><span class="sxs-lookup"><span data-stu-id="a1ccd-132">Namespace</span></span>|<span data-ttu-id="a1ccd-133">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a1ccd-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a1ccd-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1ccd-134">See also</span></span>
- <xref:System.Xml.XmlDictionaryReaderQuotas>
- <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
