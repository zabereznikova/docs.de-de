---
title: <parameter>
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: 8b14dc1908ef3a06549154f70efb2d4e5cb10076
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55289429"
---
# <a name="parameter"></a><span data-ttu-id="8505e-101">\<parameter></span><span class="sxs-lookup"><span data-stu-id="8505e-101">\<parameter></span></span>
<span data-ttu-id="8505e-102">Gibt den generischen Parameter an, wenn ein deklarierter Typ ein generischer Typ ist.</span><span class="sxs-lookup"><span data-stu-id="8505e-102">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
 <span data-ttu-id="8505e-103">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="8505e-103">\<system.runtime.serialization></span></span>  
<span data-ttu-id="8505e-104">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="8505e-104">\<dataContractSerializer></span></span>  
<span data-ttu-id="8505e-105">\<DeclaredTypes >-Element</span><span class="sxs-lookup"><span data-stu-id="8505e-105">\<declaredTypes> Element</span></span>  
<span data-ttu-id="8505e-106">\<Hinzufügen >-Element für \<DeclaredTypes ></span><span class="sxs-lookup"><span data-stu-id="8505e-106">\<add> element for \<declaredTypes></span></span>  
<span data-ttu-id="8505e-107">\<KnownType >-Element</span><span class="sxs-lookup"><span data-stu-id="8505e-107">\<knownType> Element</span></span>  
<span data-ttu-id="8505e-108">\<Parameter >-Element</span><span class="sxs-lookup"><span data-stu-id="8505e-108">\<parameter> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8505e-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="8505e-109">Syntax</span></span>  
  
```xml  
<parameter index="Integer"
           type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8505e-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8505e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8505e-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8505e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8505e-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="8505e-112">Attributes</span></span>  
  
|<span data-ttu-id="8505e-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="8505e-113">Attribute</span></span>|<span data-ttu-id="8505e-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8505e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8505e-115">Index</span><span class="sxs-lookup"><span data-stu-id="8505e-115">index</span></span>|<span data-ttu-id="8505e-116">Gibt den generischen Parameter an, der den bekannten Typ zurückgibt, wenn der deklarierte Typ ein generischer Typ ist.</span><span class="sxs-lookup"><span data-stu-id="8505e-116">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="8505e-117">Typ</span><span class="sxs-lookup"><span data-stu-id="8505e-117">type</span></span>|<span data-ttu-id="8505e-118">Eine Zeichenfolge, mit der der für die Serialisierung und Deserialisierung verwendete bekannte Typ beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="8505e-118">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="8505e-119">Indexattribut</span><span class="sxs-lookup"><span data-stu-id="8505e-119">index Attribute</span></span>  
  
|<span data-ttu-id="8505e-120">Wert</span><span class="sxs-lookup"><span data-stu-id="8505e-120">Value</span></span>|<span data-ttu-id="8505e-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8505e-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8505e-122">"0"</span><span class="sxs-lookup"><span data-stu-id="8505e-122">"0"</span></span>|<span data-ttu-id="8505e-123">Der erste Parameter im generischen Typ.</span><span class="sxs-lookup"><span data-stu-id="8505e-123">The first parameter in the generic type.</span></span> <span data-ttu-id="8505e-124">Zum Beispiel verfügt <xref:System.Collections.Generic.List%601> nur über einen Parameter.</span><span class="sxs-lookup"><span data-stu-id="8505e-124">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="8505e-125">Falls dieser als deklarierter Typ verwendet wird, wäre der Index auf "0" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8505e-125">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="8505e-126">"1"</span><span class="sxs-lookup"><span data-stu-id="8505e-126">"1"</span></span>|<span data-ttu-id="8505e-127">Der zweite Parameter in einem generischen Typ.</span><span class="sxs-lookup"><span data-stu-id="8505e-127">The second parameter in a generic type.</span></span> <span data-ttu-id="8505e-128">Zum Beispiel verfügt <xref:System.Collections.Generic.Dictionary%602> über zwei Parameter.</span><span class="sxs-lookup"><span data-stu-id="8505e-128">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="8505e-129">Falls der bekannte Typ vom zweiten Parameter zurückgegeben wird, legen Sie das Indexattribut auf "1" fest.</span><span class="sxs-lookup"><span data-stu-id="8505e-129">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8505e-130">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8505e-130">Child Elements</span></span>  
 <span data-ttu-id="8505e-131">Keine</span><span class="sxs-lookup"><span data-stu-id="8505e-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8505e-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8505e-132">Parent Elements</span></span>  
  
|<span data-ttu-id="8505e-133">Element</span><span class="sxs-lookup"><span data-stu-id="8505e-133">Element</span></span>|<span data-ttu-id="8505e-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8505e-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8505e-135">\<knownType></span><span class="sxs-lookup"><span data-stu-id="8505e-135">\<knownType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|<span data-ttu-id="8505e-136">Gibt einen bekannten Typ an, der von einem Feld oder einer Eigenschaft des deklarierten Typs zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="8505e-136">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8505e-137">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8505e-137">Remarks</span></span>  
 <span data-ttu-id="8505e-138">Weitere Informationen zu bekannten Typen finden Sie unter [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) und <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="8505e-138">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="8505e-139">Finden Sie unter den [ \<DataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) ein Beispiel für die Verwendung dieses Elements.</span><span class="sxs-lookup"><span data-stu-id="8505e-139">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="8505e-140">Dieses Konfigurationselement darf nicht über zwei Attribute gleichzeitig verfügen.</span><span class="sxs-lookup"><span data-stu-id="8505e-140">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="8505e-141">Falls beide Attribute festgelegt sind, tritt <xref:System.Configuration.ConfigurationErrorsException> auf.</span><span class="sxs-lookup"><span data-stu-id="8505e-141">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8505e-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8505e-142">See also</span></span>
- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="8505e-143">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="8505e-143">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="8505e-144">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="8505e-144">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)
- [<span data-ttu-id="8505e-145">\<add></span><span class="sxs-lookup"><span data-stu-id="8505e-145">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
