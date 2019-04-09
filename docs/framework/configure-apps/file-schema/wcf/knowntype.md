---
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: 4d3dd9042951ffb46b8e0a3f7bb7bcdee23fd58b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148836"
---
# <a name="knowntype"></a><span data-ttu-id="ce716-101">\<knownType></span><span class="sxs-lookup"><span data-stu-id="ce716-101">\<knownType></span></span>
<span data-ttu-id="ce716-102">Gibt einen Typ an, der vom <xref:System.Runtime.Serialization.DataContractSerializer> während der Deserialisierung verwendet werden sollte.</span><span class="sxs-lookup"><span data-stu-id="ce716-102">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="ce716-103">Dieses Element gibt einen "bekannten Typ" an, der von einem Feld oder einer Eigenschaft eines "deklarierten Typs" zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="ce716-103">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="ce716-104">Weitere Informationen finden Sie unter [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="ce716-104">For more information, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="ce716-105">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="ce716-105">\<system.runtime.serialization></span></span>  
<span data-ttu-id="ce716-106">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="ce716-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="ce716-107">\<DeclaredTypes >-Element</span><span class="sxs-lookup"><span data-stu-id="ce716-107">\<declaredTypes> Element</span></span>  
<span data-ttu-id="ce716-108">\<add> of \<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="ce716-108">\<add> of \<declaredTypes></span></span>  
<span data-ttu-id="ce716-109">\<KnownType >-Element</span><span class="sxs-lookup"><span data-stu-id="ce716-109">\<knownType> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce716-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce716-110">Syntax</span></span>  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a><span data-ttu-id="ce716-111">Typ</span><span class="sxs-lookup"><span data-stu-id="ce716-111">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce716-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ce716-112">Attributes and Elements</span></span>  
 <span data-ttu-id="ce716-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ce716-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce716-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="ce716-114">Attributes</span></span>  
  
|<span data-ttu-id="ce716-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="ce716-115">Attribute</span></span>|<span data-ttu-id="ce716-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce716-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ce716-117">Typ</span><span class="sxs-lookup"><span data-stu-id="ce716-117">type</span></span>|<span data-ttu-id="ce716-118">Gibt den Typ (einschließlich Namespace), den Assemblynamen, die Version, die Kultur und das öffentliche Schlüsseltoken an.</span><span class="sxs-lookup"><span data-stu-id="ce716-118">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ce716-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ce716-119">Child Elements</span></span>  
  
|<span data-ttu-id="ce716-120">Element</span><span class="sxs-lookup"><span data-stu-id="ce716-120">Element</span></span>|<span data-ttu-id="ce716-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce716-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce716-122">\<parameter></span><span class="sxs-lookup"><span data-stu-id="ce716-122">\<parameter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/parameter.md)|<span data-ttu-id="ce716-123">Gibt einen Parameterindex an, wenn der deklarierte Typ ein generischer Typ ist.</span><span class="sxs-lookup"><span data-stu-id="ce716-123">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ce716-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ce716-124">Parent Elements</span></span>  
  
|<span data-ttu-id="ce716-125">Element</span><span class="sxs-lookup"><span data-stu-id="ce716-125">Element</span></span>|<span data-ttu-id="ce716-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce716-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce716-127">\<add></span><span class="sxs-lookup"><span data-stu-id="ce716-127">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|<span data-ttu-id="ce716-128">Fügt der Auflistung deklarierter Typen einen deklarierten Typ hinzu.</span><span class="sxs-lookup"><span data-stu-id="ce716-128">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce716-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ce716-129">Remarks</span></span>  
 <span data-ttu-id="ce716-130">Weitere Informationen zu bekannten Typen finden Sie unter [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) und <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="ce716-130">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="ce716-131">Finden Sie unter den [ \<DataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) ein Beispiel für die Verwendung dieses Elements.</span><span class="sxs-lookup"><span data-stu-id="ce716-131">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce716-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ce716-132">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ce716-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce716-133">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="ce716-134">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="ce716-134">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="ce716-135">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="ce716-135">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)
- [<span data-ttu-id="ce716-136">\<add></span><span class="sxs-lookup"><span data-stu-id="ce716-136">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
