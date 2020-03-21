---
title: Konfiguration und Metadatenunterstützung
ms.date: 03/30/2017
ms.assetid: 27c240cb-8cab-472c-87f8-c864f4978758
ms.openlocfilehash: 0ec8c3286037e7adbe6f5efb73e846a30b9d48d3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185666"
---
# <a name="configuration-and-metadata-support"></a>Konfiguration und Metadatenunterstützung
In diesem Thema wird beschrieben, wie Konfigurations- und Metadatenunterstützung für Bindungen und Bindungselemente aktiviert wird.  
  
## <a name="overview-of-configuration-and-metadata"></a>Überblick über Konfiguration und Metadaten  
 In diesem Thema werden die folgenden Aufgaben erläutert, d. h. die optionalen Elemente 1, 2 und 4 in der Aufgabenliste ["Entwicklungskanäle".](developing-channels.md)  
  
- Aktivierung von Unterstützung der Konfigurationsdatei für ein Bindungselement.  
  
- Aktivierung von Unterstützung der Konfigurationsdatei für eine Bindung.  
  
- Export von WSDL und Richtlinienassertionen für ein Bindungselement.  
  
- Identifizierung von WSDL und Richtlinienassertionen für das Einsetzen und Konfigurieren der Bindung oder des Bindungselements.  
  
 Informationen zum Erstellen benutzerdefinierter Bindungen und Bindungselemente finden Sie unter [Erstellen von benutzerdefinierten Bindungen](creating-user-defined-bindings.md) bzw. Erstellen eines [BindingElements.](creating-a-bindingelement.md)  
  
## <a name="adding-configuration-support"></a>Hinzufügen von Konfigurationsunterstützung  
 Zum Aktivieren der Konfigurationsdateiunterstützung für einen Kanal müssen Sie zwei Konfigurationsabschnitte implementieren, <xref:System.ServiceModel.Configuration.BindingElementExtensionElement?displayProperty=nameWithType>, wodurch die Konfigurationsunterstützung für Bindungselemente aktiviert wird, und das <xref:System.ServiceModel.Configuration.StandardBindingElement?displayProperty=nameWithType> sowie das <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602?displayProperty=nameWithType> implementieren, wodurch die Konfigurationsunterstützung für Bindungen aktiviert wird.  
  
 Eine einfachere Möglichkeit hierzu ist die Verwendung des [Beispieltools ConfigurationCodeGenerator](../samples/configurationcodegenerator.md) zum Generieren von Konfigurationscode für Ihre Bindungen und Bindungselemente.  
  
### <a name="extending-bindingelementextensionelement"></a>Erweitern von BindingElementExtensionElement  
 Der folgende Beispielcode wird aus dem [Beispiel Transport: UDP](../samples/transport-udp.md) übernommen. `UdpTransportElement` ist ein <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>, das `UdpTransportBindingElement` für das Konfigurationssystem verfügbar macht. Mit wenigen grundlegenden Überschreibungen definiert das Beispiel den Konfigurationsabschnittsnamen, den Typ des Bindungselements und wie das Bindungselement erstellt wird. Benutzer können dann wie folgt den Erweiterungsabschnitt in einer Konfigurationsdatei registrieren.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <extensions>  
      <bindingElementExtensions>  
      <add name="udpTransport" type="Microsoft.ServiceModel.Samples.UdpTransportElement, UdpTransport />  
      </bindingElementExtensions>  
    </extensions>  
  </system.serviceModel>  
</configuration>  
```  
  
 Auf die Erweiterung kann von benutzerdefinierten Bindungen verwiesen werden, um UDP als Transport zu nutzen.  
  
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
  
### <a name="adding-configuration-for-a-binding"></a>Hinzufügen einer Konfiguration für eine Bindung  
 Der Abschnitt `SampleProfileUdpBindingCollectionElement` ist ein <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602>, das die `SampleProfileUdpBinding` für das Konfigurationssystem verfügbar macht. Dem `SampleProfileUdpBindingConfigurationElement`, das sich von <xref:System.ServiceModel.Configuration.StandardBindingElement> herleitet, wird der Großteil der Implementierung übertragen. Der `SampleProfileUdpBindingConfigurationElement` verfügt über Eigenschaften, `SampleProfileUdpBinding`die den Eigenschaften auf `ConfigurationElement` entsprechen, und Funktionen, die aus der Bindung zugeordnet werden sollen. Schließlich wird die `OnApplyConfiguration`-Methode in der `SampleProfileUdpBinding` überschrieben. Dies wird im folgenden Beispielcode veranschaulicht.  
  
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
  
 Um diesen Handler mit dem Konfigurationssystem zu registrieren, fügen Sie der relevanten Konfigurationsdatei den folgenden Abschnitt hinzu.  
  
```xml  
<configuration>  
  <configSections>  
     <sectionGroup name="system.serviceModel">  
         <sectionGroup name="bindings">  
                 <section name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport />  
         </sectionGroup>  
     </sectionGroup>  
  </configSections>  
</configuration>  
```  
  
 Auf sie kann dann im Konfigurationsabschnitt [ \<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) verwiesen werden.  
  
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
  
## <a name="adding-metadata-support-for-a-binding-element"></a>Hinzufügen von Metadatenunterstützung für ein Bindungselement  
 Um einen Kanal in ein Metadatensystem zu integrieren, muss dieser sowohl den Import als auch den Export von Richtlinien unterstützen. Dadurch können Tools wie [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) Clients des Bindungselements generieren.  
  
### <a name="adding-wsdl-support"></a>Hinzufügen von WSDL-Unterstützung  
 Das Transportbindungselement in einer Bindung ist für den Export und Import von Adressierungsinformationen in/zu Metadaten verantwortlich. Bei der Nutzung einer SOAP-Bindung sollte das Transportbindungselement ebenfalls einen korrekten Transport-URI in die Metadaten exportieren. Der folgende Beispielcode wird aus dem [Beispiel Transport: UDP](../samples/transport-udp.md) übernommen.  
  
#### <a name="wsdl-export"></a>WSDL-Export  
 Um Adressierungsinformationen `UdpTransportBindingElement` zu <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> exportieren, implementiert der die Schnittstelle. Die <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A?displayProperty=nameWithType>-Methode fügt dem WSDL-Port die richtigen Adressierungsinformationen hinzu.  
  
```csharp  
if (context.WsdlPort != null)  
{  
    AddAddressToWsdlPort(context.WsdlPort, context.Endpoint.Address, encodingBindingElement.MessageVersion.Addressing);  
}  
```  
  
 Die `UdpTransportBindingElement`-Implementierung der <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A>-Methode exportiert ebenfalls einen Transport-URI, wenn der Endpunkt eine SOAP-Bindung verwendet.  
  
```csharp  
WsdlNS.SoapBinding soapBinding = GetSoapBinding(context, exporter);  
if (soapBinding != null)  
{  
    soapBinding.Transport = UdpPolicyStrings.UdpNamespace;  
}  
```  
  
#### <a name="wsdl-import"></a>WSDL-Import  
 Um das WSDL-Importsystem auf die Handhabung des Imports von Adressen zu erweitern, fügen Sie die folgende Konfiguration zur Konfigurationsdatei für Svcutil.exe hinzu (wie in der Datei Svcutil.exe.config gezeigt):  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <metadata>  
        <wsdlImporters>  
          <extension type=" Microsoft.ServiceModel.Samples.UdpBindingElementImporter, UdpTransport" />  
        </policyImporters>  
      </metadata>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
 Bei der Ausführung von "Svcutil.exe" gibt es zwei Optionen, um "Svcutil.exe" dazu zu bewegen, die WSDL-Importerweiterungen zu laden:  
  
1. Zeigen Sie Svcutil.exe mit der Datei /SvcutilConfig:\<> auf die Konfigurationsdatei.  
  
2. Fügen Sie den Konfigurationsabschnitt zu Svcutil.exe.config im gleichen Verzeichnis wie Svcutil.exe hinzu.  
  
 Der `UdpBindingElementImporter`-Typ implementiert die <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType>-Schnittstelle. Die `ImportEndpoint`-Methode importiert die Adresse vom WSDL-Anschluss:  
  
```csharp  
BindingElementCollection bindingElements = context.Endpoint.Binding.CreateBindingElements();  
TransportBindingElement transportBindingElement = bindingElements.Find<TransportBindingElement>();  
if (transportBindingElement is UdpTransportBindingElement)  
{  
    ImportAddress(context);  
}  
```  
  
### <a name="adding-policy-support"></a>Hinzufügen von Richtlinienunterstützung  
 Das benutzerdefinierte Bindungselement kann Richtlinienassertionen in die WSDL-Bindung für einen Dienstendpunkt exportieren, um die Funktionen dieses Bindungselements auszudrücken. Der folgende Beispielcode wird aus dem [Beispiel Transport: UDP](../samples/transport-udp.md) übernommen.  
  
#### <a name="policy-export"></a>Richtlinienexport  
 Der `UdpTransportBindingElement` Typ <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> wird implementiert, um Unterstützung für den Export von Richtlinien hinzuzufügen. Als Ergebnis schließt <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType>`UdpTransportBindingElement` in die Generierung der Richtlinie für eine Bindung ein, die dieses enthält.  
  
 Fügen Sie in <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A?displayProperty=nameWithType> eine Assertion für UDP und eine weitere Assertion ein, wenn der Kanal sich im Multicastmodus befindet. Grund hierfür ist, dass der Multicastmodus Einfluss auf die Art und Weise hat, in der der Kommunikationsstapel erstellt wird, weshalb eine Koordinierung zwischen beiden Seiten stattfinden muss.  
  
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
  
 Da benutzerdefinierte Transportbindungselemente für die Handhabung der Adressierung verantwortlich sind, muss die <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType>-Implementierung auf dem `UdpTransportBindingElement` auch den Export der geeigneten WS-Adressierungsrichtlinienassertionen handhaben, um die Version der verwendeten WS-Adressierung anzugeben.  
  
```csharp  
AddWSAddressingAssertion(context, encodingBindingElement.MessageVersion.Addressing);  
```  
  
#### <a name="policy-import"></a>Richtlinienimport  
 Um das Richtlinienimportsystem zu erweitern, fügen Sie der Konfigurationsdatei für Svcutil.exe die folgende Konfiguration hinzu (wie in der Datei Svcutil.exe.config gezeigt):  
  
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
  
 Dann implementieren Sie <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> aus der registrierten Klasse (`UdpBindingElementImporter`). Prüfen Sie in <xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=nameWithType> die Assertionen im entsprechenden Namespace, verarbeiten Sie sie für die Generierung des Transports, und prüfen Sie, ob Multicast vorliegt. Entfernen Sie darüber hinaus die Assertionen, die das Importprogramm handhabt, aus der Liste der Bindungsassertionen. Erneut stehen bei der Ausführung von "Svcutil.exe" zwei Optionen für die Integration zur Verfügung:  
  
1. Zeigen Sie Svcutil.exe mit der Datei /SvcutilConfig:\<> auf unsere Konfigurationsdatei.  
  
2. Fügen Sie den Konfigurationsabschnitt zu Svcutil.exe.config im gleichen Verzeichnis wie Svcutil.exe hinzu.  
  
### <a name="adding-a-custom-standard-binding-importer"></a>Hinzufügen eines benutzerdefinierten Standardbindungsimportprogramms  
 Svcutil.exe und der <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType>-Typ erkennen und importieren vom System bereitgestellte Bindungen standardmäßig. Andernfalls wird die Bindung als <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>-Instanz importiert. Zur Aktivierung des Imports der <xref:System.ServiceModel.Description.WsdlImporter> für „Svcutil.exe“ und den `SampleProfileUdpBinding`, fungiert der `UdpBindingElementImporter` auch als benutzerdefiniertes Importprogramm für Standardbindungen.  
  
 Ein benutzerdefinierter Standardbindungsimporter implementiert die `ImportEndpoint` Methode auf der <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> Schnittstelle, um die <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> aus Metadaten importierte Instanz zu untersuchen, um festzustellen, ob sie durch eine bestimmte Standardbindung generiert worden sein könnte.  
  
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
  
 Allgemein beinhaltet die Implementierung eines benutzerdefinierten Importprogramms für Standardbindungen die Überprüfung der Eigenschaften der importierten Bindungen, um zu bestätigen, dass sich nur Eigenschaften geändert haben, die von der Standardbindung hätten festgelegt werden können, und es sich bei allen anderen Eigenschaften um die Standardwerte handelt. Eine grundlegende Strategie für die Implementierung eines Importprogramms für Standardbindungen ist die Erstellung einer Standardbindung, die Weitergabe der Eigenschaften von den Bindungselementen an die von der Standardbindung unterstützte Standardbindungsinstanz und der Vergleich der Bindungselemente der Standardbindung mit den importierten Bindungselementen.
