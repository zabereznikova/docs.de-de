---
title: '&lt;serviceMetadata&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2b4c3b4c-31d4-4908-a9b7-5bb411c221f2
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f4e88c6e5f03cef83e640fbca7434d10f82653f1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltservicemetadatagt"></a><span data-ttu-id="a505a-102">&lt;serviceMetadata&gt;</span><span class="sxs-lookup"><span data-stu-id="a505a-102">&lt;serviceMetadata&gt;</span></span>
<span data-ttu-id="a505a-103">Gibt die Veröffentlichung der Dienstmetadaten und der zugeordneten Informationen an.</span><span class="sxs-lookup"><span data-stu-id="a505a-103">Specifies the publication of service metadata and associated information.</span></span>  
  
<span data-ttu-id="a505a-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="a505a-104">\<system.serviceModel></span></span>  
<span data-ttu-id="a505a-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="a505a-105">\<behaviors></span></span>  
<span data-ttu-id="a505a-106">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="a505a-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="a505a-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="a505a-107">\<behavior></span></span>  
<span data-ttu-id="a505a-108">\<ServiceMetadata ></span><span class="sxs-lookup"><span data-stu-id="a505a-108">\<serviceMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a505a-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="a505a-109">Syntax</span></span>  
  
```xml
<serviceMetadata externalMetadataLocation="String"  
                 httpGetBinding="String" 
                 httpGetBindingConfiguration="String"  
                 httpGetEnabled="Boolean" 
                 httpGetUrl="String" 
                 httpsGetBinding="String" 
                 httpsGetBindingConfiguration="String"  
                 httpsGetEnabled="Boolean"   
                 httpsGetUrl="String"  
                 policyVersion="Policy12/Policy15" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a505a-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a505a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a505a-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a505a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a505a-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="a505a-112">Attributes</span></span>  
  
|<span data-ttu-id="a505a-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="a505a-113">Attribute</span></span>|<span data-ttu-id="a505a-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a505a-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a505a-115">externalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="a505a-115">externalMetadataLocation</span></span>|<span data-ttu-id="a505a-116">Ein URI, der den Speicherort einer WSDL-Datei enthält, die dem Benutzer als Antwort auf WSDL- und MEX-Anforderungen statt der automatisch generierten WSDL-Datei zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a505a-116">A Uri that contains the location of a WSDL file, which is returned to the user in response to WSDL and MEX requests instead of the auto-generated WSDL.</span></span> <span data-ttu-id="a505a-117">Wenn dieses Attribut nicht festgelegt wird, wird die WSDL-Standarddatei zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a505a-117">When this attribute is not set, the default WSDL is returned.</span></span> <span data-ttu-id="a505a-118">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a505a-118">The default is an empty string.</span></span>|  
|<span data-ttu-id="a505a-119">httpGetBinding</span><span class="sxs-lookup"><span data-stu-id="a505a-119">httpGetBinding</span></span>|<span data-ttu-id="a505a-120">Eine Zeichenfolge, die den Typ der Bindung angibt, die für den Abruf von Metadaten mit HTTP GET verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a505a-120">A string that specifies the type of the binding that will be used for metadata retrieval via HTTP GET.</span></span> <span data-ttu-id="a505a-121">Diese Einstellung ist optional.</span><span class="sxs-lookup"><span data-stu-id="a505a-121">This setting is optional.</span></span> <span data-ttu-id="a505a-122">Wenn nicht angegeben, werden die Standardbindungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="a505a-122">If it is not specified, the default bindings will be used.</span></span><br /><br /> <span data-ttu-id="a505a-123">Nur Bindungen mit inneren Bindungselementen, die <xref:System.ServiceModel.Channels.IReplyChannel> unterstützen, werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a505a-123">Only bindings with inner binding elements that support <xref:System.ServiceModel.Channels.IReplyChannel> will be supported.</span></span> <span data-ttu-id="a505a-124">Darüber hinaus muss die <xref:System.ServiceModel.Channels.MessageVersion>-Eigenschaft der Bindung <xref:System.ServiceModel.Channels.MessageVersion.None%2A> lauten.</span><span class="sxs-lookup"><span data-stu-id="a505a-124">Additionally, the <xref:System.ServiceModel.Channels.MessageVersion> property of the binding must be <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>|  
|<span data-ttu-id="a505a-125">httpGetBindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="a505a-125">httpGetBindingConfiguration</span></span>|<span data-ttu-id="a505a-126">Eine Zeichenfolge mit dem Namen der Bindung, die im `httpGetBinding`-Attribut angegeben ist, das auf die zusätzlichen Konfigurationsinformationen dieser Bindung verweist.</span><span class="sxs-lookup"><span data-stu-id="a505a-126">A string that sets the name of the binding that is specified in the `httpGetBinding` attribute, which references to the additional configuration information of this binding.</span></span> <span data-ttu-id="a505a-127">Der gleiche Name muss im Abschnitt `<bindings>` definiert werden.</span><span class="sxs-lookup"><span data-stu-id="a505a-127">The same name must be defined in the `<bindings>` section.</span></span>|  
|<span data-ttu-id="a505a-128">httpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="a505a-128">httpGetEnabled</span></span>|<span data-ttu-id="a505a-129">Ein boolescher Wert, der angibt, ob die Dienstmetadaten zum Abrufen anhand einer HTTP/Get-Anforderung veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a505a-129">A Boolean value that specifies whether to publish service metadata for retrieval using an HTTP/Get request.</span></span> <span data-ttu-id="a505a-130">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="a505a-130">The default is `false`.</span></span><br /><br /> <span data-ttu-id="a505a-131">Falls das httpGetUrl-Attribut nicht angegeben ist, ist die Adresse, an der die Metadaten veröffentlicht werden, die Dienstadresse plus ein "?wsdl".</span><span class="sxs-lookup"><span data-stu-id="a505a-131">If the httpGetUrl attribute is not specified, the address at which the metadata is published is the service address plus a "?wsdl".</span></span> <span data-ttu-id="a505a-132">Wenn die Dienstadresse beispielsweise "http://localhost:8080/CalculatorService" lautet, ist die HTTP/GET-Metadatenadresse "http://localhost:8080/CalculatorService? wsdl".</span><span class="sxs-lookup"><span data-stu-id="a505a-132">For example, if the service address is "http://localhost:8080/CalculatorService", the HTTP/Get metadata address is "http://localhost:8080/CalculatorService?wsdl".</span></span><br /><br /> <span data-ttu-id="a505a-133">Wenn diese Eigenschaft ist `false`, oder die Adresse des Diensts nicht auf HTTP oder HTTPS basiert "? Wsdl" ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a505a-133">If this property is `false`, or the address of the service is not based on HTTP or HTTPS, "?wsdl" is ignored.</span></span>|  
|<span data-ttu-id="a505a-134">httpGetUrl</span><span class="sxs-lookup"><span data-stu-id="a505a-134">httpGetUrl</span></span>|<span data-ttu-id="a505a-135">Ein URI, der die Adresse angibt, an der die Metadaten zum Abrufen anhand einer HTTP/Get-Anforderung veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="a505a-135">A Uri that specifies the address at which the metadata is published for retrieval using an HTTP/Get request.</span></span> <span data-ttu-id="a505a-136">Wenn ein relativer URI angegeben ist, wird er als relativ zur Basisadresse des Diensts behandelt.</span><span class="sxs-lookup"><span data-stu-id="a505a-136">If a relative Uri is specified it will be treated as relative to the service’s base address.</span></span>|  
|<span data-ttu-id="a505a-137">httpsGetBinding</span><span class="sxs-lookup"><span data-stu-id="a505a-137">httpsGetBinding</span></span>|<span data-ttu-id="a505a-138">Eine Zeichenfolge, die den Typ der Bindung angibt, die für den Abruf von Metadaten mit HTTPS GET verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a505a-138">A string that specifies the type of the binding that will be used for metadata retrieval via HTTPS GET.</span></span> <span data-ttu-id="a505a-139">Diese Einstellung ist optional.</span><span class="sxs-lookup"><span data-stu-id="a505a-139">This setting is optional.</span></span> <span data-ttu-id="a505a-140">Wenn nicht angegeben, werden die Standardbindungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="a505a-140">If it is not specified, the default bindings will be used.</span></span><br /><br /> <span data-ttu-id="a505a-141">Nur Bindungen mit inneren Bindungselementen, die <xref:System.ServiceModel.Channels.IReplyChannel> unterstützen, werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a505a-141">Only bindings with inner binding elements that support <xref:System.ServiceModel.Channels.IReplyChannel> will be supported.</span></span> <span data-ttu-id="a505a-142">Darüber hinaus muss die <xref:System.ServiceModel.Channels.MessageVersion>-Eigenschaft der Bindung <xref:System.ServiceModel.Channels.MessageVersion.None%2A> lauten.</span><span class="sxs-lookup"><span data-stu-id="a505a-142">Additionally, the <xref:System.ServiceModel.Channels.MessageVersion> property of the binding must be <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>|  
|<span data-ttu-id="a505a-143">httpsGetBindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="a505a-143">httpsGetBindingConfiguration</span></span>|<span data-ttu-id="a505a-144">Eine Zeichenfolge mit dem Namen der Bindung, die im `httpsGetBinding`-Attribut angegeben ist, das auf die zusätzlichen Konfigurationsinformationen dieser Bindung verweist.</span><span class="sxs-lookup"><span data-stu-id="a505a-144">A string that sets the name of the binding that is specified in the `httpsGetBinding` attribute, which references to the additional configuration information of this binding.</span></span> <span data-ttu-id="a505a-145">Der gleiche Name muss im Abschnitt `<bindings>` definiert werden.</span><span class="sxs-lookup"><span data-stu-id="a505a-145">The same name must be defined in the `<bindings>` section.</span></span>|  
|<span data-ttu-id="a505a-146">httpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="a505a-146">httpsGetEnabled</span></span>|<span data-ttu-id="a505a-147">Ein boolescher Wert, der angibt, ob die Dienstmetadaten zum Abrufen anhand einer HTTPS/Get-Anforderung veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a505a-147">A Boolean value that specifies whether to publish service metadata for retrieval using an HTTPS/Get request.</span></span> <span data-ttu-id="a505a-148">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="a505a-148">The default is `false`.</span></span><br /><br /> <span data-ttu-id="a505a-149">Falls das httpsGetUrl-Attribut nicht angegeben ist, ist die Adresse, an der die Metadaten veröffentlicht werden, die Dienstadresse plus ein "?wsdl".</span><span class="sxs-lookup"><span data-stu-id="a505a-149">If the httpsGetUrl attribute is not specified, the address at which the metadata is published is the service address plus a "?wsdl".</span></span> <span data-ttu-id="a505a-150">Wenn die Dienstadresse beispielsweise "https://localhost:8080/CalculatorService" lautet, ist die HTTP/GET-Metadatenadresse "https://localhost:8080/CalculatorService? wsdl".</span><span class="sxs-lookup"><span data-stu-id="a505a-150">For example, if the service address is "https://localhost:8080/CalculatorService", the HTTP/Get metadata address is "https://localhost:8080/CalculatorService?wsdl".</span></span><br /><br /> <span data-ttu-id="a505a-151">Wenn diese Eigenschaft ist `false`, oder die Adresse des Diensts nicht auf HTTP oder HTTPS basiert "? Wsdl" ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a505a-151">If this property is `false`, or the address of the service is not based on HTTP or HTTPS, "?wsdl" is ignored.</span></span>|  
|<span data-ttu-id="a505a-152">httpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="a505a-152">httpsGetUrl</span></span>|<span data-ttu-id="a505a-153">Ein URI, der die Adresse angibt, an der die Metadaten zum Abrufen anhand einer HTTPS/Get-Anforderung veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="a505a-153">A Uri that specifies the address at which the metadata is published for retrieval using an HTTPS/Get request.</span></span>|  
|<span data-ttu-id="a505a-154">policyVersion</span><span class="sxs-lookup"><span data-stu-id="a505a-154">policyVersion</span></span>|<span data-ttu-id="a505a-155">Eine Zeichenfolge, die angibt, welche Version der WS-Policy-Spezifikation verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a505a-155">A string that specifies the version of the WS-Policy specification being used.</span></span> <span data-ttu-id="a505a-156">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Description.PolicyVersion>.</span><span class="sxs-lookup"><span data-stu-id="a505a-156">This attribute is of type <xref:System.ServiceModel.Description.PolicyVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a505a-157">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a505a-157">Child Elements</span></span>  
 <span data-ttu-id="a505a-158">Keine</span><span class="sxs-lookup"><span data-stu-id="a505a-158">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a505a-159">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a505a-159">Parent Elements</span></span>  
  
|<span data-ttu-id="a505a-160">Element</span><span class="sxs-lookup"><span data-stu-id="a505a-160">Element</span></span>|<span data-ttu-id="a505a-161">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a505a-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a505a-162">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="a505a-162">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="a505a-163">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="a505a-163">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a505a-164">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a505a-164">Remarks</span></span>  
 <span data-ttu-id="a505a-165">Mit diesem Konfigurationselement können Sie die Metadatenveröffentlichungs-Funktionen eines Diensts steuern.</span><span class="sxs-lookup"><span data-stu-id="a505a-165">This configuration element allows you to control the metadata publishing features of a service.</span></span> <span data-ttu-id="a505a-166">Um ein unbeabsichtigtes Veröffentlichen von möglicherweise vertraulichen Dienstmetadaten zu vermeiden, wird mit der Standardkonfiguration für [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Dienste die Metadatenveröffentlichung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a505a-166">To prevent unintentional disclosure of potentially sensitive service metadata, the default configuration for [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services disables metadata publishing.</span></span> <span data-ttu-id="a505a-167">Dieses Verhalten ist in der Standardeinstellung sicher, bedeutet aber auch, dass man den zum Aufrufen des Diensts erforderlichen Clientcode nicht mithilfe eines Tools zum Importieren von Metadaten (wie Svcutil.exe) generieren kann. Dies ist nur dann möglich, wenn das Verhalten des Diensts zum Veröffentlichen von Metadaten in der Konfiguration explizit aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="a505a-167">This behavior is secure by default, but also means that you cannot use a metadata import tool (such as Svcutil.exe) to generate the client code required to call the service unless the service’s metadata publishing behavior is explicitly enabled in configuration.</span></span> <span data-ttu-id="a505a-168">Wenn Sie dieses Konfigurationselement verwenden, können Sie dieses Veröffentlichungsverhalten für Ihren Dienst aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a505a-168">Using this configuration element, you can enable this publishing behavior for your service.</span></span>  
  
 <span data-ttu-id="a505a-169">Ein ausführliches Beispiel zum Konfigurieren dieses Verhaltens finden Sie unter [Metadatenveröffentlichungsverhalten](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md).</span><span class="sxs-lookup"><span data-stu-id="a505a-169">For a detailed example of configuring this behavior, see [Metadata Publishing Behavior](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md).</span></span>  
  
 <span data-ttu-id="a505a-170">Das optionale `httpGetBinding`-Attribut und `httpsGetBinding`-Attribut ermöglichen Ihnen das Konfigurieren der zum Abrufen der Metadaten über HTTP-GET (oder HTTPS-GET) verwendeten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="a505a-170">The optional `httpGetBinding` and `httpsGetBinding` attributes allow you to configure the bindings used for metadata retrieval via HTTP GET (or HTTPS GET).</span></span> <span data-ttu-id="a505a-171">Wenn sie nicht festgelegt sind, werden die Standardbindungen (`HttpTransportBindingElement` für HTTP und `HttpsTransportBindingElement` für HTTPS) entsprechend zum Abrufen der Metadaten verwendet.</span><span class="sxs-lookup"><span data-stu-id="a505a-171">If they are not specified, the default bindings (`HttpTransportBindingElement`, in the case of HTTP and `HttpsTransportBindingElement`, in the case of HTTPS) are used for metadata retrieval as appropriate.</span></span> <span data-ttu-id="a505a-172">Beachten Sie, dass Sie diese Attribute nicht mit den integrierten WCF-Bindungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a505a-172">Notice that you cannot use these attributes with the built-in WCF bindings.</span></span> <span data-ttu-id="a505a-173">Nur Bindungen mit inneren Bindungselementen, die <xref:System.ServiceModel.Channels.IReplyChannel> unterstützen, werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a505a-173">Only bindings with inner binding elements that support <xref:System.ServiceModel.Channels.IReplyChannel> will be supported.</span></span> <span data-ttu-id="a505a-174">Darüber hinaus muss die <xref:System.ServiceModel.Channels.MessageVersion>-Eigenschaft der Bindung <xref:System.ServiceModel.Channels.MessageVersion.None%2A> lauten.</span><span class="sxs-lookup"><span data-stu-id="a505a-174">Additionally, the <xref:System.ServiceModel.Channels.MessageVersion> property of the binding must be <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>  
  
 <span data-ttu-id="a505a-175">Damit der Dienst möglichst gut vor böswilligen Benutzern geschützt wird, können Sie für die Übertragung den HTTPS-Mechanismus (SSL über HTTP) verwenden.</span><span class="sxs-lookup"><span data-stu-id="a505a-175">To reduce the exposure of a service to malicious users, it is possible to secure the transfer using the SSL over HTTP (HTTPS) mechanism.</span></span> <span data-ttu-id="a505a-176">Hierfür müssen Sie zunächst ein geeignetes X.509-Zertifikat an einen bestimmten Port des Computers, auf dem der Dienst gehostet wird, binden.</span><span class="sxs-lookup"><span data-stu-id="a505a-176">To do so, you must first bind a suitable X.509 certificate to a specific port on the computer that is hosting the service.</span></span> <span data-ttu-id="a505a-177">([!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)] [Arbeiten mit Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).) Fügen Sie dann dieses Element der Dienstkonfiguration hinzu, und legen Sie für das `httpsGetEnabled`-Attribut den Wert `true` fest.</span><span class="sxs-lookup"><span data-stu-id="a505a-177">([!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)] [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).) Second, add this element to the service configuration and set the `httpsGetEnabled` attribute to `true`.</span></span> <span data-ttu-id="a505a-178">Setzen Sie abschließend wie im folgenden Beispiel gezeigt das `httpsGetUrl`-Attribut auf den URL des Dienstmetadaten-Endpunkts:</span><span class="sxs-lookup"><span data-stu-id="a505a-178">Finally, set the `httpsGetUrl` attribute to the URL of the service metadata endpoint, as shown in the following example.</span></span>  
  
```xml
<behaviors>  
  <serviceBehaviors>  
    <behavior name="NewBehavior">  
      <serviceMetadata httpsGetEnabled="true"   
                       httpsGetUrl="https://myComputerName/myEndpoint" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="example"></a><span data-ttu-id="a505a-179">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a505a-179">Example</span></span>  
 <span data-ttu-id="a505a-180">Im folgende Beispiel konfigurieren Sie einen Dienst Metadaten verfügbar gemacht, mit der \<ServiceMetadata > Element.</span><span class="sxs-lookup"><span data-stu-id="a505a-180">The following example configure a service to expose metadata by using the \<serviceMetadata> element.</span></span> <span data-ttu-id="a505a-181">Es wird auch ein Endpunkt konfiguriert, mit dem der `IMetadataExchange`-Vertrag als Implementierung eines WS-MetadataExchange (MEX)-Protokolls verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="a505a-181">It also configures an endpoint to expose the `IMetadataExchange` contract as an implementation of a WS-MetadataExchange (MEX) protocol.</span></span> <span data-ttu-id="a505a-182">In dem Beispiel wird `mexHttpBinding` verwendet, eine benutzerfreundliche Standardbindung, die `wsHttpBinding` entspricht und für die der Sicherheitsmodus auf `None` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="a505a-182">The example uses the `mexHttpBinding`, which is a convenience standard binding that is equivalent to the `wsHttpBinding` with the security mode set to `None`.</span></span> <span data-ttu-id="a505a-183">Im Endpunkt wird eine relative Adresse von "mex" verwendet, die beim Auflösen der Dienstbasisadresse in einer Endpunktadresse von http://localhost/servicemodelsamples/service.svc/mex resultiert.</span><span class="sxs-lookup"><span data-stu-id="a505a-183">A relative address of "mex" is used in the endpoint, which when resolved against the services base address results in an endpoint address of http://localhost/servicemodelsamples/service.svc/mex.</span></span>  
  
```xml
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Microsoft.ServiceModel.Samples.CalculatorService" 
               behaviorConfiguration="CalculatorServiceBehavior">  
        <!-- This endpoint is exposed at the base address provided by the host: http://localhost/servicemodelsamples/service.svc -->  
        <endpoint address=""  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- The mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex   
             To expose the IMetadataExchange contract, you must enable the serviceMetadata behavior as demonstrated below. -->  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  

    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <!-- The serviceMetadata behavior publishes metadata through   
               the IMetadataExchange contract. When this behavior is   
               present, you can expose this contract through an endpoint   
               as shown above. Setting httpGetEnabled to true publishes   
               the service's WSDL at the <baseaddress>?wsdl  
               eg. http://localhost/servicemodelsamples/service.svc?wsdl -->  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a505a-184">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a505a-184">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceMetadataPublishingElement>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>  
 [<span data-ttu-id="a505a-185">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="a505a-185">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="a505a-186">Metadatenveröffentlichungsverhalten</span><span class="sxs-lookup"><span data-stu-id="a505a-186">Metadata Publishing Behavior</span></span>](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md)
