---
title: <dataContractSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: 1b4fd959d5e522150751d2e9b8be8c5b2252bf27
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254950"
---
# <a name="datacontractserializer"></a><span data-ttu-id="726d5-101">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="726d5-101">\<dataContractSerializer></span></span>
<span data-ttu-id="726d5-102">Enthält Konfigurationsdaten für den <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="726d5-102">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="726d5-103">Dieses Element befindet sich in zwei verschiedenen Hierarchien.</span><span class="sxs-lookup"><span data-stu-id="726d5-103">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="726d5-104">Eine wird im folgenden Abschnitt "Schemahierarchie" aufgeführt, die andere im Abschnitt "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="726d5-104">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
 <span data-ttu-id="726d5-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="726d5-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="726d5-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="726d5-106">\<behaviors></span></span>  
<span data-ttu-id="726d5-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="726d5-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="726d5-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="726d5-108">\<behavior></span></span>  
<span data-ttu-id="726d5-109">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="726d5-109">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="726d5-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="726d5-110">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="726d5-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="726d5-111">Attributes and Elements</span></span>  
 <span data-ttu-id="726d5-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="726d5-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="726d5-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="726d5-113">Attributes</span></span>  
  
|<span data-ttu-id="726d5-114">Element</span><span class="sxs-lookup"><span data-stu-id="726d5-114">Element</span></span>|<span data-ttu-id="726d5-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="726d5-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="726d5-116">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="726d5-116">ignoreExtensionDataObject</span></span>|<span data-ttu-id="726d5-117">Ein boolescher Wert, der angibt, ob vom Endpunkt bereitgestellte Daten ignoriert werden sollen, wenn dieser serialisiert oder deserialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="726d5-117">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="726d5-118">Dieses Attribut kann nur im `<dataContractSerializer>` unter dem `<behavior>`-Element festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="726d5-118">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="726d5-119">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="726d5-119">maxItemsInObjectGraph</span></span>|<span data-ttu-id="726d5-120">Eine ganze Zahl, die die maximale Anzahl der zu serialisierenden oder zu deserialisierenden Elemente angibt.</span><span class="sxs-lookup"><span data-stu-id="726d5-120">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="726d5-121">Dieses Attribut hat den Wert 65536.</span><span class="sxs-lookup"><span data-stu-id="726d5-121">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="726d5-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="726d5-122">Child Elements</span></span>  
 <span data-ttu-id="726d5-123">Keine</span><span class="sxs-lookup"><span data-stu-id="726d5-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="726d5-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="726d5-124">Parent Elements</span></span>  
  
|<span data-ttu-id="726d5-125">Element</span><span class="sxs-lookup"><span data-stu-id="726d5-125">Element</span></span>|<span data-ttu-id="726d5-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="726d5-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="726d5-127">\<behavior></span><span class="sxs-lookup"><span data-stu-id="726d5-127">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)|<span data-ttu-id="726d5-128">Eine Auflistung der Einstellungen für das Verhalten eines Diensts.</span><span class="sxs-lookup"><span data-stu-id="726d5-128">A collection of settings for the behavior of a service.</span></span>|  
|[<span data-ttu-id="726d5-129">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="726d5-129">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<span data-ttu-id="726d5-130">Stellt das Stammelement für den <xref:System.Runtime.Serialization>-Namespaceabschnitt dar und enthält Elemente zum Festlegen von <xref:System.Runtime.Serialization.DataContractSerializer>-Optionen.</span><span class="sxs-lookup"><span data-stu-id="726d5-130">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="726d5-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="726d5-131">Remarks</span></span>  
 <span data-ttu-id="726d5-132">Wie in der Einführung dieses Themas erwähnt, ist dies die zweite Hierarchie, in dem die \<X509Extension >-Element befindet.</span><span class="sxs-lookup"><span data-stu-id="726d5-132">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [<span data-ttu-id="726d5-133">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="726d5-133">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
  
 [<span data-ttu-id="726d5-134">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="726d5-134">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
  
 <span data-ttu-id="726d5-135">Weitere Informationen über bekannte Typen finden Sie unter <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="726d5-135">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="726d5-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="726d5-136">See also</span></span>
- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="726d5-137">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="726d5-137">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="726d5-138">Datenübertragung und Serialisierung</span><span class="sxs-lookup"><span data-stu-id="726d5-138">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
