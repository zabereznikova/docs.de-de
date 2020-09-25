---
title: <dataContractSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: 2a994a8ba97d4c65fdaba5a85e779dd9935e3074
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195030"
---
# \<dataContractSerializer>

<span data-ttu-id="7caed-101">Enthält Konfigurationsdaten für den <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="7caed-101">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="7caed-102">Dieses Element befindet sich in zwei verschiedenen Hierarchien.</span><span class="sxs-lookup"><span data-stu-id="7caed-102">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="7caed-103">Eine wird im folgenden Abschnitt "Schemahierarchie" aufgeführt, die andere im Abschnitt "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="7caed-103">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**  
  
## <a name="syntax"></a><span data-ttu-id="7caed-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7caed-104">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7caed-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7caed-105">Attributes and Elements</span></span>  

 <span data-ttu-id="7caed-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7caed-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7caed-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="7caed-107">Attributes</span></span>  
  
|<span data-ttu-id="7caed-108">Element</span><span class="sxs-lookup"><span data-stu-id="7caed-108">Element</span></span>|<span data-ttu-id="7caed-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7caed-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7caed-110">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="7caed-110">ignoreExtensionDataObject</span></span>|<span data-ttu-id="7caed-111">Ein boolescher Wert, der angibt, ob vom Endpunkt bereitgestellte Daten ignoriert werden sollen, wenn dieser serialisiert oder deserialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="7caed-111">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="7caed-112">Dieses Attribut kann nur im `<dataContractSerializer>` unter dem `<behavior>`-Element festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="7caed-112">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="7caed-113">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="7caed-113">maxItemsInObjectGraph</span></span>|<span data-ttu-id="7caed-114">Eine ganze Zahl, die die maximale Anzahl der zu serialisierenden oder zu deserialisierenden Elemente angibt.</span><span class="sxs-lookup"><span data-stu-id="7caed-114">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="7caed-115">Dieses Attribut hat den Wert 65536.</span><span class="sxs-lookup"><span data-stu-id="7caed-115">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7caed-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7caed-116">Child Elements</span></span>  

 <span data-ttu-id="7caed-117">Keine</span><span class="sxs-lookup"><span data-stu-id="7caed-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7caed-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7caed-118">Parent Elements</span></span>  
  
|<span data-ttu-id="7caed-119">Element</span><span class="sxs-lookup"><span data-stu-id="7caed-119">Element</span></span>|<span data-ttu-id="7caed-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7caed-120">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-servicebehaviors.md)|<span data-ttu-id="7caed-121">Eine Auflistung der Einstellungen für das Verhalten eines Diensts.</span><span class="sxs-lookup"><span data-stu-id="7caed-121">A collection of settings for the behavior of a service.</span></span>|  
|[\<system.runtime.serialization>](system-runtime-serialization.md)|<span data-ttu-id="7caed-122">Stellt das Stammelement für den <xref:System.Runtime.Serialization>-Namespaceabschnitt dar und enthält Elemente zum Festlegen von <xref:System.Runtime.Serialization.DataContractSerializer>-Optionen.</span><span class="sxs-lookup"><span data-stu-id="7caed-122">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7caed-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7caed-123">Remarks</span></span>  

 <span data-ttu-id="7caed-124">Wie in der Einführung dieses Themas erwähnt, ist dies die zweite Hierarchie, in der das- \<X509Extension> Element auftritt.</span><span class="sxs-lookup"><span data-stu-id="7caed-124">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [\<system.runtime.serialization>](system-runtime-serialization.md)  
  
 [\<dataContractSerializer>](datacontractserializer-element.md)  
  
 <span data-ttu-id="7caed-125">Weitere Informationen über bekannte Typen finden Sie unter <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="7caed-125">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7caed-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7caed-126">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="7caed-127">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="7caed-127">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="7caed-128">Datenübertragung und Serialisierung</span><span class="sxs-lookup"><span data-stu-id="7caed-128">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
