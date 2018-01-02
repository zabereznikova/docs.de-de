---
title: '&lt;knownType&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 439d241d73df4db2820eac72c5e88e7d9023c6a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltknowntypegt"></a><span data-ttu-id="55831-102">&lt;knownType&gt;</span><span class="sxs-lookup"><span data-stu-id="55831-102">&lt;knownType&gt;</span></span>
<span data-ttu-id="55831-103">Gibt einen Typ an, der vom <xref:System.Runtime.Serialization.DataContractSerializer> während der Deserialisierung verwendet werden sollte.</span><span class="sxs-lookup"><span data-stu-id="55831-103">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="55831-104">Dieses Element gibt einen "bekannten Typ" an, der von einem Feld oder einer Eigenschaft eines "deklarierten Typs" zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="55831-104">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="55831-105">Weitere Informationen finden Sie unter [Datenvertragstypen bezeichnet](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="55831-105">For more information, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="55831-106">\<System.Runtime.Serialization ></span><span class="sxs-lookup"><span data-stu-id="55831-106">\<system.runtime.serialization></span></span>  
<span data-ttu-id="55831-107">\<"DataContractSerializer" ></span><span class="sxs-lookup"><span data-stu-id="55831-107">\<dataContractSerializer></span></span>  
<span data-ttu-id="55831-108">\<DeclaredTypes >-Element</span><span class="sxs-lookup"><span data-stu-id="55831-108">\<declaredTypes> Element</span></span>  
<span data-ttu-id="55831-109">\<Hinzufügen > der \<DeclaredTypes ></span><span class="sxs-lookup"><span data-stu-id="55831-109">\<add> of \<declaredTypes></span></span>  
<span data-ttu-id="55831-110">\<KnownType >-Element</span><span class="sxs-lookup"><span data-stu-id="55831-110">\<knownType> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55831-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="55831-111">Syntax</span></span>  
  
```xml  
<knownType type="String">  
     <parameter index="Integer"  
                type="String" />  
</knownType>  
```  
  
## <a name="type"></a><span data-ttu-id="55831-112">Typ</span><span class="sxs-lookup"><span data-stu-id="55831-112">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="55831-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="55831-113">Attributes and Elements</span></span>  
 <span data-ttu-id="55831-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="55831-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="55831-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="55831-115">Attributes</span></span>  
  
|<span data-ttu-id="55831-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="55831-116">Attribute</span></span>|<span data-ttu-id="55831-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55831-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="55831-118">Typ</span><span class="sxs-lookup"><span data-stu-id="55831-118">type</span></span>|<span data-ttu-id="55831-119">Gibt den Typ (einschließlich Namespace), den Assemblynamen, die Version, die Kultur und das öffentliche Schlüsseltoken an.</span><span class="sxs-lookup"><span data-stu-id="55831-119">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="55831-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="55831-120">Child Elements</span></span>  
  
|<span data-ttu-id="55831-121">Element</span><span class="sxs-lookup"><span data-stu-id="55831-121">Element</span></span>|<span data-ttu-id="55831-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55831-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="55831-123">\<Parameter ></span><span class="sxs-lookup"><span data-stu-id="55831-123">\<parameter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/parameter.md)|<span data-ttu-id="55831-124">Gibt einen Parameterindex an, wenn der deklarierte Typ ein generischer Typ ist.</span><span class="sxs-lookup"><span data-stu-id="55831-124">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="55831-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="55831-125">Parent Elements</span></span>  
  
|<span data-ttu-id="55831-126">Element</span><span class="sxs-lookup"><span data-stu-id="55831-126">Element</span></span>|<span data-ttu-id="55831-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55831-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="55831-128">\<add></span><span class="sxs-lookup"><span data-stu-id="55831-128">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|<span data-ttu-id="55831-129">Fügt der Auflistung deklarierter Typen einen deklarierten Typ hinzu.</span><span class="sxs-lookup"><span data-stu-id="55831-129">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55831-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="55831-130">Remarks</span></span>  
 <span data-ttu-id="55831-131">Weitere Informationen über bekannte Typen finden Sie unter [Datenvertragstypen bezeichnet](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) und <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="55831-131">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="55831-132">Finden Sie unter der [ \<"DataContractSerializer" >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) für ein Beispiel für dieses Element.</span><span class="sxs-lookup"><span data-stu-id="55831-132">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55831-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="55831-133">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="55831-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55831-134">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="55831-135">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="55831-135">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="55831-136">\<"DataContractSerializer" ></span><span class="sxs-lookup"><span data-stu-id="55831-136">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="55831-137">\<add></span><span class="sxs-lookup"><span data-stu-id="55831-137">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
