---
title: <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 5076644b-1f33-4f26-9488-87de9fcda04c
ms.openlocfilehash: be4224ef1a8b17653df8123aaf89e105a496355a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400020"
---
# <a name="protocolmapping"></a><span data-ttu-id="a2694-101">\<protocolMapping></span><span class="sxs-lookup"><span data-stu-id="a2694-101">\<protocolMapping></span></span>
<span data-ttu-id="a2694-102">Stellt einen Konfigurations Abschnitt zum Definieren eines Satzes von Standardprotokoll Zuordnungen zwischen Transportprotokoll Schemas (z. b. http, net. TCP, net. Pipe usw.) und WCF-Bindungen dar.</span><span class="sxs-lookup"><span data-stu-id="a2694-102">Represents a configuration section for defining a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span> <span data-ttu-id="a2694-103">Beim Erstellen von Standard Endpunkten zur Laufzeit untersucht Windows Communication Foundation (WCF) die konfigurierten Zuordnungen und entscheidet, welche Bindung für eine bestimmte basierte Adresse verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a2694-103">When creating default endpoints at runtime, Windows Communication Foundation (WCF) looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
<span data-ttu-id="a2694-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a2694-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a2694-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a2694-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a2694-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<protocolmapping->**</span><span class="sxs-lookup"><span data-stu-id="a2694-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<protocolMapping>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2694-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="a2694-107">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2694-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a2694-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a2694-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a2694-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2694-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="a2694-110">Attributes</span></span>  
 <span data-ttu-id="a2694-111">Keine</span><span class="sxs-lookup"><span data-stu-id="a2694-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a2694-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a2694-112">Child Elements</span></span>  
  
|<span data-ttu-id="a2694-113">Element</span><span class="sxs-lookup"><span data-stu-id="a2694-113">Element</span></span>|<span data-ttu-id="a2694-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2694-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a2694-115">\<filters></span><span class="sxs-lookup"><span data-stu-id="a2694-115">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="a2694-116">Enthält eine Standardprotokoll Zuordnung zwischen einem Transportprotokoll Schema (z. b. http, net. TCP, net. Pipe usw.) und einer WCF-Bindung.</span><span class="sxs-lookup"><span data-stu-id="a2694-116">Contains a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a WCF binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a2694-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a2694-117">Parent Elements</span></span>  
  
|<span data-ttu-id="a2694-118">Element</span><span class="sxs-lookup"><span data-stu-id="a2694-118">Element</span></span>|<span data-ttu-id="a2694-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2694-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a2694-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a2694-120">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="a2694-121">Das Stammelement aller WCF-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="a2694-121">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a2694-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a2694-122">Example</span></span>  
 <span data-ttu-id="a2694-123">Im folgenden Konfigurationsbeispiel wird die Standardprotokollzuordnung in der Datei machine.config veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a2694-123">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="a2694-124">Sie können diese Standardzuordnung auf Computerebene überschreiben, indem Sie die Datei machine.config ändern.</span><span class="sxs-lookup"><span data-stu-id="a2694-124">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="a2694-125">Wenn Sie sie lediglich innerhalb des Bereichs einer Anwendung überschreiben möchten, können Sie diesen Abschnitt innerhalb der Anwendungskonfigurationsdatei überschreiben und die Zuordnung für einzelne Protokollschemas ändern.</span><span class="sxs-lookup"><span data-stu-id="a2694-125">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a2694-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2694-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
