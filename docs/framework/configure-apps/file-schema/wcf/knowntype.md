---
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: 6bb6a419d863172951d82a67de044cb8cfc30f49
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183792"
---
# \<knownType>

<span data-ttu-id="3250f-101">Gibt einen Typ an, der vom <xref:System.Runtime.Serialization.DataContractSerializer> während der Deserialisierung verwendet werden sollte.</span><span class="sxs-lookup"><span data-stu-id="3250f-101">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="3250f-102">Dieses Element gibt einen "bekannten Typ" an, der von einem Feld oder einer Eigenschaft eines "deklarierten Typs" zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="3250f-102">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="3250f-103">Weitere Informationen finden Sie unter [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="3250f-103">For more information, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-of-declaredtypes-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<knownType>**  
  
## <a name="syntax"></a><span data-ttu-id="3250f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3250f-104">Syntax</span></span>  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a><span data-ttu-id="3250f-105">Typ</span><span class="sxs-lookup"><span data-stu-id="3250f-105">Type</span></span>  

 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3250f-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3250f-106">Attributes and Elements</span></span>  

 <span data-ttu-id="3250f-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3250f-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3250f-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="3250f-108">Attributes</span></span>  
  
|<span data-ttu-id="3250f-109">attribute</span><span class="sxs-lookup"><span data-stu-id="3250f-109">Attribute</span></span>|<span data-ttu-id="3250f-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3250f-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3250f-111">type</span><span class="sxs-lookup"><span data-stu-id="3250f-111">type</span></span>|<span data-ttu-id="3250f-112">Gibt den Typ (einschließlich Namespace), den Assemblynamen, die Version, die Kultur und das öffentliche Schlüsseltoken an.</span><span class="sxs-lookup"><span data-stu-id="3250f-112">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3250f-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3250f-113">Child Elements</span></span>  
  
|<span data-ttu-id="3250f-114">Element</span><span class="sxs-lookup"><span data-stu-id="3250f-114">Element</span></span>|<span data-ttu-id="3250f-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3250f-115">Description</span></span>|  
|-------------|-----------------|  
|[\<parameter>](parameter.md)|<span data-ttu-id="3250f-116">Gibt einen Parameterindex an, wenn der deklarierte Typ ein generischer Typ ist.</span><span class="sxs-lookup"><span data-stu-id="3250f-116">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3250f-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3250f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="3250f-118">Element</span><span class="sxs-lookup"><span data-stu-id="3250f-118">Element</span></span>|<span data-ttu-id="3250f-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3250f-119">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-declaredtypes-element.md)|<span data-ttu-id="3250f-120">Fügt der Auflistung deklarierter Typen einen deklarierten Typ hinzu.</span><span class="sxs-lookup"><span data-stu-id="3250f-120">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3250f-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3250f-121">Remarks</span></span>  

 <span data-ttu-id="3250f-122">Weitere Informationen zu bekannten Typen finden Sie unter [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="3250f-122">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="3250f-123">[\<dataContractSerializer>](datacontractserializer-element.md)Ein Beispiel für die Verwendung dieses Elements finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="3250f-123">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3250f-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3250f-124">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3250f-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3250f-125">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="3250f-126">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="3250f-126">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [\<add>](add-of-declaredtypes-element.md)
