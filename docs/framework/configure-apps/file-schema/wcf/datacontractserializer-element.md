---
title: <dataContractSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: b635f03d1e4a6628a76d678f7366482717276376
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704140"
---
# <a name="datacontractserializer"></a><span data-ttu-id="15869-101">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="15869-101">\<dataContractSerializer></span></span>
<span data-ttu-id="15869-102">Enthält Konfigurationsdaten für den <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="15869-102">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="15869-103">Dieses Element befindet sich in zwei verschiedenen Hierarchien.</span><span class="sxs-lookup"><span data-stu-id="15869-103">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="15869-104">Eine wird im folgenden Abschnitt "Schemahierarchie" aufgeführt, die andere im Abschnitt "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="15869-104">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
 <span data-ttu-id="15869-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="15869-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="15869-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="15869-106">\<behaviors></span></span>  
<span data-ttu-id="15869-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="15869-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="15869-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="15869-108">\<behavior></span></span>  
<span data-ttu-id="15869-109">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="15869-109">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15869-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="15869-110">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15869-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="15869-111">Attributes and Elements</span></span>  
 <span data-ttu-id="15869-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="15869-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15869-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="15869-113">Attributes</span></span>  
  
|<span data-ttu-id="15869-114">Element</span><span class="sxs-lookup"><span data-stu-id="15869-114">Element</span></span>|<span data-ttu-id="15869-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15869-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="15869-116">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="15869-116">ignoreExtensionDataObject</span></span>|<span data-ttu-id="15869-117">Ein boolescher Wert, der angibt, ob vom Endpunkt bereitgestellte Daten ignoriert werden sollen, wenn dieser serialisiert oder deserialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="15869-117">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="15869-118">Dieses Attribut kann nur im `<dataContractSerializer>` unter dem `<behavior>`-Element festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="15869-118">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="15869-119">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="15869-119">maxItemsInObjectGraph</span></span>|<span data-ttu-id="15869-120">Eine ganze Zahl, die die maximale Anzahl der zu serialisierenden oder zu deserialisierenden Elemente angibt.</span><span class="sxs-lookup"><span data-stu-id="15869-120">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="15869-121">Dieses Attribut hat den Wert 65536.</span><span class="sxs-lookup"><span data-stu-id="15869-121">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="15869-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="15869-122">Child Elements</span></span>  
 <span data-ttu-id="15869-123">Keine</span><span class="sxs-lookup"><span data-stu-id="15869-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="15869-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="15869-124">Parent Elements</span></span>  
  
|<span data-ttu-id="15869-125">Element</span><span class="sxs-lookup"><span data-stu-id="15869-125">Element</span></span>|<span data-ttu-id="15869-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15869-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15869-127">\<behavior></span><span class="sxs-lookup"><span data-stu-id="15869-127">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)|<span data-ttu-id="15869-128">Eine Auflistung der Einstellungen für das Verhalten eines Diensts.</span><span class="sxs-lookup"><span data-stu-id="15869-128">A collection of settings for the behavior of a service.</span></span>|  
|[<span data-ttu-id="15869-129">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="15869-129">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<span data-ttu-id="15869-130">Stellt das Stammelement für den <xref:System.Runtime.Serialization>-Namespaceabschnitt dar und enthält Elemente zum Festlegen von <xref:System.Runtime.Serialization.DataContractSerializer>-Optionen.</span><span class="sxs-lookup"><span data-stu-id="15869-130">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15869-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="15869-131">Remarks</span></span>  
 <span data-ttu-id="15869-132">Wie in der Einführung dieses Themas erwähnt, ist dies die zweite Hierarchie, in dem die \<X509Extension >-Element befindet.</span><span class="sxs-lookup"><span data-stu-id="15869-132">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [<span data-ttu-id="15869-133">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="15869-133">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
  
 [<span data-ttu-id="15869-134">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="15869-134">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
  
 <span data-ttu-id="15869-135">Weitere Informationen über bekannte Typen finden Sie unter <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="15869-135">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15869-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15869-136">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="15869-137">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="15869-137">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="15869-138">Datenübertragung und Serialisierung</span><span class="sxs-lookup"><span data-stu-id="15869-138">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
