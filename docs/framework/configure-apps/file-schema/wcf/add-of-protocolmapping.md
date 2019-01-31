---
title: <add> von <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
ms.openlocfilehash: 18b50ec2d848bc6bb920fb8f630ac7703654b286
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55280734"
---
# <a name="add-of-protocolmapping"></a><span data-ttu-id="3933a-102">\<Hinzufügen > der \<ProtocolMapping ></span><span class="sxs-lookup"><span data-stu-id="3933a-102">\<add> of \<protocolMapping></span></span>
<span data-ttu-id="3933a-103">Stellt eine standardprotokollzuordnung zwischen einem transportprotokollschema (z. B. http, net.tcp, net.pipe usw.) und einer Windows Communication Foundation (WCF)-Bindung dar.</span><span class="sxs-lookup"><span data-stu-id="3933a-103">Represents a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a Windows Communication Foundation (WCF) binding.</span></span> <span data-ttu-id="3933a-104">Beim Erstellen von Standardendpunkten zur Laufzeit wird WCF untersucht die konfigurierten Zuordnungen und entscheidet, auf die Bindung für die Verwendung für eine bestimmte Adresse basiert.</span><span class="sxs-lookup"><span data-stu-id="3933a-104">When creating default endpoints at runtime, WCF looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
 <span data-ttu-id="3933a-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3933a-105">\<system.serviceModel></span></span>  
<span data-ttu-id="3933a-106">\<protocolMapping></span><span class="sxs-lookup"><span data-stu-id="3933a-106">\<protocolMapping></span></span>  
<span data-ttu-id="3933a-107">\<add></span><span class="sxs-lookup"><span data-stu-id="3933a-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3933a-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="3933a-108">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3933a-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3933a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3933a-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3933a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3933a-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="3933a-111">Attributes</span></span>  
  
|<span data-ttu-id="3933a-112">Element</span><span class="sxs-lookup"><span data-stu-id="3933a-112">Element</span></span>|<span data-ttu-id="3933a-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3933a-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3933a-114">Bindung</span><span class="sxs-lookup"><span data-stu-id="3933a-114">binding</span></span>|<span data-ttu-id="3933a-115">Eine Zeichenfolge, die den Typ der Bindung angibt, die während der Standardendpunkterstellung für einen Endpunkt verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3933a-115">A string that specifies the type of binding to be used for an endpoint during default endpoint creation.</span></span>|  
|<span data-ttu-id="3933a-116">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="3933a-116">bindingConfiguration</span></span>|<span data-ttu-id="3933a-117">Eine Zeichenfolge, die den Namen des Bindungskonfigurationsabschnitts angibt, auf den verwiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="3933a-117">A string that specifies the name of the binding configuration section to be referenced.</span></span>|  
|<span data-ttu-id="3933a-118">scheme</span><span class="sxs-lookup"><span data-stu-id="3933a-118">scheme</span></span>|<span data-ttu-id="3933a-119">Das für den Standardendpunkt zu verwendende Transportprotokollschema.</span><span class="sxs-lookup"><span data-stu-id="3933a-119">The transport protocol scheme to be used for the default endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3933a-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3933a-120">Child Elements</span></span>  
 <span data-ttu-id="3933a-121">Keine</span><span class="sxs-lookup"><span data-stu-id="3933a-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3933a-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3933a-122">Parent Elements</span></span>  
  
|<span data-ttu-id="3933a-123">Element</span><span class="sxs-lookup"><span data-stu-id="3933a-123">Element</span></span>|<span data-ttu-id="3933a-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3933a-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3933a-125">\<protocolMapping></span><span class="sxs-lookup"><span data-stu-id="3933a-125">\<protocolMapping></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/protocolmapping.md)|<span data-ttu-id="3933a-126">Stellt einen Konfigurationsabschnitt zum Definieren von standardprotokollzuordnungen zwischen transportprotokollschemas (z. B. http, net.tcp, net.pipe usw.) und Windows Communication Foundation (WCF)-Bindungen dar.</span><span class="sxs-lookup"><span data-stu-id="3933a-126">Represents a configuration section for defining default protocol mappings between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and Windows Communication Foundation (WCF) bindings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3933a-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3933a-127">Example</span></span>  
 <span data-ttu-id="3933a-128">Im folgenden Konfigurationsbeispiel wird die Standardprotokollzuordnung in der Datei machine.config veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="3933a-128">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="3933a-129">Sie können diese Standardzuordnung auf Computerebene überschreiben, indem Sie die Datei machine.config ändern.</span><span class="sxs-lookup"><span data-stu-id="3933a-129">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="3933a-130">Wenn Sie sie lediglich innerhalb des Bereichs einer Anwendung überschreiben möchten, können Sie diesen Abschnitt innerhalb der Anwendungskonfigurationsdatei überschreiben und die Zuordnung für einzelne Protokollschemas ändern.</span><span class="sxs-lookup"><span data-stu-id="3933a-130">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3933a-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3933a-131">See also</span></span>
- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
