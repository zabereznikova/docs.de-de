---
title: <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 5076644b-1f33-4f26-9488-87de9fcda04c
ms.openlocfilehash: 0a79aa18c74ddb8ec47f02620d16d391b4a36b68
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162295"
---
# \<protocolMapping>

<span data-ttu-id="a3486-101">Stellt einen Konfigurationsabschnitt zur Definition eines Satzes von Standardprotokollzuordnungen zwischen Transportprotokollschemas (z. B. http, net.tcp, net.pipe usw.) und WCF-Bindungen dar.</span><span class="sxs-lookup"><span data-stu-id="a3486-101">Represents a configuration section for defining a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span> <span data-ttu-id="a3486-102">Beim Erstellen von Standard Endpunkten zur Laufzeit untersucht Windows Communication Foundation (WCF) die konfigurierten Zuordnungen und entscheidet, welche Bindung für eine bestimmte basierte Adresse verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a3486-102">When creating default endpoints at runtime, Windows Communication Foundation (WCF) looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<protocolMapping>**  
  
## <a name="syntax"></a><span data-ttu-id="a3486-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="a3486-103">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3486-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a3486-104">Attributes and Elements</span></span>  

 <span data-ttu-id="a3486-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a3486-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3486-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="a3486-106">Attributes</span></span>  

 <span data-ttu-id="a3486-107">Keine</span><span class="sxs-lookup"><span data-stu-id="a3486-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a3486-108">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a3486-108">Child Elements</span></span>  
  
|<span data-ttu-id="a3486-109">Element</span><span class="sxs-lookup"><span data-stu-id="a3486-109">Element</span></span>|<span data-ttu-id="a3486-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a3486-110">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="a3486-111">Enthält eine Standardprotokollzuordnung zwischen einem Transportprotokollschema (z. B. http, net.tcp, net.pipe usw.) und einer WCF-Bindung. </span><span class="sxs-lookup"><span data-stu-id="a3486-111">Contains a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a WCF binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a3486-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a3486-112">Parent Elements</span></span>  
  
|<span data-ttu-id="a3486-113">Element</span><span class="sxs-lookup"><span data-stu-id="a3486-113">Element</span></span>|<span data-ttu-id="a3486-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a3486-114">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="a3486-115">Das Stammelement aller WCF-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="a3486-115">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a3486-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a3486-116">Example</span></span>  

 <span data-ttu-id="a3486-117">Im folgenden Konfigurationsbeispiel wird die Standardprotokollzuordnung in der Datei machine.config veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a3486-117">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="a3486-118">Sie können diese Standardzuordnung auf Computerebene überschreiben, indem Sie die Datei machine.config ändern.</span><span class="sxs-lookup"><span data-stu-id="a3486-118">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="a3486-119">Wenn Sie sie lediglich innerhalb des Bereichs einer Anwendung überschreiben möchten, können Sie diesen Abschnitt innerhalb der Anwendungskonfigurationsdatei überschreiben und die Zuordnung für einzelne Protokollschemas ändern.</span><span class="sxs-lookup"><span data-stu-id="a3486-119">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a3486-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a3486-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
