---
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: 1224a410d030669e340bd328c9158c85cdfeaeee
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266454"
---
# <a name="knowntype"></a><span data-ttu-id="7b0a4-101">\<knownType></span><span class="sxs-lookup"><span data-stu-id="7b0a4-101">\<knownType></span></span>
<span data-ttu-id="7b0a4-102">Gibt einen Typ an, der vom <xref:System.Runtime.Serialization.DataContractSerializer> während der Deserialisierung verwendet werden sollte.</span><span class="sxs-lookup"><span data-stu-id="7b0a4-102">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="7b0a4-103">Dieses Element gibt einen "bekannten Typ" an, der von einem Feld oder einer Eigenschaft eines "deklarierten Typs" zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="7b0a4-103">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="7b0a4-104">Weitere Informationen finden Sie unter [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="7b0a4-104">For more information, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="7b0a4-105">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="7b0a4-105">\<system.runtime.serialization></span></span>  
<span data-ttu-id="7b0a4-106">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="7b0a4-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="7b0a4-107">\<DeclaredTypes >-Element</span><span class="sxs-lookup"><span data-stu-id="7b0a4-107">\<declaredTypes> Element</span></span>  
<span data-ttu-id="7b0a4-108">\<add> of \<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="7b0a4-108">\<add> of \<declaredTypes></span></span>  
<span data-ttu-id="7b0a4-109">\<KnownType >-Element</span><span class="sxs-lookup"><span data-stu-id="7b0a4-109">\<knownType> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b0a4-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="7b0a4-110">Syntax</span></span>  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a><span data-ttu-id="7b0a4-111">Typ</span><span class="sxs-lookup"><span data-stu-id="7b0a4-111">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b0a4-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7b0a4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="7b0a4-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7b0a4-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7b0a4-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="7b0a4-114">Attributes</span></span>  
  
|<span data-ttu-id="7b0a4-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="7b0a4-115">Attribute</span></span>|<span data-ttu-id="7b0a4-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b0a4-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7b0a4-117">Typ</span><span class="sxs-lookup"><span data-stu-id="7b0a4-117">type</span></span>|<span data-ttu-id="7b0a4-118">Gibt den Typ (einschließlich Namespace), den Assemblynamen, die Version, die Kultur und das öffentliche Schlüsseltoken an.</span><span class="sxs-lookup"><span data-stu-id="7b0a4-118">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7b0a4-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7b0a4-119">Child Elements</span></span>  
  
|<span data-ttu-id="7b0a4-120">Element</span><span class="sxs-lookup"><span data-stu-id="7b0a4-120">Element</span></span>|<span data-ttu-id="7b0a4-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b0a4-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7b0a4-122">\<parameter></span><span class="sxs-lookup"><span data-stu-id="7b0a4-122">\<parameter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/parameter.md)|<span data-ttu-id="7b0a4-123">Gibt einen Parameterindex an, wenn der deklarierte Typ ein generischer Typ ist.</span><span class="sxs-lookup"><span data-stu-id="7b0a4-123">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7b0a4-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7b0a4-124">Parent Elements</span></span>  
  
|<span data-ttu-id="7b0a4-125">Element</span><span class="sxs-lookup"><span data-stu-id="7b0a4-125">Element</span></span>|<span data-ttu-id="7b0a4-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b0a4-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7b0a4-127">\<add></span><span class="sxs-lookup"><span data-stu-id="7b0a4-127">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|<span data-ttu-id="7b0a4-128">Fügt der Auflistung deklarierter Typen einen deklarierten Typ hinzu.</span><span class="sxs-lookup"><span data-stu-id="7b0a4-128">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b0a4-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7b0a4-129">Remarks</span></span>  
 <span data-ttu-id="7b0a4-130">Weitere Informationen zu bekannten Typen finden Sie unter [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) und <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="7b0a4-130">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="7b0a4-131">Finden Sie unter den [ \<DataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) ein Beispiel für die Verwendung dieses Elements.</span><span class="sxs-lookup"><span data-stu-id="7b0a4-131">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b0a4-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7b0a4-132">Example</span></span>  
  
```xml  
<add type="MyCompany.Library.Shape,
           MyAssembly, Version=2.0.0.0, Culture=neutral,
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">
  <knownType type="MyCompany.Library.Circle,
                   MyAssembly, Version=2.0.0.0, Culture=neutral,
                   PublicKeyToken=XXXXXX,
                   processorArchitecture=MSIL"/>
</add>
```  
  
## <a name="see-also"></a><span data-ttu-id="7b0a4-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b0a4-133">See also</span></span>
- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="7b0a4-134">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="7b0a4-134">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="7b0a4-135">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="7b0a4-135">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)
- [<span data-ttu-id="7b0a4-136">\<add></span><span class="sxs-lookup"><span data-stu-id="7b0a4-136">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
