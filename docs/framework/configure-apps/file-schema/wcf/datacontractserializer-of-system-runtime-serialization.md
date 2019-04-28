---
title: <dataContractSerializer> der < system.runtime.serialization >
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: c81fdb040f2e0d6c9a3728d8ed3b917443ecb42e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700981"
---
# <a name="datacontractserializer-of-systemruntimeserialization"></a><span data-ttu-id="907bf-102">\<DataContractSerializer > von \<system.runtime.serialization ></span><span class="sxs-lookup"><span data-stu-id="907bf-102">\<dataContractSerializer> of \<system.runtime.serialization></span></span>
<span data-ttu-id="907bf-103">Enthält Konfigurationsdaten für den <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="907bf-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="907bf-104">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="907bf-104">\<system.runtime.serialization></span></span>  
<span data-ttu-id="907bf-105">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="907bf-105">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="907bf-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="907bf-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="907bf-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="907bf-107">Attributes and Elements</span></span>  
 <span data-ttu-id="907bf-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="907bf-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="907bf-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="907bf-109">Attributes</span></span>  
  
|<span data-ttu-id="907bf-110">Element</span><span class="sxs-lookup"><span data-stu-id="907bf-110">Element</span></span>|<span data-ttu-id="907bf-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="907bf-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="907bf-112">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="907bf-112">ignoreExtensionDataObject</span></span>|<span data-ttu-id="907bf-113">Ein boolescher Wert, der angibt, ob vom Endpunkt bereitgestellte Daten ignoriert werden sollen, wenn dieser serialisiert oder deserialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="907bf-113">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="907bf-114">Dieses Attribut kann nur im `<dataContractSerializer>` unter dem `<behavior>`-Element festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="907bf-114">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="907bf-115">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="907bf-115">maxItemsInObjectGraph</span></span>|<span data-ttu-id="907bf-116">Eine ganze Zahl, die die maximale Anzahl der zu serialisierenden oder zu deserialisierenden Elemente angibt.</span><span class="sxs-lookup"><span data-stu-id="907bf-116">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="907bf-117">Dieses Attribut hat den Wert 65536.</span><span class="sxs-lookup"><span data-stu-id="907bf-117">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="907bf-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="907bf-118">Child Elements</span></span>  
  
|<span data-ttu-id="907bf-119">Element</span><span class="sxs-lookup"><span data-stu-id="907bf-119">Element</span></span>|<span data-ttu-id="907bf-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="907bf-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="907bf-121">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="907bf-121">\<declaredTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/declaredtypes.md)|<span data-ttu-id="907bf-122">Enthält die bekannten Typen, die der <xref:System.Runtime.Serialization.DataContractSerializer> bei der Deserialisierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="907bf-122">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span><br /><br /> <span data-ttu-id="907bf-123">Weitere Informationen über Datenverträge und bekannte Typen finden Sie unter [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="907bf-123">For more information about data contracts and known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="907bf-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="907bf-124">Parent Elements</span></span>  
  
|<span data-ttu-id="907bf-125">Element</span><span class="sxs-lookup"><span data-stu-id="907bf-125">Element</span></span>|<span data-ttu-id="907bf-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="907bf-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="907bf-127">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="907bf-127">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<span data-ttu-id="907bf-128">Stellt das Stammelement für den <xref:System.Runtime.Serialization>-Namespaceabschnitt dar und enthält Elemente zum Festlegen von <xref:System.Runtime.Serialization.DataContractSerializer>-Optionen.</span><span class="sxs-lookup"><span data-stu-id="907bf-128">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="907bf-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="907bf-129">Remarks</span></span>  
 <span data-ttu-id="907bf-130">Weitere Informationen zu bekannten Typen finden Sie unter <xref:System.Runtime.Serialization.DataContractSerializer> und [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="907bf-130">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer> and [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="907bf-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="907bf-131">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- [<span data-ttu-id="907bf-132">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="907bf-132">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
