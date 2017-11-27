---
title: '&lt;serviceHostingEnvironment&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4f8a7c4f-e735-4987-979a-b74fcdae2652
caps.latest.revision: "24"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5770cb8fd68eb68145f3f7fbcf197302883efe9f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltservicehostingenvironmentgt"></a><span data-ttu-id="c4869-102">&lt;serviceHostingEnvironment&gt;</span><span class="sxs-lookup"><span data-stu-id="c4869-102">&lt;serviceHostingEnvironment&gt;</span></span>
<span data-ttu-id="c4869-103">Dieses Element definiert den Typ, der von der Diensthostingumgebung für einen bestimmten Transport instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="c4869-103">This element defines the type the service hosting environment instantiates for a particular transport.</span></span> <span data-ttu-id="c4869-104">Falls dieses Element leer ist, wird der Standardtyp verwendet.</span><span class="sxs-lookup"><span data-stu-id="c4869-104">If this element is empty, the default type is used.</span></span> <span data-ttu-id="c4869-105">Dieses Element kann nur über die Anwendungskonfigurationsdatei bzw. die Computerkonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c4869-105">This element can only be used at the application or machine level configuration files.</span></span>  
  
 <span data-ttu-id="c4869-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="c4869-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="c4869-107">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="c4869-107">\<ServiceHostingEnvironment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4869-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4869-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment aspNetCompatibilityEnabled="Boolean" 
                           minFreeMemoryPercentageToActivateService="Integer" 
                           multipleSiteBindingsEnabled="Boolean">
  <baseAddressPrefixFilters>
    <add prefix="string" />
  </baseAddressPrefixFilters>
  <serviceActivations>
    <add factory="String" service="String" />
  </serviceActivations>
  <transportConfigurationTypes>
    <add name="String" transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c4869-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c4869-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c4869-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c4869-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c4869-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="c4869-111">Attributes</span></span>  
  
|<span data-ttu-id="c4869-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="c4869-112">Attribute</span></span>|<span data-ttu-id="c4869-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c4869-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c4869-114">aspNetCompatibilityEnabled</span><span class="sxs-lookup"><span data-stu-id="c4869-114">aspNetCompatibilityEnabled</span></span>|<span data-ttu-id="c4869-115">Ein boolescher Wert, der angibt, ob der ASP.NET-Kompatibilitätsmodus für die aktuelle Anwendung aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="c4869-115">A Boolean value indicating whether the ASP.NET compatibility mode has been turned on for the current application.</span></span> <span data-ttu-id="c4869-116">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="c4869-116">The default is `false`.</span></span><br /><br /> <span data-ttu-id="c4869-117">Wenn dieses Attribut auf `true` festgelegt wird, fließen die Anforderungen an die [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Dienste durch die ASP.NET-HTTP-Pipeline, und die Kommunikation über Nicht-HTTP-Protokolle wird untersagt.</span><span class="sxs-lookup"><span data-stu-id="c4869-117">When this attribute is set to `true`, requests to [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services flow through the ASP.NET HTTP pipeline, and communication over non-HTTP protocols is prohibited.</span></span> <span data-ttu-id="c4869-118">Weitere Informationen finden Sie unter [WCF-Dienste und ASP.NET](../../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).</span><span class="sxs-lookup"><span data-stu-id="c4869-118">For more information, see [WCF Services and ASP.NET](../../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).</span></span>|  
|<span data-ttu-id="c4869-119">minFreeMemoryPercentageToActivateService</span><span class="sxs-lookup"><span data-stu-id="c4869-119">minFreeMemoryPercentageToActivateService</span></span>|<span data-ttu-id="c4869-120">Eine ganze Zahl, welche die Mindestmenge des freien Arbeitsspeichers angibt, der auf dem System zur Verfügung stehen sollte, bevor ein [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Dienst aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="c4869-120">An integer that specifies the minimum amount of free memory that should be available to the system, before a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service can be activated.</span></span> <span data-ttu-id="c4869-121">**Vorsicht:** Festlegen dieses Attributs zusammen mit teilweiser Vertrauenswürdigkeit in der Datei "Web.config" ein [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] Dienst führt zu einer <xref:System.Security.SecurityException> Wenn der Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c4869-121">**Caution:**  Specifying this attribute along with partial trust in the web.config file of a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service will result in a <xref:System.Security.SecurityException> when the service is run.</span></span>|  
|<span data-ttu-id="c4869-122">multipleSiteBindingsEnabled</span><span class="sxs-lookup"><span data-stu-id="c4869-122">multipleSiteBindingsEnabled</span></span>|<span data-ttu-id="c4869-123">Ein boolescher Wert, der angibt, ob mehrere IIS-Bindungen pro Website aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="c4869-123">A Boolean value that specifies whether multiple IIS bindings per site is enabled.</span></span><br /><br /> <span data-ttu-id="c4869-124">IIS besteht aus Websites, die als Container für virtuelle Anwendungen fungieren, die virtuelle Verzeichnisse enthalten.</span><span class="sxs-lookup"><span data-stu-id="c4869-124">IIS consists of web sites, which are containers for virtual applications containing virtual directories.</span></span> <span data-ttu-id="c4869-125">Auf die Anwendung auf einer Website kann über eine oder mehrere IIS-Bindungen zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="c4869-125">The application in a site can be accessed through one or more IIS binding.</span></span> <span data-ttu-id="c4869-126">IIS-Bindungen stellen zwei Angaben bereit: ein Bindungsprotokoll und Bindungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="c4869-126">An IIS binding provides two pieces of information: a binding protocol and binding information.</span></span> <span data-ttu-id="c4869-127">Das Bindungsprotokoll definiert das Schema, das für die Kommunikation verwendet wird, und die Bindungsinformationen dienen dem Zugriff auf die Website.</span><span class="sxs-lookup"><span data-stu-id="c4869-127">Binding protocol defines the scheme over which communication occurs, and binding information is the information used to access the site.</span></span> <span data-ttu-id="c4869-128">Ein Beispiel für ein Bindungsprotokoll kann HTTP sein, wohingegen Bindungsinformationen eine IP-Adresse, einen Port, einen Hostheader usw. enthalten können.</span><span class="sxs-lookup"><span data-stu-id="c4869-128">An example of a binding protocol can be HTTP, whereas binding information can contain an IP address, Port, host header, etc.</span></span><br /><br /> <span data-ttu-id="c4869-129">IIS unterstützt die Angabe mehrerer IIS-Bindungen pro Website, was zu mehreren Basisadressen pro Schema führt.</span><span class="sxs-lookup"><span data-stu-id="c4869-129">IIS supports specifying multiple IIS bindings per site, which results in multiple base addresses per scheme.</span></span> <span data-ttu-id="c4869-130">Ein unter einer Website gehosteter [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Dienst ermöglicht die Bindung zu nur einem baseAddress-Element pro Schema.</span><span class="sxs-lookup"><span data-stu-id="c4869-130">However, a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service hosted under a site allows binding to only one baseAddress per scheme.</span></span><br /><br /> <span data-ttu-id="c4869-131">Um mehrere IIS-Bindungen pro Website für einen [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Dienst zu aktivieren, legen Sie dieses Attribut auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="c4869-131">To enable multiple IIS bindings per site for a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service, set this attribute to `true`.</span></span> <span data-ttu-id="c4869-132">Beachten Sie, dass mehrere Bindungen pro Website nur für das HTTP-Protokoll unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="c4869-132">Notice that multiple site binding is supported only for the HTTP protocol.</span></span> <span data-ttu-id="c4869-133">Die Adresse der Endpunkte in der Konfigurationsdatei muss ein vollständiger URI sein.</span><span class="sxs-lookup"><span data-stu-id="c4869-133">The address of endpoints in the configuration file needs to be a complete URI.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c4869-134">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c4869-134">Child Elements</span></span>  
  
|<span data-ttu-id="c4869-135">Element</span><span class="sxs-lookup"><span data-stu-id="c4869-135">Element</span></span>|<span data-ttu-id="c4869-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c4869-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c4869-137">\<BaseAddressPrefixFilters ></span><span class="sxs-lookup"><span data-stu-id="c4869-137">\<baseAddressPrefixFilters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md)|<span data-ttu-id="c4869-138">Eine Auflistung der Konfigurationselemente, die den Präfixfilter für die vom Diensthost verwendeten Basisadressen angeben.</span><span class="sxs-lookup"><span data-stu-id="c4869-138">A collection of configuration elements that specify prefix filters for the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="c4869-139">\<ServiceActivations ></span><span class="sxs-lookup"><span data-stu-id="c4869-139">\<serviceActivations></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/serviceactivations.md)|<span data-ttu-id="c4869-140">Ein Konfigurationsabschnitt, der Aktivierungseinstellungen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="c4869-140">A configuration section that describes activation settings.</span></span>|  
|[<span data-ttu-id="c4869-141">\<TransportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="c4869-141">\<transportConfigurationTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transportconfigurationtypes.md)|<span data-ttu-id="c4869-142">Eine Auflistung der Konfigurationselemente, die den Typ eines bestimmten Transports identifizieren.</span><span class="sxs-lookup"><span data-stu-id="c4869-142">A collection of configuration elements that identify the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c4869-143">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c4869-143">Parent Elements</span></span>  
  
|<span data-ttu-id="c4869-144">Element</span><span class="sxs-lookup"><span data-stu-id="c4869-144">Element</span></span>|<span data-ttu-id="c4869-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c4869-145">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c4869-146">serviceModel</span><span class="sxs-lookup"><span data-stu-id="c4869-146">serviceModel</span></span>|<span data-ttu-id="c4869-147">Das Stammelement aller Windows Communication Foundation (WCF)-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="c4869-147">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4869-148">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c4869-148">Remarks</span></span>  
 <span data-ttu-id="c4869-149">WCF-Dienste werden in gehosteten Anwendungsdomänen (AppDomain) standardmäßig zusammen mit ASP.NET ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c4869-149">By default, WCF services run side-by-side with ASP.NET in hosted Application Domains (AppDomain).</span></span> <span data-ttu-id="c4869-150">Selbst wenn WCF und ASP.NET in derselben AppDomain gleichzeitig ausgeführt werden können, werden die WCF-Anforderungen nicht standardmäßig von der ASP.NET-HTTP-Pipeline verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="c4869-150">Even though WCF and ASP.NET can coexist in the same AppDomain, WCF requests are not processed by the ASP.NET HTTP Pipeline by default.</span></span> <span data-ttu-id="c4869-151">Folglich stehen einige Elemente der ASP.NET-Anwendungsplattform nicht für WCF-Dienste zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="c4869-151">As a result, several elements of the ASP.NET application platform are not available to WCF services.</span></span> <span data-ttu-id="c4869-152">Dazu gehören</span><span class="sxs-lookup"><span data-stu-id="c4869-152">These include</span></span>  
  
-   <span data-ttu-id="c4869-153">ASP.NET-Datei-/URL-Autorisierung</span><span class="sxs-lookup"><span data-stu-id="c4869-153">ASP.NET File/URL Authorization</span></span>  
  
-   <span data-ttu-id="c4869-154">ASP.NET-Identitätswechsel</span><span class="sxs-lookup"><span data-stu-id="c4869-154">ASP.NET Impersonation</span></span>  
  
-   <span data-ttu-id="c4869-155">Cookiebasierter Sitzungszustand</span><span class="sxs-lookup"><span data-stu-id="c4869-155">Cookie-based Session State</span></span>  
  
-   <span data-ttu-id="c4869-156">HttpContext.Current</span><span class="sxs-lookup"><span data-stu-id="c4869-156">HttpContext.Current</span></span>  
  
-   <span data-ttu-id="c4869-157">Pipeline-Erweiterbarkeit über benutzerdefiniertes HttpModule</span><span class="sxs-lookup"><span data-stu-id="c4869-157">Pipeline Extensibility via custom HttpModule</span></span>  
  
 <span data-ttu-id="c4869-158">Falls Ihre WCF-Dienste im ASP.NET-Kontext funktionieren müssen und nur über HTTP kommunizieren, können Sie den ASP.NET-Kompatibilitätsmodus von WCF verwenden.</span><span class="sxs-lookup"><span data-stu-id="c4869-158">If your WCF services need to function in the ASP.NET context, and communicate only over HTTP, you can use WCF’s ASP.NET compatibility mode.</span></span> <span data-ttu-id="c4869-159">Dieser Modus wird aktiviert, wenn das `aspNetCompatibilityEnabled`-Attribut auf Anwendungsebene auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c4869-159">This mode is turned on when the `aspNetCompatibilityEnabled` attribute is set to `true` at the application level.</span></span> <span data-ttu-id="c4869-160">Die Dienstimplementierungen müssen die Möglichkeit, im Kompatibilitätsmodus ausgeführt zu werden, mit der <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>-Klasse deklarieren.</span><span class="sxs-lookup"><span data-stu-id="c4869-160">Service implementations must declare their ability to run in compatibility mode using the <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> class.</span></span> <span data-ttu-id="c4869-161">Wenn der Kompatibilitätsmodus aktiviert ist,</span><span class="sxs-lookup"><span data-stu-id="c4869-161">When the compatibility mode is enabled,</span></span>  
  
-   <span data-ttu-id="c4869-162">wird vor der WCF-Autorisierung die ASP.NET-Datei-/URL-Autorisierung erzwungen.</span><span class="sxs-lookup"><span data-stu-id="c4869-162">ASP.NET File/URL Authorization is enforced prior to WCF authorization.</span></span> <span data-ttu-id="c4869-163">Eine Autorisierungsentscheidung basiert auf der Anforderungsidentität auf der Transportebene.</span><span class="sxs-lookup"><span data-stu-id="c4869-163">An authorization decision is based on the transport-level identity of the request.</span></span> <span data-ttu-id="c4869-164">Identitäten auf der Nachrichtenebene werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="c4869-164">Identities at the message level are ignored.</span></span>  
  
-   <span data-ttu-id="c4869-165">beginnen die WCF-Dienstvorgänge mit der Ausführung im ASP.NET-Identitätswechselkontext.</span><span class="sxs-lookup"><span data-stu-id="c4869-165">WCF service operations start to execute in the ASP.NET impersonation context.</span></span> <span data-ttu-id="c4869-166">Falls sowohl der ASP.NET-Identitätswechsel als auch der WCF-Identitätswechsel für einen bestimmten Dienst aktiviert sind, gilt der WCF-Identitätswechselkontext.</span><span class="sxs-lookup"><span data-stu-id="c4869-166">If both ASP.NET impersonation and WCF impersonation are enabled for a specific service, the WCF impersonation context applies.</span></span>  
  
-   <span data-ttu-id="c4869-167">kann HttpContext.Current im WCF-Dienstcode verwendet werden. Die Dienste werden daran gehindert, Nicht-HTTP-Endpunkte verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="c4869-167">HttpContext.Current can be used from WCF service code, and services are prevented from exposing non-HTTP endpoints.</span></span>  
  
-   <span data-ttu-id="c4869-168">werden die WCF-Anforderungen von der ASP.NET-Pipeline verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="c4869-168">WCF requests are processed by the ASP.NET pipeline.</span></span> <span data-ttu-id="c4869-169">HttpModules, die für eingehende Anforderungen konfiguriert wurden, können ebenfalls WCF-Anforderungen verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="c4869-169">HttpModules that have been configured to act on incoming requests can also process WCF requests.</span></span> <span data-ttu-id="c4869-170">Dazu gehören ASP.NET-Plattformkomponenten (z.&#160;B. <xref:System.Web.SessionState.SessionStateModule>) sowie benutzerdefinierte Drittanbietermodule.</span><span class="sxs-lookup"><span data-stu-id="c4869-170">These can include ASP.NET platform components (e.g., <xref:System.Web.SessionState.SessionStateModule>), as well as custom third party modules.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4869-171">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c4869-171">Example</span></span>  
 <span data-ttu-id="c4869-172">Das folgende Codebeispiel zeigt, wie der ASP-Kompatibilitätsmodus aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="c4869-172">The following code sample shows how to enable ASP Compatibility Mode.</span></span>  
  
## <a name="code"></a><span data-ttu-id="c4869-173">Code</span><span class="sxs-lookup"><span data-stu-id="c4869-173">Code</span></span>  
  
```xml  
<serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4869-174">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4869-174">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 [<span data-ttu-id="c4869-175">Hosting</span><span class="sxs-lookup"><span data-stu-id="c4869-175">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)  
 [<span data-ttu-id="c4869-176">WCF-Dienste und ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c4869-176">WCF Services and ASP.NET</span></span>](../../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)
