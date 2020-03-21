---
title: <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: c93a1f482882cc8cd9d229d82597efa64ba209bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152969"
---
# <a name="systemruntimeserialization"></a><span data-ttu-id="32287-102">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="32287-102">\<system.runtime.serialization></span></span>
<span data-ttu-id="32287-103">Stellt das Stammelement für den <xref:System.Runtime.Serialization>-Namespaceabschnitt dar und enthält Elemente zum Festlegen von <xref:System.Runtime.Serialization.DataContractSerializer>-Optionen.</span><span class="sxs-lookup"><span data-stu-id="32287-103">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  

<span data-ttu-id="32287-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="32287-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="32287-105">&nbsp;&nbsp;**\<system.runtime.serialization>**</span><span class="sxs-lookup"><span data-stu-id="32287-105">&nbsp;&nbsp;**\<system.runtime.serialization>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32287-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="32287-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32287-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="32287-107">Attributes and Elements</span></span>  
 <span data-ttu-id="32287-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="32287-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32287-109">Attributes</span><span class="sxs-lookup"><span data-stu-id="32287-109">Attributes</span></span>  
 <span data-ttu-id="32287-110">Keine.</span><span class="sxs-lookup"><span data-stu-id="32287-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="32287-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="32287-111">Child Elements</span></span>  
  
|<span data-ttu-id="32287-112">Element</span><span class="sxs-lookup"><span data-stu-id="32287-112">Element</span></span>|<span data-ttu-id="32287-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32287-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="32287-114">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="32287-114">\<dataContractSerializer></span></span>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="32287-115">Aktiviert die Hinzufügung bekannter, für die Deserialisierung verwendeter Typen.</span><span class="sxs-lookup"><span data-stu-id="32287-115">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="32287-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="32287-116">Parent Elements</span></span>  
  
|<span data-ttu-id="32287-117">Element</span><span class="sxs-lookup"><span data-stu-id="32287-117">Element</span></span>|<span data-ttu-id="32287-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32287-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="32287-119">\<Konfiguration> Element</span><span class="sxs-lookup"><span data-stu-id="32287-119">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="32287-120">Das Element der obersten Ebene für die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="32287-120">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="32287-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="32287-121">See also</span></span>

- <xref:System.Runtime.Serialization>
- [<span data-ttu-id="32287-122">Verwenden von Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="32287-122">Using Data Contracts</span></span>](../../../wcf/feature-details/using-data-contracts.md)
- [<span data-ttu-id="32287-123">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="32287-123">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
