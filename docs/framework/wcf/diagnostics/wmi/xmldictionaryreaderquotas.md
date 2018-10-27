---
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: 9bc519509b00383be333ac605688950d2709117c
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50044228"
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="53558-102">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="53558-102">XmlDictionaryReaderQuotas</span></span>
<span data-ttu-id="53558-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="53558-103">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53558-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="53558-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="53558-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="53558-105">Methods</span></span>  
 <span data-ttu-id="53558-106">Von der XmlDictionaryReaderQuotas-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="53558-106">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="53558-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="53558-107">Properties</span></span>  
 <span data-ttu-id="53558-108">Die XmlDictionaryReaderQuotas-Klasse weist die folgenden Eigenschaften auf:</span><span class="sxs-lookup"><span data-stu-id="53558-108">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="53558-109">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="53558-109">MaxArrayLength</span></span>  
 <span data-ttu-id="53558-110">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="53558-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="53558-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="53558-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="53558-112">Die maximal zulässige Arraylänge.</span><span class="sxs-lookup"><span data-stu-id="53558-112">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="53558-113">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="53558-113">MaxBytesPerRead</span></span>  
 <span data-ttu-id="53558-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="53558-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="53558-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="53558-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="53558-116">Die maximal zulässigen Bytes, die bei jedem Lesevorgang zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="53558-116">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="53558-117">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="53558-117">MaxDepth</span></span>  
 <span data-ttu-id="53558-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="53558-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="53558-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="53558-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="53558-120">Die maximale geschachtelte Knotentiefe für jeden Lesevorgang.</span><span class="sxs-lookup"><span data-stu-id="53558-120">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="53558-121">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="53558-121">MaxNameTableCharCount</span></span>  
 <span data-ttu-id="53558-122">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="53558-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="53558-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="53558-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="53558-124">Die maximal zulässigen Zeichen in einem Tabellennamen.</span><span class="sxs-lookup"><span data-stu-id="53558-124">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="53558-125">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="53558-125">MaxStringContentLength</span></span>  
 <span data-ttu-id="53558-126">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="53558-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="53558-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="53558-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="53558-128">Die maximale Zeichenanzahl, die in XML-Elementinhalten zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="53558-128">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53558-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="53558-129">Requirements</span></span>  
  
|<span data-ttu-id="53558-130">MOF</span><span class="sxs-lookup"><span data-stu-id="53558-130">MOF</span></span>|<span data-ttu-id="53558-131">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="53558-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="53558-132">Namespace</span><span class="sxs-lookup"><span data-stu-id="53558-132">Namespace</span></span>|<span data-ttu-id="53558-133">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="53558-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="53558-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53558-134">See Also</span></span>  
 <xref:System.Xml.XmlDictionaryReaderQuotas>  
 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
