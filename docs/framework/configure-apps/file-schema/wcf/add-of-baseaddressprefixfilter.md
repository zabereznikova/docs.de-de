---
title: <add> von <baseAddressPrefixFilter>
ms.date: 03/30/2017
ms.assetid: b226bede-8459-4de9-b2ac-3d39604ce2bc
ms.openlocfilehash: 809e6d5504b56f86eb09a5d57931f922e1c18348
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73973824"
---
# <a name="add-of-baseaddressprefixfilter"></a><span data-ttu-id="6b4bb-102">\<> \<baseadresssspree fixfilter hinzufügen ></span><span class="sxs-lookup"><span data-stu-id="6b4bb-102">\<add> of \<baseAddressPrefixFilter></span></span>
<span data-ttu-id="6b4bb-103">Stellt ein Konfigurationselement dar, das einen Pass-Through-Filter angibt, der einen Mechanismus zum Auswählen der entsprechenden Internetinformationsdienste (IIS)-Bindungen beim Hosten einer Windows Communication Foundation (WCF)-Anwendung in IIS bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="6b4bb-103">Represents a configuration element that specifies a pass-through filter, which provides a mechanism to pick the appropriate Internet Information Services (IIS) bindings when hosting a Windows Communication Foundation (WCF) application in IIS.</span></span>  
  
<span data-ttu-id="6b4bb-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6b4bb-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6b4bb-105">&nbsp; &nbsp;[ **\<system. Service Model->** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="6b4bb-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="6b4bb-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ServiceHost**](servicehostingenvironment.md) -></span><span class="sxs-lookup"><span data-stu-id="6b4bb-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span></span>\
<span data-ttu-id="6b4bb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<baseadresspfixfilters >** ](baseaddressprefixfilters.md)</span><span class="sxs-lookup"><span data-stu-id="6b4bb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<baseAddressPrefixFilters>**](baseaddressprefixfilters.md)</span></span>\
<span data-ttu-id="6b4bb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<hinzufügen >**</span><span class="sxs-lookup"><span data-stu-id="6b4bb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b4bb-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b4bb-109">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <baseAddressPrefixFilters>
    <add prefix="String" />
  </baseAddressPrefixFilters>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b4bb-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6b4bb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6b4bb-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6b4bb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b4bb-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="6b4bb-112">Attributes</span></span>  
  
|<span data-ttu-id="6b4bb-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="6b4bb-113">Attribute</span></span>|<span data-ttu-id="6b4bb-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6b4bb-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6b4bb-115">prefix</span><span class="sxs-lookup"><span data-stu-id="6b4bb-115">prefix</span></span>|<span data-ttu-id="6b4bb-116">Ein URI, der verwendet wird, um einen Teil einer Basisadresse abzugleichen.</span><span class="sxs-lookup"><span data-stu-id="6b4bb-116">A URI that is used to match a part of a base address.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6b4bb-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6b4bb-117">Child Elements</span></span>  
 <span data-ttu-id="6b4bb-118">Keine</span><span class="sxs-lookup"><span data-stu-id="6b4bb-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6b4bb-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6b4bb-119">Parent Elements</span></span>  
  
|<span data-ttu-id="6b4bb-120">Element</span><span class="sxs-lookup"><span data-stu-id="6b4bb-120">Element</span></span>|<span data-ttu-id="6b4bb-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6b4bb-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6b4bb-122">\<baseadresspfixfilters ></span><span class="sxs-lookup"><span data-stu-id="6b4bb-122">\<baseAddressPrefixFilters></span></span>](baseaddressprefixfilters.md)|<span data-ttu-id="6b4bb-123">Eine Auflistung von Konfigurationselementen, die Pass-Through-Filter angeben, die einen Mechanismus zum Auswählen der entsprechenden IIS-Bindungen bieten, wenn eine Windows Communication Foundation (WCF)-Anwendung in IIS gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="6b4bb-123">A collection of configuration elements that specify pass-through filters, which provide a mechanism to pick the appropriate IIS bindings when hosting a Windows Communication Foundation (WCF) application in IIS.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b4bb-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6b4bb-124">Remarks</span></span>  
 <span data-ttu-id="6b4bb-125">Ein Präfixfilter bietet gemeinsamen Hostanbietern eine Methode, um die vom Dienst zu verwendenden URIs anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6b4bb-125">A prefix filter provides a way for shared hosting providers to specify which URIs are to be used by the service.</span></span> <span data-ttu-id="6b4bb-126">Sie ermöglicht es gemeinsamen Hosts, mehrere Anwendungen mit unterschiedlichen Basisadressen für dasselbe Schema auf derselben Website zu hosten.</span><span class="sxs-lookup"><span data-stu-id="6b4bb-126">It enables shared hosts to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="6b4bb-127">IIS-Websites sind Container für virtuelle Anwendungen, die virtuelle Verzeichnisse enthalten.</span><span class="sxs-lookup"><span data-stu-id="6b4bb-127">IIS Web sites are containers for virtual applications which contain virtual directories.</span></span> <span data-ttu-id="6b4bb-128">Auf die Anwendung auf einer Website kann über eine oder mehrere IIS-Bindungen zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="6b4bb-128">The application in a site can be accessed through one or more IIS binding.</span></span> <span data-ttu-id="6b4bb-129">IIS-Bindungen stellen zwei Angaben bereit: ein Bindungsprotokoll und Bindungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="6b4bb-129">IIS bindings provide two pieces of information: binding protocol and binding information.</span></span> <span data-ttu-id="6b4bb-130">Das Bindungsprotokoll (z.&#160;B. HTTP) definiert das Schema, über das die Kommunikation erfolgt, und Bindungsinformationen (z.&#160;B. IP-Address, Anschluss, Hostheader) enthalten Daten, die für den Zugriff auf die Website verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6b4bb-130">Binding protocol (for example, HTTP) defines the scheme over which communication occurs, and binding information (for example, IP Address, Port, Hostheader) contains data used to access the site.</span></span>  
  
 <span data-ttu-id="6b4bb-131">IIS unterstützt die Angabe mehrerer IIS-Bindungen für jede Website, was zu mehreren Basisadressen für jedes Schema führt.</span><span class="sxs-lookup"><span data-stu-id="6b4bb-131">IIS supports specifying multiple IIS bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="6b4bb-132">Da ein unter einer Website gehosteter WCF-Dienst nur die Bindung an eine Basisadresse für jedes Schema ermöglicht, können Sie mit der Präfix Filterfunktion die erforderliche Basisadresse des gehosteten Dienstanbieter auswählen.</span><span class="sxs-lookup"><span data-stu-id="6b4bb-132">Because a WCF service hosted under a site allows binding to only one base address for each scheme, you can use the prefix filter feature to pick the required base address of the hosted service.</span></span> <span data-ttu-id="6b4bb-133">Die von IIS bereitgestellten eingehenden Basisadressen werden anhand des optionalen Präfixlistenfilters gefiltert.</span><span class="sxs-lookup"><span data-stu-id="6b4bb-133">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list filter.</span></span>  
  
 <span data-ttu-id="6b4bb-134">Ihre Website kann beispielsweise die folgenden Basisadressen enthalten:</span><span class="sxs-lookup"><span data-stu-id="6b4bb-134">For example, your site can contain the following base addresses:</span></span>
  
``` 
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 <span data-ttu-id="6b4bb-135">Sie können die folgende Konfigurationsdatei verwenden, um einen Präfixfilter auf AppDomain-Ebene anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6b4bb-135">You can use the following configuration file to specify a prefix filter at the appdomain level.</span></span>  
  
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
  
 <span data-ttu-id="6b4bb-136">In diesem Beispiel sind `net.tcp://test1.fabrikam.com:8000` und `http://test2.fabrikam.com:9000` die einzigen Basisadressen für die jeweiligen Schemata, die übergeben werden können.</span><span class="sxs-lookup"><span data-stu-id="6b4bb-136">In this example, `net.tcp://test1.fabrikam.com:8000` and `http://test2.fabrikam.com:9000` are the only base addresses for their respective schemes which are allowed to be passed through.</span></span>  
  
 <span data-ttu-id="6b4bb-137">Standardmäßig werden alle Adressen übergeben, wenn kein Präfix angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="6b4bb-137">By default, when prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="6b4bb-138">Wenn die Präfixergebnisse angegeben werden, wird nur die Basisadresse übergeben, die dem Schema entspricht.</span><span class="sxs-lookup"><span data-stu-id="6b4bb-138">Specifying the prefix only allows the matching base address for that scheme to be passed through.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6b4bb-139">Der Filter unterstützt keine Platzhalter.</span><span class="sxs-lookup"><span data-stu-id="6b4bb-139">The filter does not support any wildcards.</span></span> <span data-ttu-id="6b4bb-140">Darüber hinaus verfügen die von IIS angegebenen Basisadressen möglicherweise über Adressen, die an andere, nicht in der `baseAddressPrefixFilters`-Liste vorhandene Schemata gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="6b4bb-140">In addition, the baseAddresses supplied by IIS may have addresses bound to other schemes not present in the `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="6b4bb-141">Diese Adressen werden nicht herausgefiltert.</span><span class="sxs-lookup"><span data-stu-id="6b4bb-141">These addresses are not filtered out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b4bb-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b4bb-142">See also</span></span>

- <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="6b4bb-143">Hosting</span><span class="sxs-lookup"><span data-stu-id="6b4bb-143">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
