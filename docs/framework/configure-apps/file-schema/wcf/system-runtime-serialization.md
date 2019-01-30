---
title: <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: 5aa5d75e12852fe6a0e4e9a2eb4ae57d25d1022c
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55272681"
---
# <a name="systemruntimeserialization"></a><span data-ttu-id="ec416-102">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="ec416-102">\<system.runtime.serialization></span></span>
<span data-ttu-id="ec416-103">Stellt das Stammelement für den <xref:System.Runtime.Serialization>-Namespaceabschnitt dar und enthält Elemente zum Festlegen von <xref:System.Runtime.Serialization.DataContractSerializer>-Optionen.</span><span class="sxs-lookup"><span data-stu-id="ec416-103">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="ec416-104">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="ec416-104">system.runtime.serialization</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec416-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ec416-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec416-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ec416-106">Attributes and Elements</span></span>  
 <span data-ttu-id="ec416-107">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ec416-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec416-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="ec416-108">Attributes</span></span>  
 <span data-ttu-id="ec416-109">Keine</span><span class="sxs-lookup"><span data-stu-id="ec416-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ec416-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ec416-110">Child Elements</span></span>  
  
|<span data-ttu-id="ec416-111">Element</span><span class="sxs-lookup"><span data-stu-id="ec416-111">Element</span></span>|<span data-ttu-id="ec416-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec416-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ec416-113">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="ec416-113">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="ec416-114">Aktiviert die Hinzufügung bekannter, für die Deserialisierung verwendeter Typen.</span><span class="sxs-lookup"><span data-stu-id="ec416-114">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ec416-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ec416-115">Parent Elements</span></span>  
  
|<span data-ttu-id="ec416-116">Element</span><span class="sxs-lookup"><span data-stu-id="ec416-116">Element</span></span>|<span data-ttu-id="ec416-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec416-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ec416-118">\<configuration> Element</span><span class="sxs-lookup"><span data-stu-id="ec416-118">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="ec416-119">Das Element der obersten Ebene für die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="ec416-119">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ec416-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec416-120">See also</span></span>
- <xref:System.Runtime.Serialization>
- [<span data-ttu-id="ec416-121">Verwenden von Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="ec416-121">Using Data Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/using-data-contracts.md)
- [<span data-ttu-id="ec416-122">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="ec416-122">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
