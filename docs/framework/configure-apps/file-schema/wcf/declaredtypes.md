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
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398054"
---
# <a name="declaredtypes"></a><span data-ttu-id="2fbf6-101">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="2fbf6-101">\<declaredTypes></span></span>
<span data-ttu-id="2fbf6-102">Enthält die bekannten Typen, die der <xref:System.Runtime.Serialization.DataContractSerializer> bei der Deserialisierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="2fbf6-102">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span>  
  
 <span data-ttu-id="2fbf6-103">Weitere Informationen zu Daten Verträgen und bekannten Typen finden Sie unter [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="2fbf6-103">For more information about data contracts and known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
<span data-ttu-id="2fbf6-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2fbf6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2fbf6-105">&nbsp;&nbsp;[ **\<System. Runtime. Serialization >** ](system-runtime-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="2fbf6-105">&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)</span></span>\
<span data-ttu-id="2fbf6-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<DataContractSerializer->** ](datacontractserializer.md)</span><span class="sxs-lookup"><span data-stu-id="2fbf6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)</span></span>\
<span data-ttu-id="2fbf6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<DeclaredTypes->**</span><span class="sxs-lookup"><span data-stu-id="2fbf6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<declaredTypes>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fbf6-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="2fbf6-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2fbf6-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2fbf6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2fbf6-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2fbf6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2fbf6-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="2fbf6-111">Attributes</span></span>  
 <span data-ttu-id="2fbf6-112">Keine</span><span class="sxs-lookup"><span data-stu-id="2fbf6-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2fbf6-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2fbf6-113">Child Elements</span></span>  
  
|<span data-ttu-id="2fbf6-114">Element</span><span class="sxs-lookup"><span data-stu-id="2fbf6-114">Element</span></span>|<span data-ttu-id="2fbf6-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2fbf6-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2fbf6-116">\<add></span><span class="sxs-lookup"><span data-stu-id="2fbf6-116">\<add></span></span>](add-of-declaredtypes-element.md)|<span data-ttu-id="2fbf6-117">Fügt Typen hinzu, die bekannte Typen erfordern.</span><span class="sxs-lookup"><span data-stu-id="2fbf6-117">Adds types that require known types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2fbf6-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2fbf6-118">Parent Elements</span></span>  
  
|<span data-ttu-id="2fbf6-119">Element</span><span class="sxs-lookup"><span data-stu-id="2fbf6-119">Element</span></span>|<span data-ttu-id="2fbf6-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2fbf6-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2fbf6-121">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="2fbf6-121">\<dataContractSerializer></span></span>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="2fbf6-122">Enthält Konfigurationsdaten für den <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="2fbf6-122">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2fbf6-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2fbf6-123">Remarks</span></span>  
 <span data-ttu-id="2fbf6-124">Weitere Informationen zu bekannten Typen finden Sie unter [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="2fbf6-124">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2fbf6-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2fbf6-125">Example</span></span>  
 <span data-ttu-id="2fbf6-126">Der folgende XML-Code zeigt deklarierte Typen und bekannte Typen, `DataContractSerializer` die zu einem-Element hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="2fbf6-126">The following XML code shows declared types and known types added to a `DataContractSerializer` element.</span></span> <span data-ttu-id="2fbf6-127">Im Beispiel werden drei hinzugefügte Typen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2fbf6-127">The example shows three types being added.</span></span> <span data-ttu-id="2fbf6-128">Der erste ist ein benutzerdefinierter Typ mit dem Namen "Orders", der einen bekannten Typ mit dem Namen "Item" verwendet.</span><span class="sxs-lookup"><span data-stu-id="2fbf6-128">The first is a custom type named "Orders" that uses a known type named "Item".</span></span> <span data-ttu-id="2fbf6-129">Der zweite deklarierte Typ ist <xref:System.Collections.Generic.List%601> und verwendet `Item` als bekannten Typ.</span><span class="sxs-lookup"><span data-stu-id="2fbf6-129">The second declared type is a <xref:System.Collections.Generic.List%601> that uses `Item` as a known type.</span></span> <span data-ttu-id="2fbf6-130">Der dritte deklarierte Typ ist <xref:System.Collections.Generic.Dictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="2fbf6-130">Finally the third declared type is a <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="2fbf6-131">Der <xref:System.Collections.Generic.Dictionary%602>-Klassentyp ist ein generischer Typ mit zwei Typparametern.</span><span class="sxs-lookup"><span data-stu-id="2fbf6-131">The <xref:System.Collections.Generic.Dictionary%602> class type is a generic type, with two type parameters.</span></span> <span data-ttu-id="2fbf6-132">Der erste stellt den Schlüssel dar und der zweite den Wert.</span><span class="sxs-lookup"><span data-stu-id="2fbf6-132">The first represents the key and the second represents the value.</span></span> <span data-ttu-id="2fbf6-133">Im folgenden Beispiel wird ein <xref:System.Collections.Generic.List%601> des zweiten Typs (der Wert) zur Liste bekannter Typen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2fbf6-133">The following example adds a <xref:System.Collections.Generic.List%601> of the second type (the value) to the list of known types.</span></span> <span data-ttu-id="2fbf6-134">Sie müssen das `index`-Attribut verwenden, um anzugeben, welcher Typparameter im bekannten Typ verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2fbf6-134">You must use the `index` attribute to specify which type parameter to use in the known type.</span></span> <span data-ttu-id="2fbf6-135">In diesem Fall wird der Werttyp über das Indexattribut angegeben, das auf "1" festgelegt ist (die Auflistung ist nullbasiert).</span><span class="sxs-lookup"><span data-stu-id="2fbf6-135">In this case, the value type is indicated by the index attribute set to "1" (the collection is zero-based).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2fbf6-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2fbf6-136">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="2fbf6-137">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="2fbf6-137">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="2fbf6-138">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="2fbf6-138">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="2fbf6-139">\<add></span><span class="sxs-lookup"><span data-stu-id="2fbf6-139">\<add></span></span>](add-of-declaredtypes-element.md)
