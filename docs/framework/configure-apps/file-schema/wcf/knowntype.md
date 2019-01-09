---
title: '&lt;knownType&gt;'
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: 6156f102573333ec0d5533b8f1a8506d91215f47
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151929"
---
# <a name="ltknowntypegt"></a><span data-ttu-id="528f4-102">&lt;knownType&gt;</span><span class="sxs-lookup"><span data-stu-id="528f4-102">&lt;knownType&gt;</span></span>
<span data-ttu-id="528f4-103">Gibt einen Typ an, der vom <xref:System.Runtime.Serialization.DataContractSerializer> während der Deserialisierung verwendet werden sollte.</span><span class="sxs-lookup"><span data-stu-id="528f4-103">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="528f4-104">Dieses Element gibt einen "bekannten Typ" an, der von einem Feld oder einer Eigenschaft eines "deklarierten Typs" zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="528f4-104">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="528f4-105">Weitere Informationen finden Sie unter [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="528f4-105">For more information, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="528f4-106">\<System.Runtime.Serialization ></span><span class="sxs-lookup"><span data-stu-id="528f4-106">\<system.runtime.serialization></span></span>  
<span data-ttu-id="528f4-107">\<DataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="528f4-107">\<dataContractSerializer></span></span>  
<span data-ttu-id="528f4-108">\<DeclaredTypes >-Element</span><span class="sxs-lookup"><span data-stu-id="528f4-108">\<declaredTypes> Element</span></span>  
<span data-ttu-id="528f4-109">\<Hinzufügen > der \<DeclaredTypes ></span><span class="sxs-lookup"><span data-stu-id="528f4-109">\<add> of \<declaredTypes></span></span>  
<span data-ttu-id="528f4-110">\<KnownType >-Element</span><span class="sxs-lookup"><span data-stu-id="528f4-110">\<knownType> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="528f4-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="528f4-111">Syntax</span></span>  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a><span data-ttu-id="528f4-112">Typ</span><span class="sxs-lookup"><span data-stu-id="528f4-112">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="528f4-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="528f4-113">Attributes and Elements</span></span>  
 <span data-ttu-id="528f4-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="528f4-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="528f4-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="528f4-115">Attributes</span></span>  
  
|<span data-ttu-id="528f4-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="528f4-116">Attribute</span></span>|<span data-ttu-id="528f4-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="528f4-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="528f4-118">Typ</span><span class="sxs-lookup"><span data-stu-id="528f4-118">type</span></span>|<span data-ttu-id="528f4-119">Gibt den Typ (einschließlich Namespace), den Assemblynamen, die Version, die Kultur und das öffentliche Schlüsseltoken an.</span><span class="sxs-lookup"><span data-stu-id="528f4-119">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="528f4-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="528f4-120">Child Elements</span></span>  
  
|<span data-ttu-id="528f4-121">Element</span><span class="sxs-lookup"><span data-stu-id="528f4-121">Element</span></span>|<span data-ttu-id="528f4-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="528f4-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="528f4-123">\<Parameter ></span><span class="sxs-lookup"><span data-stu-id="528f4-123">\<parameter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/parameter.md)|<span data-ttu-id="528f4-124">Gibt einen Parameterindex an, wenn der deklarierte Typ ein generischer Typ ist.</span><span class="sxs-lookup"><span data-stu-id="528f4-124">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="528f4-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="528f4-125">Parent Elements</span></span>  
  
|<span data-ttu-id="528f4-126">Element</span><span class="sxs-lookup"><span data-stu-id="528f4-126">Element</span></span>|<span data-ttu-id="528f4-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="528f4-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="528f4-128">\<add></span><span class="sxs-lookup"><span data-stu-id="528f4-128">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|<span data-ttu-id="528f4-129">Fügt der Auflistung deklarierter Typen einen deklarierten Typ hinzu.</span><span class="sxs-lookup"><span data-stu-id="528f4-129">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="528f4-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="528f4-130">Remarks</span></span>  
 <span data-ttu-id="528f4-131">Weitere Informationen zu bekannten Typen finden Sie unter [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) und <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="528f4-131">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="528f4-132">Finden Sie unter den [ \<DataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) ein Beispiel für die Verwendung dieses Elements.</span><span class="sxs-lookup"><span data-stu-id="528f4-132">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="528f4-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="528f4-133">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="528f4-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="528f4-134">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="528f4-135">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="528f4-135">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="528f4-136">\<DataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="528f4-136">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="528f4-137">\<add></span><span class="sxs-lookup"><span data-stu-id="528f4-137">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
