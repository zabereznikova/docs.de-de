---
title: <add> von <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
ms.openlocfilehash: 6197d01665d49a7c97ac9e44251abf15faf80a8f
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850378"
---
# <a name="add-of-protocolmapping"></a><span data-ttu-id="eb9e7-102">\<Fügen Sie > \<von protocolmapping hinzu ></span><span class="sxs-lookup"><span data-stu-id="eb9e7-102">\<add> of \<protocolMapping></span></span>
<span data-ttu-id="eb9e7-103">Stellt eine Standardprotokoll Zuordnung zwischen einem Transportprotokoll Schema (z. b. http, net. TCP, net. Pipe usw.) und einer Windows Communication Foundation (WCF)-Bindung dar.</span><span class="sxs-lookup"><span data-stu-id="eb9e7-103">Represents a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a Windows Communication Foundation (WCF) binding.</span></span> <span data-ttu-id="eb9e7-104">Beim Erstellen von Standard Endpunkten zur Laufzeit prüft WCF die konfigurierten Zuordnungen und entscheidet, welche Bindung für eine bestimmte basierte Adresse verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="eb9e7-104">When creating default endpoints at runtime, WCF looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
<span data-ttu-id="eb9e7-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="eb9e7-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="eb9e7-106">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="eb9e7-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="eb9e7-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<protocolmapping->** ](protocolmapping.md)</span><span class="sxs-lookup"><span data-stu-id="eb9e7-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<protocolMapping>**](protocolmapping.md)</span></span>\
<span data-ttu-id="eb9e7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> Hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="eb9e7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb9e7-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="eb9e7-109">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb9e7-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="eb9e7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="eb9e7-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="eb9e7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb9e7-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="eb9e7-112">Attributes</span></span>  
  
|<span data-ttu-id="eb9e7-113">Element</span><span class="sxs-lookup"><span data-stu-id="eb9e7-113">Element</span></span>|<span data-ttu-id="eb9e7-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb9e7-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eb9e7-115">Bindung</span><span class="sxs-lookup"><span data-stu-id="eb9e7-115">binding</span></span>|<span data-ttu-id="eb9e7-116">Eine Zeichenfolge, die den Typ der Bindung angibt, die während der Standardendpunkterstellung für einen Endpunkt verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="eb9e7-116">A string that specifies the type of binding to be used for an endpoint during default endpoint creation.</span></span>|  
|<span data-ttu-id="eb9e7-117">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="eb9e7-117">bindingConfiguration</span></span>|<span data-ttu-id="eb9e7-118">Eine Zeichenfolge, die den Namen des Bindungskonfigurationsabschnitts angibt, auf den verwiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="eb9e7-118">A string that specifies the name of the binding configuration section to be referenced.</span></span>|  
|<span data-ttu-id="eb9e7-119">scheme</span><span class="sxs-lookup"><span data-stu-id="eb9e7-119">scheme</span></span>|<span data-ttu-id="eb9e7-120">Das für den Standardendpunkt zu verwendende Transportprotokollschema.</span><span class="sxs-lookup"><span data-stu-id="eb9e7-120">The transport protocol scheme to be used for the default endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eb9e7-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eb9e7-121">Child Elements</span></span>  
 <span data-ttu-id="eb9e7-122">Keine</span><span class="sxs-lookup"><span data-stu-id="eb9e7-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eb9e7-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eb9e7-123">Parent Elements</span></span>  
  
|<span data-ttu-id="eb9e7-124">Element</span><span class="sxs-lookup"><span data-stu-id="eb9e7-124">Element</span></span>|<span data-ttu-id="eb9e7-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb9e7-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb9e7-126">\<protocolMapping></span><span class="sxs-lookup"><span data-stu-id="eb9e7-126">\<protocolMapping></span></span>](protocolmapping.md)|<span data-ttu-id="eb9e7-127">Stellt einen Konfigurations Abschnitt zum Definieren von Standardprotokoll Zuordnungen zwischen Transportprotokoll Schemas (z. b. http, net. TCP, net. Pipe usw.) und Windows Communication Foundation (WCF)-Bindungen dar.</span><span class="sxs-lookup"><span data-stu-id="eb9e7-127">Represents a configuration section for defining default protocol mappings between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and Windows Communication Foundation (WCF) bindings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="eb9e7-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eb9e7-128">Example</span></span>  
 <span data-ttu-id="eb9e7-129">Im folgenden Konfigurationsbeispiel wird die Standardprotokollzuordnung in der Datei machine.config veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="eb9e7-129">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="eb9e7-130">Sie können diese Standardzuordnung auf Computerebene überschreiben, indem Sie die Datei machine.config ändern.</span><span class="sxs-lookup"><span data-stu-id="eb9e7-130">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="eb9e7-131">Wenn Sie sie lediglich innerhalb des Bereichs einer Anwendung überschreiben möchten, können Sie diesen Abschnitt innerhalb der Anwendungskonfigurationsdatei überschreiben und die Zuordnung für einzelne Protokollschemas ändern.</span><span class="sxs-lookup"><span data-stu-id="eb9e7-131">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="eb9e7-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb9e7-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
