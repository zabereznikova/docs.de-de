---
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: c5bb7813a680c89eb90f4ccf4ed6f09a831c8095
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262202"
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="190d1-102">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="190d1-102">XmlDictionaryReaderQuotas</span></span>

<span data-ttu-id="190d1-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="190d1-103">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="190d1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="190d1-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="190d1-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="190d1-105">Methods</span></span>  

 <span data-ttu-id="190d1-106">Von der XmlDictionaryReaderQuotas-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="190d1-106">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="190d1-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="190d1-107">Properties</span></span>  

 <span data-ttu-id="190d1-108">Die XmlDictionaryReaderQuotas-Klasse weist die folgenden Eigenschaften auf:</span><span class="sxs-lookup"><span data-stu-id="190d1-108">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="190d1-109">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="190d1-109">MaxArrayLength</span></span>  

 <span data-ttu-id="190d1-110">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="190d1-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="190d1-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="190d1-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="190d1-112">Die maximal zulässige Arraylänge.</span><span class="sxs-lookup"><span data-stu-id="190d1-112">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="190d1-113">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="190d1-113">MaxBytesPerRead</span></span>  

 <span data-ttu-id="190d1-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="190d1-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="190d1-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="190d1-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="190d1-116">Die maximal zulässigen Bytes, die bei jedem Lesevorgang zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="190d1-116">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="190d1-117">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="190d1-117">MaxDepth</span></span>  

 <span data-ttu-id="190d1-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="190d1-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="190d1-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="190d1-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="190d1-120">Die maximale geschachtelte Knotentiefe für jeden Lesevorgang.</span><span class="sxs-lookup"><span data-stu-id="190d1-120">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="190d1-121">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="190d1-121">MaxNameTableCharCount</span></span>  

 <span data-ttu-id="190d1-122">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="190d1-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="190d1-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="190d1-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="190d1-124">Die maximal zulässigen Zeichen in einem Tabellennamen.</span><span class="sxs-lookup"><span data-stu-id="190d1-124">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="190d1-125">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="190d1-125">MaxStringContentLength</span></span>  

 <span data-ttu-id="190d1-126">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="190d1-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="190d1-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="190d1-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="190d1-128">Die maximale Zeichenanzahl, die in XML-Elementinhalten zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="190d1-128">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="190d1-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="190d1-129">Requirements</span></span>  
  
|<span data-ttu-id="190d1-130">MOF</span><span class="sxs-lookup"><span data-stu-id="190d1-130">MOF</span></span>|<span data-ttu-id="190d1-131">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="190d1-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="190d1-132">Namespace</span><span class="sxs-lookup"><span data-stu-id="190d1-132">Namespace</span></span>|<span data-ttu-id="190d1-133">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="190d1-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="190d1-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="190d1-134">See also</span></span>

- <xref:System.Xml.XmlDictionaryReaderQuotas>
- <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
