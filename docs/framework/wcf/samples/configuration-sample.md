---
title: Konfigurationsbeispiel
ms.date: 03/30/2017
ms.assetid: 75515b4a-8d70-44c8-99e0-7423df41380e
ms.openlocfilehash: 78108dc9b28657f0479e9e39ad134f03cf6c877b
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714954"
---
# <a name="configuration-sample"></a>Konfigurationsbeispiel
In diesem Beispiel wird veranschaulicht, wie ein Dienst mithilfe einer Konfigurationsdatei erkennbar gemacht wird.  
  
> [!NOTE]
> In diesem Beispiel wird die Suche in die Konfiguration implementiert. Ein Beispiel, bei dem die Ermittlung im Code implementiert wird, finden Sie unter [Basic](../../../../docs/framework/wcf/samples/basic-sample.md).  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\Configuration`  
  
## <a name="service-configuration"></a>Dienstkonfiguration  
 Die Konfigurationsdatei in diesem Beispiel veranschaulicht zwei Funktionen:  
  
- Erkennbar machen des Diensts über einen standardmäßigen <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.  
  
- Anpassen von die Suche betreffenden Informationen für den Anwendungsendpunkt des Diensts und Anpassen von die Suche betreffenden Einstellungen am Standardendpunkt.  
  
 Um die Suche zu aktivieren, müssen einige Änderungen in der Anwendungskonfigurationsdatei für den Dienst vorgenommen werden:  
  
- Ein Suchendpunkt muss zum `<service>`-Element hinzugefügt werden. Dabei handelt es sich um einen standardmäßigen <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>-Endpunkt. Diesen Systemendpunkt ordnet die Laufzeit dem Suchdienst zu. Der Suchdienst lauscht an diesem Endpunkt nach Nachrichten.  
  
- Das `<serviceDiscovery>`-Verhalten wird zum `<serviceBehaviors>`-Abschnitt hinzugefügt. Auf diese Weise kann der Dienst zur Laufzeit erkannt werden. Der zuvor erwähnte Suchendpunkt wird zum Lauschen nach Such-`Probe`-Nachrichten und Such-`Resolve`-Nachrichten verwendet. Mit diesen beiden Ergänzungen ist der Dienst am angegebenen Suchendpunkt erkennbar.  
  
 Der folgende Konfigurationsausschnitt zeigt einen Dienst mit einem definierten Anwendungsendpunkt und einem definierten Suchendpunkt:  
  
```xml
<services>  
        <service name="Microsoft.Samples.Discovery.CalculatorService"  
                 behaviorConfiguration="calculatorServiceBehavior">  
          <endpoint address=""  
                    binding="wsHttpBinding"  
                    contract="Microsoft.Samples.Discovery.ICalculatorService"  
                    behaviorConfiguration="endpointBehaviorConfiguration" />  
          <endpoint name="udpDiscovery"   
                    kind="udpDiscoveryEndpoint"   
                endpointConfiguration="adhocDiscoveryEndpointConfiguration"/>        </service>  
      </services>  
```  
  
 Um Ankündigungen zu nutzen, müssen Sie einen Ankündigungsendpunkt hinzufügen. Ändern Sie hierfür die Konfigurationsdatei wie im folgenden Code gezeigt.  
  
```xml  
<serviceDiscovery>  
            <announcementEndpoints>  
              <endpoint kind="udpAnnouncementEndpoint"/>  
            </announcementEndpoints>  
          </serviceDiscovery>  
```  
  
 Wenn Sie dem Suchdienstverhalten einen Ankündigungsendpunkt hinzufügen, wird für den Dienst ein Standardankündigungsclient erstellt. Hiermit wird sichergestellt, dass der Dienst eine Online- und eine Offlineankündigung sendet, wenn er geöffnet bzw. geschlossen wird.  
  
 In dieser Konfigurationsdatei werden neben diesen einfachen Schritten noch zusätzliche Verhaltensweisen geändert. Durch die Verwendung von bestimmten Endpunkten können die Suche betreffende Informationen gesteuert werden. Das bedeutet, dass ein Benutzer steuern kann, ob ein Endpunkt erkennbar ist. Der Benutzer kann diesen Endpunkt außerdem mit <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior.Scopes%2A> und benutzerdefinierten XML-Metadaten markieren. Hierzu muss der Benutzer eine `behaviorConfiguration`-Eigenschaft zum Anwendungsendpunkt hinzufügen. In diesem Fall wird dem Anwendungsendpunkt die folgende Eigenschaft hinzugefügt.  
  
`behaviorConfiguration="endpointBehaviorConfiguration"`  
  
 Mit dem Verhaltenskonfigurationselement können Sie die Suche betreffende Attribute steuern. In diesem Fall werden dem Anwendungsendpunkt zwei Bereiche hinzugefügt.  
  
```xml  
<endpointBehaviors>  
          <behavior name="endpointBehaviorConfiguration">  
            <endpointDiscovery>  
              <scopes>  
                <add scope="http://www.example.com/calculator"/>  
                <add scope="ldap:///ou=engineering,o=examplecom,c=us"/>  
              </scopes>  
            </endpointDiscovery>  
  
          </behavior>            
        </endpointBehaviors>  
```  
  
 Weitere Informationen zu Bereichen finden Sie unter Ermittlung [und FindCriteria](../../../../docs/framework/wcf/feature-details/discovery-find-and-findcriteria.md).  
  
 Sie können auch bestimmte Details des Suchendpunkts steuern. Dies erfolgt mithilfe von <xref:System.ServiceModel.Configuration.StandardEndpointsSection>. In diesem Beispiel wird die Version des verwendeten Protokolls geändert und ein `maxResponseDelay`-Attribut wie im folgenden Codebeispiel hinzugefügt.  
  
```xml  
<standardEndpoints>  
   <udpDiscoveryEndpoint>  
      <standardEndpoint name="adhocDiscoveryEndpointConfiguration" discoveryVersion="WSDiscovery11" maxResponseDelay="00:00:00.600" />    
   </udpDiscoveryEndpoint>  
</standardEndpoints>  
```  
  
 Im Folgenden finden Sie die vollständige Konfigurationsdatei, die in diesem Beispiel verwendet wird:  
  
```xml  
<configuration>  
    <system.serviceModel>  
  
      <services>  
        <service name="Microsoft.Samples.Discovery.CalculatorService"  
                 behaviorConfiguration="calculatorServiceBehavior">  
          <endpoint address=""  
                    binding="wsHttpBinding"  
                    contract="Microsoft.Samples.Discovery.ICalculatorService"  
                    behaviorConfiguration="endpointBehaviorConfiguration" />  
         <!-- Define the discovery endpoint -->            
<endpoint name="udpDiscovery" kind="udpDiscoveryEndpoint" endpointConfiguration="adhocDiscoveryEndpointConfiguration"/>        </service>  
      </services>  
  
      <behaviors>  
  
        <serviceBehaviors>  
          <behavior name="calculatorServiceBehavior">  
  
            <!-- Add an announcement endpoint -->  
            <serviceDiscovery>  
              <announcementEndpoints>  
                <endpoint kind="udpAnnouncementEndpoint"/>  
              </announcementEndpoints>  
            </serviceDiscovery>  
          </behavior>  
        </serviceBehaviors>  
  
        <endpointBehaviors>  
          <behavior name="endpointBehaviorConfiguration">  
            <!-- Add scopes used to identify the service -->  
            <endpointDiscovery>  
              <scopes>  
                <add scope="http://www.example.com/calculator"/>  
                <add scope="ldap:///ou=engineering,o=examplecom,c=us"/>  
              </scopes>  
            </endpointDiscovery>  
  
          </behavior>            
        </endpointBehaviors>  
  
      </behaviors>  
  
      <standardEndpoints>  
        <udpDiscoveryEndpoint>  
         <!-- Configure the UDP discovery endpoint -->  
          <standardEndpoint name="adhocDiscoveryEndpointConfiguration" discoveryVersion="WSDiscovery11" maxResponseDelay="00:00:00.600" />    
        </udpDiscoveryEndpoint>  
      </standardEndpoints>  
  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="client-configuration"></a>Clientkonfiguration  
 In der Anwendungskonfigurationsdatei für den Client wird ein `standardEndpoint` des Typs `dynamicEndpoint` zur Nutzung der Suche verwendet, wie im folgenden Konfigurationsausschnitt gezeigt.  
  
```xml  
<client>  
   <!--  Create an endpoint, make kind="dynamicEndpoint" and use the endpointConfiguration to change settings of DynamicEndpoint -->  
   <endpoint name="calculatorEndpoint"  
             binding="wsHttpBinding"  
             contract="ICalculatorService"  
             kind ="dynamicEndpoint"  
             endpointConfiguration="dynamicEndpointConfiguration">  
   </endpoint>  
</client>  
```  
  
 Wenn ein Client einen `dynamicEndpoint` verwendet, führt die Laufzeit die Suche automatisch durch. Bei der Suche werden verschiedene Einstellungen verwendet, z. B. die im Abschnitt `discoveryClientSettings` definierten Einstellungen. Dieser Abschnitt gibt den Typ des zu verwendenden Suchendpunkts an:  
  
```xml  
<endpoint kind="udpDiscoveryEndpoint" endpointConfiguration="adhocDiscoveryEndpointConfiguration" />  
```  
  
 Die Suchkriterien, die bei der Suche nach Diensten verwendet werden:  
  
```xml  
<!-- Add Scopes, ScopeMatchBy, Extensions and termination criteria in FindCriteria -->  
<findCriteria scopeMatchBy="http://schemas.microsoft.com/ws/2008/06/discovery/rfc" duration="00:00:10" maxResults="1">  
   <scopes>  
      <add scope="http://www.microsoft.com/building42/floor1"/>  
   </scopes>  
   <!-- These extensions are sent from the client to the service as part of the probe message -->  
   <extensions>  
      <CustomMetadata>This is custom metadata that is sent to the service along with the client's find request.</CustomMetadata>  
   </extensions>  
</findCriteria>  
```  
  
 In diesem Beispiel wird diese Funktion erweitert. Außerdem werden die vom Client verwendeten <xref:System.ServiceModel.Discovery.FindCriteria> sowie einige für die Suche verwendete Standard-`updDiscoveryEndpoint`-Eigenschaften geändert. Die <xref:System.ServiceModel.Discovery.FindCriteria> werden geändert, um einen Bereich und einen bestimmten `scopeMatchBy`-Algorithmus sowie benutzerdefinierte Beendigungskriterien zu verwenden. Weiterhin wird im Beispiel gezeigt, wie ein Client XML-Elemente mit `Probe`-Nachrichten senden kann. Schließlich werden einige Änderungen am <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> vorgenommen, z. B. die Version des verwendeten Protokolls und UDP-spezifische Einstellungen, wie in der folgenden Konfigurationsdatei gezeigt.  
  
```xml  
<udpDiscoveryEndpoint>    
        <!-- Specify the discovery protocol version and UDP transport settings. -->   
        <standardEndpoint name="adhocDiscoveryEndpointConfiguration" discoveryVersion="WSDiscovery11">  
          <transportSettings duplicateMessageHistoryLength="2048"  
                             maxPendingMessageCount="5"  
                             maxReceivedMessageSize="8192"  
                             maxBufferPoolSize="262144"/>  
        </standardEndpoint>        
      </udpDiscoveryEndpoint>  
```  
  
 Im Folgenden finden Sie die vollständige Clientkonfiguration, die im Beispiel verwendet wird.  
  
```xml  
<configuration>  
  <system.serviceModel>  
  
    <client>  
      <!--  Create an endpoint, make kind="dynamicEndpoint" and use the endpointConfiguration to change settings of DynamicEndpoint -->  
      <endpoint name="calculatorEndpoint"  
                binding="wsHttpBinding"  
                contract="ICalculatorService"  
                kind ="dynamicEndpoint"  
                endpointConfiguration="dynamicEndpointConfiguration">  
      </endpoint>  
    </client>  
  
    <standardEndpoints>  
  
      <dynamicEndpoint>        
        <standardEndpoint name="dynamicEndpointConfiguration">  
          <discoveryClientSettings>  
            <!-- Controls where the discovery happens. In this case, Probe message is sent over UdpDiscoveryEndpoint. -->  
            <endpoint kind="udpDiscoveryEndpoint" endpointConfiguration="adhocDiscoveryEndpointConfiguration" />  
  
            <!-- Add Scopes, ScopeMatchBy, Extensions and termination criteria in FindCriteria -->  
            <findCriteria scopeMatchBy="http://schemas.microsoft.com/ws/2008/06/discovery/rfc" duration="00:00:10" maxResults="1">  
              <scopes>  
                <add scope="http://www.microsoft.com/building42/floor1"/>  
              </scopes>  
              <!-- These extensions are sent from the client to the service as part of the probe message -->  
              <extensions>  
                <CustomMetadata>This is custom metadata that is sent to the service along with the client's find request.</CustomMetadata>  
              </extensions>  
            </findCriteria>  
          </discoveryClientSettings>  
        </standardEndpoint>     
      </dynamicEndpoint>  
  
      <udpDiscoveryEndpoint>    
        <!-- Specify the discovery protocol version and UDP transport settings. -->   
        <standardEndpoint name="adhocDiscoveryEndpointConfiguration" discoveryVersion="WSDiscovery11">  
          <transportSettings duplicateMessageHistoryLength="2048"  
                             maxPendingMessageCount="5"  
                             maxReceivedMessageSize="8192"  
                             maxBufferPoolSize="262144"/>  
        </standardEndpoint>        
      </udpDiscoveryEndpoint>  
  
    </standardEndpoints>  
  
  </system.serviceModel>  
```  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1. In diesem Beispiel werden HTTP-Endpunkte verwendet. zum Ausführen dieses Beispiels müssen die richtigen URL-ACLs hinzugefügt werden. Weitere Informationen finden Sie unter [Konfigurieren von http und HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353) . Durch die Ausführung des folgenden Befehls mit erweiterten Berechtigungen werden die entsprechenden ACLs hinzugefügt. Es empfiehlt sich, die Domäne und den Benutzernamen durch die folgenden Argumente zu ersetzen, wenn der Befehl nicht funktioniert. `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`  
  
2. Erstellen Sie die Projektmappe.  
  
3. Führen Sie die ausführbare Dienstdatei aus dem Buildverzeichnis aus.  
  
4. Führen Sie die ausführbare Clientanwendung aus. Beachten Sie, dass der Client in der Lage ist, den Dienst zu finden.  
