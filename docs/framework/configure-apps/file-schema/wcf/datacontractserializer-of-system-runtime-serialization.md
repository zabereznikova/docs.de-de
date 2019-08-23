---
title: <dataContractSerializer>von < System. Runtime. Serialization >
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: 380d9ba5b8407d78b5045fd34fcdf37c0818d6f9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919351"
---
# <a name="datacontractserializer-of-systemruntimeserialization"></a><span data-ttu-id="d7d23-102">\<DataContractSerializer-> \<von System. Runtime. Serialization ></span><span class="sxs-lookup"><span data-stu-id="d7d23-102">\<dataContractSerializer> of \<system.runtime.serialization></span></span>
<span data-ttu-id="d7d23-103">Enthält Konfigurationsdaten für den <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="d7d23-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="d7d23-104">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="d7d23-104">\<system.runtime.serialization></span></span>  
<span data-ttu-id="d7d23-105">\<DataContractSerializer-></span><span class="sxs-lookup"><span data-stu-id="d7d23-105">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7d23-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d7d23-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d7d23-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d7d23-107">Attributes and Elements</span></span>  
 <span data-ttu-id="d7d23-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d7d23-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d7d23-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="d7d23-109">Attributes</span></span>  
  
|<span data-ttu-id="d7d23-110">Element</span><span class="sxs-lookup"><span data-stu-id="d7d23-110">Element</span></span>|<span data-ttu-id="d7d23-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d7d23-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d7d23-112">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="d7d23-112">ignoreExtensionDataObject</span></span>|<span data-ttu-id="d7d23-113">Ein boolescher Wert, der angibt, ob vom Endpunkt bereitgestellte Daten ignoriert werden sollen, wenn dieser serialisiert oder deserialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="d7d23-113">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="d7d23-114">Dieses Attribut kann nur im `<dataContractSerializer>` unter dem `<behavior>`-Element festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="d7d23-114">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="d7d23-115">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="d7d23-115">maxItemsInObjectGraph</span></span>|<span data-ttu-id="d7d23-116">Eine ganze Zahl, die die maximale Anzahl der zu serialisierenden oder zu deserialisierenden Elemente angibt.</span><span class="sxs-lookup"><span data-stu-id="d7d23-116">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="d7d23-117">Dieses Attribut hat den Wert 65536.</span><span class="sxs-lookup"><span data-stu-id="d7d23-117">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d7d23-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d7d23-118">Child Elements</span></span>  
  
|<span data-ttu-id="d7d23-119">Element</span><span class="sxs-lookup"><span data-stu-id="d7d23-119">Element</span></span>|<span data-ttu-id="d7d23-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d7d23-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7d23-121">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="d7d23-121">\<declaredTypes></span></span>](declaredtypes.md)|<span data-ttu-id="d7d23-122">Enthält die bekannten Typen, die der <xref:System.Runtime.Serialization.DataContractSerializer> bei der Deserialisierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="d7d23-122">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span><br /><br /> <span data-ttu-id="d7d23-123">Weitere Informationen zu Daten Verträgen und bekannten Typen finden Sie unter [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="d7d23-123">For more information about data contracts and known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d7d23-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d7d23-124">Parent Elements</span></span>  
  
|<span data-ttu-id="d7d23-125">Element</span><span class="sxs-lookup"><span data-stu-id="d7d23-125">Element</span></span>|<span data-ttu-id="d7d23-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d7d23-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7d23-127">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="d7d23-127">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)|<span data-ttu-id="d7d23-128">Stellt das Stammelement für den <xref:System.Runtime.Serialization>-Namespaceabschnitt dar und enthält Elemente zum Festlegen von <xref:System.Runtime.Serialization.DataContractSerializer>-Optionen.</span><span class="sxs-lookup"><span data-stu-id="d7d23-128">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7d23-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d7d23-129">Remarks</span></span>  
 <span data-ttu-id="d7d23-130">Weitere Informationen zu bekannten Typen finden <xref:System.Runtime.Serialization.DataContractSerializer> Sie unter und in den [bekannten Typen von Daten Verträgen](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="d7d23-130">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer> and [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7d23-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7d23-131">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- [<span data-ttu-id="d7d23-132">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="d7d23-132">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
