---
title: <dataContractSerializer>von < System. Runtime. Serialization >
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: eb556f533af1f99049382e9a2e34465f88d563db
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398081"
---
# <a name="datacontractserializer-of-systemruntimeserialization"></a><span data-ttu-id="e5992-102">\<DataContractSerializer-> \<von System. Runtime. Serialization ></span><span class="sxs-lookup"><span data-stu-id="e5992-102">\<dataContractSerializer> of \<system.runtime.serialization></span></span>
<span data-ttu-id="e5992-103">Enthält Konfigurationsdaten für den <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="e5992-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
<span data-ttu-id="e5992-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e5992-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e5992-105">&nbsp;&nbsp;[ **\<System. Runtime. Serialization >** ](system-runtime-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="e5992-105">&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)</span></span>\
<span data-ttu-id="e5992-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<DataContractSerializer->**</span><span class="sxs-lookup"><span data-stu-id="e5992-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5992-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="e5992-107">Syntax</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer ignoreExtensionDataObject="Boolean"
                            maxItemsInObjectGraph="Integer">
      <declaredTypes>
        <add type="String">
          <knownType type="String">
            <parameter index="Integer"
                       type="String" />
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5992-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e5992-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e5992-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e5992-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5992-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="e5992-110">Attributes</span></span>  
  
|<span data-ttu-id="e5992-111">Element</span><span class="sxs-lookup"><span data-stu-id="e5992-111">Element</span></span>|<span data-ttu-id="e5992-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e5992-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e5992-113">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="e5992-113">ignoreExtensionDataObject</span></span>|<span data-ttu-id="e5992-114">Ein boolescher Wert, der angibt, ob vom Endpunkt bereitgestellte Daten ignoriert werden sollen, wenn dieser serialisiert oder deserialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="e5992-114">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="e5992-115">Dieses Attribut kann nur im `<dataContractSerializer>` unter dem `<behavior>`-Element festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="e5992-115">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="e5992-116">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="e5992-116">maxItemsInObjectGraph</span></span>|<span data-ttu-id="e5992-117">Eine ganze Zahl, die die maximale Anzahl der zu serialisierenden oder zu deserialisierenden Elemente angibt.</span><span class="sxs-lookup"><span data-stu-id="e5992-117">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="e5992-118">Dieses Attribut hat den Wert 65536.</span><span class="sxs-lookup"><span data-stu-id="e5992-118">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e5992-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e5992-119">Child Elements</span></span>  
  
|<span data-ttu-id="e5992-120">Element</span><span class="sxs-lookup"><span data-stu-id="e5992-120">Element</span></span>|<span data-ttu-id="e5992-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e5992-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5992-122">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="e5992-122">\<declaredTypes></span></span>](declaredtypes.md)|<span data-ttu-id="e5992-123">Enthält die bekannten Typen, die der <xref:System.Runtime.Serialization.DataContractSerializer> bei der Deserialisierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="e5992-123">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span><br /><br /> <span data-ttu-id="e5992-124">Weitere Informationen zu Daten Verträgen und bekannten Typen finden Sie unter [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="e5992-124">For more information about data contracts and known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e5992-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e5992-125">Parent Elements</span></span>  
  
|<span data-ttu-id="e5992-126">Element</span><span class="sxs-lookup"><span data-stu-id="e5992-126">Element</span></span>|<span data-ttu-id="e5992-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e5992-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5992-128">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="e5992-128">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)|<span data-ttu-id="e5992-129">Stellt das Stammelement für den <xref:System.Runtime.Serialization>-Namespaceabschnitt dar und enthält Elemente zum Festlegen von <xref:System.Runtime.Serialization.DataContractSerializer>-Optionen.</span><span class="sxs-lookup"><span data-stu-id="e5992-129">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5992-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e5992-130">Remarks</span></span>  
 <span data-ttu-id="e5992-131">Weitere Informationen zu bekannten Typen finden <xref:System.Runtime.Serialization.DataContractSerializer> Sie unter und in den [bekannten Typen von Daten Verträgen](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="e5992-131">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer> and [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5992-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5992-132">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- [<span data-ttu-id="e5992-133">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="e5992-133">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
