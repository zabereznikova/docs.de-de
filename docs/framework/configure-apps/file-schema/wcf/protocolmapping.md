---
title: '&lt;protocolMapping&gt;'
ms.date: 03/30/2017
ms.assetid: 5076644b-1f33-4f26-9488-87de9fcda04c
ms.openlocfilehash: a376f1eaa7c8790cf2174335749ed3001b403967
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147303"
---
# <a name="ltprotocolmappinggt"></a><span data-ttu-id="8053c-102">&lt;protocolMapping&gt;</span><span class="sxs-lookup"><span data-stu-id="8053c-102">&lt;protocolMapping&gt;</span></span>
<span data-ttu-id="8053c-103">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von standardprotokollzuordnungen zwischen transportprotokollschemas (z. B. http, net.tcp, net.pipe usw.) und WCF-Bindungen dar.</span><span class="sxs-lookup"><span data-stu-id="8053c-103">Represents a configuration section for defining a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span> <span data-ttu-id="8053c-104">Beim Erstellen von Standardendpunkten zur Laufzeit wird Windows Communication Foundation (WCF) untersucht die konfigurierten Zuordnungen und entscheidet, auf die Bindung für die Verwendung für eine bestimmte Adresse basiert.</span><span class="sxs-lookup"><span data-stu-id="8053c-104">When creating default endpoints at runtime, Windows Communication Foundation (WCF) looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
[<span data-ttu-id="8053c-105">**\<system.serviceModel >**</span><span class="sxs-lookup"><span data-stu-id="8053c-105">**\<system.serviceModel>**</span></span>](system-servicemodel.md)  
<span data-ttu-id="8053c-106">&nbsp;&nbsp;**\<ProtocolMapping >**</span><span class="sxs-lookup"><span data-stu-id="8053c-106">&nbsp;&nbsp;**\<protocolMapping>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8053c-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="8053c-107">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8053c-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8053c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8053c-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8053c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8053c-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="8053c-110">Attributes</span></span>  
 <span data-ttu-id="8053c-111">Keine</span><span class="sxs-lookup"><span data-stu-id="8053c-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8053c-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8053c-112">Child Elements</span></span>  
  
|<span data-ttu-id="8053c-113">Element</span><span class="sxs-lookup"><span data-stu-id="8053c-113">Element</span></span>|<span data-ttu-id="8053c-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8053c-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8053c-115">\<Filter ></span><span class="sxs-lookup"><span data-stu-id="8053c-115">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="8053c-116">Enthält eine standardprotokollzuordnung zwischen einem transportprotokollschema (z. B. http, net.tcp, net.pipe usw.) und einer WCF-Bindung.</span><span class="sxs-lookup"><span data-stu-id="8053c-116">Contains a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a WCF binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8053c-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8053c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="8053c-118">Element</span><span class="sxs-lookup"><span data-stu-id="8053c-118">Element</span></span>|<span data-ttu-id="8053c-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8053c-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8053c-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8053c-120">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="8053c-121">Das Stammelement aller WCF-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="8053c-121">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8053c-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8053c-122">Example</span></span>  
 <span data-ttu-id="8053c-123">Im folgenden Konfigurationsbeispiel wird die Standardprotokollzuordnung in der Datei machine.config veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="8053c-123">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="8053c-124">Sie können diese Standardzuordnung auf Computerebene überschreiben, indem Sie die Datei machine.config ändern.</span><span class="sxs-lookup"><span data-stu-id="8053c-124">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="8053c-125">Wenn Sie sie lediglich innerhalb des Bereichs einer Anwendung überschreiben möchten, können Sie diesen Abschnitt innerhalb der Anwendungskonfigurationsdatei überschreiben und die Zuordnung für einzelne Protokollschemas ändern.</span><span class="sxs-lookup"><span data-stu-id="8053c-125">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
```xml  
<protocolMapping>
  <add scheme="http"
       binding="basicHttpBinding" />
  <add scheme="net.tcp"
       binding="netTcpBinding" />
  <add scheme="net.pipe"
       binding="netNamedPipeBinding" />
  <add scheme="net.msmq"
       binding="netMsmqBinding" />
</protocolMapping>
```  
  
## <a name="see-also"></a><span data-ttu-id="8053c-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8053c-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>    
