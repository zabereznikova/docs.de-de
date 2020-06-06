---
title: <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: c93a1f482882cc8cd9d229d82597efa64ba209bc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152969"
---
# \<system.runtime.serialization>
<span data-ttu-id="ea46e-102">Stellt das Stammelement für den <xref:System.Runtime.Serialization>-Namespaceabschnitt dar und enthält Elemente zum Festlegen von <xref:System.Runtime.Serialization.DataContractSerializer>-Optionen.</span><span class="sxs-lookup"><span data-stu-id="ea46e-102">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.runtime.serialization>**  
  
## <a name="syntax"></a><span data-ttu-id="ea46e-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="ea46e-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea46e-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ea46e-104">Attributes and Elements</span></span>  
 <span data-ttu-id="ea46e-105">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ea46e-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea46e-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="ea46e-106">Attributes</span></span>  
 <span data-ttu-id="ea46e-107">Keine</span><span class="sxs-lookup"><span data-stu-id="ea46e-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ea46e-108">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ea46e-108">Child Elements</span></span>  
  
|<span data-ttu-id="ea46e-109">Element</span><span class="sxs-lookup"><span data-stu-id="ea46e-109">Element</span></span>|<span data-ttu-id="ea46e-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ea46e-110">Description</span></span>|  
|-------------|-----------------|  
|[\<dataContractSerializer>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="ea46e-111">Aktiviert die Hinzufügung bekannter, für die Deserialisierung verwendeter Typen.</span><span class="sxs-lookup"><span data-stu-id="ea46e-111">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ea46e-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ea46e-112">Parent Elements</span></span>  
  
|<span data-ttu-id="ea46e-113">Element</span><span class="sxs-lookup"><span data-stu-id="ea46e-113">Element</span></span>|<span data-ttu-id="ea46e-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ea46e-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea46e-115">\<configuration>Gewisses</span><span class="sxs-lookup"><span data-stu-id="ea46e-115">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="ea46e-116">Das Element der obersten Ebene für die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="ea46e-116">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ea46e-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea46e-117">See also</span></span>

- <xref:System.Runtime.Serialization>
- [<span data-ttu-id="ea46e-118">Verwenden von Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="ea46e-118">Using Data Contracts</span></span>](../../../wcf/feature-details/using-data-contracts.md)
- [<span data-ttu-id="ea46e-119">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="ea46e-119">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
