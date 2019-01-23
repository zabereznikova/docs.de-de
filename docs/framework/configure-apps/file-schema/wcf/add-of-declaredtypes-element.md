---
title: '&lt;add&gt; des &lt;declaredTypes&gt;-Elements'
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
ms.openlocfilehash: dd5972c2bb25367f2566bcf77e53e7a3341d89b4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54519462"
---
# <a name="ltaddgt-of-ltdeclaredtypesgt-element"></a><span data-ttu-id="0481f-102">&lt;add&gt; des &lt;declaredTypes&gt;-Elements</span><span class="sxs-lookup"><span data-stu-id="0481f-102">&lt;add&gt; of &lt;declaredTypes&gt; Element</span></span>
<span data-ttu-id="0481f-103">Fügt einen während der Deserialisierung vom <xref:System.Runtime.Serialization.DataContractSerializer> verwendeten Typ hinzu.</span><span class="sxs-lookup"><span data-stu-id="0481f-103">Adds a type used by the <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="0481f-104">Jeder deklarierte Typ umfasst die bekannten Typen, die als Feld oder Eigenschaft des deklarierten Typs zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0481f-104">Each declared type includes the known types that will be returned as a field or property of the declared type.</span></span>  
  
 <span data-ttu-id="0481f-105">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="0481f-105">system.runtime.serialization</span></span>  
<span data-ttu-id="0481f-106">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="0481f-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="0481f-107">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="0481f-107">\<declaredTypes></span></span>  
<span data-ttu-id="0481f-108">\<add> of \<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="0481f-108">\<add> of \<declaredTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0481f-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="0481f-109">Syntax</span></span>  
  
```xml  
<add type="String">
  <knownType type="String">
    <parameter index="Integer"
               type="String" />
  </knownType>
</add>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0481f-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0481f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0481f-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0481f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0481f-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="0481f-112">Attributes</span></span>  
  
|<span data-ttu-id="0481f-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="0481f-113">Attribute</span></span>|<span data-ttu-id="0481f-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0481f-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0481f-115">Typ</span><span class="sxs-lookup"><span data-stu-id="0481f-115">type</span></span>|<span data-ttu-id="0481f-116">Erforderliches Zeichenfolgenattribut.</span><span class="sxs-lookup"><span data-stu-id="0481f-116">Required string attribute.</span></span><br /><br /> <span data-ttu-id="0481f-117">Gibt den Typnamen (einschließlich Namespace), den Assemblynamen, die Versionsnummer, die Kultur und das öffentliche Schlüsseltoken an.</span><span class="sxs-lookup"><span data-stu-id="0481f-117">Specifies the type name (including namespace), assembly name, version number, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0481f-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0481f-118">Child Elements</span></span>  
  
|<span data-ttu-id="0481f-119">Element</span><span class="sxs-lookup"><span data-stu-id="0481f-119">Element</span></span>|<span data-ttu-id="0481f-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0481f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0481f-121">\<knownType></span><span class="sxs-lookup"><span data-stu-id="0481f-121">\<knownType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|<span data-ttu-id="0481f-122">Gibt den bekannten Typ für den deklarierten Typ an, der hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="0481f-122">Specifies the known type for the declared type that is being added.</span></span> <span data-ttu-id="0481f-123">Falls es sich bei dem deklarierten Typ um einen generischen Typ handelt, müssen Sie auch dem `<knownType>`-Element ein Parameterelement hinzufügen, um anzugeben, welcher generische Parameter zum Zurückgeben des bekannten Typs verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0481f-123">If the declared type is a generic type, then you must also add a parameter element to the `<knownType>` element to specify which generic parameter is used to return the known type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0481f-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0481f-124">Parent Elements</span></span>  
  
|<span data-ttu-id="0481f-125">Element</span><span class="sxs-lookup"><span data-stu-id="0481f-125">Element</span></span>|<span data-ttu-id="0481f-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0481f-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0481f-127">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="0481f-127">\<declaredTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/declaredtypes.md)|<span data-ttu-id="0481f-128">Enthält die Typen, die während der Deserialisierung vom <xref:System.Runtime.Serialization.DataContractSerializer> bekannte Typen erfordern.</span><span class="sxs-lookup"><span data-stu-id="0481f-128">Contains the types that require known types during deserialization by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0481f-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0481f-129">Remarks</span></span>  
 <span data-ttu-id="0481f-130">Weitere Informationen zu bekannten Typen finden Sie unter [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) und <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="0481f-130">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="0481f-131">Finden Sie unter den [ \<DataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) ein Beispiel für die Verwendung dieses Elements.</span><span class="sxs-lookup"><span data-stu-id="0481f-131">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0481f-132">Wenn Sie den <xref:System.Object>-Typ als `<declaredType>` hinzufügen, wird eine <xref:System.Configuration.ConfigurationErrorsException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="0481f-132">If you add the <xref:System.Object> type as a `<declaredType>`, a <xref:System.Configuration.ConfigurationErrorsException> is thrown.</span></span> <span data-ttu-id="0481f-133">Der Grund hierfür ist, dass der <xref:System.Object>-Typ in der Konfiguration nicht als deklarierter Typ verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="0481f-133">This is because the <xref:System.Object> type cannot be used as a declared type in configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0481f-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0481f-134">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0481f-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0481f-135">See also</span></span>
- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="0481f-136">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="0481f-136">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="0481f-137">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="0481f-137">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)
- [<span data-ttu-id="0481f-138">\<Hinzufügen > der \<DeclaredTypes ></span><span class="sxs-lookup"><span data-stu-id="0481f-138">\<add> of \<declaredTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
