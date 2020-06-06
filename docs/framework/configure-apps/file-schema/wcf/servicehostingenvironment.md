---
title: <serviceHostingEnvironment>
ms.date: 03/30/2017
ms.assetid: 4f8a7c4f-e735-4987-979a-b74fcdae2652
ms.openlocfilehash: 165dbed1b78d00f8d4dd3e482b9fee8a23db60da
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399615"
---
# \<serviceHostingEnvironment>
<span data-ttu-id="d863e-101">Dieses Element definiert den Typ, der von der Diensthostingumgebung für einen bestimmten Transport instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="d863e-101">This element defines the type the service hosting environment instantiates for a particular transport.</span></span> <span data-ttu-id="d863e-102">Falls dieses Element leer ist, wird der Standardtyp verwendet.</span><span class="sxs-lookup"><span data-stu-id="d863e-102">If this element is empty, the default type is used.</span></span> <span data-ttu-id="d863e-103">Dieses Element kann nur über die Anwendungskonfigurationsdatei bzw. die Computerkonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d863e-103">This element can only be used at the application or machine level configuration files.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceHostingEnvironment>**  
  
## <a name="syntax"></a><span data-ttu-id="d863e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d863e-104">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment aspNetCompatibilityEnabled="Boolean"
                           minFreeMemoryPercentageToActivateService="Integer"
                           multipleSiteBindingsEnabled="Boolean">
  <baseAddressPrefixFilters>
    <add prefix="string" />
  </baseAddressPrefixFilters>
  <serviceActivations>
    <add factory="String"
         service="String" />
  </serviceActivations>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d863e-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d863e-105">Attributes and Elements</span></span>  
 <span data-ttu-id="d863e-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d863e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d863e-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="d863e-107">Attributes</span></span>  
  
|<span data-ttu-id="d863e-108">attribute</span><span class="sxs-lookup"><span data-stu-id="d863e-108">Attribute</span></span>|<span data-ttu-id="d863e-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d863e-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d863e-110">aspNetCompatibilityEnabled</span><span class="sxs-lookup"><span data-stu-id="d863e-110">aspNetCompatibilityEnabled</span></span>|<span data-ttu-id="d863e-111">Ein boolescher Wert, der angibt, ob der ASP.NET-Kompatibilitätsmodus für die aktuelle Anwendung aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="d863e-111">A Boolean value indicating whether the ASP.NET compatibility mode has been turned on for the current application.</span></span> <span data-ttu-id="d863e-112">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="d863e-112">The default is `false`.</span></span><br /><br /> <span data-ttu-id="d863e-113">Wenn dieses Attribut auf festgelegt ist `true` , werden Anforderungen an Windows Communication Foundation (WCF)-Dienste über die ASP.NET-HTTP-Pipeline geleitet, und die Kommunikation über nicht-HTTP-Protokolle ist unzulässig.</span><span class="sxs-lookup"><span data-stu-id="d863e-113">When this attribute is set to `true`, requests to Windows Communication Foundation (WCF) services flow through the ASP.NET HTTP pipeline, and communication over non-HTTP protocols is prohibited.</span></span> <span data-ttu-id="d863e-114">Weitere Informationen finden Sie unter [WCF-Dienste und ASP.net](../../../wcf/feature-details/wcf-services-and-aspnet.md).</span><span class="sxs-lookup"><span data-stu-id="d863e-114">For more information, see [WCF Services and ASP.NET](../../../wcf/feature-details/wcf-services-and-aspnet.md).</span></span>|  
|<span data-ttu-id="d863e-115">minFreeMemoryPercentageToActivateService</span><span class="sxs-lookup"><span data-stu-id="d863e-115">minFreeMemoryPercentageToActivateService</span></span>|<span data-ttu-id="d863e-116">Eine ganze Zahl, die den minimalen freien Speicherplatz angibt, der für das System verfügbar sein sollte, bevor ein WCF-Dienst aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="d863e-116">An integer that specifies the minimum amount of free memory that should be available to the system, before a WCF service can be activated.</span></span> <span data-ttu-id="d863e-117">**Vorsicht:**  Wenn Sie dieses Attribut zusammen mit teilweiser Vertrauenswürdigkeit in der Datei "Web. config" eines WCF-Diensts angeben, führt dies zu einer, <xref:System.Security.SecurityException> Wenn der Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d863e-117">**Caution:**  Specifying this attribute along with partial trust in the web.config file of a WCF service will result in a <xref:System.Security.SecurityException> when the service is run.</span></span>|  
|<span data-ttu-id="d863e-118">multipleSiteBindingsEnabled</span><span class="sxs-lookup"><span data-stu-id="d863e-118">multipleSiteBindingsEnabled</span></span>|<span data-ttu-id="d863e-119">Ein boolescher Wert, der angibt, ob mehrere IIS-Bindungen pro Website aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="d863e-119">A Boolean value that specifies whether multiple IIS bindings per site is enabled.</span></span><br /><br /> <span data-ttu-id="d863e-120">IIS besteht aus Websites, die als Container für virtuelle Anwendungen fungieren, die virtuelle Verzeichnisse enthalten.</span><span class="sxs-lookup"><span data-stu-id="d863e-120">IIS consists of web sites, which are containers for virtual applications containing virtual directories.</span></span> <span data-ttu-id="d863e-121">Auf die Anwendung auf einer Website kann über eine oder mehrere IIS-Bindungen zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="d863e-121">The application in a site can be accessed through one or more IIS binding.</span></span> <span data-ttu-id="d863e-122">IIS-Bindungen stellen zwei Angaben bereit: ein Bindungsprotokoll und Bindungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="d863e-122">An IIS binding provides two pieces of information: a binding protocol and binding information.</span></span> <span data-ttu-id="d863e-123">Das Bindungsprotokoll definiert das Schema, das für die Kommunikation verwendet wird, und die Bindungsinformationen dienen dem Zugriff auf die Website.</span><span class="sxs-lookup"><span data-stu-id="d863e-123">Binding protocol defines the scheme over which communication occurs, and binding information is the information used to access the site.</span></span> <span data-ttu-id="d863e-124">Ein Beispiel für ein Bindungsprotokoll kann HTTP sein, wohingegen Bindungsinformationen eine IP-Adresse, einen Port, einen Hostheader usw. enthalten können.</span><span class="sxs-lookup"><span data-stu-id="d863e-124">An example of a binding protocol can be HTTP, whereas binding information can contain an IP address, Port, host header, etc.</span></span><br /><br /> <span data-ttu-id="d863e-125">IIS unterstützt die Angabe mehrerer IIS-Bindungen pro Website, was zu mehreren Basisadressen pro Schema führt.</span><span class="sxs-lookup"><span data-stu-id="d863e-125">IIS supports specifying multiple IIS bindings per site, which results in multiple base addresses per scheme.</span></span> <span data-ttu-id="d863e-126">Ein Windows Communication Foundation (WCF)-Dienst, der unter einer Site gehostet wird, ermöglicht jedoch nur das Binden an eine BaseAddress pro Schema.</span><span class="sxs-lookup"><span data-stu-id="d863e-126">However, a Windows Communication Foundation (WCF) service hosted under a site allows binding to only one baseAddress per scheme.</span></span><br /><br /> <span data-ttu-id="d863e-127">Um mehrere IIS-Bindungen pro Website für einen Windows Communication Foundation (WCF)-Dienst zu aktivieren, legen Sie dieses Attribut auf fest `true` .</span><span class="sxs-lookup"><span data-stu-id="d863e-127">To enable multiple IIS bindings per site for a Windows Communication Foundation (WCF) service, set this attribute to `true`.</span></span> <span data-ttu-id="d863e-128">Beachten Sie, dass mehrere Bindungen pro Website nur für das HTTP-Protokoll unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="d863e-128">Notice that multiple site binding is supported only for the HTTP protocol.</span></span> <span data-ttu-id="d863e-129">Die Adresse der Endpunkte in der Konfigurationsdatei muss ein vollständiger URI sein.</span><span class="sxs-lookup"><span data-stu-id="d863e-129">The address of endpoints in the configuration file needs to be a complete URI.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d863e-130">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d863e-130">Child Elements</span></span>  
  
|<span data-ttu-id="d863e-131">Element</span><span class="sxs-lookup"><span data-stu-id="d863e-131">Element</span></span>|<span data-ttu-id="d863e-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d863e-132">Description</span></span>|  
|-------------|-----------------|  
|[\<baseAddressPrefixFilters>](baseaddressprefixfilters.md)|<span data-ttu-id="d863e-133">Eine Auflistung der Konfigurationselemente, die den Präfixfilter für die vom Diensthost verwendeten Basisadressen angeben.</span><span class="sxs-lookup"><span data-stu-id="d863e-133">A collection of configuration elements that specify prefix filters for the base addresses used by the service host.</span></span>|  
|[\<serviceActivations>](serviceactivations.md)|<span data-ttu-id="d863e-134">Ein Konfigurationsabschnitt, der Aktivierungseinstellungen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="d863e-134">A configuration section that describes activation settings.</span></span>|  
|[\<transportConfigurationTypes>](transportconfigurationtypes.md)|<span data-ttu-id="d863e-135">Eine Auflistung der Konfigurationselemente, die den Typ eines bestimmten Transports identifizieren.</span><span class="sxs-lookup"><span data-stu-id="d863e-135">A collection of configuration elements that identify the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d863e-136">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d863e-136">Parent Elements</span></span>  
  
|<span data-ttu-id="d863e-137">Element</span><span class="sxs-lookup"><span data-stu-id="d863e-137">Element</span></span>|<span data-ttu-id="d863e-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d863e-138">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d863e-139">serviceModel</span><span class="sxs-lookup"><span data-stu-id="d863e-139">serviceModel</span></span>|<span data-ttu-id="d863e-140">Das Stammelement aller Windows Communication Foundation (WCF)-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="d863e-140">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d863e-141">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d863e-141">Remarks</span></span>  
 <span data-ttu-id="d863e-142">WCF-Dienste werden in gehosteten Anwendungsdomänen (AppDomain) standardmäßig zusammen mit ASP.NET ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d863e-142">By default, WCF services run side-by-side with ASP.NET in hosted Application Domains (AppDomain).</span></span> <span data-ttu-id="d863e-143">Selbst wenn WCF und ASP.NET in derselben AppDomain gleichzeitig ausgeführt werden können, werden die WCF-Anforderungen nicht standardmäßig von der ASP.NET-HTTP-Pipeline verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="d863e-143">Even though WCF and ASP.NET can coexist in the same AppDomain, WCF requests are not processed by the ASP.NET HTTP Pipeline by default.</span></span> <span data-ttu-id="d863e-144">Folglich stehen einige Elemente der ASP.NET-Anwendungsplattform nicht für WCF-Dienste zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="d863e-144">As a result, several elements of the ASP.NET application platform are not available to WCF services.</span></span> <span data-ttu-id="d863e-145">Dies sind:</span><span class="sxs-lookup"><span data-stu-id="d863e-145">These include</span></span>  
  
- <span data-ttu-id="d863e-146">ASP.NET-Datei-/URL-Autorisierung</span><span class="sxs-lookup"><span data-stu-id="d863e-146">ASP.NET File/URL Authorization</span></span>  
  
- <span data-ttu-id="d863e-147">ASP.NET-Identitätswechsel</span><span class="sxs-lookup"><span data-stu-id="d863e-147">ASP.NET Impersonation</span></span>  
  
- <span data-ttu-id="d863e-148">Cookiebasierter Sitzungszustand</span><span class="sxs-lookup"><span data-stu-id="d863e-148">Cookie-based Session State</span></span>  
  
- <span data-ttu-id="d863e-149">HttpContext.Current</span><span class="sxs-lookup"><span data-stu-id="d863e-149">HttpContext.Current</span></span>  
  
- <span data-ttu-id="d863e-150">Pipeline-Erweiterbarkeit über benutzerdefiniertes HttpModule</span><span class="sxs-lookup"><span data-stu-id="d863e-150">Pipeline Extensibility via custom HttpModule</span></span>  
  
 <span data-ttu-id="d863e-151">Falls Ihre WCF-Dienste im ASP.NET-Kontext funktionieren müssen und nur über HTTP kommunizieren, können Sie den ASP.NET-Kompatibilitätsmodus von WCF verwenden.</span><span class="sxs-lookup"><span data-stu-id="d863e-151">If your WCF services need to function in the ASP.NET context, and communicate only over HTTP, you can use WCF’s ASP.NET compatibility mode.</span></span> <span data-ttu-id="d863e-152">Dieser Modus wird aktiviert, wenn das `aspNetCompatibilityEnabled`-Attribut auf Anwendungsebene auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="d863e-152">This mode is turned on when the `aspNetCompatibilityEnabled` attribute is set to `true` at the application level.</span></span> <span data-ttu-id="d863e-153">Die Dienstimplementierungen müssen die Möglichkeit, im Kompatibilitätsmodus ausgeführt zu werden, mit der <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>-Klasse deklarieren.</span><span class="sxs-lookup"><span data-stu-id="d863e-153">Service implementations must declare their ability to run in compatibility mode using the <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> class.</span></span> <span data-ttu-id="d863e-154">Wenn der Kompatibilitätsmodus aktiviert ist,</span><span class="sxs-lookup"><span data-stu-id="d863e-154">When the compatibility mode is enabled,</span></span>  
  
- <span data-ttu-id="d863e-155">wird vor der WCF-Autorisierung die ASP.NET-Datei-/URL-Autorisierung erzwungen.</span><span class="sxs-lookup"><span data-stu-id="d863e-155">ASP.NET File/URL Authorization is enforced prior to WCF authorization.</span></span> <span data-ttu-id="d863e-156">Eine Autorisierungsentscheidung basiert auf der Anforderungsidentität auf der Transportebene.</span><span class="sxs-lookup"><span data-stu-id="d863e-156">An authorization decision is based on the transport-level identity of the request.</span></span> <span data-ttu-id="d863e-157">Identitäten auf der Nachrichtenebene werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="d863e-157">Identities at the message level are ignored.</span></span>  
  
- <span data-ttu-id="d863e-158">beginnen die WCF-Dienstvorgänge mit der Ausführung im ASP.NET-Identitätswechselkontext.</span><span class="sxs-lookup"><span data-stu-id="d863e-158">WCF service operations start to execute in the ASP.NET impersonation context.</span></span> <span data-ttu-id="d863e-159">Falls sowohl der ASP.NET-Identitätswechsel als auch der WCF-Identitätswechsel für einen bestimmten Dienst aktiviert sind, gilt der WCF-Identitätswechselkontext.</span><span class="sxs-lookup"><span data-stu-id="d863e-159">If both ASP.NET impersonation and WCF impersonation are enabled for a specific service, the WCF impersonation context applies.</span></span>  
  
- <span data-ttu-id="d863e-160">kann HttpContext.Current im WCF-Dienstcode verwendet werden. Die Dienste werden daran gehindert, Nicht-HTTP-Endpunkte verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="d863e-160">HttpContext.Current can be used from WCF service code, and services are prevented from exposing non-HTTP endpoints.</span></span>  
  
- <span data-ttu-id="d863e-161">werden die WCF-Anforderungen von der ASP.NET-Pipeline verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="d863e-161">WCF requests are processed by the ASP.NET pipeline.</span></span> <span data-ttu-id="d863e-162">HttpModules, die für eingehende Anforderungen konfiguriert wurden, können ebenfalls WCF-Anforderungen verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d863e-162">HttpModules that have been configured to act on incoming requests can also process WCF requests.</span></span> <span data-ttu-id="d863e-163">Dazu gehören ASP.NET-Plattformkomponenten (z.&#160;B. <xref:System.Web.SessionState.SessionStateModule>) sowie benutzerdefinierte Drittanbietermodule.</span><span class="sxs-lookup"><span data-stu-id="d863e-163">These can include ASP.NET platform components (e.g., <xref:System.Web.SessionState.SessionStateModule>), as well as custom third party modules.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d863e-164">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d863e-164">Example</span></span>  
 <span data-ttu-id="d863e-165">Das folgende Codebeispiel zeigt, wie der ASP-Kompatibilitätsmodus aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="d863e-165">The following code sample shows how to enable ASP Compatibility Mode.</span></span>  
  
## <a name="code"></a><span data-ttu-id="d863e-166">Code</span><span class="sxs-lookup"><span data-stu-id="d863e-166">Code</span></span>  
  
```xml  
<serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>
```  
  
## <a name="see-also"></a><span data-ttu-id="d863e-167">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d863e-167">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="d863e-168">Hosting</span><span class="sxs-lookup"><span data-stu-id="d863e-168">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
- [<span data-ttu-id="d863e-169">WCF-Dienste und ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d863e-169">WCF Services and ASP.NET</span></span>](../../../wcf/feature-details/wcf-services-and-aspnet.md)
