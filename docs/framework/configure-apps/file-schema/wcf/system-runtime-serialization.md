---
title: <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: c34eba2614a354f1753d8da077f8653f2c260a97
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165892"
---
# <a name="systemruntimeserialization"></a><span data-ttu-id="b621c-102">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="b621c-102">\<system.runtime.serialization></span></span>
<span data-ttu-id="b621c-103">Stellt das Stammelement für den <xref:System.Runtime.Serialization>-Namespaceabschnitt dar und enthält Elemente zum Festlegen von <xref:System.Runtime.Serialization.DataContractSerializer>-Optionen.</span><span class="sxs-lookup"><span data-stu-id="b621c-103">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="b621c-104">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="b621c-104">system.runtime.serialization</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b621c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b621c-105">Syntax</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer ignoreExtensionDataObject="Boolean"
                            maxItemsInObjectGraph="Integer">
      <declaredTypes>
        <add type="String">
          <knownType type="String">
            <parameter index="Integer" />
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b621c-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b621c-106">Attributes and Elements</span></span>  
 <span data-ttu-id="b621c-107">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b621c-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b621c-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="b621c-108">Attributes</span></span>  
 <span data-ttu-id="b621c-109">Keine</span><span class="sxs-lookup"><span data-stu-id="b621c-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b621c-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b621c-110">Child Elements</span></span>  
  
|<span data-ttu-id="b621c-111">Element</span><span class="sxs-lookup"><span data-stu-id="b621c-111">Element</span></span>|<span data-ttu-id="b621c-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b621c-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b621c-113">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="b621c-113">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="b621c-114">Aktiviert die Hinzufügung bekannter, für die Deserialisierung verwendeter Typen.</span><span class="sxs-lookup"><span data-stu-id="b621c-114">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b621c-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b621c-115">Parent Elements</span></span>  
  
|<span data-ttu-id="b621c-116">Element</span><span class="sxs-lookup"><span data-stu-id="b621c-116">Element</span></span>|<span data-ttu-id="b621c-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b621c-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b621c-118">\<Configuration >-Element</span><span class="sxs-lookup"><span data-stu-id="b621c-118">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="b621c-119">Das Element der obersten Ebene für die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="b621c-119">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b621c-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b621c-120">See also</span></span>

- <xref:System.Runtime.Serialization>
- [<span data-ttu-id="b621c-121">Verwenden von Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="b621c-121">Using Data Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/using-data-contracts.md)
- [<span data-ttu-id="b621c-122">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="b621c-122">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
