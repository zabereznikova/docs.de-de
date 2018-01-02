---
title: '&lt;declaredTypes&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dataContractSerializer element
- declaredTypes element
- DataContractSerializer
- KnownTypes
- <declaredTypes> element
ms.assetid: f35184e4-9d9e-4d37-8fb4-d5b58220eb3e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3066ee9247e69c746c28251b975bb80425ccbc8f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltdeclaredtypesgt"></a><span data-ttu-id="86312-102">&lt;declaredTypes&gt;</span><span class="sxs-lookup"><span data-stu-id="86312-102">&lt;declaredTypes&gt;</span></span>
<span data-ttu-id="86312-103">Enthält die bekannten Typen, die der <xref:System.Runtime.Serialization.DataContractSerializer> bei der Deserialisierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="86312-103">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span>  
  
 <span data-ttu-id="86312-104">Weitere Informationen über Datenverträge und bekannte Typen finden Sie unter [Datenvertragstypen bezeichnet](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="86312-104">For more information about data contracts and known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="86312-105">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="86312-105">system.runtime.serialization</span></span>  
<span data-ttu-id="86312-106">\<"DataContractSerializer" ></span><span class="sxs-lookup"><span data-stu-id="86312-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="86312-107">\<DeclaredTypes ></span><span class="sxs-lookup"><span data-stu-id="86312-107">\<declaredTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86312-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="86312-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86312-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="86312-109">Attributes and Elements</span></span>  
 <span data-ttu-id="86312-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="86312-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86312-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="86312-111">Attributes</span></span>  
 <span data-ttu-id="86312-112">Keine</span><span class="sxs-lookup"><span data-stu-id="86312-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="86312-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="86312-113">Child Elements</span></span>  
  
|<span data-ttu-id="86312-114">Element</span><span class="sxs-lookup"><span data-stu-id="86312-114">Element</span></span>|<span data-ttu-id="86312-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="86312-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="86312-116">\<add></span><span class="sxs-lookup"><span data-stu-id="86312-116">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|<span data-ttu-id="86312-117">Fügt Typen hinzu, die bekannte Typen erfordern.</span><span class="sxs-lookup"><span data-stu-id="86312-117">Adds types that require known types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="86312-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="86312-118">Parent Elements</span></span>  
  
|<span data-ttu-id="86312-119">Element</span><span class="sxs-lookup"><span data-stu-id="86312-119">Element</span></span>|<span data-ttu-id="86312-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="86312-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="86312-121">\<"DataContractSerializer" ></span><span class="sxs-lookup"><span data-stu-id="86312-121">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="86312-122">Enthält Konfigurationsdaten für den <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="86312-122">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86312-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="86312-123">Remarks</span></span>  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)]<span data-ttu-id="86312-124">bekannten Typen finden Sie unter [Datenvertragstypen bezeichnet](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) und <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="86312-124"> known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86312-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="86312-125">Example</span></span>  
 <span data-ttu-id="86312-126">Der folgende XML-Code zeigt deklarierte Typen und zu bekannten Typen hinzugefügt, ein `DataContractSerializer` Element.</span><span class="sxs-lookup"><span data-stu-id="86312-126">The following XML code shows declared types and known types added to a `DataContractSerializer` element.</span></span> <span data-ttu-id="86312-127">Im Beispiel werden drei hinzugefügte Typen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="86312-127">The example shows three types being added.</span></span> <span data-ttu-id="86312-128">Der erste ist ein benutzerdefinierter Typ mit dem Namen "Orders", der einen bekannten Typ mit dem Namen "Item" verwendet.</span><span class="sxs-lookup"><span data-stu-id="86312-128">The first is a custom type named "Orders" that uses a known type named "Item".</span></span> <span data-ttu-id="86312-129">Der zweite deklarierte Typ ist <xref:System.Collections.Generic.List%601> und verwendet `Item` als bekannten Typ.</span><span class="sxs-lookup"><span data-stu-id="86312-129">The second declared type is a <xref:System.Collections.Generic.List%601> that uses `Item` as a known type.</span></span> <span data-ttu-id="86312-130">Der dritte deklarierte Typ ist <xref:System.Collections.Generic.Dictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="86312-130">Finally the third declared type is a <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="86312-131">Der <xref:System.Collections.Generic.Dictionary%602>-Klassentyp ist ein generischer Typ mit zwei Typparametern.</span><span class="sxs-lookup"><span data-stu-id="86312-131">The <xref:System.Collections.Generic.Dictionary%602> class type is a generic type, with two type parameters.</span></span> <span data-ttu-id="86312-132">Der erste stellt den Schlüssel dar und der zweite den Wert.</span><span class="sxs-lookup"><span data-stu-id="86312-132">The first represents the key and the second represents the value.</span></span> <span data-ttu-id="86312-133">Im folgenden Beispiel wird ein <xref:System.Collections.Generic.List%601> des zweiten Typs (der Wert) zur Liste bekannter Typen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="86312-133">The following example adds a <xref:System.Collections.Generic.List%601> of the second type (the value) to the list of known types.</span></span> <span data-ttu-id="86312-134">Sie müssen das `index`-Attribut verwenden, um anzugeben, welcher Typparameter im bekannten Typ verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="86312-134">You must use the `index` attribute to specify which type parameter to use in the known type.</span></span> <span data-ttu-id="86312-135">In diesem Fall wird der Werttyp über das Indexattribut angegeben, das auf "1" festgelegt ist (die Auflistung ist nullbasiert).</span><span class="sxs-lookup"><span data-stu-id="86312-135">In this case, the value type is indicated by the index attribute set to "1" (the collection is zero-based).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="86312-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86312-136">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="86312-137">\<"DataContractSerializer" ></span><span class="sxs-lookup"><span data-stu-id="86312-137">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="86312-138">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="86312-138">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="86312-139">\<add></span><span class="sxs-lookup"><span data-stu-id="86312-139">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
