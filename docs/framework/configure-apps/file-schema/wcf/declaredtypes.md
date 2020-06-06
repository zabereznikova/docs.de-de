---
title: <declaredTypes>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- declaredTypes element
- DataContractSerializer
- KnownTypes
- <declaredTypes> element
ms.assetid: f35184e4-9d9e-4d37-8fb4-d5b58220eb3e
ms.openlocfilehash: c45a4e67d0a2d98c0e9c1a91e07f25b81370244c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398054"
---
# \<declaredTypes>
<span data-ttu-id="8e578-101">Enthält die bekannten Typen, die der <xref:System.Runtime.Serialization.DataContractSerializer> bei der Deserialisierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="8e578-101">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span>  
  
 <span data-ttu-id="8e578-102">Weitere Informationen zu Daten Verträgen und bekannten Typen finden Sie unter [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="8e578-102">For more information about data contracts and known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<declaredTypes>**  
  
## <a name="syntax"></a><span data-ttu-id="8e578-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="8e578-103">Syntax</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer>
      <declaredTypes>
        <add type="String ">
          <knownType type="String">
            <parameter index="Integer"/>
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e578-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8e578-104">Attributes and Elements</span></span>  
 <span data-ttu-id="8e578-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8e578-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e578-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="8e578-106">Attributes</span></span>  
 <span data-ttu-id="8e578-107">Keine</span><span class="sxs-lookup"><span data-stu-id="8e578-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8e578-108">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8e578-108">Child Elements</span></span>  
  
|<span data-ttu-id="8e578-109">Element</span><span class="sxs-lookup"><span data-stu-id="8e578-109">Element</span></span>|<span data-ttu-id="8e578-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8e578-110">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-declaredtypes-element.md)|<span data-ttu-id="8e578-111">Fügt Typen hinzu, die bekannte Typen erfordern.</span><span class="sxs-lookup"><span data-stu-id="8e578-111">Adds types that require known types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8e578-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8e578-112">Parent Elements</span></span>  
  
|<span data-ttu-id="8e578-113">Element</span><span class="sxs-lookup"><span data-stu-id="8e578-113">Element</span></span>|<span data-ttu-id="8e578-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8e578-114">Description</span></span>|  
|-------------|-----------------|  
|[\<dataContractSerializer>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="8e578-115">Enthält Konfigurationsdaten für den <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="8e578-115">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e578-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8e578-116">Remarks</span></span>  
 <span data-ttu-id="8e578-117">Weitere Informationen zu bekannten Typen finden Sie unter [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="8e578-117">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e578-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8e578-118">Example</span></span>  
 <span data-ttu-id="8e578-119">Der folgende XML-Code zeigt deklarierte Typen und bekannte Typen, die zu einem-Element hinzugefügt werden `DataContractSerializer` .</span><span class="sxs-lookup"><span data-stu-id="8e578-119">The following XML code shows declared types and known types added to a `DataContractSerializer` element.</span></span> <span data-ttu-id="8e578-120">Im Beispiel werden drei hinzugefügte Typen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="8e578-120">The example shows three types being added.</span></span> <span data-ttu-id="8e578-121">Der erste ist ein benutzerdefinierter Typ mit dem Namen "Orders", der einen bekannten Typ mit dem Namen "Item" verwendet.</span><span class="sxs-lookup"><span data-stu-id="8e578-121">The first is a custom type named "Orders" that uses a known type named "Item".</span></span> <span data-ttu-id="8e578-122">Der zweite deklarierte Typ ist <xref:System.Collections.Generic.List%601> und verwendet `Item` als bekannten Typ.</span><span class="sxs-lookup"><span data-stu-id="8e578-122">The second declared type is a <xref:System.Collections.Generic.List%601> that uses `Item` as a known type.</span></span> <span data-ttu-id="8e578-123">Der dritte deklarierte Typ ist <xref:System.Collections.Generic.Dictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="8e578-123">Finally the third declared type is a <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="8e578-124">Der <xref:System.Collections.Generic.Dictionary%602>-Klassentyp ist ein generischer Typ mit zwei Typparametern.</span><span class="sxs-lookup"><span data-stu-id="8e578-124">The <xref:System.Collections.Generic.Dictionary%602> class type is a generic type, with two type parameters.</span></span> <span data-ttu-id="8e578-125">Der erste stellt den Schlüssel dar und der zweite den Wert.</span><span class="sxs-lookup"><span data-stu-id="8e578-125">The first represents the key and the second represents the value.</span></span> <span data-ttu-id="8e578-126">Im folgenden Beispiel wird ein <xref:System.Collections.Generic.List%601> des zweiten Typs (der Wert) zur Liste bekannter Typen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8e578-126">The following example adds a <xref:System.Collections.Generic.List%601> of the second type (the value) to the list of known types.</span></span> <span data-ttu-id="8e578-127">Sie müssen das `index`-Attribut verwenden, um anzugeben, welcher Typparameter im bekannten Typ verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8e578-127">You must use the `index` attribute to specify which type parameter to use in the known type.</span></span> <span data-ttu-id="8e578-128">In diesem Fall wird der Werttyp über das Indexattribut angegeben, das auf "1" festgelegt ist (die Auflistung ist nullbasiert).</span><span class="sxs-lookup"><span data-stu-id="8e578-128">In this case, the value type is indicated by the index attribute set to "1" (the collection is zero-based).</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer>
      <declaredTypes>
        <add type="Examples.Types.Orders, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />
        </add>
        <add type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />
        </add>
        <add type="System.Collections.Generic.Dictionary`2, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
            <parameter index="1"/>
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="8e578-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8e578-129">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [<span data-ttu-id="8e578-130">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="8e578-130">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [\<add>](add-of-declaredtypes-element.md)
