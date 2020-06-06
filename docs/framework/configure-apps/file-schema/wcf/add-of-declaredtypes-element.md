---
title: <add>of- <declaredTypes> Element
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
ms.openlocfilehash: a001e8743b2c24f68b1b23cbccf3e5ac162c4e71
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400657"
---
# <a name="add-of-declaredtypes-element"></a><span data-ttu-id="1d4a7-102">\<add>of- \<declaredTypes> Element</span><span class="sxs-lookup"><span data-stu-id="1d4a7-102">\<add> of \<declaredTypes> Element</span></span>
<span data-ttu-id="1d4a7-103">Fügt einen während der Deserialisierung vom <xref:System.Runtime.Serialization.DataContractSerializer> verwendeten Typ hinzu.</span><span class="sxs-lookup"><span data-stu-id="1d4a7-103">Adds a type used by the <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="1d4a7-104">Jeder deklarierte Typ umfasst die bekannten Typen, die als Feld oder Eigenschaft des deklarierten Typs zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1d4a7-104">Each declared type includes the known types that will be returned as a field or property of the declared type.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="1d4a7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1d4a7-105">Syntax</span></span>  
  
```xml  
<add type="String">
  <knownType type="String">
    <parameter index="Integer"
               type="String" />
  </knownType>
</add>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1d4a7-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1d4a7-106">Attributes and Elements</span></span>  
 <span data-ttu-id="1d4a7-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1d4a7-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1d4a7-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="1d4a7-108">Attributes</span></span>  
  
|<span data-ttu-id="1d4a7-109">attribute</span><span class="sxs-lookup"><span data-stu-id="1d4a7-109">Attribute</span></span>|<span data-ttu-id="1d4a7-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1d4a7-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1d4a7-111">type</span><span class="sxs-lookup"><span data-stu-id="1d4a7-111">type</span></span>|<span data-ttu-id="1d4a7-112">Erforderliches Zeichenfolgenattribut.</span><span class="sxs-lookup"><span data-stu-id="1d4a7-112">Required string attribute.</span></span><br /><br /> <span data-ttu-id="1d4a7-113">Gibt den Typnamen (einschließlich Namespace), den Assemblynamen, die Versionsnummer, die Kultur und das öffentliche Schlüsseltoken an.</span><span class="sxs-lookup"><span data-stu-id="1d4a7-113">Specifies the type name (including namespace), assembly name, version number, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1d4a7-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1d4a7-114">Child Elements</span></span>  
  
|<span data-ttu-id="1d4a7-115">Element</span><span class="sxs-lookup"><span data-stu-id="1d4a7-115">Element</span></span>|<span data-ttu-id="1d4a7-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1d4a7-116">Description</span></span>|  
|-------------|-----------------|  
|[\<knownType>](knowntype.md)|<span data-ttu-id="1d4a7-117">Gibt den bekannten Typ für den deklarierten Typ an, der hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="1d4a7-117">Specifies the known type for the declared type that is being added.</span></span> <span data-ttu-id="1d4a7-118">Falls es sich bei dem deklarierten Typ um einen generischen Typ handelt, müssen Sie auch dem `<knownType>`-Element ein Parameterelement hinzufügen, um anzugeben, welcher generische Parameter zum Zurückgeben des bekannten Typs verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1d4a7-118">If the declared type is a generic type, then you must also add a parameter element to the `<knownType>` element to specify which generic parameter is used to return the known type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1d4a7-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1d4a7-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1d4a7-120">Element</span><span class="sxs-lookup"><span data-stu-id="1d4a7-120">Element</span></span>|<span data-ttu-id="1d4a7-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1d4a7-121">Description</span></span>|  
|-------------|-----------------|  
|[\<declaredTypes>](declaredtypes.md)|<span data-ttu-id="1d4a7-122">Enthält die Typen, die während der Deserialisierung vom <xref:System.Runtime.Serialization.DataContractSerializer> bekannte Typen erfordern.</span><span class="sxs-lookup"><span data-stu-id="1d4a7-122">Contains the types that require known types during deserialization by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d4a7-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1d4a7-123">Remarks</span></span>  
 <span data-ttu-id="1d4a7-124">Weitere Informationen zu bekannten Typen finden Sie unter [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="1d4a7-124">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="1d4a7-125">[\<dataContractSerializer>](datacontractserializer-element.md)Ein Beispiel für die Verwendung dieses Elements finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="1d4a7-125">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1d4a7-126">Wenn Sie den <xref:System.Object>-Typ als `<declaredType>` hinzufügen, wird eine <xref:System.Configuration.ConfigurationErrorsException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="1d4a7-126">If you add the <xref:System.Object> type as a `<declaredType>`, a <xref:System.Configuration.ConfigurationErrorsException> is thrown.</span></span> <span data-ttu-id="1d4a7-127">Der Grund hierfür ist, dass der <xref:System.Object>-Typ in der Konfiguration nicht als deklarierter Typ verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="1d4a7-127">This is because the <xref:System.Object> type cannot be used as a declared type in configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d4a7-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1d4a7-128">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1d4a7-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1d4a7-129">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="1d4a7-130">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="1d4a7-130">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [<span data-ttu-id="1d4a7-131">\<add>Natürlich\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="1d4a7-131">\<add> of \<declaredTypes></span></span>](add-of-declaredtypes-element.md)
