---
title: <add>of <declaredTypes> -Element
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
ms.openlocfilehash: a001e8743b2c24f68b1b23cbccf3e5ac162c4e71
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400657"
---
# <a name="add-of-declaredtypes-element"></a><span data-ttu-id="7d987-102">\<> von \<DeclaredTypes > Element hinzufügen</span><span class="sxs-lookup"><span data-stu-id="7d987-102">\<add> of \<declaredTypes> Element</span></span>
<span data-ttu-id="7d987-103">Fügt einen während der Deserialisierung vom <xref:System.Runtime.Serialization.DataContractSerializer> verwendeten Typ hinzu.</span><span class="sxs-lookup"><span data-stu-id="7d987-103">Adds a type used by the <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="7d987-104">Jeder deklarierte Typ umfasst die bekannten Typen, die als Feld oder Eigenschaft des deklarierten Typs zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7d987-104">Each declared type includes the known types that will be returned as a field or property of the declared type.</span></span>  
  
<span data-ttu-id="7d987-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7d987-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7d987-106">&nbsp;&nbsp;[ **\<System. Runtime. Serialization >** ](system-runtime-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="7d987-106">&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)</span></span>\
<span data-ttu-id="7d987-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<DataContractSerializer->** ](datacontractserializer.md)</span><span class="sxs-lookup"><span data-stu-id="7d987-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)</span></span>\
<span data-ttu-id="7d987-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<DeclaredTypes->** ](declaredtypes.md)</span><span class="sxs-lookup"><span data-stu-id="7d987-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)</span></span>\
<span data-ttu-id="7d987-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> Hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="7d987-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d987-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="7d987-110">Syntax</span></span>  
  
```xml  
<add type="String">
  <knownType type="String">
    <parameter index="Integer"
               type="String" />
  </knownType>
</add>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d987-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7d987-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7d987-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7d987-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d987-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="7d987-113">Attributes</span></span>  
  
|<span data-ttu-id="7d987-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="7d987-114">Attribute</span></span>|<span data-ttu-id="7d987-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7d987-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7d987-116">Typ</span><span class="sxs-lookup"><span data-stu-id="7d987-116">type</span></span>|<span data-ttu-id="7d987-117">Erforderliches Zeichenfolgenattribut.</span><span class="sxs-lookup"><span data-stu-id="7d987-117">Required string attribute.</span></span><br /><br /> <span data-ttu-id="7d987-118">Gibt den Typnamen (einschließlich Namespace), den Assemblynamen, die Versionsnummer, die Kultur und das öffentliche Schlüsseltoken an.</span><span class="sxs-lookup"><span data-stu-id="7d987-118">Specifies the type name (including namespace), assembly name, version number, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7d987-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7d987-119">Child Elements</span></span>  
  
|<span data-ttu-id="7d987-120">Element</span><span class="sxs-lookup"><span data-stu-id="7d987-120">Element</span></span>|<span data-ttu-id="7d987-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7d987-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d987-122">\<knownType></span><span class="sxs-lookup"><span data-stu-id="7d987-122">\<knownType></span></span>](knowntype.md)|<span data-ttu-id="7d987-123">Gibt den bekannten Typ für den deklarierten Typ an, der hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="7d987-123">Specifies the known type for the declared type that is being added.</span></span> <span data-ttu-id="7d987-124">Falls es sich bei dem deklarierten Typ um einen generischen Typ handelt, müssen Sie auch dem `<knownType>`-Element ein Parameterelement hinzufügen, um anzugeben, welcher generische Parameter zum Zurückgeben des bekannten Typs verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7d987-124">If the declared type is a generic type, then you must also add a parameter element to the `<knownType>` element to specify which generic parameter is used to return the known type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7d987-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7d987-125">Parent Elements</span></span>  
  
|<span data-ttu-id="7d987-126">Element</span><span class="sxs-lookup"><span data-stu-id="7d987-126">Element</span></span>|<span data-ttu-id="7d987-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7d987-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d987-128">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="7d987-128">\<declaredTypes></span></span>](declaredtypes.md)|<span data-ttu-id="7d987-129">Enthält die Typen, die während der Deserialisierung vom <xref:System.Runtime.Serialization.DataContractSerializer> bekannte Typen erfordern.</span><span class="sxs-lookup"><span data-stu-id="7d987-129">Contains the types that require known types during deserialization by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d987-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7d987-130">Remarks</span></span>  
 <span data-ttu-id="7d987-131">Weitere Informationen zu bekannten Typen finden Sie unter [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="7d987-131">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="7d987-132">Ein Beispiel für die Verwendung dieses Elements finden Sie im [ \<> DataContractSerializer](datacontractserializer-element.md) .</span><span class="sxs-lookup"><span data-stu-id="7d987-132">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7d987-133">Wenn Sie den <xref:System.Object>-Typ als `<declaredType>` hinzufügen, wird eine <xref:System.Configuration.ConfigurationErrorsException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="7d987-133">If you add the <xref:System.Object> type as a `<declaredType>`, a <xref:System.Configuration.ConfigurationErrorsException> is thrown.</span></span> <span data-ttu-id="7d987-134">Der Grund hierfür ist, dass der <xref:System.Object>-Typ in der Konfiguration nicht als deklarierter Typ verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="7d987-134">This is because the <xref:System.Object> type cannot be used as a declared type in configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d987-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7d987-135">Example</span></span>  
  
```xml  
<add type="MyCompany.Library.Shape,
           MyAssembly, Version=2.0.0.0, Culture=neutral,
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">
  <knownType type="MyCompany.Library.Circle,
                   MyAssembly, Version=2.0.0.0, Culture=neutral,
                   PublicKeyToken=XXXXXX,
                   processorArchitecture=MSIL" />
</add>
```  
  
## <a name="see-also"></a><span data-ttu-id="7d987-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d987-136">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="7d987-137">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="7d987-137">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="7d987-138">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="7d987-138">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="7d987-139">\<Fügen Sie > \<von DeclaredTypes hinzu ></span><span class="sxs-lookup"><span data-stu-id="7d987-139">\<add> of \<declaredTypes></span></span>](add-of-declaredtypes-element.md)
