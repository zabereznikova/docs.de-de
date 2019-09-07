---
title: <dataContractSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: e24dae47171f741af064ca2eaa822928690acf6e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400450"
---
# <a name="datacontractserializer"></a><span data-ttu-id="dd086-101">\<DataContractSerializer-></span><span class="sxs-lookup"><span data-stu-id="dd086-101">\<dataContractSerializer></span></span>
<span data-ttu-id="dd086-102">Enthält Konfigurationsdaten für den <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="dd086-102">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="dd086-103">Dieses Element befindet sich in zwei verschiedenen Hierarchien.</span><span class="sxs-lookup"><span data-stu-id="dd086-103">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="dd086-104">Eine wird im folgenden Abschnitt "Schemahierarchie" aufgeführt, die andere im Abschnitt "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="dd086-104">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
<span data-ttu-id="dd086-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="dd086-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="dd086-106">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="dd086-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="dd086-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="dd086-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="dd086-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceverhaltens>** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="dd086-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="dd086-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="dd086-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="dd086-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<DataContractSerializer->**</span><span class="sxs-lookup"><span data-stu-id="dd086-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd086-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="dd086-111">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dd086-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="dd086-112">Attributes and Elements</span></span>  
 <span data-ttu-id="dd086-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dd086-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dd086-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="dd086-114">Attributes</span></span>  
  
|<span data-ttu-id="dd086-115">Element</span><span class="sxs-lookup"><span data-stu-id="dd086-115">Element</span></span>|<span data-ttu-id="dd086-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dd086-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dd086-117">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="dd086-117">ignoreExtensionDataObject</span></span>|<span data-ttu-id="dd086-118">Ein boolescher Wert, der angibt, ob vom Endpunkt bereitgestellte Daten ignoriert werden sollen, wenn dieser serialisiert oder deserialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="dd086-118">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="dd086-119">Dieses Attribut kann nur im `<dataContractSerializer>` unter dem `<behavior>`-Element festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="dd086-119">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="dd086-120">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="dd086-120">maxItemsInObjectGraph</span></span>|<span data-ttu-id="dd086-121">Eine ganze Zahl, die die maximale Anzahl der zu serialisierenden oder zu deserialisierenden Elemente angibt.</span><span class="sxs-lookup"><span data-stu-id="dd086-121">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="dd086-122">Dieses Attribut hat den Wert 65536.</span><span class="sxs-lookup"><span data-stu-id="dd086-122">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dd086-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dd086-123">Child Elements</span></span>  
 <span data-ttu-id="dd086-124">Keine</span><span class="sxs-lookup"><span data-stu-id="dd086-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dd086-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dd086-125">Parent Elements</span></span>  
  
|<span data-ttu-id="dd086-126">Element</span><span class="sxs-lookup"><span data-stu-id="dd086-126">Element</span></span>|<span data-ttu-id="dd086-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dd086-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dd086-128">\<behavior></span><span class="sxs-lookup"><span data-stu-id="dd086-128">\<behavior></span></span>](behavior-of-servicebehaviors.md)|<span data-ttu-id="dd086-129">Eine Auflistung der Einstellungen für das Verhalten eines Diensts.</span><span class="sxs-lookup"><span data-stu-id="dd086-129">A collection of settings for the behavior of a service.</span></span>|  
|[<span data-ttu-id="dd086-130">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="dd086-130">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)|<span data-ttu-id="dd086-131">Stellt das Stammelement für den <xref:System.Runtime.Serialization>-Namespaceabschnitt dar und enthält Elemente zum Festlegen von <xref:System.Runtime.Serialization.DataContractSerializer>-Optionen.</span><span class="sxs-lookup"><span data-stu-id="dd086-131">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd086-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dd086-132">Remarks</span></span>  
 <span data-ttu-id="dd086-133">Wie in der Einführung dieses Themas erwähnt, ist dies die zweite Hierarchie, in der \<das X509Extension->-Element auftritt.</span><span class="sxs-lookup"><span data-stu-id="dd086-133">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [<span data-ttu-id="dd086-134">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="dd086-134">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)  
  
 [<span data-ttu-id="dd086-135">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="dd086-135">\<dataContractSerializer></span></span>](datacontractserializer-element.md)  
  
 <span data-ttu-id="dd086-136">Weitere Informationen über bekannte Typen finden Sie unter <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="dd086-136">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd086-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd086-137">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="dd086-138">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="dd086-138">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="dd086-139">Datenübertragung und Serialisierung</span><span class="sxs-lookup"><span data-stu-id="dd086-139">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
