---
title: '&lt;knownType&gt;'
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: b2445f12f1eaac03b3f3ab66f3d13a5f465a1133
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32753325"
---
# <a name="ltknowntypegt"></a><span data-ttu-id="f9fc2-102">&lt;knownType&gt;</span><span class="sxs-lookup"><span data-stu-id="f9fc2-102">&lt;knownType&gt;</span></span>
<span data-ttu-id="f9fc2-103">Gibt einen Typ an, der vom <xref:System.Runtime.Serialization.DataContractSerializer> während der Deserialisierung verwendet werden sollte.</span><span class="sxs-lookup"><span data-stu-id="f9fc2-103">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="f9fc2-104">Dieses Element gibt einen "bekannten Typ" an, der von einem Feld oder einer Eigenschaft eines "deklarierten Typs" zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="f9fc2-104">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="f9fc2-105">Weitere Informationen finden Sie unter [Datenvertragstypen bezeichnet](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="f9fc2-105">For more information, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="f9fc2-106">\<System.Runtime.Serialization ></span><span class="sxs-lookup"><span data-stu-id="f9fc2-106">\<system.runtime.serialization></span></span>  
<span data-ttu-id="f9fc2-107">\<"DataContractSerializer" ></span><span class="sxs-lookup"><span data-stu-id="f9fc2-107">\<dataContractSerializer></span></span>  
<span data-ttu-id="f9fc2-108">\<DeclaredTypes >-Element</span><span class="sxs-lookup"><span data-stu-id="f9fc2-108">\<declaredTypes> Element</span></span>  
<span data-ttu-id="f9fc2-109">\<Hinzufügen > der \<DeclaredTypes ></span><span class="sxs-lookup"><span data-stu-id="f9fc2-109">\<add> of \<declaredTypes></span></span>  
<span data-ttu-id="f9fc2-110">\<KnownType >-Element</span><span class="sxs-lookup"><span data-stu-id="f9fc2-110">\<knownType> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9fc2-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="f9fc2-111">Syntax</span></span>  
  
```xml  
<knownType type="String">  
     <parameter index="Integer"  
                type="String" />  
</knownType>  
```  
  
## <a name="type"></a><span data-ttu-id="f9fc2-112">Typ</span><span class="sxs-lookup"><span data-stu-id="f9fc2-112">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9fc2-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f9fc2-113">Attributes and Elements</span></span>  
 <span data-ttu-id="f9fc2-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f9fc2-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9fc2-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="f9fc2-115">Attributes</span></span>  
  
|<span data-ttu-id="f9fc2-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="f9fc2-116">Attribute</span></span>|<span data-ttu-id="f9fc2-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f9fc2-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f9fc2-118">Typ</span><span class="sxs-lookup"><span data-stu-id="f9fc2-118">type</span></span>|<span data-ttu-id="f9fc2-119">Gibt den Typ (einschließlich Namespace), den Assemblynamen, die Version, die Kultur und das öffentliche Schlüsseltoken an.</span><span class="sxs-lookup"><span data-stu-id="f9fc2-119">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f9fc2-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f9fc2-120">Child Elements</span></span>  
  
|<span data-ttu-id="f9fc2-121">Element</span><span class="sxs-lookup"><span data-stu-id="f9fc2-121">Element</span></span>|<span data-ttu-id="f9fc2-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f9fc2-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9fc2-123">\<Parameter ></span><span class="sxs-lookup"><span data-stu-id="f9fc2-123">\<parameter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/parameter.md)|<span data-ttu-id="f9fc2-124">Gibt einen Parameterindex an, wenn der deklarierte Typ ein generischer Typ ist.</span><span class="sxs-lookup"><span data-stu-id="f9fc2-124">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f9fc2-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f9fc2-125">Parent Elements</span></span>  
  
|<span data-ttu-id="f9fc2-126">Element</span><span class="sxs-lookup"><span data-stu-id="f9fc2-126">Element</span></span>|<span data-ttu-id="f9fc2-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f9fc2-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9fc2-128">\<add></span><span class="sxs-lookup"><span data-stu-id="f9fc2-128">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|<span data-ttu-id="f9fc2-129">Fügt der Auflistung deklarierter Typen einen deklarierten Typ hinzu.</span><span class="sxs-lookup"><span data-stu-id="f9fc2-129">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9fc2-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f9fc2-130">Remarks</span></span>  
 <span data-ttu-id="f9fc2-131">Weitere Informationen über bekannte Typen finden Sie unter [Datenvertragstypen bezeichnet](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) und <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="f9fc2-131">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="f9fc2-132">Finden Sie unter der [ \<"DataContractSerializer" >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) für ein Beispiel für dieses Element.</span><span class="sxs-lookup"><span data-stu-id="f9fc2-132">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9fc2-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f9fc2-133">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f9fc2-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9fc2-134">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="f9fc2-135">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="f9fc2-135">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="f9fc2-136">\<"DataContractSerializer" ></span><span class="sxs-lookup"><span data-stu-id="f9fc2-136">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="f9fc2-137">\<add></span><span class="sxs-lookup"><span data-stu-id="f9fc2-137">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
