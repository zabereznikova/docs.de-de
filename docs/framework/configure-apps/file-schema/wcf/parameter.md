---
title: <parameter>
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: 07fa410109a7bd2fa315132c4737301698bb3a93
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400113"
---
# \<parameter>
<span data-ttu-id="1ccc4-101">Gibt den generischen Parameter an, wenn ein deklarierter Typ ein generischer Typ ist.</span><span class="sxs-lookup"><span data-stu-id="1ccc4-101">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-of-declaredtypes-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<knownType>**](knowntype.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<parameter>**  
  
## <a name="syntax"></a><span data-ttu-id="1ccc4-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="1ccc4-102">Syntax</span></span>  
  
```xml  
<parameter index="Integer"
           type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ccc4-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1ccc4-103">Attributes and Elements</span></span>  
 <span data-ttu-id="1ccc4-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1ccc4-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ccc4-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="1ccc4-105">Attributes</span></span>  
  
|<span data-ttu-id="1ccc4-106">attribute</span><span class="sxs-lookup"><span data-stu-id="1ccc4-106">Attribute</span></span>|<span data-ttu-id="1ccc4-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1ccc4-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1ccc4-108">Index</span><span class="sxs-lookup"><span data-stu-id="1ccc4-108">index</span></span>|<span data-ttu-id="1ccc4-109">Gibt den generischen Parameter an, der den bekannten Typ zurückgibt, wenn der deklarierte Typ ein generischer Typ ist.</span><span class="sxs-lookup"><span data-stu-id="1ccc4-109">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="1ccc4-110">type</span><span class="sxs-lookup"><span data-stu-id="1ccc4-110">type</span></span>|<span data-ttu-id="1ccc4-111">Eine Zeichenfolge, mit der der für die Serialisierung und Deserialisierung verwendete bekannte Typ beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="1ccc4-111">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="1ccc4-112">Indexattribut</span><span class="sxs-lookup"><span data-stu-id="1ccc4-112">index Attribute</span></span>  
  
|<span data-ttu-id="1ccc4-113">Wert</span><span class="sxs-lookup"><span data-stu-id="1ccc4-113">Value</span></span>|<span data-ttu-id="1ccc4-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1ccc4-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1ccc4-115">"0"</span><span class="sxs-lookup"><span data-stu-id="1ccc4-115">"0"</span></span>|<span data-ttu-id="1ccc4-116">Der erste Parameter im generischen Typ.</span><span class="sxs-lookup"><span data-stu-id="1ccc4-116">The first parameter in the generic type.</span></span> <span data-ttu-id="1ccc4-117">Zum Beispiel verfügt <xref:System.Collections.Generic.List%601> nur über einen Parameter.</span><span class="sxs-lookup"><span data-stu-id="1ccc4-117">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="1ccc4-118">Falls dieser als deklarierter Typ verwendet wird, wäre der Index auf "0" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1ccc4-118">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="1ccc4-119">"1"</span><span class="sxs-lookup"><span data-stu-id="1ccc4-119">"1"</span></span>|<span data-ttu-id="1ccc4-120">Der zweite Parameter in einem generischen Typ.</span><span class="sxs-lookup"><span data-stu-id="1ccc4-120">The second parameter in a generic type.</span></span> <span data-ttu-id="1ccc4-121">Zum Beispiel verfügt <xref:System.Collections.Generic.Dictionary%602> über zwei Parameter.</span><span class="sxs-lookup"><span data-stu-id="1ccc4-121">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="1ccc4-122">Falls der bekannte Typ vom zweiten Parameter zurückgegeben wird, legen Sie das Indexattribut auf "1" fest.</span><span class="sxs-lookup"><span data-stu-id="1ccc4-122">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1ccc4-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1ccc4-123">Child Elements</span></span>  
 <span data-ttu-id="1ccc4-124">Keine</span><span class="sxs-lookup"><span data-stu-id="1ccc4-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1ccc4-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1ccc4-125">Parent Elements</span></span>  
  
|<span data-ttu-id="1ccc4-126">Element</span><span class="sxs-lookup"><span data-stu-id="1ccc4-126">Element</span></span>|<span data-ttu-id="1ccc4-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ccc4-127">Description</span></span>|  
|-------------|-----------------|  
|[\<knownType>](knowntype.md)|<span data-ttu-id="1ccc4-128">Gibt einen bekannten Typ an, der von einem Feld oder einer Eigenschaft des deklarierten Typs zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="1ccc4-128">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ccc4-129">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1ccc4-129">Remarks</span></span>  
 <span data-ttu-id="1ccc4-130">Weitere Informationen zu bekannten Typen finden Sie unter [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="1ccc4-130">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="1ccc4-131">[\<dataContractSerializer>](datacontractserializer-element.md)Ein Beispiel für die Verwendung dieses Elements finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="1ccc4-131">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="1ccc4-132">Dieses Konfigurationselement darf nicht über zwei Attribute gleichzeitig verfügen.</span><span class="sxs-lookup"><span data-stu-id="1ccc4-132">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="1ccc4-133">Falls beide Attribute festgelegt sind, tritt <xref:System.Configuration.ConfigurationErrorsException> auf.</span><span class="sxs-lookup"><span data-stu-id="1ccc4-133">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ccc4-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ccc4-134">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="1ccc4-135">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="1ccc4-135">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [\<add>](add-of-declaredtypes-element.md)
