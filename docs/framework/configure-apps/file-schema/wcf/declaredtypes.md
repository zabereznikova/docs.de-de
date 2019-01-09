---
title: '&lt;declaredTypes&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- declaredTypes element
- DataContractSerializer
- KnownTypes
- <declaredTypes> element
ms.assetid: f35184e4-9d9e-4d37-8fb4-d5b58220eb3e
ms.openlocfilehash: 0fadb13d4fcfbe87eb2c08fc35323c726c0ac2a6
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146419"
---
# <a name="ltdeclaredtypesgt"></a><span data-ttu-id="c4893-102">&lt;declaredTypes&gt;</span><span class="sxs-lookup"><span data-stu-id="c4893-102">&lt;declaredTypes&gt;</span></span>
<span data-ttu-id="c4893-103">Enthält die bekannten Typen, die der <xref:System.Runtime.Serialization.DataContractSerializer> bei der Deserialisierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="c4893-103">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span>  
  
 <span data-ttu-id="c4893-104">Weitere Informationen über Datenverträge und bekannte Typen finden Sie unter [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="c4893-104">For more information about data contracts and known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="c4893-105">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="c4893-105">system.runtime.serialization</span></span>  
<span data-ttu-id="c4893-106">\<DataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="c4893-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="c4893-107">\<DeclaredTypes ></span><span class="sxs-lookup"><span data-stu-id="c4893-107">\<declaredTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4893-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4893-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c4893-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c4893-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c4893-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c4893-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c4893-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="c4893-111">Attributes</span></span>  
 <span data-ttu-id="c4893-112">Keine</span><span class="sxs-lookup"><span data-stu-id="c4893-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c4893-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c4893-113">Child Elements</span></span>  
  
|<span data-ttu-id="c4893-114">Element</span><span class="sxs-lookup"><span data-stu-id="c4893-114">Element</span></span>|<span data-ttu-id="c4893-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c4893-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c4893-116">\<add></span><span class="sxs-lookup"><span data-stu-id="c4893-116">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|<span data-ttu-id="c4893-117">Fügt Typen hinzu, die bekannte Typen erfordern.</span><span class="sxs-lookup"><span data-stu-id="c4893-117">Adds types that require known types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c4893-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c4893-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c4893-119">Element</span><span class="sxs-lookup"><span data-stu-id="c4893-119">Element</span></span>|<span data-ttu-id="c4893-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c4893-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c4893-121">\<DataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="c4893-121">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="c4893-122">Enthält Konfigurationsdaten für den <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="c4893-122">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4893-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c4893-123">Remarks</span></span>  
 <span data-ttu-id="c4893-124">Weitere Informationen zu bekannten Typen finden Sie unter [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) und <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="c4893-124">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4893-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c4893-125">Example</span></span>  
 <span data-ttu-id="c4893-126">Der folgende XML-Code zeigt deklarierte Typen und bekannte Typen hinzugefügt, ein `DataContractSerializer` Element.</span><span class="sxs-lookup"><span data-stu-id="c4893-126">The following XML code shows declared types and known types added to a `DataContractSerializer` element.</span></span> <span data-ttu-id="c4893-127">Im Beispiel werden drei hinzugefügte Typen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c4893-127">The example shows three types being added.</span></span> <span data-ttu-id="c4893-128">Der erste ist ein benutzerdefinierter Typ mit dem Namen "Orders", der einen bekannten Typ mit dem Namen "Item" verwendet.</span><span class="sxs-lookup"><span data-stu-id="c4893-128">The first is a custom type named "Orders" that uses a known type named "Item".</span></span> <span data-ttu-id="c4893-129">Der zweite deklarierte Typ ist <xref:System.Collections.Generic.List%601> und verwendet `Item` als bekannten Typ.</span><span class="sxs-lookup"><span data-stu-id="c4893-129">The second declared type is a <xref:System.Collections.Generic.List%601> that uses `Item` as a known type.</span></span> <span data-ttu-id="c4893-130">Der dritte deklarierte Typ ist <xref:System.Collections.Generic.Dictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="c4893-130">Finally the third declared type is a <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="c4893-131">Der <xref:System.Collections.Generic.Dictionary%602>-Klassentyp ist ein generischer Typ mit zwei Typparametern.</span><span class="sxs-lookup"><span data-stu-id="c4893-131">The <xref:System.Collections.Generic.Dictionary%602> class type is a generic type, with two type parameters.</span></span> <span data-ttu-id="c4893-132">Der erste stellt den Schlüssel dar und der zweite den Wert.</span><span class="sxs-lookup"><span data-stu-id="c4893-132">The first represents the key and the second represents the value.</span></span> <span data-ttu-id="c4893-133">Im folgenden Beispiel wird ein <xref:System.Collections.Generic.List%601> des zweiten Typs (der Wert) zur Liste bekannter Typen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c4893-133">The following example adds a <xref:System.Collections.Generic.List%601> of the second type (the value) to the list of known types.</span></span> <span data-ttu-id="c4893-134">Sie müssen das `index`-Attribut verwenden, um anzugeben, welcher Typparameter im bekannten Typ verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c4893-134">You must use the `index` attribute to specify which type parameter to use in the known type.</span></span> <span data-ttu-id="c4893-135">In diesem Fall wird der Werttyp über das Indexattribut angegeben, das auf "1" festgelegt ist (die Auflistung ist nullbasiert).</span><span class="sxs-lookup"><span data-stu-id="c4893-135">In this case, the value type is indicated by the index attribute set to "1" (the collection is zero-based).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c4893-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4893-136">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="c4893-137">\<DataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="c4893-137">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="c4893-138">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="c4893-138">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="c4893-139">\<add></span><span class="sxs-lookup"><span data-stu-id="c4893-139">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
