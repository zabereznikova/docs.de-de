---
title: '&lt;add&gt; von &lt;baseAddressPrefixFilter&gt;'
ms.date: 03/30/2017
ms.assetid: b226bede-8459-4de9-b2ac-3d39604ce2bc
ms.openlocfilehash: ece3178c48c84c609ab959a5cfc426062de9255f
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145600"
---
# <a name="ltaddgt-of-ltbaseaddressprefixfiltergt"></a><span data-ttu-id="ee540-102">&lt;add&gt; von &lt;baseAddressPrefixFilter&gt;</span><span class="sxs-lookup"><span data-stu-id="ee540-102">&lt;add&gt; of &lt;baseAddressPrefixFilter&gt;</span></span>
<span data-ttu-id="ee540-103">Stellt ein Konfigurationselement, das einen Pass-Through-Filter, der einen Mechanismus angibt, um die entsprechenden (Internet Information Services, IIS)-Bindungen auszuwählen, wenn Sie eine Windows Communication Foundation (WCF)-Anwendung in IIS zu hosten.</span><span class="sxs-lookup"><span data-stu-id="ee540-103">Represents a configuration element that specifies a pass-through filter, which provides a mechanism to pick the appropriate Internet Information Services (IIS) bindings when hosting a Windows Communication Foundation (WCF) application in IIS.</span></span>  
  
 <span data-ttu-id="ee540-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ee540-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ee540-105">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="ee540-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="ee540-106">\<BaseAddressPrefixFilters ></span><span class="sxs-lookup"><span data-stu-id="ee540-106">\<baseAddressPrefixFilters></span></span>  
<span data-ttu-id="ee540-107">\<add></span><span class="sxs-lookup"><span data-stu-id="ee540-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee540-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="ee540-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <baseAddressPrefixFilters>
    <add prefix="String" />
  </baseAddressPrefixFilters>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ee540-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ee540-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ee540-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ee540-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ee540-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="ee540-111">Attributes</span></span>  
  
|<span data-ttu-id="ee540-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="ee540-112">Attribute</span></span>|<span data-ttu-id="ee540-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ee540-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ee540-114">prefix</span><span class="sxs-lookup"><span data-stu-id="ee540-114">prefix</span></span>|<span data-ttu-id="ee540-115">Ein URI, der verwendet wird, um einen Teil einer Basisadresse abzugleichen.</span><span class="sxs-lookup"><span data-stu-id="ee540-115">A URI that is used to match a part of a base address.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ee540-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ee540-116">Child Elements</span></span>  
 <span data-ttu-id="ee540-117">Keine</span><span class="sxs-lookup"><span data-stu-id="ee540-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ee540-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ee540-118">Parent Elements</span></span>  
  
|<span data-ttu-id="ee540-119">Element</span><span class="sxs-lookup"><span data-stu-id="ee540-119">Element</span></span>|<span data-ttu-id="ee540-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ee540-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ee540-121">\<BaseAddressPrefixFilters ></span><span class="sxs-lookup"><span data-stu-id="ee540-121">\<baseAddressPrefixFilters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md)|<span data-ttu-id="ee540-122">Eine Auflistung von Konfigurationselementen, die durchlauffilter, die einen Mechanismus angeben, um die entsprechenden IIS-Bindungen auszuwählen, wenn Sie eine Windows Communication Foundation (WCF)-Anwendung in IIS hosten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ee540-122">A collection of configuration elements that specify pass-through filters, which provide a mechanism to pick the appropriate IIS bindings when hosting a Windows Communication Foundation (WCF) application in IIS.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee540-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ee540-123">Remarks</span></span>  
 <span data-ttu-id="ee540-124">Ein Präfixfilter bietet gemeinsamen Hostanbietern eine Methode, um die vom Dienst zu verwendenden URIs anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ee540-124">A prefix filter provides a way for shared hosting providers to specify which URIs are to be used by the service.</span></span> <span data-ttu-id="ee540-125">Sie ermöglicht es gemeinsamen Hosts, mehrere Anwendungen mit unterschiedlichen Basisadressen für dasselbe Schema auf derselben Website zu hosten.</span><span class="sxs-lookup"><span data-stu-id="ee540-125">It enables shared hosts to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="ee540-126">IIS-Websites sind Container für virtuelle Anwendungen, die virtuelle Verzeichnisse enthalten.</span><span class="sxs-lookup"><span data-stu-id="ee540-126">IIS Web sites are containers for virtual applications which contain virtual directories.</span></span> <span data-ttu-id="ee540-127">Auf die Anwendung auf einer Website kann über eine oder mehrere IIS-Bindungen zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="ee540-127">The application in a site can be accessed through one or more IIS binding.</span></span> <span data-ttu-id="ee540-128">IIS-Bindungen stellen zwei Angaben bereit: ein Bindungsprotokoll und Bindungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="ee540-128">IIS bindings provide two pieces of information: binding protocol and binding information.</span></span> <span data-ttu-id="ee540-129">Das Bindungsprotokoll (z.&#160;B. HTTP) definiert das Schema, über das die Kommunikation erfolgt, und Bindungsinformationen (z.&#160;B. IP-Address, Anschluss, Hostheader) enthalten Daten, die für den Zugriff auf die Website verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ee540-129">Binding protocol (for example, HTTP) defines the scheme over which communication occurs, and binding information (for example, IP Address, Port, Hostheader) contains data used to access the site.</span></span>  
  
 <span data-ttu-id="ee540-130">IIS unterstützt die Angabe mehrerer IIS-Bindungen für jede Website, was zu mehreren Basisadressen für jedes Schema führt.</span><span class="sxs-lookup"><span data-stu-id="ee540-130">IIS supports specifying multiple IIS bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="ee540-131">Da ein unter einer Website gehosteter WCF-Dienst-Bindung an nur eine Basisadresse für jedes Schema ermöglicht, können Sie die Funktion "präfixfilter", um die erforderliche Basisadresse des gehosteten Dienstes auswählen.</span><span class="sxs-lookup"><span data-stu-id="ee540-131">Because a WCF service hosted under a site allows binding to only one base address for each scheme, you can use the prefix filter feature to pick the required base address of the hosted service.</span></span> <span data-ttu-id="ee540-132">Die von IIS bereitgestellten eingehenden Basisadressen werden anhand des optionalen Präfixlistenfilters gefiltert.</span><span class="sxs-lookup"><span data-stu-id="ee540-132">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list filter.</span></span>  
  
 <span data-ttu-id="ee540-133">Ihre Website kann beispielsweise die folgenden Basisadressen enthalten.</span><span class="sxs-lookup"><span data-stu-id="ee540-133">For example, your site can contain the following base addresses.</span></span>  
  
```  
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 <span data-ttu-id="ee540-134">Sie können die folgende Konfigurationsdatei verwenden, um einen Präfixfilter auf AppDomain-Ebene anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ee540-134">You can use the following configuration file to specify a prefix filter at the appdomain level.</span></span>  
  
```xml  
<system.serviceModel>
  <serviceHostingEnvironment>
    <baseAddressPrefixFilters>
      <add prefix="net.tcp://test1.fabrikam.com:8000" />
      <add prefix="http://test2.fabrikam.com:9000" />
    </baseAddressPrefixFilters>
  </serviceHostingEnvironment>
</system.serviceModel>
```  
  
 <span data-ttu-id="ee540-135">In diesem Beispiel sind `net.tcp://test1.fabrikam.com:8000` und `http://test2.fabrikam.com:9000` die einzigen Basisadressen für die jeweiligen Schemata, die übergeben werden können.</span><span class="sxs-lookup"><span data-stu-id="ee540-135">In this example, `net.tcp://test1.fabrikam.com:8000` and `http://test2.fabrikam.com:9000` are the only base addresses for their respective schemes which are allowed to be passed through.</span></span>  
  
 <span data-ttu-id="ee540-136">Standardmäßig werden alle Adressen übergeben, wenn kein Präfix angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="ee540-136">By default, when prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="ee540-137">Wenn die Präfixergebnisse angegeben werden, wird nur die Basisadresse übergeben, die dem Schema entspricht.</span><span class="sxs-lookup"><span data-stu-id="ee540-137">Specifying the prefix only allows the matching base address for that scheme to be passed through.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ee540-138">Der Filter unterstützt keine Platzhalter.</span><span class="sxs-lookup"><span data-stu-id="ee540-138">The filter does not support any wildcards.</span></span> <span data-ttu-id="ee540-139">Darüber hinaus verfügen die von IIS angegebenen Basisadressen möglicherweise über Adressen, die an andere, nicht in der `baseAddressPrefixFilters`-Liste vorhandene Schemata gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="ee540-139">In addition, the baseAddresses supplied by IIS may have addresses bound to other schemes not present in the `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="ee540-140">Diese Adressen werden nicht herausgefiltert.</span><span class="sxs-lookup"><span data-stu-id="ee540-140">These addresses are not filtered out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee540-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee540-141">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElement>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 [<span data-ttu-id="ee540-142">Hosting</span><span class="sxs-lookup"><span data-stu-id="ee540-142">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
