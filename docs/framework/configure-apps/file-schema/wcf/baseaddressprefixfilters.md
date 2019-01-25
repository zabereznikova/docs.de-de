---
title: '&lt;baseAddressPrefixFilters&gt;'
ms.date: 03/30/2017
ms.assetid: 8cab2a9a-c51f-4283-bb60-2ad0c274fd46
ms.openlocfilehash: 21a926d07aa818ce4ff5c2b85a04167fdd531047
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54667244"
---
# <a name="ltbaseaddressprefixfiltersgt"></a><span data-ttu-id="3d403-102">&lt;baseAddressPrefixFilters&gt;</span><span class="sxs-lookup"><span data-stu-id="3d403-102">&lt;baseAddressPrefixFilters&gt;</span></span>
<span data-ttu-id="3d403-103">Stellt eine Auflistung der Konfiguration, die Elemente, die angeben, durch Filtern, die bieten einen Mechanismus übergeben, um die entsprechenden (Internet Information Services, IIS)-Bindungen auszuwählen, wenn Sie die Windows Communication Foundation (WCF)-Anwendung in IIS hosten.</span><span class="sxs-lookup"><span data-stu-id="3d403-103">Represents a collection of configuration elements that specify pass through filters, which provide a mechanism to pick the appropriate Internet Information Services (IIS) bindings when hosting the Windows Communication Foundation (WCF) application in IIS.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="3d403-104">\<BaseAddressPrefixFilters > nicht "Localhost" erkannt wird, verwenden Sie stattdessen den vollqualifizierten Computernamen.</span><span class="sxs-lookup"><span data-stu-id="3d403-104">\<baseAddressPrefixFilters> does not recognize "localhost", use the fully qualified machine name instead.</span></span>  
  
 <span data-ttu-id="3d403-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3d403-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="3d403-106">\<ServiceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="3d403-106">\<ServiceHostingEnvironment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d403-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="3d403-107">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <baseAddressPrefixFilters>
    <add prefix="String" />
   </baseAddressPrefixFilters>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d403-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3d403-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3d403-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3d403-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d403-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="3d403-110">Attributes</span></span>  
 <span data-ttu-id="3d403-111">Keine</span><span class="sxs-lookup"><span data-stu-id="3d403-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3d403-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3d403-112">Child Elements</span></span>  
  
|<span data-ttu-id="3d403-113">Element</span><span class="sxs-lookup"><span data-stu-id="3d403-113">Element</span></span>|<span data-ttu-id="3d403-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3d403-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d403-115">\<add></span><span class="sxs-lookup"><span data-stu-id="3d403-115">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddressprefixfilter.md)|<span data-ttu-id="3d403-116">Fügt ein Konfigurationselement hinzu, das einen Präfixfilter für die vom Diensthost verwendeten Basisadressen angibt.</span><span class="sxs-lookup"><span data-stu-id="3d403-116">Adds a configuration element that specifies a prefix filter for the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3d403-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3d403-117">Parent Elements</span></span>  
  
|<span data-ttu-id="3d403-118">Element</span><span class="sxs-lookup"><span data-stu-id="3d403-118">Element</span></span>|<span data-ttu-id="3d403-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3d403-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d403-120">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="3d403-120">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="3d403-121">Definiert den Typ, der von der Diensthostumgebung für einen besonderen Transport instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="3d403-121">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d403-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3d403-122">Remarks</span></span>  
 <span data-ttu-id="3d403-123">Ein Präfixfilter bietet gemeinsamen Hostanbietern eine Methode, um die vom Dienst zu verwendenden URIs anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3d403-123">A prefix filter provides a way for shared hosting providers to specify which URIs are to be used by the service.</span></span> <span data-ttu-id="3d403-124">Sie ermöglicht es gemeinsamen Hosts, mehrere Anwendungen mit unterschiedlichen Basisadressen für dasselbe Schema auf derselben Website zu hosten.</span><span class="sxs-lookup"><span data-stu-id="3d403-124">It enables shared hosts to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="3d403-125">IIS-Websites sind Container für virtuelle Anwendungen, die virtuelle Verzeichnisse enthalten.</span><span class="sxs-lookup"><span data-stu-id="3d403-125">IIS Web sites are containers for virtual applications which contain virtual directories.</span></span> <span data-ttu-id="3d403-126">Auf die Anwendung auf einer Website kann über eine oder mehrere IIS-Bindungen zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="3d403-126">The application in a site can be accessed through one or more IIS bindings.</span></span> <span data-ttu-id="3d403-127">IIS-Bindungen stellen zwei Angaben bereit: ein Bindungsprotokoll und Bindungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="3d403-127">IIS bindings provide two pieces of information: binding protocol and binding information.</span></span> <span data-ttu-id="3d403-128">Das Bindungsprotokoll (z.&#160;B. HTTP) definiert das Schema, über das die Kommunikation erfolgt, und Bindungsinformationen (z.&#160;B. IP-Address, Anschluss, Hostheader) enthalten Daten, die für den Zugriff auf die Website verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3d403-128">Binding protocol (for example, HTTP) defines the scheme over which communication occurs, and binding information (for example, IP Address, Port, Hostheader) contains data used to access the site.</span></span>  
  
 <span data-ttu-id="3d403-129">IIS unterstützt die Angabe mehrerer IIS-Bindungen für jede Website, was zu mehreren Basisadressen für jedes Schema führt.</span><span class="sxs-lookup"><span data-stu-id="3d403-129">IIS supports specifying multiple IIS bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="3d403-130">Da ein unter einer Website gehosteter WCF-Dienst-Bindung an nur eine Basisadresse für jedes Schema ermöglicht, können Sie die Funktion "präfixfilter", um die erforderliche Basisadresse des gehosteten Dienstes auswählen.</span><span class="sxs-lookup"><span data-stu-id="3d403-130">Because a WCF service hosted under a site allows binding to only one base address for each scheme, you can use the prefix filter feature to pick the required base address of the hosted service.</span></span> <span data-ttu-id="3d403-131">Die von IIS bereitgestellten eingehenden Basisadressen werden anhand des optionalen Präfixlistenfilters gefiltert.</span><span class="sxs-lookup"><span data-stu-id="3d403-131">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list filter.</span></span>  
  
 <span data-ttu-id="3d403-132">Ihre Website kann beispielsweise die folgenden Basisadressen enthalten.</span><span class="sxs-lookup"><span data-stu-id="3d403-132">For example, your site can contain the following base addresses.</span></span>  
  
```  
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 <span data-ttu-id="3d403-133">Sie können die folgende Konfigurationsdatei verwenden, um einen Präfixfilter auf AppDomain-Ebene anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3d403-133">You can use the following configuration file to specify a prefix filter at the appdomain level.</span></span>  
  
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
  
 <span data-ttu-id="3d403-134">In diesem Beispiel sind `net.tcp://test1.fabrikam.com:8000` und `http://test2.fabrikam.com:9000` die einzigen Basisadressen für die jeweiligen Schemata, die übergeben werden können.</span><span class="sxs-lookup"><span data-stu-id="3d403-134">In this example, `net.tcp://test1.fabrikam.com:8000` and `http://test2.fabrikam.com:9000` are the only base addresses for their respective schemes, which are allowed to be passed through.</span></span>  
  
 <span data-ttu-id="3d403-135">Standardmäßig werden alle Adressen übergeben, wenn kein Präfix angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="3d403-135">By default, when prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="3d403-136">Wenn die Präfixergebnisse angegeben werden, wird nur die Basisadresse übergeben, die dem Schema entspricht.</span><span class="sxs-lookup"><span data-stu-id="3d403-136">Specifying the prefix only allows the matching base address for that scheme to be passed through.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d403-137">Der Filter unterstützt keine Platzhalter.</span><span class="sxs-lookup"><span data-stu-id="3d403-137">The filter does not support any wildcards.</span></span> <span data-ttu-id="3d403-138">Darüber hinaus verfügen die von IIS angegebenen Basisadressen möglicherweise über Adressen, die an andere, nicht in der `baseAddressPrefixFilters`-Liste vorhandene Schemata gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="3d403-138">In addition, the baseAddresses supplied by IIS may have addresses bound to other schemes not present in the `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="3d403-139">Diese Adressen werden nicht herausgefiltert.</span><span class="sxs-lookup"><span data-stu-id="3d403-139">These addresses are not filtered out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d403-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d403-140">See also</span></span>
- <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="3d403-141">Hosting</span><span class="sxs-lookup"><span data-stu-id="3d403-141">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
