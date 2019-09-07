---
title: <parameter>
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: 07fa410109a7bd2fa315132c4737301698bb3a93
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400113"
---
# <a name="parameter"></a><span data-ttu-id="437d3-101">\<Parameter ></span><span class="sxs-lookup"><span data-stu-id="437d3-101">\<parameter></span></span>
<span data-ttu-id="437d3-102">Gibt den generischen Parameter an, wenn ein deklarierter Typ ein generischer Typ ist.</span><span class="sxs-lookup"><span data-stu-id="437d3-102">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
<span data-ttu-id="437d3-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="437d3-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="437d3-104">&nbsp;&nbsp;[ **\<System. Runtime. Serialization >** ](system-runtime-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="437d3-104">&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)</span></span>\
<span data-ttu-id="437d3-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<DataContractSerializer->** ](datacontractserializer.md)</span><span class="sxs-lookup"><span data-stu-id="437d3-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)</span></span>\
<span data-ttu-id="437d3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<DeclaredTypes->** ](declaredtypes.md)</span><span class="sxs-lookup"><span data-stu-id="437d3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)</span></span>\
<span data-ttu-id="437d3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> Hinzufügen**](add-of-declaredtypes-element.md)</span><span class="sxs-lookup"><span data-stu-id="437d3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-of-declaredtypes-element.md)</span></span>\
<span data-ttu-id="437d3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<KnownType->** ](knowntype.md)</span><span class="sxs-lookup"><span data-stu-id="437d3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<knownType>**](knowntype.md)</span></span>\
<span data-ttu-id="437d3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Parameter >**</span><span class="sxs-lookup"><span data-stu-id="437d3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<parameter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="437d3-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="437d3-110">Syntax</span></span>  
  
```xml  
<parameter index="Integer"
           type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="437d3-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="437d3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="437d3-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="437d3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="437d3-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="437d3-113">Attributes</span></span>  
  
|<span data-ttu-id="437d3-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="437d3-114">Attribute</span></span>|<span data-ttu-id="437d3-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="437d3-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="437d3-116">Index</span><span class="sxs-lookup"><span data-stu-id="437d3-116">index</span></span>|<span data-ttu-id="437d3-117">Gibt den generischen Parameter an, der den bekannten Typ zurückgibt, wenn der deklarierte Typ ein generischer Typ ist.</span><span class="sxs-lookup"><span data-stu-id="437d3-117">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="437d3-118">Typ</span><span class="sxs-lookup"><span data-stu-id="437d3-118">type</span></span>|<span data-ttu-id="437d3-119">Eine Zeichenfolge, mit der der für die Serialisierung und Deserialisierung verwendete bekannte Typ beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="437d3-119">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="437d3-120">Indexattribut</span><span class="sxs-lookup"><span data-stu-id="437d3-120">index Attribute</span></span>  
  
|<span data-ttu-id="437d3-121">Wert</span><span class="sxs-lookup"><span data-stu-id="437d3-121">Value</span></span>|<span data-ttu-id="437d3-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="437d3-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="437d3-123">"0"</span><span class="sxs-lookup"><span data-stu-id="437d3-123">"0"</span></span>|<span data-ttu-id="437d3-124">Der erste Parameter im generischen Typ.</span><span class="sxs-lookup"><span data-stu-id="437d3-124">The first parameter in the generic type.</span></span> <span data-ttu-id="437d3-125">Zum Beispiel verfügt <xref:System.Collections.Generic.List%601> nur über einen Parameter.</span><span class="sxs-lookup"><span data-stu-id="437d3-125">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="437d3-126">Falls dieser als deklarierter Typ verwendet wird, wäre der Index auf "0" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="437d3-126">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="437d3-127">"1"</span><span class="sxs-lookup"><span data-stu-id="437d3-127">"1"</span></span>|<span data-ttu-id="437d3-128">Der zweite Parameter in einem generischen Typ.</span><span class="sxs-lookup"><span data-stu-id="437d3-128">The second parameter in a generic type.</span></span> <span data-ttu-id="437d3-129">Zum Beispiel verfügt <xref:System.Collections.Generic.Dictionary%602> über zwei Parameter.</span><span class="sxs-lookup"><span data-stu-id="437d3-129">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="437d3-130">Falls der bekannte Typ vom zweiten Parameter zurückgegeben wird, legen Sie das Indexattribut auf "1" fest.</span><span class="sxs-lookup"><span data-stu-id="437d3-130">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="437d3-131">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="437d3-131">Child Elements</span></span>  
 <span data-ttu-id="437d3-132">Keine</span><span class="sxs-lookup"><span data-stu-id="437d3-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="437d3-133">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="437d3-133">Parent Elements</span></span>  
  
|<span data-ttu-id="437d3-134">Element</span><span class="sxs-lookup"><span data-stu-id="437d3-134">Element</span></span>|<span data-ttu-id="437d3-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="437d3-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="437d3-136">\<knownType></span><span class="sxs-lookup"><span data-stu-id="437d3-136">\<knownType></span></span>](knowntype.md)|<span data-ttu-id="437d3-137">Gibt einen bekannten Typ an, der von einem Feld oder einer Eigenschaft des deklarierten Typs zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="437d3-137">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="437d3-138">Hinweise</span><span class="sxs-lookup"><span data-stu-id="437d3-138">Remarks</span></span>  
 <span data-ttu-id="437d3-139">Weitere Informationen zu bekannten Typen finden Sie unter [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="437d3-139">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="437d3-140">Ein Beispiel für die Verwendung dieses Elements finden Sie im [ \<> DataContractSerializer](datacontractserializer-element.md) .</span><span class="sxs-lookup"><span data-stu-id="437d3-140">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="437d3-141">Dieses Konfigurationselement darf nicht über zwei Attribute gleichzeitig verfügen.</span><span class="sxs-lookup"><span data-stu-id="437d3-141">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="437d3-142">Falls beide Attribute festgelegt sind, tritt <xref:System.Configuration.ConfigurationErrorsException> auf.</span><span class="sxs-lookup"><span data-stu-id="437d3-142">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="437d3-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="437d3-143">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="437d3-144">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="437d3-144">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="437d3-145">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="437d3-145">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="437d3-146">\<add></span><span class="sxs-lookup"><span data-stu-id="437d3-146">\<add></span></span>](add-of-declaredtypes-element.md)
