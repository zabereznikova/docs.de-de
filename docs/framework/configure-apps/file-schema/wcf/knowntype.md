---
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: 61f51b2ecd572ba254317a01e0f514503c7cc9e4
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397870"
---
# <a name="knowntype"></a><span data-ttu-id="aac88-101">\<knownType></span><span class="sxs-lookup"><span data-stu-id="aac88-101">\<knownType></span></span>
<span data-ttu-id="aac88-102">Gibt einen Typ an, der vom <xref:System.Runtime.Serialization.DataContractSerializer> während der Deserialisierung verwendet werden sollte.</span><span class="sxs-lookup"><span data-stu-id="aac88-102">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="aac88-103">Dieses Element gibt einen "bekannten Typ" an, der von einem Feld oder einer Eigenschaft eines "deklarierten Typs" zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="aac88-103">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="aac88-104">Weitere Informationen finden Sie unter [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="aac88-104">For more information, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
<span data-ttu-id="aac88-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="aac88-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="aac88-106">&nbsp;&nbsp;[ **\<System. Runtime. Serialization >** ](system-runtime-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="aac88-106">&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)</span></span>\
<span data-ttu-id="aac88-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<DataContractSerializer->** ](datacontractserializer.md)</span><span class="sxs-lookup"><span data-stu-id="aac88-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)</span></span>\
<span data-ttu-id="aac88-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<DeclaredTypes->** ](declaredtypes.md)</span><span class="sxs-lookup"><span data-stu-id="aac88-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)</span></span>\
<span data-ttu-id="aac88-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> Hinzufügen**](add-of-declaredtypes-element.md)</span><span class="sxs-lookup"><span data-stu-id="aac88-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-of-declaredtypes-element.md)</span></span>\
<span data-ttu-id="aac88-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<KnownType->**</span><span class="sxs-lookup"><span data-stu-id="aac88-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<knownType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aac88-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="aac88-111">Syntax</span></span>  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a><span data-ttu-id="aac88-112">Typ</span><span class="sxs-lookup"><span data-stu-id="aac88-112">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aac88-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="aac88-113">Attributes and Elements</span></span>  
 <span data-ttu-id="aac88-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="aac88-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aac88-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="aac88-115">Attributes</span></span>  
  
|<span data-ttu-id="aac88-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="aac88-116">Attribute</span></span>|<span data-ttu-id="aac88-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aac88-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aac88-118">Typ</span><span class="sxs-lookup"><span data-stu-id="aac88-118">type</span></span>|<span data-ttu-id="aac88-119">Gibt den Typ (einschließlich Namespace), den Assemblynamen, die Version, die Kultur und das öffentliche Schlüsseltoken an.</span><span class="sxs-lookup"><span data-stu-id="aac88-119">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aac88-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aac88-120">Child Elements</span></span>  
  
|<span data-ttu-id="aac88-121">Element</span><span class="sxs-lookup"><span data-stu-id="aac88-121">Element</span></span>|<span data-ttu-id="aac88-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aac88-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aac88-123">\<parameter></span><span class="sxs-lookup"><span data-stu-id="aac88-123">\<parameter></span></span>](parameter.md)|<span data-ttu-id="aac88-124">Gibt einen Parameterindex an, wenn der deklarierte Typ ein generischer Typ ist.</span><span class="sxs-lookup"><span data-stu-id="aac88-124">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aac88-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aac88-125">Parent Elements</span></span>  
  
|<span data-ttu-id="aac88-126">Element</span><span class="sxs-lookup"><span data-stu-id="aac88-126">Element</span></span>|<span data-ttu-id="aac88-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aac88-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aac88-128">\<add></span><span class="sxs-lookup"><span data-stu-id="aac88-128">\<add></span></span>](add-of-declaredtypes-element.md)|<span data-ttu-id="aac88-129">Fügt der Auflistung deklarierter Typen einen deklarierten Typ hinzu.</span><span class="sxs-lookup"><span data-stu-id="aac88-129">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aac88-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aac88-130">Remarks</span></span>  
 <span data-ttu-id="aac88-131">Weitere Informationen zu bekannten Typen finden Sie unter [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="aac88-131">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="aac88-132">Ein Beispiel für die Verwendung dieses Elements finden Sie im [ \<> DataContractSerializer](datacontractserializer-element.md) .</span><span class="sxs-lookup"><span data-stu-id="aac88-132">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aac88-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aac88-133">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="aac88-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aac88-134">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="aac88-135">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="aac88-135">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="aac88-136">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="aac88-136">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="aac88-137">\<add></span><span class="sxs-lookup"><span data-stu-id="aac88-137">\<add></span></span>](add-of-declaredtypes-element.md)
