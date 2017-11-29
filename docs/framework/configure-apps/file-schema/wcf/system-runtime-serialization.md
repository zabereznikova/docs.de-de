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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5a47417ded6e0917fadf2134eed5997d9d3b3d74
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltsystemruntimeserializationgt"></a><span data-ttu-id="6a365-102">&lt;System.Runtime.Serialization&gt;</span><span class="sxs-lookup"><span data-stu-id="6a365-102">&lt;system.runtime.serialization&gt;</span></span>
<span data-ttu-id="6a365-103">Stellt das Stammelement für den <xref:System.Runtime.Serialization>-Namespaceabschnitt dar und enthält Elemente zum Festlegen von <xref:System.Runtime.Serialization.DataContractSerializer>-Optionen.</span><span class="sxs-lookup"><span data-stu-id="6a365-103">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="6a365-104">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="6a365-104">system.runtime.serialization</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a365-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6a365-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6a365-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6a365-106">Attributes and Elements</span></span>  
 <span data-ttu-id="6a365-107">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6a365-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6a365-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="6a365-108">Attributes</span></span>  
 <span data-ttu-id="6a365-109">Keine.</span><span class="sxs-lookup"><span data-stu-id="6a365-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6a365-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6a365-110">Child Elements</span></span>  
  
|<span data-ttu-id="6a365-111">Element</span><span class="sxs-lookup"><span data-stu-id="6a365-111">Element</span></span>|<span data-ttu-id="6a365-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6a365-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6a365-113">\<"DataContractSerializer" ></span><span class="sxs-lookup"><span data-stu-id="6a365-113">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="6a365-114">Aktiviert die Hinzufügung bekannter, für die Deserialisierung verwendeter Typen.</span><span class="sxs-lookup"><span data-stu-id="6a365-114">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6a365-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6a365-115">Parent Elements</span></span>  
  
|<span data-ttu-id="6a365-116">Element</span><span class="sxs-lookup"><span data-stu-id="6a365-116">Element</span></span>|<span data-ttu-id="6a365-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6a365-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6a365-118">\<configuration>-Element</span><span class="sxs-lookup"><span data-stu-id="6a365-118">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="6a365-119">Das Element der obersten Ebene für die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="6a365-119">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6a365-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a365-120">See Also</span></span>  
 <xref:System.Runtime.Serialization>  
 [<span data-ttu-id="6a365-121">Verwenden von Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="6a365-121">Using Data Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 [<span data-ttu-id="6a365-122">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="6a365-122">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
