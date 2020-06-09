---
title: Konfigurationsbeispiel
ms.date: 03/30/2017
ms.assetid: 75515b4a-8d70-44c8-99e0-7423df41380e
ms.openlocfilehash: 6d84085d06da117ebf13fa4bb714513aacc3abd6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594724"
---
# <a name="configuration-sample"></a><span data-ttu-id="c2a61-102">Konfigurationsbeispiel</span><span class="sxs-lookup"><span data-stu-id="c2a61-102">Configuration Sample</span></span>
<span data-ttu-id="c2a61-103">In diesem Beispiel wird veranschaulicht, wie ein Dienst mithilfe einer Konfigurationsdatei erkennbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="c2a61-103">This sample demonstrates the use of a configuration file to make a service discoverable.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c2a61-104">In diesem Beispiel wird die Suche in die Konfiguration implementiert.</span><span class="sxs-lookup"><span data-stu-id="c2a61-104">This sample implements discovery in configuration.</span></span> <span data-ttu-id="c2a61-105">Ein Beispiel, bei dem die Ermittlung im Code implementiert wird, finden Sie unter [Basic](basic-sample.md).</span><span class="sxs-lookup"><span data-stu-id="c2a61-105">For a sample that implements discovery in code, see [Basic](basic-sample.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c2a61-106">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="c2a61-106">The samples may already be installed on your computer.</span></span> <span data-ttu-id="c2a61-107">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="c2a61-107">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="c2a61-108">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c2a61-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c2a61-109">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c2a61-109">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\Configuration`  
  
## <a name="service-configuration"></a><span data-ttu-id="c2a61-110">Dienstkonfiguration</span><span class="sxs-lookup"><span data-stu-id="c2a61-110">Service Configuration</span></span>  
 <span data-ttu-id="c2a61-111">Die Konfigurationsdatei in diesem Beispiel veranschaulicht zwei Funktionen:</span><span class="sxs-lookup"><span data-stu-id="c2a61-111">The configuration file in this sample demonstrates two features:</span></span>  
  
- <span data-ttu-id="c2a61-112">Erkennbar machen des Diensts über einen standardmäßigen <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="c2a61-112">Making the service discoverable over a standard <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.</span></span>  
  
- <span data-ttu-id="c2a61-113">Anpassen von die Suche betreffenden Informationen für den Anwendungsendpunkt des Diensts und Anpassen von die Suche betreffenden Einstellungen am Standardendpunkt.</span><span class="sxs-lookup"><span data-stu-id="c2a61-113">Adjusting discovery-related information for the service’s application endpoint and adjusting some of the discovery-related settings on the standard endpoint.</span></span>  
  
 <span data-ttu-id="c2a61-114">Um die Suche zu aktivieren, müssen einige Änderungen in der Anwendungskonfigurationsdatei für den Dienst vorgenommen werden:</span><span class="sxs-lookup"><span data-stu-id="c2a61-114">To enable discovery, a few changes must be made in the application configuration file for the service:</span></span>  
  
- <span data-ttu-id="c2a61-115">Ein Suchendpunkt muss zum `<service>`-Element hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="c2a61-115">A discovery endpoint must be added to the `<service>` element.</span></span> <span data-ttu-id="c2a61-116">Dabei handelt es sich um einen standardmäßigen <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>-Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="c2a61-116">This is a standard <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> endpoint.</span></span> <span data-ttu-id="c2a61-117">Diesen Systemendpunkt ordnet die Laufzeit dem Suchdienst zu.</span><span class="sxs-lookup"><span data-stu-id="c2a61-117">This is a system endpoint that the runtime associates with the discovery service.</span></span> <span data-ttu-id="c2a61-118">Der Suchdienst lauscht an diesem Endpunkt nach Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="c2a61-118">The discovery service listens for messages on this endpoint.</span></span>  
  
- <span data-ttu-id="c2a61-119">Das `<serviceDiscovery>`-Verhalten wird zum `<serviceBehaviors>`-Abschnitt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c2a61-119">A `<serviceDiscovery>` behavior is added to the `<serviceBehaviors>` section.</span></span> <span data-ttu-id="c2a61-120">Auf diese Weise kann der Dienst zur Laufzeit erkannt werden. Der zuvor erwähnte Suchendpunkt wird zum Lauschen nach Such-`Probe`-Nachrichten und Such-`Resolve`-Nachrichten verwendet.</span><span class="sxs-lookup"><span data-stu-id="c2a61-120">This enables the service to be discovered at runtime and uses the discovery endpoint mentioned previously to listen for discovery `Probe` and `Resolve` messages.</span></span> <span data-ttu-id="c2a61-121">Mit diesen beiden Ergänzungen ist der Dienst am angegebenen Suchendpunkt erkennbar.</span><span class="sxs-lookup"><span data-stu-id="c2a61-121">With these two additions, the service is discoverable at the discovery endpoint specified.</span></span>  
  
 <span data-ttu-id="c2a61-122">Der folgende Konfigurationsausschnitt zeigt einen Dienst mit einem definierten Anwendungsendpunkt und einem definierten Suchendpunkt:</span><span class="sxs-lookup"><span data-stu-id="c2a61-122">The following config snippet shows a service with an application endpoint and a discovery endpoint defined:</span></span>  
  
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
  
 <span data-ttu-id="c2a61-123">Um Ankündigungen zu nutzen, müssen Sie einen Ankündigungsendpunkt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c2a61-123">To take advantage of announcements, you will need to add an announcement endpoint.</span></span> <span data-ttu-id="c2a61-124">Ändern Sie hierfür die Konfigurationsdatei wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c2a61-124">To do this, modify the configuration file as shown in the following code.</span></span>  
  
```xml  
<serviceDiscovery>  
            <announcementEndpoints>  
              <endpoint kind="udpAnnouncementEndpoint"/>  
            </announcementEndpoints>  
          </serviceDiscovery>  
```  
  
 <span data-ttu-id="c2a61-125">Wenn Sie dem Suchdienstverhalten einen Ankündigungsendpunkt hinzufügen, wird für den Dienst ein Standardankündigungsclient erstellt.</span><span class="sxs-lookup"><span data-stu-id="c2a61-125">Adding an announcement endpoint to the discovery service behavior creates a default announcement client for the service.</span></span> <span data-ttu-id="c2a61-126">Hiermit wird sichergestellt, dass der Dienst eine Online- und eine Offlineankündigung sendet, wenn er geöffnet bzw. geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="c2a61-126">This guarantees that the service will send an online and offline announcement when the service is opened and closed respectively.</span></span>  
  
 <span data-ttu-id="c2a61-127">In dieser Konfigurationsdatei werden neben diesen einfachen Schritten noch zusätzliche Verhaltensweisen geändert.</span><span class="sxs-lookup"><span data-stu-id="c2a61-127">This configuration file goes beyond just those simple steps by modifying additional behaviors.</span></span> <span data-ttu-id="c2a61-128">Durch die Verwendung von bestimmten Endpunkten können die Suche betreffende Informationen gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="c2a61-128">It is possible to control discovery-related information by using specific endpoints.</span></span> <span data-ttu-id="c2a61-129">Das bedeutet, dass ein Benutzer steuern kann, ob ein Endpunkt erkennbar ist. Der Benutzer kann diesen Endpunkt außerdem mit <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior.Scopes%2A> und benutzerdefinierten XML-Metadaten markieren.</span><span class="sxs-lookup"><span data-stu-id="c2a61-129">That is, a user can control whether an endpoint can be discovered and the user can also mark that endpoint with <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior.Scopes%2A> and custom XML metadata.</span></span> <span data-ttu-id="c2a61-130">Hierzu muss der Benutzer eine `behaviorConfiguration`-Eigenschaft zum Anwendungsendpunkt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c2a61-130">To do this, the user must add a `behaviorConfiguration` property to the application endpoint.</span></span> <span data-ttu-id="c2a61-131">In diesem Fall wird dem Anwendungsendpunkt die folgende Eigenschaft hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c2a61-131">In this case, the following property is added to the application endpoint.</span></span>  
  
`behaviorConfiguration="endpointBehaviorConfiguration"`  
  
 <span data-ttu-id="c2a61-132">Mit dem Verhaltenskonfigurationselement können Sie die Suche betreffende Attribute steuern.</span><span class="sxs-lookup"><span data-stu-id="c2a61-132">Now, through the behavior configuration element, you can control discovery-related attributes.</span></span> <span data-ttu-id="c2a61-133">In diesem Fall werden dem Anwendungsendpunkt zwei Bereiche hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c2a61-133">In this case, two scopes are added to the application endpoint.</span></span>  
  
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
  
 <span data-ttu-id="c2a61-134">Weitere Informationen zu Bereichen finden Sie unter Ermittlung [und FindCriteria](../feature-details/discovery-find-and-findcriteria.md).</span><span class="sxs-lookup"><span data-stu-id="c2a61-134">For more information about scopes, see [Discovery Find and FindCriteria](../feature-details/discovery-find-and-findcriteria.md).</span></span>  
  
 <span data-ttu-id="c2a61-135">Sie können auch bestimmte Details des Suchendpunkts steuern.</span><span class="sxs-lookup"><span data-stu-id="c2a61-135">You can also control specific details of the discovery endpoint.</span></span> <span data-ttu-id="c2a61-136">Dies erfolgt mithilfe von <xref:System.ServiceModel.Configuration.StandardEndpointsSection>.</span><span class="sxs-lookup"><span data-stu-id="c2a61-136">This is done through the <xref:System.ServiceModel.Configuration.StandardEndpointsSection>.</span></span> <span data-ttu-id="c2a61-137">In diesem Beispiel wird die Version des verwendeten Protokolls geändert und ein `maxResponseDelay`-Attribut wie im folgenden Codebeispiel hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c2a61-137">In this sample, the version of the protocol used is modified as well as adding a `maxResponseDelay` attribute as shown in the following code example.</span></span>  
  
```xml  
<standardEndpoints>  
   <udpDiscoveryEndpoint>  
      <standardEndpoint name="adhocDiscoveryEndpointConfiguration" discoveryVersion="WSDiscovery11" maxResponseDelay="00:00:00.600" />
   </udpDiscoveryEndpoint>  
</standardEndpoints>  
```  
  
 <span data-ttu-id="c2a61-138">Im Folgenden finden Sie die vollständige Konfigurationsdatei, die in diesem Beispiel verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="c2a61-138">The following is the complete configuration file used in this example:</span></span>  
  
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
  
## <a name="client-configuration"></a><span data-ttu-id="c2a61-139">Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="c2a61-139">Client Configuration</span></span>  
 <span data-ttu-id="c2a61-140">In der Anwendungskonfigurationsdatei für den Client wird ein `standardEndpoint` des Typs `dynamicEndpoint` zur Nutzung der Suche verwendet, wie im folgenden Konfigurationsausschnitt gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c2a61-140">In the application configuration file for the client, a `standardEndpoint` of type `dynamicEndpoint` is used to utilize discovery as shown in the following config snippet.</span></span>  
  
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
  
 <span data-ttu-id="c2a61-141">Wenn ein Client einen `dynamicEndpoint` verwendet, führt die Laufzeit die Suche automatisch durch.</span><span class="sxs-lookup"><span data-stu-id="c2a61-141">When a client is using a `dynamicEndpoint`, the runtime performs discovery automatically.</span></span> <span data-ttu-id="c2a61-142">Bei der Suche werden verschiedene Einstellungen verwendet, z. B. die im Abschnitt `discoveryClientSettings` definierten Einstellungen. Dieser Abschnitt gibt den Typ des zu verwendenden Suchendpunkts an:</span><span class="sxs-lookup"><span data-stu-id="c2a61-142">Various settings are used during discovery, such as those defined in the  `discoveryClientSettings` section, which specifies the type of discovery endpoint to use:</span></span>  
  
```xml  
<endpoint kind="udpDiscoveryEndpoint" endpointConfiguration="adhocDiscoveryEndpointConfiguration" />  
```  
  
 <span data-ttu-id="c2a61-143">Die Suchkriterien, die bei der Suche nach Diensten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="c2a61-143">The find criteria used to search for services:</span></span>  
  
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
  
 <span data-ttu-id="c2a61-144">In diesem Beispiel wird diese Funktion erweitert. Außerdem werden die vom Client verwendeten <xref:System.ServiceModel.Discovery.FindCriteria> sowie einige für die Suche verwendete Standard-`updDiscoveryEndpoint`-Eigenschaften geändert.</span><span class="sxs-lookup"><span data-stu-id="c2a61-144">This sample extends this feature and modifies the <xref:System.ServiceModel.Discovery.FindCriteria> used by the client, as well as some properties of the standard `updDiscoveryEndpoint` used for discovery.</span></span> <span data-ttu-id="c2a61-145">Die <xref:System.ServiceModel.Discovery.FindCriteria> werden geändert, um einen Bereich und einen bestimmten `scopeMatchBy`-Algorithmus sowie benutzerdefinierte Beendigungskriterien zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c2a61-145">The <xref:System.ServiceModel.Discovery.FindCriteria> are modified to use a scope and a specific `scopeMatchBy` algorithm, as well as custom termination criteria.</span></span> <span data-ttu-id="c2a61-146">Weiterhin wird im Beispiel gezeigt, wie ein Client XML-Elemente mit `Probe`-Nachrichten senden kann.</span><span class="sxs-lookup"><span data-stu-id="c2a61-146">Furthermore, the sample also shows how a client can send XML elements using `Probe` messages.</span></span> <span data-ttu-id="c2a61-147">Schließlich werden einige Änderungen am <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> vorgenommen, z. B. die Version des verwendeten Protokolls und UDP-spezifische Einstellungen, wie in der folgenden Konfigurationsdatei gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c2a61-147">Lastly, some changes are made to the <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, such as the version of the protocol used and UDP-specific settings as shown in the following configuration file.</span></span>  
  
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
  
 <span data-ttu-id="c2a61-148">Im Folgenden finden Sie die vollständige Clientkonfiguration, die im Beispiel verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c2a61-148">The following is the complete client configuration used in the sample.</span></span>  
  
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
</configuration>
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="c2a61-149">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="c2a61-149">To use this sample</span></span>  
  
1. <span data-ttu-id="c2a61-150">In diesem Beispiel werden HTTP-Endpunkte verwendet. Zur Ausführung des Beispiels müssen die richtigen URL-ACLs hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="c2a61-150">This sample uses HTTP endpoints and to run this sample, proper URL ACLs must be added.</span></span> <span data-ttu-id="c2a61-151">Weitere Informationen finden Sie unter [Konfigurieren von http und HTTPS](../feature-details/configuring-http-and-https.md).</span><span class="sxs-lookup"><span data-stu-id="c2a61-151">For more information, see [Configuring HTTP and HTTPS](../feature-details/configuring-http-and-https.md).</span></span> <span data-ttu-id="c2a61-152">Durch die Ausführung des folgenden Befehls mit erweiterten Berechtigungen werden die entsprechenden ACLs hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c2a61-152">Executing the following command at an elevated privilege should add the appropriate ACLs.</span></span> <span data-ttu-id="c2a61-153">Es empfiehlt sich, die Domäne und den Benutzernamen durch die folgenden Argumente zu ersetzen, wenn der Befehl nicht funktioniert.</span><span class="sxs-lookup"><span data-stu-id="c2a61-153">You may want to substitute your Domain and Username for the following arguments if the command does not work as is.</span></span> `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`  
  
2. <span data-ttu-id="c2a61-154">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="c2a61-154">Build the solution.</span></span>  
  
3. <span data-ttu-id="c2a61-155">Führen Sie die ausführbare Dienstdatei aus dem Buildverzeichnis aus.</span><span class="sxs-lookup"><span data-stu-id="c2a61-155">Run the service executable from the build directory.</span></span>  
  
4. <span data-ttu-id="c2a61-156">Führen Sie die ausführbare Clientanwendung aus.</span><span class="sxs-lookup"><span data-stu-id="c2a61-156">Run the client executable.</span></span> <span data-ttu-id="c2a61-157">Beachten Sie, dass der Client in der Lage ist, den Dienst zu finden.</span><span class="sxs-lookup"><span data-stu-id="c2a61-157">Note that the client is able to locate the service.</span></span>  
