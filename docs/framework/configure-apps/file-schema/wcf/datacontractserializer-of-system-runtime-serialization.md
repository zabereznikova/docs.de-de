---
title: <dataContractSerializer>von <System. Runtime. Serialization>
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: eb556f533af1f99049382e9a2e34465f88d563db
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398081"
---
# <a name="datacontractserializer-of-systemruntimeserialization"></a><span data-ttu-id="42741-102">\<dataContractSerializer> von \<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="42741-102">\<dataContractSerializer> of \<system.runtime.serialization></span></span>
<span data-ttu-id="42741-103">Enthält Konfigurationsdaten für den <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="42741-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**  
  
## <a name="syntax"></a><span data-ttu-id="42741-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="42741-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42741-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="42741-105">Attributes and Elements</span></span>  
 <span data-ttu-id="42741-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="42741-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42741-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="42741-107">Attributes</span></span>  
  
|<span data-ttu-id="42741-108">Element</span><span class="sxs-lookup"><span data-stu-id="42741-108">Element</span></span>|<span data-ttu-id="42741-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="42741-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="42741-110">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="42741-110">ignoreExtensionDataObject</span></span>|<span data-ttu-id="42741-111">Ein boolescher Wert, der angibt, ob vom Endpunkt bereitgestellte Daten ignoriert werden sollen, wenn dieser serialisiert oder deserialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="42741-111">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="42741-112">Dieses Attribut kann nur im `<dataContractSerializer>` unter dem `<behavior>`-Element festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="42741-112">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="42741-113">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="42741-113">maxItemsInObjectGraph</span></span>|<span data-ttu-id="42741-114">Eine ganze Zahl, die die maximale Anzahl der zu serialisierenden oder zu deserialisierenden Elemente angibt.</span><span class="sxs-lookup"><span data-stu-id="42741-114">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="42741-115">Dieses Attribut hat den Wert 65536.</span><span class="sxs-lookup"><span data-stu-id="42741-115">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="42741-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="42741-116">Child Elements</span></span>  
  
|<span data-ttu-id="42741-117">Element</span><span class="sxs-lookup"><span data-stu-id="42741-117">Element</span></span>|<span data-ttu-id="42741-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="42741-118">Description</span></span>|  
|-------------|-----------------|  
|[\<declaredTypes>](declaredtypes.md)|<span data-ttu-id="42741-119">Enthält die bekannten Typen, die der <xref:System.Runtime.Serialization.DataContractSerializer> bei der Deserialisierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="42741-119">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span><br /><br /> <span data-ttu-id="42741-120">Weitere Informationen zu Daten Verträgen und bekannten Typen finden Sie unter [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="42741-120">For more information about data contracts and known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="42741-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="42741-121">Parent Elements</span></span>  
  
|<span data-ttu-id="42741-122">Element</span><span class="sxs-lookup"><span data-stu-id="42741-122">Element</span></span>|<span data-ttu-id="42741-123">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="42741-123">Description</span></span>|  
|-------------|-----------------|  
|[\<system.runtime.serialization>](system-runtime-serialization.md)|<span data-ttu-id="42741-124">Stellt das Stammelement für den <xref:System.Runtime.Serialization>-Namespaceabschnitt dar und enthält Elemente zum Festlegen von <xref:System.Runtime.Serialization.DataContractSerializer>-Optionen.</span><span class="sxs-lookup"><span data-stu-id="42741-124">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42741-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="42741-125">Remarks</span></span>  
 <span data-ttu-id="42741-126">Weitere Informationen zu bekannten Typen finden Sie unter <xref:System.Runtime.Serialization.DataContractSerializer> und in den [bekannten Typen von Daten Verträgen](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="42741-126">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer> and [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42741-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="42741-127">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- [<span data-ttu-id="42741-128">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="42741-128">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
