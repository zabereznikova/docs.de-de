---
title: Konfigurieren der Suche in einer Konfigurationsdatei
ms.date: 03/30/2017
ms.assetid: b9884c11-8011-4763-bc2c-c526b80175d0
ms.openlocfilehash: b2e604f6168e4adff36bfb0c22861124743b358d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185331"
---
# <a name="configuring-discovery-in-a-configuration-file"></a><span data-ttu-id="01d18-102">Konfigurieren der Suche in einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="01d18-102">Configuring Discovery in a Configuration File</span></span>
<span data-ttu-id="01d18-103">Es gibt vier Hauptgruppen von Konfigurationseinstellungen, die bei der Suche verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="01d18-103">There are four major groups of configuration settings used in discovery.</span></span> <span data-ttu-id="01d18-104">In diesem Thema werden die Gruppen beschrieben und jeweils Beispiele für deren Konfiguration angegeben.</span><span class="sxs-lookup"><span data-stu-id="01d18-104">This topic will briefly describe each and show examples of how to configure them.</span></span> <span data-ttu-id="01d18-105">Nach jedem Abschnitt folgt ein Link zu einer ausführlicheren Dokumentation der einzelnen Bereiche.</span><span class="sxs-lookup"><span data-stu-id="01d18-105">Following each section will be a link to more in-depth documentation about each area.</span></span>  
  
## <a name="behavior-configuration"></a><span data-ttu-id="01d18-106">Verhaltenskonfiguration</span><span class="sxs-lookup"><span data-stu-id="01d18-106">Behavior Configuration</span></span>  
 <span data-ttu-id="01d18-107">Bei der Suche werden Dienstverhalten und Endpunktverhalten verwendet.</span><span class="sxs-lookup"><span data-stu-id="01d18-107">Discovery uses service behaviors and endpoint behaviors.</span></span> <span data-ttu-id="01d18-108">Das <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>-Verhalten aktiviert die Suche für alle Endpunkte eines Diensts und ermöglicht Ihnen das Angeben von Ankündigungsendpunkten.</span><span class="sxs-lookup"><span data-stu-id="01d18-108">The <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> behavior enables discovery for all of a service’s endpoints and allows you to specify announcement endpoints.</span></span>  <span data-ttu-id="01d18-109">Das folgende Beispiel zeigt, wie Sie das <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> hinzufügen und einen Ankündigungsendpunkt angeben.</span><span class="sxs-lookup"><span data-stu-id="01d18-109">The following example shows how to add the <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> and specify an announcement endpoint.</span></span>  
  
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
```  
  
 <span data-ttu-id="01d18-110">Nachdem Sie das Verhalten angegeben haben, verweisen Sie auf ein <`service`>-Element, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="01d18-110">Once you specify the behavior, reference it from a <`service`> element as shown in the following sample.</span></span>  
  
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
    </service>  
```  
  
 <span data-ttu-id="01d18-111">Damit ein Dienst erkennbar ist, müssen Sie auch einen Suchendpunkt hinzufügen. Im Beispiel oben wird ein <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>-Standardendpunkt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="01d18-111">In order for a service to be discoverable, you must also add a discovery endpoint, the example above adds a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> standard endpoint.</span></span>  
  
 <span data-ttu-id="01d18-112">Wenn Sie Ankündigungsendpunkte hinzufügen, müssen Sie dem `services` <>-Element auch einen Ankündigungslistenerdienst hinzufügen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="01d18-112">When you add announcement endpoints you must also add an announcement listener service to the <`services`> element as shown in the following example.</span></span>  
  
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
```  
  
 <span data-ttu-id="01d18-113">Das <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>-Verhalten wird verwendet, um die Suche nach einem bestimmten Endpunkt zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="01d18-113">The <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> behavior is used to enable or disable discovery of a specific endpoint.</span></span>  <span data-ttu-id="01d18-114">Im folgenden Beispiel wird ein Dienst mit zwei Anwendungsendpunkten konfiguriert, wobei die Suche für einen Endpunkt aktiviert und für den anderen deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="01d18-114">The following example configures a service with two application endpoints, one with discovery enabled and one with discovery disabled.</span></span> <span data-ttu-id="01d18-115">Für jeden Endpunkt wird ein <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>-Verhalten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="01d18-115">For each endpoint an <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> behavior is added.</span></span>  
  
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
```  
  
 <span data-ttu-id="01d18-116">Sie können das <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>-Verhalten auch verwenden, um den vom Dienst zurückgegebenen Endpunktmetadaten benutzerdefinierte Metadaten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="01d18-116">The <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> behavior can also be used to add custom metadata to the endpoint metadata returned by the service.</span></span> <span data-ttu-id="01d18-117">Das folgende Beispiel zeigt die erforderliche Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="01d18-117">The following example shows how to do this.</span></span>  
  
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
  
 <span data-ttu-id="01d18-118">Sie können das <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>-Verhalten auch verwenden, um Bereiche und Typen hinzuzufügen, mit denen Clients nach Diensten suchen.</span><span class="sxs-lookup"><span data-stu-id="01d18-118">The <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> behavior can also be used to add scopes and types that clients use to search for services.</span></span> <span data-ttu-id="01d18-119">Im folgenden Beispiel wird gezeigt, wie Sie dies in einer clientseitigen Konfigurationsdatei durchführen können.</span><span class="sxs-lookup"><span data-stu-id="01d18-119">The following example shows how to do this in a client side configuration file.</span></span>  
  
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
  
 <span data-ttu-id="01d18-120">Weitere Informationen <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> zu <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> [WCF Discovery Overview](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)finden Sie unter WCF Discovery Overview .</span><span class="sxs-lookup"><span data-stu-id="01d18-120">For more information about <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> and <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> see [WCF Discovery Overview](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md).</span></span>  
  
## <a name="binding-element-configuration"></a><span data-ttu-id="01d18-121">Bindungselementkonfiguration</span><span class="sxs-lookup"><span data-stu-id="01d18-121">Binding Element Configuration</span></span>  
 <span data-ttu-id="01d18-122">Die Bindungselementkonfiguration eignet sich am besten auf der Clientseite.</span><span class="sxs-lookup"><span data-stu-id="01d18-122">Binding element configuration is most interesting on the client side.</span></span> <span data-ttu-id="01d18-123">Sie können die Konfiguration verwenden, um die Suchkriterien anzugeben, mit deren Hilfe die Dienste einer WCF-Clientanwendung ermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="01d18-123">You can use configuration to specify the find criteria used to discover services from a WCF client application.</span></span>  <span data-ttu-id="01d18-124">Im folgenden Beispiel wird eine benutzerdefinierte Bindung mit dem <xref:System.ServiceModel.Discovery.DiscoveryClient>-Kanal erstellt, und es werden die Suchkriterien angegeben, die einen Typ und einen Bereich enthalten.</span><span class="sxs-lookup"><span data-stu-id="01d18-124">The following example creates a custom binding with the <xref:System.ServiceModel.Discovery.DiscoveryClient> channel and specifies find criteria that includes a type and scope.</span></span> <span data-ttu-id="01d18-125">Außerdem werden Werte für die Eigenschaften <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> und <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> angegeben.</span><span class="sxs-lookup"><span data-stu-id="01d18-125">In addition it specifies values for the <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> and <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> properties.</span></span>  
  
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
```  
  
 <span data-ttu-id="01d18-126">Auf diese benutzerdefinierte Bindungskonfiguration muss von einem Clientendpunkt aus verwiesen werden:</span><span class="sxs-lookup"><span data-stu-id="01d18-126">This custom binding configuration must be referenced by a client endpoint:</span></span>  
  
```xml  
<client>  
      <endpoint address="http://schemas.microsoft.com/discovery/dynamic"  
                binding="customBinding"  
                bindingConfiguration="discoBindingConfiguration"  
                contract="IHelloWorldService" />  
    </client>  
```  
  
 <span data-ttu-id="01d18-127">Weitere Informationen zu Suchenvonkriterien finden Sie unter [Ermittlungssuche und FindCriteria](../../../../docs/framework/wcf/feature-details/discovery-find-and-findcriteria.md).</span><span class="sxs-lookup"><span data-stu-id="01d18-127">For more information about find criteria see [Discovery Find and FindCriteria](../../../../docs/framework/wcf/feature-details/discovery-find-and-findcriteria.md).</span></span> <span data-ttu-id="01d18-128">Weitere Informationen zu Ermittlungs- und Bindungselementen finden Sie unter [WCF Discovery Overview](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)</span><span class="sxs-lookup"><span data-stu-id="01d18-128">For more information about discovery and binding elements see, [WCF Discovery Overview](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)</span></span>  
  
## <a name="standard-endpoint-configuration"></a><span data-ttu-id="01d18-129">Konfiguration eines Standardendpunkts</span><span class="sxs-lookup"><span data-stu-id="01d18-129">Standard Endpoint Configuration</span></span>  
 <span data-ttu-id="01d18-130">Standardendpunkte sind vordefinierte Endpunkte, die Standardwerte für eine oder mehrere Eigenschaften (Adresse, Bindung oder Vertrag) bzw. einen oder mehrere Eigenschaftenwerte aufweisen, die nicht geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="01d18-130">Standard endpoints are predefined endpoints that have default values for one or more properties (address, binding, or contract) or one or more property values that cannot change.</span></span> <span data-ttu-id="01d18-131">Im Lieferumfang von .NET 4 sind drei Standardendpunkte für die Suche enthalten: <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> und <xref:System.ServiceModel.Discovery.DynamicEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="01d18-131">.NET 4 ships with 3 discovery related standard endpoints: <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>, and <xref:System.ServiceModel.Discovery.DynamicEndpoint>.</span></span>  <span data-ttu-id="01d18-132">Die <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>-Klasse ist ein Standardendpunkt, der für Suchvorgänge über eine UDP-Multicastbindung vorkonfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="01d18-132">The <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> is a standard endpoint that is pre-configured for discovery operations over a UDP multicast binding.</span></span> <span data-ttu-id="01d18-133"><xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> ist ein Standardendpunkt, der für das Senden von Ankündigungsnachrichten über eine UDP-Bindung vorkonfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="01d18-133">The <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> is a standard endpoint that is pre-configured to send announcement messages over a UDP binding.</span></span> <span data-ttu-id="01d18-134"><xref:System.ServiceModel.Discovery.DynamicEndpoint> ist ein Standardendpunkt, der die Suche verwendet, um zur Laufzeit dynamisch nach der Endpunktadresse eines ermittelten Diensts zu suchen.</span><span class="sxs-lookup"><span data-stu-id="01d18-134">The <xref:System.ServiceModel.Discovery.DynamicEndpoint> is a standard endpoint that uses discovery to find the endpoint address of a discovered service dynamically at runtime.</span></span>  <span data-ttu-id="01d18-135">Standardbindungen werden mit einem `endpoint` <>-Element angegeben, das das Kind-Attribut enthält, das den Typ des hinzuzufügenden Standardendpunkts angegeben hat.</span><span class="sxs-lookup"><span data-stu-id="01d18-135">Standard bindings are specified with an <`endpoint`> element that contains kind attribute that specified the type of standard endpoint to add.</span></span> <span data-ttu-id="01d18-136">Im folgenden Beispiel wird gezeigt, wie ein <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> und ein <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> addiert werden.</span><span class="sxs-lookup"><span data-stu-id="01d18-136">The following example shows how to add a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> and a <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>.</span></span>  
  
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
  
 <span data-ttu-id="01d18-137">Standardendpunkte werden in einem `standardEndpoints` <>-Element konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="01d18-137">Standard endpoints are configured in a <`standardEndpoints`> element.</span></span> <span data-ttu-id="01d18-138">Das folgende Beispiel zeigt, wie Sie <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> und <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="01d18-138">The following example shows how to configure the <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> and the <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>.</span></span>  
  
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
```  
  
 <span data-ttu-id="01d18-139">Nachdem Sie die Standardendpunktkonfiguration hinzugefügt haben, verweisen `endpoint` Sie auf die Konfiguration im <>-Element für jeden Endpunkt, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="01d18-139">Once you’ve added the standard endpoint configuration, reference the configuration in the <`endpoint`> element for each endpoint as shown in the following sample.</span></span>  
  
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
  
 <span data-ttu-id="01d18-140">Im Gegensatz zu den anderen Standardendpunkten, die in der Suche verwendet werden, geben Sie für <xref:System.ServiceModel.Discovery.DynamicEndpoint> eine Bindung und einen Vertrag an.</span><span class="sxs-lookup"><span data-stu-id="01d18-140">Unlike the other standard endpoints used in discovery, you specify a binding and contract for <xref:System.ServiceModel.Discovery.DynamicEndpoint>.</span></span> <span data-ttu-id="01d18-141">Das folgende Beispiel zeigt, wie Sie <xref:System.ServiceModel.Discovery.DynamicEndpoint> hinzufügen und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="01d18-141">The following example shows how to add and configure a <xref:System.ServiceModel.Discovery.DynamicEndpoint>.</span></span>  
  
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
  
 <span data-ttu-id="01d18-142">Weitere Informationen zu Standardendpunkten finden Sie unter [Standardendpunkte](standard-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="01d18-142">For more information about standard endpoints see [Standard Endpoints](standard-endpoints.md).</span></span>
