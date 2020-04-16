---
title: Konfigurieren der Suche in einer Konfigurationsdatei
ms.date: 03/30/2017
ms.assetid: b9884c11-8011-4763-bc2c-c526b80175d0
ms.openlocfilehash: 934b04b51b9954cf943f57f33250951048e5671b
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81464204"
---
# <a name="configuring-discovery-in-a-configuration-file"></a>Konfigurieren der Suche in einer Konfigurationsdatei
Es gibt vier Hauptgruppen von Konfigurationseinstellungen, die bei der Suche verwendet wurden. In diesem Thema werden die Gruppen beschrieben und jeweils Beispiele für deren Konfiguration angegeben. Nach jedem Abschnitt folgt ein Link zu einer ausführlicheren Dokumentation der einzelnen Bereiche.  
  
## <a name="behavior-configuration"></a>Verhaltenskonfiguration  
 Bei der Suche werden Dienstverhalten und Endpunktverhalten verwendet. Das <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>-Verhalten aktiviert die Suche für alle Endpunkte eines Diensts und ermöglicht Ihnen das Angeben von Ankündigungsendpunkten.  Das folgende Beispiel zeigt, wie Sie das <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> hinzufügen und einen Ankündigungsendpunkt angeben.  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior name="helloWorldServiceBehavior">  
          <serviceDiscovery>  
            <announcementEndpoints>  
              <endpoint kind="udpAnnouncementEndpoint"/>  
            </announcementEndpoints>  
          </serviceDiscovery>  
        </behavior>  
      </serviceBehaviors>  
</behaviors>  
```  
  
 Nachdem Sie das Verhalten angegeben haben, verweisen Sie auf ein <`service`>-Element, wie im folgenden Beispiel gezeigt.  
  
```xml  
<system.serviceModel>  
   <services>  
      <service name="HelloWorldService" behaviorConfiguration="helloWorldServiceBehavior">  
         <!-- Application Endpoint -->  
         <endpoint address="endpoint0"  
                   binding="basicHttpBinding"  
                   contract="IHelloWorldService" />  
         <!-- Discovery Endpoints -->  
         <endpoint kind="udpDiscoveryEndpoint" />  
        </service>  
    </services>  
</system.serviceModel>  
```  
  
 Damit ein Dienst erkennbar ist, müssen Sie auch einen Suchendpunkt hinzufügen. Im Beispiel oben wird ein <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>-Standardendpunkt hinzugefügt.  
  
 Wenn Sie Ankündigungsendpunkte hinzufügen, müssen Sie dem `services` <>-Element auch einen Ankündigungslistenerdienst hinzufügen, wie im folgenden Beispiel gezeigt.  
  
```xml  
<services>  
   <service name="HelloWorldService" behaviorConfiguration="helloWorldServiceBehavior">  
      <!-- Application Endpoint -->  
      <endpoint address="endpoint0"  
                binding="basicHttpBinding"  
                contract="IHelloWorldService" />  
      <!-- Discovery Endpoints -->  
      <endpoint kind="udpDiscoveryEndpoint" />  
   </service>  
   <!-- Announcement Listener Configuration -->  
   <service name="AnnouncementListener">  
      <endpoint kind="udpAnnouncementEndpoint" />  
   </service>  
</services>
```  
  
 Das <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>-Verhalten wird verwendet, um die Suche nach einem bestimmten Endpunkt zu aktivieren oder zu deaktivieren.  Im folgenden Beispiel wird ein Dienst mit zwei Anwendungsendpunkten konfiguriert, wobei die Suche für einen Endpunkt aktiviert und für den anderen deaktiviert ist. Für jeden Endpunkt wird ein <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>-Verhalten hinzugefügt.  
  
```xml  
<system.serviceModel>  
   <services>  
      <service name="HelloWorldService"  
               behaviorConfiguration="helloWorldServiceBehavior">  
  
        <!-- Application Endpoints -->  
        <endpoint address="endpoint0"  
                 binding="basicHttpBinding"  
                 contract="IHelloWorldService"
                 behaviorConfiguration="ep0Behavior" />  
  
        <endpoint address="endpoint1"  
                  binding="basicHttpBinding"  
                  contract="IHelloWorldService"  
                  behaviorConfiguration="ep1Behavior" />  
  
        <!-- Discovery Endpoints -->  
        <endpoint kind="udpDiscoveryEndpoint" />  
      </service>  
   </services>  
   <behaviors>  
      <serviceBehaviors>  
        <behavior name="helloWorldServiceBehavior">  
          <serviceDiscovery />  
        </behavior>  
      </serviceBehaviors>  
      <endpointBehaviors>  
        <behavior name="ep0Behavior">  
          <endpointDiscovery enabled="true"/>  
        </behavior>  
        <behavior name="ep1Behavior">  
          <endpointDiscovery enabled="false"/>  
        </behavior>  
     </endpointBehaviors>  
   </behaviors>  
</system.serviceModel>  
```  
  
 Sie können das <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>-Verhalten auch verwenden, um den vom Dienst zurückgegebenen Endpunktmetadaten benutzerdefinierte Metadaten hinzuzufügen. Das folgende Beispiel zeigt die erforderliche Vorgehensweise.  
  
```xml  
<behavior name="ep4Behavior">  
   <endpointDiscovery enabled="true">  
      <extensions>  
         <CustomMetadata>This is custom metadata.</CustomMetadata>  
         <d:Types xmlns:d="http://schemas.xmlsoap.org/ws/2005/04/discovery" xmlns:i="http://printer.example.org/2003/imaging">i:PrintBasic</d:Types>  
         <CustomMetadata netsted="true">  
            <NestedMetadata>This is a nested custom metadata.</NestedMetadata>  
         </CustomMetadata>  
      </extensions>  
   </endpointDiscovery>  
</behavior>  
```  
  
 Sie können das <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>-Verhalten auch verwenden, um Bereiche und Typen hinzuzufügen, mit denen Clients nach Diensten suchen. Im folgenden Beispiel wird gezeigt, wie Sie dies in einer clientseitigen Konfigurationsdatei durchführen können.  
  
```xml  
<behavior name="ep2Behavior">  
   <endpointDiscovery enabled="true">  
      <scopes>  
         <add scope="http://www.microsoft.com/building42/floor1"/>  
         <add scope="ldap:///ou=engineeringo=examplecomc=us"/>  
      </scopes>  
      <types>  
         <add name="test" namespace="http://example.microsoft.com/" />  
         <add name="additionalContract" namespace="http://example.microsoft.com/" />  
      </types>  
   </endpointDiscovery>  
</behavior>  
```  
  
 Weitere Informationen <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> zu <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> [WCF Discovery Overview](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)finden Sie unter WCF Discovery Overview .  
  
## <a name="binding-element-configuration"></a>Bindungselementkonfiguration  
 Die Bindungselementkonfiguration eignet sich am besten auf der Clientseite. Sie können die Konfiguration verwenden, um die Suchkriterien anzugeben, mit deren Hilfe die Dienste einer WCF-Clientanwendung ermittelt werden.  Im folgenden Beispiel wird eine benutzerdefinierte Bindung mit dem <xref:System.ServiceModel.Discovery.DiscoveryClient>-Kanal erstellt, und es werden die Suchkriterien angegeben, die einen Typ und einen Bereich enthalten. Außerdem werden Werte für die Eigenschaften <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> und <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> angegeben.  
  
```xml  
<bindings>  
   <customBinding>  
      <!-- Binding Configuration for the Application Endpoint -->  
      <binding name="discoBindingConfiguration">  
         <discoveryClient>  
            <endpoint kind="discoveryEndpoint"  
                      address="http://localhost:8000/ConfigTest/Discovery"  
                      binding="customBinding"  
                      bindingConfiguration="httpSoap12WSAddressing10"/>  
            <findCriteria duration="00:00:10" maxResults="2">  
              <types>  
                <add name="IHelloWorldService"/>  
              </types>  
              <scopes>  
                <add scope="http://www.microsoft.com/building42/floor1"/>  
              </scopes>
            </findCriteria>  
          </discoveryClient>  
          <textMessageEncoding messageVersion="Soap11"/>  
          <httpTransport />  
      </binding>
   </customBinding>
</bindings>  
```  
  
 Auf diese benutzerdefinierte Bindungskonfiguration muss von einem Clientendpunkt aus verwiesen werden:  
  
```xml  
<client>  
      <endpoint address="http://schemas.microsoft.com/discovery/dynamic"  
                binding="customBinding"  
                bindingConfiguration="discoBindingConfiguration"  
                contract="IHelloWorldService" />  
</client>  
```  
  
 Weitere Informationen zu Suchenvonkriterien finden Sie unter [Ermittlungssuche und FindCriteria](../../../../docs/framework/wcf/feature-details/discovery-find-and-findcriteria.md). Weitere Informationen zu Ermittlungs- und Bindungselementen finden Sie unter [WCF Discovery Overview](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
  
## <a name="standard-endpoint-configuration"></a>Konfiguration eines Standardendpunkts  
 Standardendpunkte sind vordefinierte Endpunkte, die Standardwerte für eine oder mehrere Eigenschaften (Adresse, Bindung oder Vertrag) bzw. einen oder mehrere Eigenschaftenwerte aufweisen, die nicht geändert werden können. Im Lieferumfang von .NET 4 sind drei Standardendpunkte für die Suche enthalten: <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> und <xref:System.ServiceModel.Discovery.DynamicEndpoint>.  Die <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>-Klasse ist ein Standardendpunkt, der für Suchvorgänge über eine UDP-Multicastbindung vorkonfiguriert ist. <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> ist ein Standardendpunkt, der für das Senden von Ankündigungsnachrichten über eine UDP-Bindung vorkonfiguriert ist. <xref:System.ServiceModel.Discovery.DynamicEndpoint> ist ein Standardendpunkt, der die Suche verwendet, um zur Laufzeit dynamisch nach der Endpunktadresse eines ermittelten Diensts zu suchen.  Standardbindungen werden mit einem `endpoint` <>-Element angegeben, das das Kind-Attribut enthält, das den Typ des hinzuzufügenden Standardendpunkts angegeben hat. Im folgenden Beispiel wird gezeigt, wie ein <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> und ein <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> addiert werden.  
  
```xml  
<services>  
   <service name="HelloWorldService">  
      <!-- ...  -->
      <endpoint kind="udpDiscoveryEndpoint" />  
   </service>  
   <service name="AnnouncementListener">  
      <endpoint kind="udpAnnouncementEndpoint" />  
   </service>  
</services>  
```  
  
 Standardendpunkte werden in einem `standardEndpoints` <>-Element konfiguriert. Das folgende Beispiel zeigt, wie Sie <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> und <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> konfigurieren.  
  
```xml  
<standardEndpoints>  
      <udpAnnouncementEndpoint>  
        <standardEndpoint
            name="udpAnnouncementEndpointSettings"
            multicastAddress="soap.udp://239.255.255.250:3703"
            maxAnnouncementDelay="00:00:00.800">  
          <transportSettings  
            duplicateMessageHistoryLength="1028"  
            maxPendingMessageCount="10"  
            maxMulticastRetransmitCount="3"  
            maxUnicastRetransmitCount="2"  
            socketReceiveBufferSize="131072"  
            timeToLive="2" />  
        </standardEndpoint>  
      </udpAnnouncementEndpoint>  
      <udpDiscoveryEndpoint>  
        <standardEndpoint  
            name="udpDiscoveryEndpointSettings"  
            multicastAddress="soap.udp://239.255.255.252:3704"  
            maxResponseDelay="00:00:00.800">  
          <transportSettings  
            duplicateMessageHistoryLength="2048"  
            maxPendingMessageCount="5"  
            maxReceivedMessageSize="8192"  
            maxBufferPoolSize="262144"/>  
        </standardEndpoint>  
      </udpDiscoveryEndpoint>
</standardEndpoints>
```  
  
 Nachdem Sie die Standardendpunktkonfiguration hinzugefügt haben, verweisen `endpoint` Sie auf die Konfiguration im <>-Element für jeden Endpunkt, wie im folgenden Beispiel gezeigt.  
  
```xml  
<services>  
   <service name="HelloWorldService">  
      <!-- ...  -->
      <endpoint kind="udpDiscoveryEndpoint" endpointConfiguration="udpDiscoveryEndpointSettings"/>  
   </service>  
   <service name="AnnouncementListener">  
      <endpoint kind="udpAnnouncementEndpoint" endpointConfiguration="udpAnnouncementEndpointSettings" >  
   </service>  
</services>  
```  
  
 Im Gegensatz zu den anderen Standardendpunkten, die in der Suche verwendet werden, geben Sie für <xref:System.ServiceModel.Discovery.DynamicEndpoint> eine Bindung und einen Vertrag an. Das folgende Beispiel zeigt, wie Sie <xref:System.ServiceModel.Discovery.DynamicEndpoint> hinzufügen und konfigurieren.  
  
```xml  
<system.serviceModel>  
    <client>  
      <endpoint kind="dynamicEndpoint" binding="basicHttpBinding" contract="IHelloWorldService" endpointConfiguration="dynamicEndpointConfiguration" />  
    </client>
   <standardEndpoints>  
      <dynamicEndpoint>  
         <standardEndpoint name="dynamicEndpointConfiguration">  
             <discoveryClientSettings>  
              <findCriteria scopeMatchBy="http://schemas.microsoft.com/ws/2008/06/discovery/rfc" duration="00:00:10" maxResults="2">  
                 <types>  
                   <add name="IHelloWorldService"/>  
                 </types>  
                 <scopes>  
                   <add scope="http://www.microsoft.com/building42/floor1"/>  
                 </scopes>  
                 <extensions>  
                   <CustomMetadata>This is custom metadata.</CustomMetadata>
                 </extensions>  
               </findCriteria>  
             </discoveryClientSettings>  
           </standardEndpoint>  
         </dynamicEndpoint>  
   </standardEndpoints>  
</system.ServiceModel>  
```  
  
 Weitere Informationen zu Standardendpunkten finden Sie unter [Standardendpunkte](standard-endpoints.md).
