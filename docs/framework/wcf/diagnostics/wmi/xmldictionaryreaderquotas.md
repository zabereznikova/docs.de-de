---
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: 9bc519509b00383be333ac605688950d2709117c
ms.sourcegitcommit: 4bca8f7e172fd019ef437a4803bf5895c6bc4781
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2018
ms.locfileid: "50980530"
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="a3597-102">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="a3597-102">XmlDictionaryReaderQuotas</span></span>
<span data-ttu-id="a3597-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="a3597-103">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3597-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a3597-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="a3597-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="a3597-105">Methods</span></span>  
 <span data-ttu-id="a3597-106">Von der XmlDictionaryReaderQuotas-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="a3597-106">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a3597-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a3597-107">Properties</span></span>  
 <span data-ttu-id="a3597-108">Die XmlDictionaryReaderQuotas-Klasse weist die folgenden Eigenschaften auf:</span><span class="sxs-lookup"><span data-stu-id="a3597-108">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="a3597-109">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="a3597-109">MaxArrayLength</span></span>  
 <span data-ttu-id="a3597-110">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="a3597-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="a3597-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a3597-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a3597-112">Die maximal zulässige Arraylänge.</span><span class="sxs-lookup"><span data-stu-id="a3597-112">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="a3597-113">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="a3597-113">MaxBytesPerRead</span></span>  
 <span data-ttu-id="a3597-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="a3597-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="a3597-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a3597-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a3597-116">Die maximal zulässigen Bytes, die bei jedem Lesevorgang zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a3597-116">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="a3597-117">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="a3597-117">MaxDepth</span></span>  
 <span data-ttu-id="a3597-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="a3597-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="a3597-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a3597-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a3597-120">Die maximale geschachtelte Knotentiefe für jeden Lesevorgang.</span><span class="sxs-lookup"><span data-stu-id="a3597-120">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="a3597-121">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="a3597-121">MaxNameTableCharCount</span></span>  
 <span data-ttu-id="a3597-122">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="a3597-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="a3597-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a3597-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a3597-124">Die maximal zulässigen Zeichen in einem Tabellennamen.</span><span class="sxs-lookup"><span data-stu-id="a3597-124">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="a3597-125">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="a3597-125">MaxStringContentLength</span></span>  
 <span data-ttu-id="a3597-126">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="a3597-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="a3597-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a3597-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a3597-128">Die maximale Zeichenanzahl, die in XML-Elementinhalten zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="a3597-128">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3597-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a3597-129">Requirements</span></span>  
  
|<span data-ttu-id="a3597-130">MOF</span><span class="sxs-lookup"><span data-stu-id="a3597-130">MOF</span></span>|<span data-ttu-id="a3597-131">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="a3597-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a3597-132">Namespace</span><span class="sxs-lookup"><span data-stu-id="a3597-132">Namespace</span></span>|<span data-ttu-id="a3597-133">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a3597-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a3597-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3597-134">See Also</span></span>  
 <xref:System.Xml.XmlDictionaryReaderQuotas>  
 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
