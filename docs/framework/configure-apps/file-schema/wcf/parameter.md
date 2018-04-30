---
title: '&lt;parameter&gt;'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: aa4b2c870864a4359ebca0a1ae47fc1c8aaebca0
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="ltparametergt"></a><span data-ttu-id="13d49-102">&lt;parameter&gt;</span><span class="sxs-lookup"><span data-stu-id="13d49-102">&lt;parameter&gt;</span></span>
<span data-ttu-id="13d49-103">Gibt den generischen Parameter an, wenn ein deklarierter Typ ein generischer Typ ist.</span><span class="sxs-lookup"><span data-stu-id="13d49-103">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
 <span data-ttu-id="13d49-104">\<System.Runtime.Serialization ></span><span class="sxs-lookup"><span data-stu-id="13d49-104">\<system.runtime.serialization></span></span>  
<span data-ttu-id="13d49-105">\<"DataContractSerializer" ></span><span class="sxs-lookup"><span data-stu-id="13d49-105">\<dataContractSerializer></span></span>  
<span data-ttu-id="13d49-106">\<DeclaredTypes >-Element</span><span class="sxs-lookup"><span data-stu-id="13d49-106">\<declaredTypes> Element</span></span>  
<span data-ttu-id="13d49-107">\<Hinzufügen >-Element für \<DeclaredTypes ></span><span class="sxs-lookup"><span data-stu-id="13d49-107">\<add> element for \<declaredTypes></span></span>  
<span data-ttu-id="13d49-108">\<KnownType >-Element</span><span class="sxs-lookup"><span data-stu-id="13d49-108">\<knownType> Element</span></span>  
<span data-ttu-id="13d49-109">\<Parameter >-Element</span><span class="sxs-lookup"><span data-stu-id="13d49-109">\<parameter> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13d49-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="13d49-110">Syntax</span></span>  
  
```xml  
<parameter index="integer"  
                      type=String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13d49-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="13d49-111">Attributes and Elements</span></span>  
 <span data-ttu-id="13d49-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="13d49-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13d49-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="13d49-113">Attributes</span></span>  
  
|<span data-ttu-id="13d49-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="13d49-114">Attribute</span></span>|<span data-ttu-id="13d49-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="13d49-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="13d49-116">Index</span><span class="sxs-lookup"><span data-stu-id="13d49-116">index</span></span>|<span data-ttu-id="13d49-117">Gibt den generischen Parameter an, der den bekannten Typ zurückgibt, wenn der deklarierte Typ ein generischer Typ ist.</span><span class="sxs-lookup"><span data-stu-id="13d49-117">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="13d49-118">Typ</span><span class="sxs-lookup"><span data-stu-id="13d49-118">type</span></span>|<span data-ttu-id="13d49-119">Eine Zeichenfolge, mit der der für die Serialisierung und Deserialisierung verwendete bekannte Typ beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="13d49-119">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="13d49-120">Indexattribut</span><span class="sxs-lookup"><span data-stu-id="13d49-120">index Attribute</span></span>  
  
|<span data-ttu-id="13d49-121">Wert</span><span class="sxs-lookup"><span data-stu-id="13d49-121">Value</span></span>|<span data-ttu-id="13d49-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="13d49-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="13d49-123">"0"</span><span class="sxs-lookup"><span data-stu-id="13d49-123">"0"</span></span>|<span data-ttu-id="13d49-124">Der erste Parameter im generischen Typ.</span><span class="sxs-lookup"><span data-stu-id="13d49-124">The first parameter in the generic type.</span></span> <span data-ttu-id="13d49-125">Zum Beispiel verfügt <xref:System.Collections.Generic.List%601> nur über einen Parameter.</span><span class="sxs-lookup"><span data-stu-id="13d49-125">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="13d49-126">Falls dieser als deklarierter Typ verwendet wird, wäre der Index auf "0" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="13d49-126">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="13d49-127">"1"</span><span class="sxs-lookup"><span data-stu-id="13d49-127">"1"</span></span>|<span data-ttu-id="13d49-128">Der zweite Parameter in einem generischen Typ.</span><span class="sxs-lookup"><span data-stu-id="13d49-128">The second parameter in a generic type.</span></span> <span data-ttu-id="13d49-129">Zum Beispiel verfügt <xref:System.Collections.Generic.Dictionary%602> über zwei Parameter.</span><span class="sxs-lookup"><span data-stu-id="13d49-129">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="13d49-130">Falls der bekannte Typ vom zweiten Parameter zurückgegeben wird, legen Sie das Indexattribut auf "1" fest.</span><span class="sxs-lookup"><span data-stu-id="13d49-130">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="13d49-131">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="13d49-131">Child Elements</span></span>  
 <span data-ttu-id="13d49-132">Keine</span><span class="sxs-lookup"><span data-stu-id="13d49-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="13d49-133">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="13d49-133">Parent Elements</span></span>  
  
|<span data-ttu-id="13d49-134">Element</span><span class="sxs-lookup"><span data-stu-id="13d49-134">Element</span></span>|<span data-ttu-id="13d49-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="13d49-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13d49-136">\<KnownType ></span><span class="sxs-lookup"><span data-stu-id="13d49-136">\<knownType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|<span data-ttu-id="13d49-137">Gibt einen bekannten Typ an, der von einem Feld oder einer Eigenschaft des deklarierten Typs zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="13d49-137">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13d49-138">Hinweise</span><span class="sxs-lookup"><span data-stu-id="13d49-138">Remarks</span></span>  
 <span data-ttu-id="13d49-139">Weitere Informationen über bekannte Typen finden Sie unter [Datenvertragstypen bezeichnet](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) und <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="13d49-139">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="13d49-140">Finden Sie unter der [ \<"DataContractSerializer" >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) für ein Beispiel für dieses Element.</span><span class="sxs-lookup"><span data-stu-id="13d49-140">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="13d49-141">Dieses Konfigurationselement darf nicht über zwei Attribute gleichzeitig verfügen.</span><span class="sxs-lookup"><span data-stu-id="13d49-141">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="13d49-142">Falls beide Attribute festgelegt sind, tritt <xref:System.Configuration.ConfigurationErrorsException> auf.</span><span class="sxs-lookup"><span data-stu-id="13d49-142">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13d49-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13d49-143">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="13d49-144">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="13d49-144">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="13d49-145">\<"DataContractSerializer" ></span><span class="sxs-lookup"><span data-stu-id="13d49-145">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="13d49-146">\<add></span><span class="sxs-lookup"><span data-stu-id="13d49-146">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
