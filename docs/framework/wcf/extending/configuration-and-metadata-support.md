---
title: Konfiguration und Metadatenunterstützung
ms.date: 03/30/2017
ms.assetid: 27c240cb-8cab-472c-87f8-c864f4978758
ms.openlocfilehash: fe7de6fddeccbc83bc81eea69c27c7da5df5c8c3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257996"
---
# <a name="configuration-and-metadata-support"></a><span data-ttu-id="336c7-102">Konfiguration und Metadatenunterstützung</span><span class="sxs-lookup"><span data-stu-id="336c7-102">Configuration and Metadata Support</span></span>

<span data-ttu-id="336c7-103">In diesem Thema wird beschrieben, wie Konfigurations- und Metadatenunterstützung für Bindungen und Bindungselemente aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="336c7-103">This topic describes how to enable configuration and metadata support for bindings and binding elements.</span></span>  
  
## <a name="overview-of-configuration-and-metadata"></a><span data-ttu-id="336c7-104">Überblick über Konfiguration und Metadaten</span><span class="sxs-lookup"><span data-stu-id="336c7-104">Overview of Configuration and Metadata</span></span>  

 <span data-ttu-id="336c7-105">In diesem Thema werden die folgenden Aufgaben erläutert, bei denen es sich um optionale Elemente 1, 2 und 4 in der Aufgabenliste zum [entwickeln von Kanälen](developing-channels.md) handelt.</span><span class="sxs-lookup"><span data-stu-id="336c7-105">This topic discusses the following tasks, which are optional items 1, 2, and 4 in the [Developing Channels](developing-channels.md) task list.</span></span>  
  
- <span data-ttu-id="336c7-106">Aktivierung von Unterstützung der Konfigurationsdatei für ein Bindungselement.</span><span class="sxs-lookup"><span data-stu-id="336c7-106">Enabling configuration file support for a binding element.</span></span>  
  
- <span data-ttu-id="336c7-107">Aktivierung von Unterstützung der Konfigurationsdatei für eine Bindung.</span><span class="sxs-lookup"><span data-stu-id="336c7-107">Enabling configuration file support for a binding.</span></span>  
  
- <span data-ttu-id="336c7-108">Export von WSDL und Richtlinienassertionen für ein Bindungselement.</span><span class="sxs-lookup"><span data-stu-id="336c7-108">Exporting WSDL and policy assertions for a binding element.</span></span>  
  
- <span data-ttu-id="336c7-109">Identifizierung von WSDL und Richtlinienassertionen für das Einsetzen und Konfigurieren der Bindung oder des Bindungselements.</span><span class="sxs-lookup"><span data-stu-id="336c7-109">Identifying WSDL and policy assertions to insert and configure your binding or binding element.</span></span>  
  
 <span data-ttu-id="336c7-110">Weitere Informationen zum Erstellen von benutzerdefinierten Bindungen und Bindungs Elementen finden Sie unter [Erstellen von User-Defined Bindungen](creating-user-defined-bindings.md) und [Erstellen eines BindingElement](creating-a-bindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="336c7-110">For information about creating user-defined bindings and binding elements, see [Creating User-Defined Bindings](creating-user-defined-bindings.md) and [Creating a BindingElement](creating-a-bindingelement.md), respectively.</span></span>  
  
## <a name="adding-configuration-support"></a><span data-ttu-id="336c7-111">Hinzufügen von Konfigurationsunterstützung</span><span class="sxs-lookup"><span data-stu-id="336c7-111">Adding Configuration Support</span></span>  

 <span data-ttu-id="336c7-112">Zum Aktivieren der Konfigurationsdateiunterstützung für einen Kanal müssen Sie zwei Konfigurationsabschnitte implementieren, <xref:System.ServiceModel.Configuration.BindingElementExtensionElement?displayProperty=nameWithType>, wodurch die Konfigurationsunterstützung für Bindungselemente aktiviert wird, und das <xref:System.ServiceModel.Configuration.StandardBindingElement?displayProperty=nameWithType> sowie das <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602?displayProperty=nameWithType> implementieren, wodurch die Konfigurationsunterstützung für Bindungen aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="336c7-112">To enable configuration file support for a channel, you must implement two configuration sections, <xref:System.ServiceModel.Configuration.BindingElementExtensionElement?displayProperty=nameWithType>, which enables configuration support for binding elements, and the <xref:System.ServiceModel.Configuration.StandardBindingElement?displayProperty=nameWithType> and <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602?displayProperty=nameWithType>, which enable configuration support for bindings.</span></span>  
  
 <span data-ttu-id="336c7-113">Eine einfachere Möglichkeit hierfür ist die Verwendung des [ConfigurationCodeGenerator](../samples/configurationcodegenerator.md) -Beispiel Tools, um Konfigurations Code für Ihre Bindungen und Bindungs Elemente zu generieren.</span><span class="sxs-lookup"><span data-stu-id="336c7-113">An easier way to do this is to use the [ConfigurationCodeGenerator](../samples/configurationcodegenerator.md) sample tool to generate configuration code for your bindings and binding elements.</span></span>  
  
### <a name="extending-bindingelementextensionelement"></a><span data-ttu-id="336c7-114">Erweitern von BindingElementExtensionElement</span><span class="sxs-lookup"><span data-stu-id="336c7-114">Extending BindingElementExtensionElement</span></span>  

 <span data-ttu-id="336c7-115">Der folgende Beispielcode stammt aus dem " [Transport: UDP](../samples/transport-udp.md) "-Beispiel.</span><span class="sxs-lookup"><span data-stu-id="336c7-115">The following example code is taken from the [Transport: UDP](../samples/transport-udp.md) sample.</span></span> <span data-ttu-id="336c7-116">`UdpTransportElement` ist ein <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>, das `UdpTransportBindingElement` für das Konfigurationssystem verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="336c7-116">The `UdpTransportElement` is a <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> that exposes `UdpTransportBindingElement` to the configuration system.</span></span> <span data-ttu-id="336c7-117">Mit wenigen grundlegenden Überschreibungen definiert das Beispiel den Konfigurationsabschnittsnamen, den Typ des Bindungselements und wie das Bindungselement erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="336c7-117">With a few basic overrides, the sample defines the configuration section name, the type of the binding element and how to create the binding element.</span></span> <span data-ttu-id="336c7-118">Benutzer können dann wie folgt den Erweiterungsabschnitt in einer Konfigurationsdatei registrieren.</span><span class="sxs-lookup"><span data-stu-id="336c7-118">Users can then register the extension section in a configuration file as follows.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <extensions>  
      <bindingElementExtensions>  
      <add name="udpTransport" type="Microsoft.ServiceModel.Samples.UdpTransportElement, UdpTransport" />  
      </bindingElementExtensions>  
    </extensions>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="336c7-119">Auf die Erweiterung kann von benutzerdefinierten Bindungen verwiesen werden, um UDP als Transport zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="336c7-119">The extension can be referenced from custom bindings to use UDP as the transport.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <customBinding>  
       <binding configurationName="UdpCustomBinding">  
         <udpTransport/>  
       </binding>  
      </customBinding>  
    </bindings>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="adding-configuration-for-a-binding"></a><span data-ttu-id="336c7-120">Hinzufügen einer Konfiguration für eine Bindung</span><span class="sxs-lookup"><span data-stu-id="336c7-120">Adding Configuration for a Binding</span></span>  

 <span data-ttu-id="336c7-121">Der Abschnitt `SampleProfileUdpBindingCollectionElement` ist ein <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602>, das die `SampleProfileUdpBinding` für das Konfigurationssystem verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="336c7-121">The section `SampleProfileUdpBindingCollectionElement` is a <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> that exposes `SampleProfileUdpBinding` to the configuration system.</span></span> <span data-ttu-id="336c7-122">Dem `SampleProfileUdpBindingConfigurationElement`, das sich von <xref:System.ServiceModel.Configuration.StandardBindingElement> herleitet, wird der Großteil der Implementierung übertragen.</span><span class="sxs-lookup"><span data-stu-id="336c7-122">The bulk of the implementation is delegated to the `SampleProfileUdpBindingConfigurationElement`, which derives from <xref:System.ServiceModel.Configuration.StandardBindingElement>.</span></span> <span data-ttu-id="336c7-123">Der `SampleProfileUdpBindingConfigurationElement` verfügt über Eigenschaften, die den Eigenschaften für entsprechen `SampleProfileUdpBinding` , und Funktionen, die der Bindung zugeordnet werden sollen `ConfigurationElement` .</span><span class="sxs-lookup"><span data-stu-id="336c7-123">The `SampleProfileUdpBindingConfigurationElement` has properties that correspond to the properties on `SampleProfileUdpBinding`, and functions to map from the `ConfigurationElement` binding.</span></span> <span data-ttu-id="336c7-124">Schließlich wird die `OnApplyConfiguration`-Methode in der `SampleProfileUdpBinding` überschrieben. Dies wird im folgenden Beispielcode veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="336c7-124">Finally, the `OnApplyConfiguration` method is overridden in the `SampleProfileUdpBinding`, as shown in the following sample code.</span></span>  
  
```csharp
protected override void OnApplyConfiguration(string configurationName)  
{  
            if (binding == null)  
                throw new ArgumentNullException("binding");  
  
            if (binding.GetType() != typeof(SampleProfileUdpBinding))  
            {  
                var expectedType = typeof(SampleProfileUdpBinding).AssemblyQualifiedName;
                var typePassedIn = binding.GetType().AssemblyQualifiedName;
                throw new ArgumentException($"Invalid type for binding. Expected type: {expectedType}. Type passed in: {typePassedIn}.");  
            }  
            SampleProfileUdpBinding udpBinding = (SampleProfileUdpBinding)binding;  
  
            udpBinding.OrderedSession = this.OrderedSession;  
            udpBinding.ReliableSessionEnabled = this.ReliableSessionEnabled;  
            udpBinding.SessionInactivityTimeout = this.SessionInactivityTimeout;  
            if (this.ClientBaseAddress != null)  
                   udpBinding.ClientBaseAddress = ClientBaseAddress;  
}  
```  
  
 <span data-ttu-id="336c7-125">Um diesen Handler mit dem Konfigurationssystem zu registrieren, fügen Sie der relevanten Konfigurationsdatei den folgenden Abschnitt hinzu.</span><span class="sxs-lookup"><span data-stu-id="336c7-125">To register this handler with the configuration system, add the following section to the relevant configuration file.</span></span>  
  
```xml  
<configuration>  
  <configSections>  
     <sectionGroup name="system.serviceModel">  
         <sectionGroup name="bindings">  
                 <section name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport" />  
         </sectionGroup>  
     </sectionGroup>  
  </configSections>  
</configuration>  
```  
  
 <span data-ttu-id="336c7-126">Anschließend kann im Konfigurations Abschnitt auf Sie verwiesen werden [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) .</span><span class="sxs-lookup"><span data-stu-id="336c7-126">It can then be referenced from the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) configuration section.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <endpoint configurationName="calculator"  
                address="soap.udp://localhost:8001/"
                bindingConfiguration="CalculatorServer"  
                binding="sampleProfileUdpBinding"
                contract= "Microsoft.ServiceModel.Samples.ICalculatorContract">  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="adding-metadata-support-for-a-binding-element"></a><span data-ttu-id="336c7-127">Hinzufügen von Metadatenunterstützung für ein Bindungselement</span><span class="sxs-lookup"><span data-stu-id="336c7-127">Adding Metadata Support for a Binding Element</span></span>  

 <span data-ttu-id="336c7-128">Um einen Kanal in ein Metadatensystem zu integrieren, muss dieser sowohl den Import als auch den Export von Richtlinien unterstützen.</span><span class="sxs-lookup"><span data-stu-id="336c7-128">To integrate a channel into the metadata system, it must support both the import and export of policy.</span></span> <span data-ttu-id="336c7-129">Dadurch können Tools wie z. b. das [Service Model Metadata Utility-Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) Clients des Bindungs Elements generieren.</span><span class="sxs-lookup"><span data-stu-id="336c7-129">This allows tools such as [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to generate clients of the binding element.</span></span>  
  
### <a name="adding-wsdl-support"></a><span data-ttu-id="336c7-130">Hinzufügen von WSDL-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="336c7-130">Adding WSDL Support</span></span>  

 <span data-ttu-id="336c7-131">Das Transportbindungselement in einer Bindung ist für den Export und Import von Adressierungsinformationen in/zu Metadaten verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="336c7-131">The transport binding element in a binding is responsible for exporting and importing addressing information in metadata.</span></span> <span data-ttu-id="336c7-132">Bei der Nutzung einer SOAP-Bindung sollte das Transportbindungselement ebenfalls einen korrekten Transport-URI in die Metadaten exportieren.</span><span class="sxs-lookup"><span data-stu-id="336c7-132">When using a SOAP binding, the transport binding element should also export a correct transport URI in metadata.</span></span> <span data-ttu-id="336c7-133">Der folgende Beispielcode stammt aus dem " [Transport: UDP](../samples/transport-udp.md) "-Beispiel.</span><span class="sxs-lookup"><span data-stu-id="336c7-133">The following example code is taken from the [Transport: UDP](../samples/transport-udp.md) sample.</span></span>  
  
#### <a name="wsdl-export"></a><span data-ttu-id="336c7-134">WSDL-Export</span><span class="sxs-lookup"><span data-stu-id="336c7-134">WSDL Export</span></span>  

 <span data-ttu-id="336c7-135">Um Adressierungs Informationen zu exportieren, `UdpTransportBindingElement` implementiert das die- <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="336c7-135">To export addressing information, the `UdpTransportBindingElement` implements the <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="336c7-136">Die <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A?displayProperty=nameWithType>-Methode fügt dem WSDL-Port die richtigen Adressierungsinformationen hinzu.</span><span class="sxs-lookup"><span data-stu-id="336c7-136">The <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A?displayProperty=nameWithType> method adds the correct addressing information to the WSDL port.</span></span>  
  
```csharp  
if (context.WsdlPort != null)  
{  
    AddAddressToWsdlPort(context.WsdlPort, context.Endpoint.Address, encodingBindingElement.MessageVersion.Addressing);  
}  
```  
  
 <span data-ttu-id="336c7-137">Die `UdpTransportBindingElement`-Implementierung der <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A>-Methode exportiert ebenfalls einen Transport-URI, wenn der Endpunkt eine SOAP-Bindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="336c7-137">The `UdpTransportBindingElement` implementation of the <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A> method also exports a transport URI when the endpoint uses a SOAP binding:</span></span>  
  
```csharp  
WsdlNS.SoapBinding soapBinding = GetSoapBinding(context, exporter);  
if (soapBinding != null)  
{  
    soapBinding.Transport = UdpPolicyStrings.UdpNamespace;  
}  
```  
  
#### <a name="wsdl-import"></a><span data-ttu-id="336c7-138">WSDL-Import</span><span class="sxs-lookup"><span data-stu-id="336c7-138">WSDL Import</span></span>  

 <span data-ttu-id="336c7-139">Um das WSDL-Importsystem auf die Handhabung des Imports von Adressen zu erweitern, fügen Sie die folgende Konfiguration zur Konfigurationsdatei für Svcutil.exe hinzu (wie in der Datei Svcutil.exe.config gezeigt):</span><span class="sxs-lookup"><span data-stu-id="336c7-139">To extend the WSDL import system to handle importing the addresses, add the following configuration to the configuration file for Svcutil.exe as shown in the Svcutil.exe.config file:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <metadata>  
        <wsdlImporters>  
          <extension type=" Microsoft.ServiceModel.Samples.UdpBindingElementImporter, UdpTransport" />  
        </wsdlImporters>  
      </metadata>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="336c7-140">Bei der Ausführung von "Svcutil.exe" gibt es zwei Optionen, um "Svcutil.exe" dazu zu bewegen, die WSDL-Importerweiterungen zu laden:</span><span class="sxs-lookup"><span data-stu-id="336c7-140">When running Svcutil.exe, there are two options for getting Svcutil.exe to load the WSDL import extensions:</span></span>  
  
1. <span data-ttu-id="336c7-141">Zeigen Sie Svcutil.exe mithilfe von/svcutilConfig auf die Konfigurationsdatei \<file> .</span><span class="sxs-lookup"><span data-stu-id="336c7-141">Point Svcutil.exe to the configuration file using the /SvcutilConfig:\<file>.</span></span>  
  
2. <span data-ttu-id="336c7-142">Fügen Sie den Konfigurationsabschnitt zu Svcutil.exe.config im gleichen Verzeichnis wie Svcutil.exe hinzu.</span><span class="sxs-lookup"><span data-stu-id="336c7-142">Add the configuration section to Svcutil.exe.config in the same directory as Svcutil.exe.</span></span>  
  
 <span data-ttu-id="336c7-143">Der `UdpBindingElementImporter`-Typ implementiert die <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="336c7-143">The `UdpBindingElementImporter` type implements the <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="336c7-144">Die `ImportEndpoint`-Methode importiert die Adresse vom WSDL-Anschluss:</span><span class="sxs-lookup"><span data-stu-id="336c7-144">The `ImportEndpoint` method imports the address from the WSDL port:</span></span>  
  
```csharp  
BindingElementCollection bindingElements = context.Endpoint.Binding.CreateBindingElements();  
TransportBindingElement transportBindingElement = bindingElements.Find<TransportBindingElement>();  
if (transportBindingElement is UdpTransportBindingElement)  
{  
    ImportAddress(context);  
}  
```  
  
### <a name="adding-policy-support"></a><span data-ttu-id="336c7-145">Hinzufügen von Richtlinienunterstützung</span><span class="sxs-lookup"><span data-stu-id="336c7-145">Adding Policy Support</span></span>  

 <span data-ttu-id="336c7-146">Das benutzerdefinierte Bindungselement kann Richtlinienassertionen in die WSDL-Bindung für einen Dienstendpunkt exportieren, um die Funktionen dieses Bindungselements auszudrücken.</span><span class="sxs-lookup"><span data-stu-id="336c7-146">The custom binding element can export policy assertions in the WSDL binding for a service endpoint to express the capabilities of that binding element.</span></span> <span data-ttu-id="336c7-147">Der folgende Beispielcode stammt aus dem " [Transport: UDP](../samples/transport-udp.md) "-Beispiel.</span><span class="sxs-lookup"><span data-stu-id="336c7-147">The following example code is taken from the [Transport: UDP](../samples/transport-udp.md) sample.</span></span>  
  
#### <a name="policy-export"></a><span data-ttu-id="336c7-148">Richtlinienexport</span><span class="sxs-lookup"><span data-stu-id="336c7-148">Policy Export</span></span>  

 <span data-ttu-id="336c7-149">Der `UdpTransportBindingElement` Typ implementiert <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> , um Unterstützung für das Exportieren von Richtlinien hinzuzufügen</span><span class="sxs-lookup"><span data-stu-id="336c7-149">The `UdpTransportBindingElement` type implements <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> to add support for exporting policy.</span></span> <span data-ttu-id="336c7-150">Als Ergebnis schließt <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType>`UdpTransportBindingElement` in die Generierung der Richtlinie für eine Bindung ein, die dieses enthält.</span><span class="sxs-lookup"><span data-stu-id="336c7-150">As a result, <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> includes `UdpTransportBindingElement` in the generation of policy for any binding that includes it.</span></span>  
  
 <span data-ttu-id="336c7-151">Fügen Sie in <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A?displayProperty=nameWithType> eine Assertion für UDP und eine weitere Assertion ein, wenn der Kanal sich im Multicastmodus befindet.</span><span class="sxs-lookup"><span data-stu-id="336c7-151">In <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A?displayProperty=nameWithType>, add an assertion for UDP and another assertion if the channel is in multicast mode.</span></span> <span data-ttu-id="336c7-152">Grund hierfür ist, dass der Multicastmodus Einfluss auf die Art und Weise hat, in der der Kommunikationsstapel erstellt wird, weshalb eine Koordinierung zwischen beiden Seiten stattfinden muss.</span><span class="sxs-lookup"><span data-stu-id="336c7-152">This is because multicast mode affects how the communication stack is constructed, and thus must be coordinated between both sides.</span></span>  
  
```csharp  
ICollection<XmlElement> bindingAssertions = context.GetBindingAssertions();  
XmlDocument xmlDocument = new XmlDocument();  
bindingAssertions.Add(xmlDocument.CreateElement(  
UdpPolicyStrings.Prefix, UdpPolicyStrings.TransportAssertion, UdpPolicyStrings.UdpNamespace));  
if (Multicast)  
{  
    bindingAssertions.Add(xmlDocument.CreateElement(  
UdpPolicyStrings.Prefix, UdpPolicyStrings.MulticastAssertion,     UdpPolicyStrings.UdpNamespace));  
}  
```  
  
 <span data-ttu-id="336c7-153">Da benutzerdefinierte Transportbindungselemente für die Handhabung der Adressierung verantwortlich sind, muss die <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType>-Implementierung auf dem `UdpTransportBindingElement` auch den Export der geeigneten WS-Adressierungsrichtlinienassertionen handhaben, um die Version der verwendeten WS-Adressierung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="336c7-153">Because custom transport binding elements are responsible for handling addressing, the <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> implementation on the `UdpTransportBindingElement` must also handle exporting the appropriate WS-Addressing policy assertions to indicate the version of WS-Addressing being used.</span></span>  
  
```csharp  
AddWSAddressingAssertion(context, encodingBindingElement.MessageVersion.Addressing);  
```  
  
#### <a name="policy-import"></a><span data-ttu-id="336c7-154">Richtlinienimport</span><span class="sxs-lookup"><span data-stu-id="336c7-154">Policy Import</span></span>  

 <span data-ttu-id="336c7-155">Um das Richtlinienimportsystem zu erweitern, fügen Sie der Konfigurationsdatei für Svcutil.exe die folgende Konfiguration hinzu (wie in der Datei Svcutil.exe.config gezeigt):</span><span class="sxs-lookup"><span data-stu-id="336c7-155">To extend the policy import system, add the following configuration to the configuration file for Svcutil.exe as shown in the Svcutil.exe.config file:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <metadata>  
        <policyImporters>  
          <extension type=" Microsoft.ServiceModel.Samples.UdpBindingElementImporter, UdpTransport" />  
        </policyImporters>  
      </metadata>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="336c7-156">Dann implementieren Sie <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> aus der registrierten Klasse (`UdpBindingElementImporter`).</span><span class="sxs-lookup"><span data-stu-id="336c7-156">Then we implement <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> from our registered class (`UdpBindingElementImporter`).</span></span> <span data-ttu-id="336c7-157">Prüfen Sie in <xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=nameWithType> die Assertionen im entsprechenden Namespace, verarbeiten Sie sie für die Generierung des Transports, und prüfen Sie, ob Multicast vorliegt.</span><span class="sxs-lookup"><span data-stu-id="336c7-157">In <xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=nameWithType>, examine the assertions in the appropriate namespace and process the ones for generating the transport and checking if it is multicast.</span></span> <span data-ttu-id="336c7-158">Entfernen Sie darüber hinaus die Assertionen, die das Importprogramm handhabt, aus der Liste der Bindungsassertionen.</span><span class="sxs-lookup"><span data-stu-id="336c7-158">In addition, remove the assertions that the importer handles from the list of binding assertions.</span></span> <span data-ttu-id="336c7-159">Erneut stehen bei der Ausführung von "Svcutil.exe" zwei Optionen für die Integration zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="336c7-159">Again, when running Svcutil.exe, there are two options for integration:</span></span>  
  
1. <span data-ttu-id="336c7-160">Zeigen Sie Svcutil.exe mithilfe von/svcutilConfig auf unsere Konfigurationsdatei \<file> .</span><span class="sxs-lookup"><span data-stu-id="336c7-160">Point Svcutil.exe to our configuration file using the /SvcutilConfig:\<file>.</span></span>  
  
2. <span data-ttu-id="336c7-161">Fügen Sie den Konfigurationsabschnitt zu Svcutil.exe.config im gleichen Verzeichnis wie Svcutil.exe hinzu.</span><span class="sxs-lookup"><span data-stu-id="336c7-161">Add the configuration section to Svcutil.exe.config in the same directory as Svcutil.exe.</span></span>  
  
### <a name="adding-a-custom-standard-binding-importer"></a><span data-ttu-id="336c7-162">Hinzufügen eines benutzerdefinierten Standardbindungsimportprogramms</span><span class="sxs-lookup"><span data-stu-id="336c7-162">Adding a Custom Standard Binding Importer</span></span>  

 <span data-ttu-id="336c7-163">Svcutil.exe und der <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType>-Typ erkennen und importieren vom System bereitgestellte Bindungen standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="336c7-163">Svcutil.exe and the <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> type, by default, recognize and import system-provided bindings.</span></span> <span data-ttu-id="336c7-164">Andernfalls wird die Bindung als <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>-Instanz importiert.</span><span class="sxs-lookup"><span data-stu-id="336c7-164">Otherwise, the binding gets imported as a <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="336c7-165">Zur Aktivierung des Imports der <xref:System.ServiceModel.Description.WsdlImporter> für „Svcutil.exe“ und den `SampleProfileUdpBinding`, fungiert der `UdpBindingElementImporter` auch als benutzerdefiniertes Importprogramm für Standardbindungen.</span><span class="sxs-lookup"><span data-stu-id="336c7-165">To enable Svcutil.exe and the <xref:System.ServiceModel.Description.WsdlImporter> to import the `SampleProfileUdpBinding` the `UdpBindingElementImporter` also acts as a custom standard binding importer.</span></span>  
  
 <span data-ttu-id="336c7-166">Ein benutzerdefiniertes standardbindungs-Import Programm implementiert die- `ImportEndpoint` Methode für die- <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> Schnittstelle, um zu prüfen <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> , ob die aus den Metadaten importierte-Instanz von einer bestimmten Standard Bindung generiert werden könnte.</span><span class="sxs-lookup"><span data-stu-id="336c7-166">A custom standard binding importer implements the `ImportEndpoint` method on the <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> interface to examine the <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> instance imported from metadata to see if it could have been generated by specific standard binding.</span></span>  
  
```csharp  
if (context.Endpoint.Binding is CustomBinding)  
{  
    Binding binding;  
    if (transportBindingElement is UdpTransportBindingElement)  
    {  
        //if TryCreate is true, the CustomBinding will be replace by a SampleProfileUdpBinding in the  
        //generated config file for better typed generation.  
        if (SampleProfileUdpBinding.TryCreate(bindingElements, out binding))  
        {  
            binding.Name = context.Endpoint.Binding.Name;  
            binding.Namespace = context.Endpoint.Binding.Namespace;  
            context.Endpoint.Binding = binding;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="336c7-167">Allgemein beinhaltet die Implementierung eines benutzerdefinierten Importprogramms für Standardbindungen die Überprüfung der Eigenschaften der importierten Bindungen, um zu bestätigen, dass sich nur Eigenschaften geändert haben, die von der Standardbindung hätten festgelegt werden können, und es sich bei allen anderen Eigenschaften um die Standardwerte handelt.</span><span class="sxs-lookup"><span data-stu-id="336c7-167">Generally, implementing a custom standard binding importer involves checking the properties of the imported binding elements to verify that only properties that could have been set by the standard binding have changed and all other properties are their defaults.</span></span> <span data-ttu-id="336c7-168">Eine grundlegende Strategie für die Implementierung eines Importprogramms für Standardbindungen ist die Erstellung einer Standardbindung, die Weitergabe der Eigenschaften von den Bindungselementen an die von der Standardbindung unterstützte Standardbindungsinstanz und der Vergleich der Bindungselemente der Standardbindung mit den importierten Bindungselementen.</span><span class="sxs-lookup"><span data-stu-id="336c7-168">A basic strategy for implementing a standard binding importer is to create an instance of the standard binding, propagate the properties from the binding elements to the standard binding instance that the standard binding supports, and the compare the binding elements from the standard binding with the imported binding elements.</span></span>
