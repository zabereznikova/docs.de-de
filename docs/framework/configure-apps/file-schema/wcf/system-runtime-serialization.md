---
title: <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: b67f51e634d1294830690dad8c8cffb1fc9a6cd2
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399464"
---
# <a name="systemruntimeserialization"></a><span data-ttu-id="c9c27-102">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="c9c27-102">\<system.runtime.serialization></span></span>
<span data-ttu-id="c9c27-103">Stellt das Stammelement für den <xref:System.Runtime.Serialization>-Namespaceabschnitt dar und enthält Elemente zum Festlegen von <xref:System.Runtime.Serialization.DataContractSerializer>-Optionen.</span><span class="sxs-lookup"><span data-stu-id="c9c27-103">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  

<span data-ttu-id="c9c27-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c9c27-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c9c27-105">&nbsp;&nbsp; **\<System. Runtime. Serialization >**</span><span class="sxs-lookup"><span data-stu-id="c9c27-105">&nbsp;&nbsp;**\<system.runtime.serialization>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9c27-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c9c27-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c9c27-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c9c27-107">Attributes and Elements</span></span>  
 <span data-ttu-id="c9c27-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c9c27-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c9c27-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="c9c27-109">Attributes</span></span>  
 <span data-ttu-id="c9c27-110">Keine</span><span class="sxs-lookup"><span data-stu-id="c9c27-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c9c27-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c9c27-111">Child Elements</span></span>  
  
|<span data-ttu-id="c9c27-112">Element</span><span class="sxs-lookup"><span data-stu-id="c9c27-112">Element</span></span>|<span data-ttu-id="c9c27-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c9c27-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9c27-114">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="c9c27-114">\<dataContractSerializer></span></span>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="c9c27-115">Aktiviert die Hinzufügung bekannter, für die Deserialisierung verwendeter Typen.</span><span class="sxs-lookup"><span data-stu-id="c9c27-115">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c9c27-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c9c27-116">Parent Elements</span></span>  
  
|<span data-ttu-id="c9c27-117">Element</span><span class="sxs-lookup"><span data-stu-id="c9c27-117">Element</span></span>|<span data-ttu-id="c9c27-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c9c27-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9c27-119">\<configuration> Element</span><span class="sxs-lookup"><span data-stu-id="c9c27-119">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="c9c27-120">Das Element der obersten Ebene für die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="c9c27-120">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c9c27-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9c27-121">See also</span></span>

- <xref:System.Runtime.Serialization>
- [<span data-ttu-id="c9c27-122">Verwenden von Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="c9c27-122">Using Data Contracts</span></span>](../../../wcf/feature-details/using-data-contracts.md)
- [<span data-ttu-id="c9c27-123">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="c9c27-123">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
 