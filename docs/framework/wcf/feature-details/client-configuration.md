---
title: Clientkonfiguration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 75b594d01c8a9297f3383c2648b3853c2c024b9b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="client-configuration"></a><span data-ttu-id="a3b00-102">Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="a3b00-102">Client Configuration</span></span>
<span data-ttu-id="a3b00-103">Mit der Clientkonfiguration von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] können Sie die Adressen, Bindungen, Verhaltensweisen sowie Verträge angeben, die von Clients zum Herstellen einer Verbindung mit Dienstendpunkten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a3b00-103">You can use the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client configuration to specify the address, binding, behavior, and contract, the "ABC" properties of the client endpoint, which clients use to connect to service endpoints.</span></span> <span data-ttu-id="a3b00-104">Die [ \<Client >](../../../../docs/framework/configure-apps/file-schema/wcf/client.md) Element verfügt über eine [ \<Endpunkt >](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) Element, dessen Attribute verwendet werden, um den Endpunkt ABC konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a3b00-104">The [\<client>](../../../../docs/framework/configure-apps/file-schema/wcf/client.md) element has an [\<endpoint>](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) element whose attributes are used to configure the endpoint ABCs.</span></span> <span data-ttu-id="a3b00-105">Diese Attribute werden im Abschnitt "Konfigurieren von Endpunkten" dieses Themas erläutert.</span><span class="sxs-lookup"><span data-stu-id="a3b00-105">These attributes are discussed in the "Configuring Endpoints" section of this topic.</span></span>  
  
 <span data-ttu-id="a3b00-106">Die [ \<Endpunkt >](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) -Element enthält auch eine [ \<Metadaten >](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) Element, das verwendet wird, um Einstellungen anzugeben, für das Importieren und Exportieren von Metadaten, eine [ \<Header >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) Element, das eine Auflistung von benutzerdefinierten Adressheadern enthält und eine [ \<Identität >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) Element, das die Authentifizierung eines Endpunkts durch andere Endpunkte ermöglicht. mit denen er Meldungen austauscht.</span><span class="sxs-lookup"><span data-stu-id="a3b00-106">The [\<endpoint>](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) element also contains a [\<metadata>](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) element that is used to specify settings for importing and exporting metadata , a [\<headers>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) element that contains a collection of custom address headers, and an [\<identity>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) element that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span> <span data-ttu-id="a3b00-107">Die [ \<Header >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) und [ \<Identität >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) Elemente sind Teil der <xref:System.ServiceModel.EndpointAddress> und werden im erläutert die [Adressen](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="a3b00-107">The [\<headers>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) and [\<identity>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) elements are part of the <xref:System.ServiceModel.EndpointAddress> and are discussed in the [Addresses](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) topic.</span></span> <span data-ttu-id="a3b00-108">Der Unterabschnitt "Konfigurieren von Metadaten" in diesem Thema enthält auch Hyperlinks zu Themen, in denen die Verwendung von Metadatenerweiterungen erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="a3b00-108">Links to topics that explain the use of metadata extensions are provided in the Configuring Metadata sub-section of this topic.</span></span>  
  
## <a name="configuring-endpoints"></a><span data-ttu-id="a3b00-109">Konfigurieren von Endpunkten</span><span class="sxs-lookup"><span data-stu-id="a3b00-109">Configuring Endpoints</span></span>  
 <span data-ttu-id="a3b00-110">Die Clientkonfiguration soll dem Client gestatten, geben Sie eine oder mehrere Endpunkte mit dem vorhandenen Namen, Adresse, und Vertrag verfügt jeder Verweis auf die [ \<Bindungen >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) und [ \< Verhalten >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) Elemente in der Clientkonfiguration zum Konfigurieren des jeweiligen Endpunkts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a3b00-110">The client configuration is designed to allow the client to specify one or more endpoints, each with its own name, address, and contract, with each referencing the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) and [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elements in the client configuration to be used to configure that endpoint.</span></span> <span data-ttu-id="a3b00-111">Die Clientkonfigurationsdatei sollte "App.config" benannt werden, da dieser Name von der Laufzeit von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="a3b00-111">The client configuration file should be named "App.config" because this is the name that the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] runtime expects.</span></span> <span data-ttu-id="a3b00-112">Das folgende Beispiel zeigt eine Clientkonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="a3b00-112">The following example shows a client configuration file.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
        <client>  
          <endpoint  
            name="endpoint1"  
            address="http://localhost/ServiceModelSamples/service.svc"  
            binding="wsHttpBinding"  
            bindingConfiguration="WSHttpBinding_IHello"  
            behaviorConfiguration="IHello_Behavior"  
            contract="IHello" >  
  
            <metadata>  
              <wsdlImporters>  
                <extension  
                  type="Microsoft.ServiceModel.Samples.WsdlDocumentationImporter, WsdlDocumentation"/>  
              </wsdlImporters>  
            </metadata>  
  
            <identity>  
              <servicePrincipalName value="host/localhost" />  
            </identity>  
          </endpoint>  
// Add another endpoint by adding another <endpoint> element.  
          <endpoint  
            name="endpoint2">  
           //Configure another endpoint here.  
          </endpoint>  
        </client>  
  
//The bindings section references by the bindingConfiguration endpoint attribute.  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_IHello"   
                 bypassProxyOnLocal="false"   
                 hostNameComparisonMode="StrongWildcard">  
          <readerQuotas maxDepth="32"/>  
          <reliableSession ordered="true"   
                           enabled="false" />  
          <security mode="Message">  
           //Security settings go here.  
          </security>  
        </binding>  
        <binding name="Another Binding"  
        //Configure this binding here.  
        </binding>  
          </wsHttpBinding>  
        </bindings>  
  
//The behavior section references by the behaviorConfiguration endpoint attribute.  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name=" IHello_Behavior ">  
                    <clientVia />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
  
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="a3b00-113">Das optionale `name`-Attribut identifiziert eindeutig einen Endpunkt für einen angegebenen Vertrag.</span><span class="sxs-lookup"><span data-stu-id="a3b00-113">The optional `name` attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="a3b00-114">Es wird von <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> oder <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> verwendet, um anzugeben, welcher Endpunkt in der Clientkonfiguration das Ziel ist, und muss beim Erstellen eines Kanals zur Verarbeitung geladen werden.</span><span class="sxs-lookup"><span data-stu-id="a3b00-114">It is used by the <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> or by the <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> to specify which endpoint in the client configuration is being targeted and must be loaded when a channel is created to service.</span></span> <span data-ttu-id="a3b00-115">Als Name für die Endpunktkonfiguration kann auch ein Platzhalterzeichen ("\*") verwendet werden. Dadurch wird die <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A>-Methode angewiesen, ggf. genau eine Endpunktkonfiguration in der Datei zu laden. Andernfalls wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a3b00-115">A wildcard endpoint configuration name "\*" is available and indicates to the <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> method that it should load any endpoint configuration in the file, provided there is precisely one available, and otherwise throws an exception.</span></span> <span data-ttu-id="a3b00-116">Wenn dieses Attribut nicht angegeben wird, wird der entsprechende Endpunkt als Standardendpunkt verwendet, der mit dem angegebenen Vertragstyp verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="a3b00-116">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified contract type.</span></span> <span data-ttu-id="a3b00-117">Der Standardwert für das `name`-Attribut ist eine leere Zeichenfolge, die wie jeder andere Name abgeglichen wird.</span><span class="sxs-lookup"><span data-stu-id="a3b00-117">The default value for the `name` attribute is an empty string which is matched like any other name.</span></span>  
  
 <span data-ttu-id="a3b00-118">Jedem Endpunkt muss eine Adresse zugeordnet sein, um diesen suchen und identifizieren zu können.</span><span class="sxs-lookup"><span data-stu-id="a3b00-118">Every endpoint must have an address associated with it to locate and identify the endpoint.</span></span> <span data-ttu-id="a3b00-119">Das `address`-Attribut kann verwendet werden, um die URL anzugeben, die den Speicherort des Endpunkts bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="a3b00-119">The `address` attribute can be used to specify the URL that provides the location of the endpoint.</span></span> <span data-ttu-id="a3b00-120">Die Adresse für einen Dienstendpunkt kann jedoch auch im Code angegeben werden, indem ein Uniform Resource Identifier (URI) erstellt und dem <xref:System.ServiceModel.ServiceHost> mit einer der <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>-Methoden hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="a3b00-120">But the address for a service endpoint can also be specified in code by creating a Uniform Resource Identifier (URI) and is added to the <xref:System.ServiceModel.ServiceHost> using one of the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> methods.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="a3b00-121">[Adressen](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md).</span><span class="sxs-lookup"><span data-stu-id="a3b00-121"> [Addresses](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md).</span></span> <span data-ttu-id="a3b00-122">Wie die Einführung gibt an, die [ \<Header >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) und [ \<Identität >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) Elemente sind Teil der <xref:System.ServiceModel.EndpointAddress> und wird außerdem erläutert, der [ Adressen](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="a3b00-122">As the introduction indicates, the [\<headers>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) and [\<identity>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) elements are part of the <xref:System.ServiceModel.EndpointAddress> and are also discussed in the [Addresses](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) topic.</span></span>  
  
 <span data-ttu-id="a3b00-123">Das `binding`-Attribut gibt den Typ der Bindung an, der vom Endpunkt beim Herstellen einer Verbindung zu einem Dienst erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="a3b00-123">The `binding` attribute indicates the type of binding the endpoint expects to use when connecting to a service.</span></span> <span data-ttu-id="a3b00-124">Dieser muss einen registrierten Konfigurationsabschnitt aufweisen, um darauf verweisen zu können.</span><span class="sxs-lookup"><span data-stu-id="a3b00-124">The type must have a registered configuration section if it is to be referenced.</span></span> <span data-ttu-id="a3b00-125">Im vorherigen Beispiel ist dies die [ \<WsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) Abschnitt, der angibt, dass der Endpunkt verwendet eine <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="a3b00-125">In the previous example, this is the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) section, which indicates that the endpoint uses a <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="a3b00-126">Möglicherweise sind jedoch mehrere Bindungen eines angegebenen Typs vorhanden, die vom Endpunkt verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="a3b00-126">But there may be more than one binding of a given type that the endpoint can use.</span></span> <span data-ttu-id="a3b00-127">Diese verfügen jeweils über eine eigene [ \<Bindung >](../../../../docs/framework/misc/binding.md) -Element im Typelement (Bindung).</span><span class="sxs-lookup"><span data-stu-id="a3b00-127">Each of these has its own [\<binding>](../../../../docs/framework/misc/binding.md) element within the (binding) type element.</span></span> <span data-ttu-id="a3b00-128">Das `bindingconfiguration`-Attribut wird verwendet, um zwischen Bindungen des gleichen Typs zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="a3b00-128">The `bindingconfiguration` attribute is used to distinguish between bindings of the same type.</span></span> <span data-ttu-id="a3b00-129">Der Wert stimmt mit der `name` Attribut des der [ \<Bindung >](../../../../docs/framework/misc/binding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="a3b00-129">Its value is matched with the `name` attribute of the [\<binding>](../../../../docs/framework/misc/binding.md) element.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="a3b00-130">Gewusst wie: Konfigurieren Sie einen Client-Konfiguration finden Sie unter [wie: Angeben einer Clientbindung in einer Konfiguration](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="a3b00-130"> how to configure a client binding using configuration, see [How to: Specify a Client Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md).</span></span>  
  
 <span data-ttu-id="a3b00-131">Die `behaviorConfiguration` Attribut wird verwendet, um anzugeben, welcher [ \<Verhalten >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) von der [ \<EndpointBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) vom Endpunkt verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a3b00-131">The `behaviorConfiguration` attribute is used to specify which [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) of the [\<endpointBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) the endpoint should use.</span></span> <span data-ttu-id="a3b00-132">Der Wert stimmt mit der `name` Attribut des der [ \<Verhalten >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) Element.</span><span class="sxs-lookup"><span data-stu-id="a3b00-132">Its value is matched with the `name` attribute of the [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element.</span></span> <span data-ttu-id="a3b00-133">Ein Beispiel zum Verwenden der Konfiguration zur Clientverhalten anzugeben, finden Sie unter [Konfigurieren von Clientverhalten](../../../../docs/framework/wcf/configuring-client-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="a3b00-133">For an example of using configuration to specify client behaviors, see [Configuring Client Behaviors](../../../../docs/framework/wcf/configuring-client-behaviors.md).</span></span>  
  
 <span data-ttu-id="a3b00-134">Das `contract`-Attribut gibt den Vertrag an, den dieser Endpunkt verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="a3b00-134">The `contract` attribute specifies which contract the endpoint is exposing.</span></span> <span data-ttu-id="a3b00-135">Dieser Wert wird dem <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> des <xref:System.ServiceModel.ServiceContractAttribute> zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="a3b00-135">This value maps to the <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> of the <xref:System.ServiceModel.ServiceContractAttribute>.</span></span> <span data-ttu-id="a3b00-136">Der Standardwert ist der vollständige Typname der Klasse, die den Dienst implementiert.</span><span class="sxs-lookup"><span data-stu-id="a3b00-136">The default value is the full type name of the class that implements the service.</span></span>  
  
### <a name="configuring-metadata"></a><span data-ttu-id="a3b00-137">Konfigurieren von Metadaten</span><span class="sxs-lookup"><span data-stu-id="a3b00-137">Configuring Metadata</span></span>  
 <span data-ttu-id="a3b00-138">Die [ \<Metadaten >](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) Element wird verwendet, um die Einstellungen zur Registrierung von metadatenimporterweiterungen angegeben.</span><span class="sxs-lookup"><span data-stu-id="a3b00-138">The [\<metadata>](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) element is used to specify settings used to register metadata import extensions.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="a3b00-139">Erweitern des metadatensystems finden Sie unter[Erweitern des Metadatensystems](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md).</span><span class="sxs-lookup"><span data-stu-id="a3b00-139"> extending the metadata system, see[Extending the Metadata System](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3b00-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3b00-140">See Also</span></span>  
 [<span data-ttu-id="a3b00-141">Endpunkte: Adressen, Bindungen und Verträge</span><span class="sxs-lookup"><span data-stu-id="a3b00-141">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
 [<span data-ttu-id="a3b00-142">Konfigurieren von Clientverhalten</span><span class="sxs-lookup"><span data-stu-id="a3b00-142">Configuring Client Behaviors</span></span>](../../../../docs/framework/wcf/configuring-client-behaviors.md)
