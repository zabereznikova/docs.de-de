---
title: <parameter>
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: 22ef3c3c6d23d6c68c27d6b5d1ed35b7c9910d48
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230797"
---
# <a name="parameter"></a><span data-ttu-id="3cbca-101">\<parameter></span><span class="sxs-lookup"><span data-stu-id="3cbca-101">\<parameter></span></span>
<span data-ttu-id="3cbca-102">Gibt den generischen Parameter an, wenn ein deklarierter Typ ein generischer Typ ist.</span><span class="sxs-lookup"><span data-stu-id="3cbca-102">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
 <span data-ttu-id="3cbca-103">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="3cbca-103">\<system.runtime.serialization></span></span>  
<span data-ttu-id="3cbca-104">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="3cbca-104">\<dataContractSerializer></span></span>  
<span data-ttu-id="3cbca-105">\<DeclaredTypes >-Element</span><span class="sxs-lookup"><span data-stu-id="3cbca-105">\<declaredTypes> Element</span></span>  
<span data-ttu-id="3cbca-106">\<Hinzufügen >-Element für \<DeclaredTypes ></span><span class="sxs-lookup"><span data-stu-id="3cbca-106">\<add> element for \<declaredTypes></span></span>  
<span data-ttu-id="3cbca-107">\<KnownType >-Element</span><span class="sxs-lookup"><span data-stu-id="3cbca-107">\<knownType> Element</span></span>  
<span data-ttu-id="3cbca-108">\<Parameter >-Element</span><span class="sxs-lookup"><span data-stu-id="3cbca-108">\<parameter> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cbca-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="3cbca-109">Syntax</span></span>  
  
```xml  
<parameter index="Integer"
           type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3cbca-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3cbca-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3cbca-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3cbca-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3cbca-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="3cbca-112">Attributes</span></span>  
  
|<span data-ttu-id="3cbca-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="3cbca-113">Attribute</span></span>|<span data-ttu-id="3cbca-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3cbca-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3cbca-115">Index</span><span class="sxs-lookup"><span data-stu-id="3cbca-115">index</span></span>|<span data-ttu-id="3cbca-116">Gibt den generischen Parameter an, der den bekannten Typ zurückgibt, wenn der deklarierte Typ ein generischer Typ ist.</span><span class="sxs-lookup"><span data-stu-id="3cbca-116">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="3cbca-117">Typ</span><span class="sxs-lookup"><span data-stu-id="3cbca-117">type</span></span>|<span data-ttu-id="3cbca-118">Eine Zeichenfolge, mit der der für die Serialisierung und Deserialisierung verwendete bekannte Typ beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="3cbca-118">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="3cbca-119">Indexattribut</span><span class="sxs-lookup"><span data-stu-id="3cbca-119">index Attribute</span></span>  
  
|<span data-ttu-id="3cbca-120">Wert</span><span class="sxs-lookup"><span data-stu-id="3cbca-120">Value</span></span>|<span data-ttu-id="3cbca-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3cbca-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3cbca-122">"0"</span><span class="sxs-lookup"><span data-stu-id="3cbca-122">"0"</span></span>|<span data-ttu-id="3cbca-123">Der erste Parameter im generischen Typ.</span><span class="sxs-lookup"><span data-stu-id="3cbca-123">The first parameter in the generic type.</span></span> <span data-ttu-id="3cbca-124">Zum Beispiel verfügt <xref:System.Collections.Generic.List%601> nur über einen Parameter.</span><span class="sxs-lookup"><span data-stu-id="3cbca-124">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="3cbca-125">Falls dieser als deklarierter Typ verwendet wird, wäre der Index auf "0" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3cbca-125">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="3cbca-126">"1"</span><span class="sxs-lookup"><span data-stu-id="3cbca-126">"1"</span></span>|<span data-ttu-id="3cbca-127">Der zweite Parameter in einem generischen Typ.</span><span class="sxs-lookup"><span data-stu-id="3cbca-127">The second parameter in a generic type.</span></span> <span data-ttu-id="3cbca-128">Zum Beispiel verfügt <xref:System.Collections.Generic.Dictionary%602> über zwei Parameter.</span><span class="sxs-lookup"><span data-stu-id="3cbca-128">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="3cbca-129">Falls der bekannte Typ vom zweiten Parameter zurückgegeben wird, legen Sie das Indexattribut auf "1" fest.</span><span class="sxs-lookup"><span data-stu-id="3cbca-129">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3cbca-130">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3cbca-130">Child Elements</span></span>  
 <span data-ttu-id="3cbca-131">Keine</span><span class="sxs-lookup"><span data-stu-id="3cbca-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3cbca-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3cbca-132">Parent Elements</span></span>  
  
|<span data-ttu-id="3cbca-133">Element</span><span class="sxs-lookup"><span data-stu-id="3cbca-133">Element</span></span>|<span data-ttu-id="3cbca-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3cbca-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3cbca-135">\<knownType></span><span class="sxs-lookup"><span data-stu-id="3cbca-135">\<knownType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|<span data-ttu-id="3cbca-136">Gibt einen bekannten Typ an, der von einem Feld oder einer Eigenschaft des deklarierten Typs zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="3cbca-136">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cbca-137">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3cbca-137">Remarks</span></span>  
 <span data-ttu-id="3cbca-138">Weitere Informationen zu bekannten Typen finden Sie unter [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) und <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="3cbca-138">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="3cbca-139">Finden Sie unter den [ \<DataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) ein Beispiel für die Verwendung dieses Elements.</span><span class="sxs-lookup"><span data-stu-id="3cbca-139">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="3cbca-140">Dieses Konfigurationselement darf nicht über zwei Attribute gleichzeitig verfügen.</span><span class="sxs-lookup"><span data-stu-id="3cbca-140">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="3cbca-141">Falls beide Attribute festgelegt sind, tritt <xref:System.Configuration.ConfigurationErrorsException> auf.</span><span class="sxs-lookup"><span data-stu-id="3cbca-141">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cbca-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3cbca-142">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="3cbca-143">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="3cbca-143">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="3cbca-144">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="3cbca-144">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)
- [<span data-ttu-id="3cbca-145">\<add></span><span class="sxs-lookup"><span data-stu-id="3cbca-145">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
