---
title: Standardendpunkte
ms.date: 03/30/2017
ms.assetid: 3fcb4225-addc-44f2-935d-30e4943a8812
ms.openlocfilehash: 880601664d7602e279c5d022fa37c44914a58772
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184406"
---
# <a name="standard-endpoints"></a>Standardendpunkte
Endpunkte werden definiert, indem eine Adresse, eine Bindung und ein Vertrag angegeben wird. Andere Parameter, die für einen Endpunkt festgelegt werden können, sind beispielsweise Verhaltenskonfigurationen, Header und Abhör-URIs.  Für bestimmte Typen von Endpunkten ändern sich diese Werte nicht. Beispielsweise verwenden Metadatenaustausch-Endpunkte immer den <xref:System.ServiceModel.Description.IMetadataExchange>-Vertrag. Andere Endpunkte, z. B. <xref:System.ServiceModel.Description.WebHttpEndpoint>, erfordern immer ein angegebenes Endpunktverhalten. Die Verwendbarkeit eines Endpunkts kann verbessert werden, indem für häufig verwendete Endpunkteigenschaften Endpunkte mit Standardwerten verwendet werden. Mithilfe von Standardendpunkten können Entwickler einen Endpunkt definieren, der über Standardwerte verfügt oder für den sich eine oder mehrere Endpunkteigenschaften nicht ändern.  Mit diesen Endpunkten können Sie einen solchen Endpunkt verwenden, ohne Informationen statischer Natur angeben zu müssen. Standardendpunkte können für Infrastruktur- und Anwendungsendpunkte verwendet werden.  
  
## <a name="infrastructure-endpoints"></a>Infrastrukturendpunkte  
 Es kann sein, dass ein Dienst Endpunkte verfügbar macht, für die einige Eigenschaften vom Dienstautor nicht explizit implementiert wurden. Der Metadatenaustausch-Endpunkt macht z. B. den <xref:System.ServiceModel.Description.IMetadataExchange>-Vertrag verfügbar. Als Dienstautor implementieren Sie diese Schnittstelle jedoch nicht, sondern sie wird von der WCF implementiert. Solche Infrastrukturendpunkte haben Standardwerte für eine oder mehrere Endpunkteigenschaften, von denen einige ggf. unveränderbar sind. Die <xref:System.ServiceModel.Description.ServiceEndpoint.Contract%2A>-Eigenschaft des Metadatenaustausch-Endpunkts muss <xref:System.ServiceModel.Description.IMetadataExchange> sein, während andere Eigenschaften wie die Bindung vom Entwickler angegeben werden können. Infrastrukturendpunkte werden identifiziert, indem die <xref:System.ServiceModel.Description.ServiceEndpoint.IsSystemEndpoint%2A>-Eigenschaft auf `true` festgelegt wird.  
  
## <a name="application-endpoints"></a>Anwendungsendpunkte  
 Anwendungsentwickler können eigene Standardendpunkte definieren, die Standardwerte für die Adresse, die Bindung oder den Vertrag angeben. Sie definieren einen Standardendpunkt, indem Sie eine Klasse von <xref:System.ServiceModel.Description.ServiceEndpoint> ableiten und die entsprechenden Endpunkteigenschaften festlegen. Sie können Standardwerte für Eigenschaften bereitstellen, die geändert werden können. Einige andere Eigenschaften verfügen über statische Werte, die sich nicht ändern können. Das folgende Beispiel zeigt, wie Sie einen Standardendpunkt implementieren.  
  
```csharp
public class CustomEndpoint : ServiceEndpoint
{
    public CustomEndpoint()
        : this(string.Empty)
    { }  

    public CustomEndpoint(string address)
        : this(address, ContractDescription.GetContract(typeof(ICalculator)))
    { }  

    // Create the custom endpoint with a fixed binding
    public CustomEndpoint(string address, ContractDescription contract)
        : base(contract)
    {
        this.Binding = new BasicHttpBinding();
        this.IsSystemEndpoint = false;
    }

    // Definition of the additional property of this endpoint
    public bool Property { get; set; }
}
```
  
 Um einen benutzerdefinierten benutzerdefinierten Endpunkt in einer Konfigurationsdatei <xref:System.ServiceModel.Configuration.StandardEndpointElement>zu verwenden, müssen <xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602>Sie eine Klasse von ableiten, eine Klasse von ableiten und den neuen Standardendpunkt im Abschnitt Erweiterungen in app.config oder machine.config registrieren.  Der <xref:System.ServiceModel.Configuration.StandardEndpointElement> bietet Konfigurationsunterstützung für den Standardendpunkt, wie im folgenden Beispiel gezeigt.  
  
```csharp
public class CustomEndpointElement : StandardEndpointElement
{
    // Definition of the additional property for the standard endpoint element
    public bool Property
    {
        get { return (bool)base["property"]; }
        set { base["property"] = value; }
    }

    // The additional property needs to be added to the properties of the standard endpoint element
    protected override ConfigurationPropertyCollection Properties
    {
        get
        {
            ConfigurationPropertyCollection properties = base.Properties;
            properties.Add(new ConfigurationProperty("property", typeof(bool), false, ConfigurationPropertyOptions.None));
            return properties;
        }
    }

    // Return the type of this standard endpoint
    protected override Type EndpointType
    {
        get { return typeof(CustomEndpoint); }
    }

    // Create the custom service endpoint
    protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contract)
    {
        return new CustomEndpoint();
    }

    // Read the value given to the property in config and save it
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    // Read the value given to the property in config and save it
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    // No validation in this sample
    protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)
    {
    }

    // No validation in this sample
    protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)
    {
    }
}
```  
  
 Der <xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602> stellt den Sicherungstyp für die `standardEndpoints` Auflistung bereit, die unter <> Abschnitt in der Konfiguration für den Standardendpunkt angezeigt wird.  Im folgenden Beispiel wird die Implementierung dieser Klasse veranschaulicht.  
  
```csharp
public class CustomEndpointCollectionElement : StandardEndpointCollectionElement<CustomEndpoint, CustomEndpointElement>
{
    // ...
}
```

Im folgenden Beispiel wird gezeigt, wie Sie einen Standardendpunkt im Abschnitt für die Erweiterungen registrieren.

```xml  
<extensions>  
      <standardEndpointExtensions>  
        <add  
          name="customStandardEndpoint"  
          type="CustomEndpointCollectionElement, Example.dll,  
                Version=1.0.0.0, Culture=neutral, PublicKeyToken=ffffffffffffffff"/>  
```  
  
## <a name="configuring-a-standard-endpoint"></a>Konfigurieren eines Standardendpunkts  
 Standardendpunkte können im Code oder in der Konfiguration hinzugefügt werden.  Um einen Standardendpunkt im Code hinzuzufügen, instanziieren Sie einfach den entsprechenden Standardendpunkttyp und fügen diesen dem Diensthost wie im folgenden Beispiel dargestellt hinzu:  
  
```csharp  
serviceHost.AddServiceEndpoint(new CustomEndpoint());  
```  
  
 Um einen Standardendpunkt in der `endpoint` Konfiguration hinzuzufügen, `service` fügen Sie dem <>-Element und allen erforderlichen Konfigurationseinstellungen im <`standardEndpoints`>-Element ein <>-Element hinzu. Im folgenden Beispiel wird gezeigt, wie Sie ein <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>-Objekt hinzufügen. Dabei handelt es sich um einen der Standardendpunkte, die im Lieferumfang von [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] enthalten sind.  
  
```xml  
<services>  
  <service>  
    <endpoint isSystemEndpoint="true" kind="udpDiscoveryEndpoint" />  
  </service>  
</services>  
<standardEndpoints>
  <udpDiscoveryEndpoint>  
     <standardEndpoint multicastAddress="soap.udp://239.255.255.250:3702" />
  </udpDiscoveryEndpoint>
</standardEndpoints>
```  
  
 Der Typ des Standardendpunkts wird mit `endpoint` dem Art-Attribut im <>-Element angegeben. Der Endpunkt wird innerhalb `standardEndpoints` des <> Elements konfiguriert. Im obigen Beispiel wird ein <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>-Endpunkt hinzugefügt und konfiguriert. Das `udpDiscoveryEndpoint` <>-Element `standardEndpoint` enthält eine <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint.MulticastAddress%2A> <<xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>>, die die Eigenschaft des festlegt.  
  
## <a name="standard-endpoints-shipped-with-the-net-framework"></a>Im Lieferumfang von .NET Framework enthaltene Standardendpunkte  
 In der folgenden Tabelle sind die im Lieferumfang von [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] enthaltenen Standardendpunkte aufgeführt.  
  
 `Mex Endpoint`  
 Ein Standardendpunkt, der verwendet wird, um Dienstmetadaten verfügbar zu machen.  
  
 <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>  
 Ein Standardendpunkt, der von Diensten verwendet wird, um Ankündigungsmeldungen zu senden.  
  
 <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>  
 Ein Standardendpunkt, der von Diensten verwendet wird, um Suchmeldungen zu senden.  
  
 <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>  
 Ein Standardendpunkt, der für Suchvorgänge über eine UDP-Multicastbindung vorkonfiguriert ist.  
  
 <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>  
 Ein Standardendpunkt, der von Diensten verwendet wird, um Ankündigungsmeldungen über eine UDP-Bindung zu senden.  
  
 <xref:System.ServiceModel.Discovery.DynamicEndpoint>  
 Ein Standardendpunkt, der die WS-Suche verwendet, um zur Laufzeit dynamisch nach der Endpunktadresse zu suchen.  
  
 <xref:System.ServiceModel.Description.ServiceMetadataEndpoint>  
 Ein Standardendpunkt für den Metadatenaustausch.  
  
 <xref:System.ServiceModel.Description.WebHttpEndpoint>  
 Ein Standardendpunkt mit einer <xref:System.ServiceModel.WebHttpBinding>-Bindung, die das <xref:System.ServiceModel.Description.WebHttpBehavior>-Verhalten automatisch hinzufügt.  
  
 <xref:System.ServiceModel.Description.WebScriptEndpoint>  
 Ein Standardendpunkt mit einer <xref:System.ServiceModel.WebHttpBinding>-Bindung, die das <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>-Verhalten automatisch hinzufügt.  
  
 <xref:System.ServiceModel.Description.WebServiceEndpoint>  
 Ein Standardendpunkt mit einer <xref:System.ServiceModel.WebHttpBinding>-Bindung.  
  
 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>  
 Ein Standardendpunkt, der es Ihnen ermöglicht, Steuerungsvorgänge für Workflowinstanzen aufzurufen.  
  
 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>  
 Ein Standardendpunkt, der die Workflowerstellung und die Wiederaufnahme von Lesezeichen unterstützt.
