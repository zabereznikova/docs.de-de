---
title: '&lt;"DataContractSerializer"&gt;'
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
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d38e3786c595c3fe6cc9ea54b68784c927901731
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltdatacontractserializergt"></a><span data-ttu-id="bb40b-102">&lt;"DataContractSerializer"&gt;</span><span class="sxs-lookup"><span data-stu-id="bb40b-102">&lt;dataContractSerializer&gt;</span></span>
<span data-ttu-id="bb40b-103">Enthält Konfigurationsdaten für den <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="bb40b-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="bb40b-104">Dieses Element befindet sich in zwei verschiedenen Hierarchien.</span><span class="sxs-lookup"><span data-stu-id="bb40b-104">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="bb40b-105">Eine wird im folgenden Abschnitt "Schemahierarchie" aufgeführt, die andere im Abschnitt "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="bb40b-105">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
 <span data-ttu-id="bb40b-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="bb40b-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="bb40b-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="bb40b-107">\<behaviors></span></span>  
<span data-ttu-id="bb40b-108">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="bb40b-108">\<serviceBehaviors></span></span>  
<span data-ttu-id="bb40b-109">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="bb40b-109">\<behavior></span></span>  
<span data-ttu-id="bb40b-110">\<"DataContractSerializer" ></span><span class="sxs-lookup"><span data-stu-id="bb40b-110">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb40b-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb40b-111">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"  
   maxItemsInObjectGraph="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb40b-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bb40b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="bb40b-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bb40b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb40b-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="bb40b-114">Attributes</span></span>  
  
|<span data-ttu-id="bb40b-115">Element</span><span class="sxs-lookup"><span data-stu-id="bb40b-115">Element</span></span>|<span data-ttu-id="bb40b-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb40b-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bb40b-117">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="bb40b-117">ignoreExtensionDataObject</span></span>|<span data-ttu-id="bb40b-118">Ein boolescher Wert, der angibt, ob vom Endpunkt bereitgestellte Daten ignoriert werden sollen, wenn dieser serialisiert oder deserialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="bb40b-118">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="bb40b-119">Dieses Attribut kann nur im `<dataContractSerializer>` unter dem `<behavior>`-Element festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="bb40b-119">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="bb40b-120">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="bb40b-120">maxItemsInObjectGraph</span></span>|<span data-ttu-id="bb40b-121">Eine ganze Zahl, die die maximale Anzahl der zu serialisierenden oder zu deserialisierenden Elemente angibt.</span><span class="sxs-lookup"><span data-stu-id="bb40b-121">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="bb40b-122">Dieses Attribut hat den Wert 65536.</span><span class="sxs-lookup"><span data-stu-id="bb40b-122">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bb40b-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bb40b-123">Child Elements</span></span>  
 <span data-ttu-id="bb40b-124">Keine</span><span class="sxs-lookup"><span data-stu-id="bb40b-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bb40b-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bb40b-125">Parent Elements</span></span>  
  
|<span data-ttu-id="bb40b-126">Element</span><span class="sxs-lookup"><span data-stu-id="bb40b-126">Element</span></span>|<span data-ttu-id="bb40b-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb40b-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bb40b-128">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="bb40b-128">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)|<span data-ttu-id="bb40b-129">Eine Auflistung der Einstellungen für das Verhalten eines Diensts.</span><span class="sxs-lookup"><span data-stu-id="bb40b-129">A collection of settings for the behavior of a service.</span></span>|  
|[<span data-ttu-id="bb40b-130">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="bb40b-130">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<span data-ttu-id="bb40b-131">Stellt das Stammelement für den <xref:System.Runtime.Serialization>-Namespaceabschnitt dar und enthält Elemente zum Festlegen von <xref:System.Runtime.Serialization.DataContractSerializer>-Optionen.</span><span class="sxs-lookup"><span data-stu-id="bb40b-131">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb40b-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bb40b-132">Remarks</span></span>  
 <span data-ttu-id="bb40b-133">Wie in der Einführung dieses Themas erwähnt, ist dies die zweite Hierarchie, in denen die \<X509Extension >-Element befindet.</span><span class="sxs-lookup"><span data-stu-id="bb40b-133">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [<span data-ttu-id="bb40b-134">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="bb40b-134">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
  
 [<span data-ttu-id="bb40b-135">\<"DataContractSerializer" ></span><span class="sxs-lookup"><span data-stu-id="bb40b-135">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
  
 <span data-ttu-id="bb40b-136">Weitere Informationen über bekannte Typen finden Sie unter <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="bb40b-136">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb40b-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb40b-137">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>  
 [<span data-ttu-id="bb40b-138">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="bb40b-138">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="bb40b-139">Die Datenübertragung und Serialisierung</span><span class="sxs-lookup"><span data-stu-id="bb40b-139">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
