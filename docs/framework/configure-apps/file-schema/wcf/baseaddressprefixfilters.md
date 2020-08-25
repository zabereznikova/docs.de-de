---
title: <baseAddressPrefixFilters>
ms.date: 03/30/2017
ms.assetid: 8cab2a9a-c51f-4283-bb60-2ad0c274fd46
ms.openlocfilehash: 635e4f02f4d286b63c4f4845563ba1953d23592a
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811898"
---
# \<baseAddressPrefixFilters>
<span data-ttu-id="9ce78-101">Stellt eine Auflistung von Konfigurationselementen dar, die Pass-Through-Filter angeben. diese bieten einen Mechanismus zum Auswählen der entsprechenden Internetinformationsdienste (IIS)-Bindungen beim Hosten der Windows Communication Foundation (WCF)-Anwendung in IIS.</span><span class="sxs-lookup"><span data-stu-id="9ce78-101">Represents a collection of configuration elements that specify pass through filters, which provide a mechanism to pick the appropriate Internet Information Services (IIS) bindings when hosting the Windows Communication Foundation (WCF) application in IIS.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="9ce78-102">\<baseAddressPrefixFilters> "localhost" wird nicht erkannt. Verwenden Sie stattdessen den voll qualifizierten Computernamen.</span><span class="sxs-lookup"><span data-stu-id="9ce78-102">\<baseAddressPrefixFilters> does not recognize "localhost"; use the fully qualified machine name instead.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<baseAddressPrefixFilters>**  
  
## <a name="syntax"></a><span data-ttu-id="9ce78-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="9ce78-103">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <baseAddressPrefixFilters>
    <add prefix="String" />
   </baseAddressPrefixFilters>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ce78-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9ce78-104">Attributes and Elements</span></span>  
 <span data-ttu-id="9ce78-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9ce78-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ce78-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="9ce78-106">Attributes</span></span>  
 <span data-ttu-id="9ce78-107">Keine</span><span class="sxs-lookup"><span data-stu-id="9ce78-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9ce78-108">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9ce78-108">Child Elements</span></span>  
  
|<span data-ttu-id="9ce78-109">Element</span><span class="sxs-lookup"><span data-stu-id="9ce78-109">Element</span></span>|<span data-ttu-id="9ce78-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9ce78-110">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-baseaddressprefixfilter.md)|<span data-ttu-id="9ce78-111">Fügt ein Konfigurationselement hinzu, das einen Präfixfilter für die vom Diensthost verwendeten Basisadressen angibt.</span><span class="sxs-lookup"><span data-stu-id="9ce78-111">Adds a configuration element that specifies a prefix filter for the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9ce78-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9ce78-112">Parent Elements</span></span>  
  
|<span data-ttu-id="9ce78-113">Element</span><span class="sxs-lookup"><span data-stu-id="9ce78-113">Element</span></span>|<span data-ttu-id="9ce78-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9ce78-114">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="9ce78-115">Definiert den Typ, der von der Diensthostumgebung für einen besonderen Transport instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="9ce78-115">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ce78-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9ce78-116">Remarks</span></span>  
 <span data-ttu-id="9ce78-117">Ein Präfixfilter bietet gemeinsamen Hostanbietern eine Methode, um die vom Dienst zu verwendenden URIs anzugeben.</span><span class="sxs-lookup"><span data-stu-id="9ce78-117">A prefix filter provides a way for shared hosting providers to specify which URIs are to be used by the service.</span></span> <span data-ttu-id="9ce78-118">Sie ermöglicht es gemeinsamen Hosts, mehrere Anwendungen mit unterschiedlichen Basisadressen für dasselbe Schema auf derselben Website zu hosten.</span><span class="sxs-lookup"><span data-stu-id="9ce78-118">It enables shared hosts to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="9ce78-119">IIS-Websites sind Container für virtuelle Anwendungen, die virtuelle Verzeichnisse enthalten.</span><span class="sxs-lookup"><span data-stu-id="9ce78-119">IIS Web sites are containers for virtual applications which contain virtual directories.</span></span> <span data-ttu-id="9ce78-120">Auf die Anwendung auf einer Website kann über eine oder mehrere IIS-Bindungen zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="9ce78-120">The application in a site can be accessed through one or more IIS bindings.</span></span> <span data-ttu-id="9ce78-121">IIS-Bindungen stellen zwei Angaben bereit: ein Bindungsprotokoll und Bindungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="9ce78-121">IIS bindings provide two pieces of information: binding protocol and binding information.</span></span> <span data-ttu-id="9ce78-122">Das Bindungsprotokoll (z.&#160;B. HTTP) definiert das Schema, über das die Kommunikation erfolgt, und Bindungsinformationen (z.&#160;B. IP-Address, Anschluss, Hostheader) enthalten Daten, die für den Zugriff auf die Website verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9ce78-122">Binding protocol (for example, HTTP) defines the scheme over which communication occurs, and binding information (for example, IP Address, Port, Hostheader) contains data used to access the site.</span></span>  
  
 <span data-ttu-id="9ce78-123">IIS unterstützt die Angabe mehrerer IIS-Bindungen für jede Website, was zu mehreren Basisadressen für jedes Schema führt.</span><span class="sxs-lookup"><span data-stu-id="9ce78-123">IIS supports specifying multiple IIS bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="9ce78-124">Da ein unter einer Website gehosteter WCF-Dienst nur die Bindung an eine Basisadresse für jedes Schema ermöglicht, können Sie mit der Präfix Filterfunktion die erforderliche Basisadresse des gehosteten Dienstanbieter auswählen.</span><span class="sxs-lookup"><span data-stu-id="9ce78-124">Because a WCF service hosted under a site allows binding to only one base address for each scheme, you can use the prefix filter feature to pick the required base address of the hosted service.</span></span> <span data-ttu-id="9ce78-125">Die von IIS bereitgestellten eingehenden Basisadressen werden anhand des optionalen Präfixlistenfilters gefiltert.</span><span class="sxs-lookup"><span data-stu-id="9ce78-125">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list filter.</span></span>  
  
 <span data-ttu-id="9ce78-126">Ihre Website kann beispielsweise die folgenden Basisadressen enthalten:</span><span class="sxs-lookup"><span data-stu-id="9ce78-126">For example, your site can contain the following base addresses:</span></span>
  
```http
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 <span data-ttu-id="9ce78-127">Sie können die folgende Konfigurationsdatei verwenden, um einen Präfixfilter auf AppDomain-Ebene anzugeben.</span><span class="sxs-lookup"><span data-stu-id="9ce78-127">You can use the following configuration file to specify a prefix filter at the appdomain level.</span></span>  
  
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
  
 <span data-ttu-id="9ce78-128">In diesem Beispiel sind `net.tcp://test1.fabrikam.com:8000` und `http://test2.fabrikam.com:9000` die einzigen Basisadressen für die jeweiligen Schemata, die übergeben werden können.</span><span class="sxs-lookup"><span data-stu-id="9ce78-128">In this example, `net.tcp://test1.fabrikam.com:8000` and `http://test2.fabrikam.com:9000` are the only base addresses for their respective schemes, which are allowed to be passed through.</span></span>  
  
 <span data-ttu-id="9ce78-129">Standardmäßig werden alle Adressen übergeben, wenn kein Präfix angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="9ce78-129">By default, when prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="9ce78-130">Wenn die Präfixergebnisse angegeben werden, wird nur die Basisadresse übergeben, die dem Schema entspricht.</span><span class="sxs-lookup"><span data-stu-id="9ce78-130">Specifying the prefix only allows the matching base address for that scheme to be passed through.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9ce78-131">Der Filter unterstützt keine Platzhalter.</span><span class="sxs-lookup"><span data-stu-id="9ce78-131">The filter does not support any wildcards.</span></span> <span data-ttu-id="9ce78-132">Darüber hinaus verfügen die von IIS angegebenen Basisadressen möglicherweise über Adressen, die an andere, nicht in der `baseAddressPrefixFilters`-Liste vorhandene Schemata gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="9ce78-132">In addition, the baseAddresses supplied by IIS may have addresses bound to other schemes not present in the `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="9ce78-133">Diese Adressen werden nicht herausgefiltert.</span><span class="sxs-lookup"><span data-stu-id="9ce78-133">These addresses are not filtered out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ce78-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9ce78-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="9ce78-135">Hosting</span><span class="sxs-lookup"><span data-stu-id="9ce78-135">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
