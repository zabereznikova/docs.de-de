---
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: f1c12a0a60397a84d4e9ff0241c4182b4511af5c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59214883"
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="50fa9-102">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="50fa9-102">XmlDictionaryReaderQuotas</span></span>
<span data-ttu-id="50fa9-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="50fa9-103">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50fa9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="50fa9-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="50fa9-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="50fa9-105">Methods</span></span>  
 <span data-ttu-id="50fa9-106">Von der XmlDictionaryReaderQuotas-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="50fa9-106">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="50fa9-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="50fa9-107">Properties</span></span>  
 <span data-ttu-id="50fa9-108">Die XmlDictionaryReaderQuotas-Klasse weist die folgenden Eigenschaften auf:</span><span class="sxs-lookup"><span data-stu-id="50fa9-108">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="50fa9-109">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="50fa9-109">MaxArrayLength</span></span>  
 <span data-ttu-id="50fa9-110">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="50fa9-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="50fa9-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="50fa9-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="50fa9-112">Die maximal zulässige Arraylänge.</span><span class="sxs-lookup"><span data-stu-id="50fa9-112">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="50fa9-113">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="50fa9-113">MaxBytesPerRead</span></span>  
 <span data-ttu-id="50fa9-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="50fa9-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="50fa9-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="50fa9-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="50fa9-116">Die maximal zulässigen Bytes, die bei jedem Lesevorgang zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="50fa9-116">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="50fa9-117">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="50fa9-117">MaxDepth</span></span>  
 <span data-ttu-id="50fa9-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="50fa9-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="50fa9-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="50fa9-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="50fa9-120">Die maximale geschachtelte Knotentiefe für jeden Lesevorgang.</span><span class="sxs-lookup"><span data-stu-id="50fa9-120">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="50fa9-121">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="50fa9-121">MaxNameTableCharCount</span></span>  
 <span data-ttu-id="50fa9-122">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="50fa9-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="50fa9-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="50fa9-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="50fa9-124">Die maximal zulässigen Zeichen in einem Tabellennamen.</span><span class="sxs-lookup"><span data-stu-id="50fa9-124">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="50fa9-125">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="50fa9-125">MaxStringContentLength</span></span>  
 <span data-ttu-id="50fa9-126">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="50fa9-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="50fa9-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="50fa9-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="50fa9-128">Die maximale Zeichenanzahl, die in XML-Elementinhalten zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="50fa9-128">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50fa9-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="50fa9-129">Requirements</span></span>  
  
|<span data-ttu-id="50fa9-130">MOF</span><span class="sxs-lookup"><span data-stu-id="50fa9-130">MOF</span></span>|<span data-ttu-id="50fa9-131">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="50fa9-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="50fa9-132">Namespace</span><span class="sxs-lookup"><span data-stu-id="50fa9-132">Namespace</span></span>|<span data-ttu-id="50fa9-133">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="50fa9-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="50fa9-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50fa9-134">See also</span></span>

- <xref:System.Xml.XmlDictionaryReaderQuotas>
- <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
