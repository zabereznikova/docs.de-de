---
title: '&lt;System.Runtime.Serialization&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8a6eb2b152f2ab11bbe0e08ff1ad22f94d45057e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltsystemruntimeserializationgt"></a><span data-ttu-id="ccff4-102">&lt;System.Runtime.Serialization&gt;</span><span class="sxs-lookup"><span data-stu-id="ccff4-102">&lt;system.runtime.serialization&gt;</span></span>
<span data-ttu-id="ccff4-103">Stellt das Stammelement für den <xref:System.Runtime.Serialization>-Namespaceabschnitt dar und enthält Elemente zum Festlegen von <xref:System.Runtime.Serialization.DataContractSerializer>-Optionen.</span><span class="sxs-lookup"><span data-stu-id="ccff4-103">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="ccff4-104">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="ccff4-104">system.runtime.serialization</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccff4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ccff4-105">Syntax</span></span>  
  
```xml  
<configuration>  
  <system.runtime.serialization>  
    <dataContractSerializer ignoreExtensionDataObject="Boolean"  
      maxItemsInObjectGraph="Integer">  
      <declaredTypes>  
        <add type="String ">  
          <knownType type="String">  
             <parameter index="Integer"/>  
          </knownType>  
        </add>  
      </declaredTypes>  
    <dataContractSerializer>  
  </system.runtime.serialization>  
</configuration>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ccff4-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ccff4-106">Attributes and Elements</span></span>  
 <span data-ttu-id="ccff4-107">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ccff4-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ccff4-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="ccff4-108">Attributes</span></span>  
 <span data-ttu-id="ccff4-109">Keine.</span><span class="sxs-lookup"><span data-stu-id="ccff4-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ccff4-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ccff4-110">Child Elements</span></span>  
  
|<span data-ttu-id="ccff4-111">Element</span><span class="sxs-lookup"><span data-stu-id="ccff4-111">Element</span></span>|<span data-ttu-id="ccff4-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ccff4-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ccff4-113">\<"DataContractSerializer" ></span><span class="sxs-lookup"><span data-stu-id="ccff4-113">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="ccff4-114">Aktiviert die Hinzufügung bekannter, für die Deserialisierung verwendeter Typen.</span><span class="sxs-lookup"><span data-stu-id="ccff4-114">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ccff4-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ccff4-115">Parent Elements</span></span>  
  
|<span data-ttu-id="ccff4-116">Element</span><span class="sxs-lookup"><span data-stu-id="ccff4-116">Element</span></span>|<span data-ttu-id="ccff4-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ccff4-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ccff4-118">\<configuration>-Element</span><span class="sxs-lookup"><span data-stu-id="ccff4-118">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="ccff4-119">Das Element der obersten Ebene für die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="ccff4-119">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ccff4-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ccff4-120">See Also</span></span>  
 <xref:System.Runtime.Serialization>  
 [<span data-ttu-id="ccff4-121">Verwenden von Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="ccff4-121">Using Data Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 [<span data-ttu-id="ccff4-122">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="ccff4-122">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
