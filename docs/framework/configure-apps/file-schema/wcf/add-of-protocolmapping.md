---
title: '&lt;add&gt; von &lt;protocolMapping&gt;'
ms.date: 03/30/2017
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
ms.openlocfilehash: b9559a6921bdededf760f54f58abadb46612b174
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-of-ltprotocolmappinggt"></a><span data-ttu-id="512b5-102">&lt;add&gt; von &lt;protocolMapping&gt;</span><span class="sxs-lookup"><span data-stu-id="512b5-102">&lt;add&gt; of &lt;protocolMapping&gt;</span></span>
<span data-ttu-id="512b5-103">Stellt eine standardprotokollzuordnung zwischen einem transportprotokollschema (z. B. http, net.tcp, net.pipe usw.) und einer Bindung Windows Communication Foundation (WCF) dar.</span><span class="sxs-lookup"><span data-stu-id="512b5-103">Represents a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a Windows Communication Foundation (WCF) binding.</span></span> <span data-ttu-id="512b5-104">Beim Erstellen von Standardendpunkten zur Laufzeit prüft [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] die konfigurierten Zuordnungen und wählt die für eine bestimmte Basisadresse zu verwendende Bindung.</span><span class="sxs-lookup"><span data-stu-id="512b5-104">When creating default endpoints at runtime, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
 <span data-ttu-id="512b5-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="512b5-105">\<system.serviceModel></span></span>  
<span data-ttu-id="512b5-106">\<ProtocolMapping ></span><span class="sxs-lookup"><span data-stu-id="512b5-106">\<protocolMapping></span></span>  
<span data-ttu-id="512b5-107">\<add></span><span class="sxs-lookup"><span data-stu-id="512b5-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="512b5-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="512b5-108">Syntax</span></span>  
  
```xml
   <protocolMapping>    <add binding="String"         bindingConfiguration="String"         scheme="http/net.msmq/net.pipe/net.tcp"/></protocolMapping>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="512b5-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="512b5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="512b5-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="512b5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="512b5-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="512b5-111">Attributes</span></span>  
  
|<span data-ttu-id="512b5-112">Element</span><span class="sxs-lookup"><span data-stu-id="512b5-112">Element</span></span>|<span data-ttu-id="512b5-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="512b5-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="512b5-114">Bindung</span><span class="sxs-lookup"><span data-stu-id="512b5-114">binding</span></span>|<span data-ttu-id="512b5-115">Eine Zeichenfolge, die den Typ der Bindung angibt, die während der Standardendpunkterstellung für einen Endpunkt verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="512b5-115">A string that specifies the type of binding to be used for an endpoint during default endpoint creation.</span></span>|  
|<span data-ttu-id="512b5-116">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="512b5-116">bindingConfiguration</span></span>|<span data-ttu-id="512b5-117">Eine Zeichenfolge, die den Namen des Bindungskonfigurationsabschnitts angibt, auf den verwiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="512b5-117">A string that specifies the name of the binding configuration section to be referenced.</span></span>|  
|<span data-ttu-id="512b5-118">scheme</span><span class="sxs-lookup"><span data-stu-id="512b5-118">scheme</span></span>|<span data-ttu-id="512b5-119">Das für den Standardendpunkt zu verwendende Transportprotokollschema.</span><span class="sxs-lookup"><span data-stu-id="512b5-119">The transport protocol scheme to be used for the default endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="512b5-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="512b5-120">Child Elements</span></span>  
 <span data-ttu-id="512b5-121">Keine</span><span class="sxs-lookup"><span data-stu-id="512b5-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="512b5-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="512b5-122">Parent Elements</span></span>  
  
|<span data-ttu-id="512b5-123">Element</span><span class="sxs-lookup"><span data-stu-id="512b5-123">Element</span></span>|<span data-ttu-id="512b5-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="512b5-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="512b5-125">\<ProtocolMapping ></span><span class="sxs-lookup"><span data-stu-id="512b5-125">\<protocolMapping></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/protocolmapping.md)|<span data-ttu-id="512b5-126">Stellt einen Konfigurationsabschnitt zur Definition von standardprotokollzuordnungen zwischen transportprotokollschemas (z. B. http, net.tcp, net.pipe usw.) und Windows Communication Foundation (WCF)-Bindungen dar.</span><span class="sxs-lookup"><span data-stu-id="512b5-126">Represents a configuration section for defining default protocol mappings between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and Windows Communication Foundation (WCF) bindings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="512b5-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="512b5-127">Example</span></span>  
 <span data-ttu-id="512b5-128">Im folgenden Konfigurationsbeispiel wird die Standardprotokollzuordnung in der Datei machine.config veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="512b5-128">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="512b5-129">Sie können diese Standardzuordnung auf Computerebene überschreiben, indem Sie die Datei machine.config ändern.</span><span class="sxs-lookup"><span data-stu-id="512b5-129">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="512b5-130">Wenn Sie sie lediglich innerhalb des Bereichs einer Anwendung überschreiben möchten, können Sie diesen Abschnitt innerhalb der Anwendungskonfigurationsdatei überschreiben und die Zuordnung für einzelne Protokollschemas ändern.</span><span class="sxs-lookup"><span data-stu-id="512b5-130">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
```xml  
<protocolMapping>  
        <add scheme="http" binding="basicHttpBinding"/>  
        <add scheme="net.tcp" binding="netTcpBinding"/>  
        <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
        <add scheme="net.msmq" binding="netMsmqBinding"/>  
</protocolMapping>  
```  
  
## <a name="see-also"></a><span data-ttu-id="512b5-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="512b5-131">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>      
 <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>    
