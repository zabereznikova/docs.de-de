---
title: Clientkonfiguration
description: Erfahren Sie, wie Sie die WCF-Client Konfiguration verwenden, um die Adresse, die Bindung, das Verhalten und den Vertrag für einen Endpunkt anzugeben, der zum Herstellen einer Verbindung mit einem Dienst verwendet wird.
ms.date: 03/30/2017
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
ms.openlocfilehash: af9101be0067311fb1a3c0e6e575f186e8ccf161
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265972"
---
# <a name="client-configuration"></a><span data-ttu-id="1fd4f-103">Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="1fd4f-103">Client Configuration</span></span>

<span data-ttu-id="1fd4f-104">Sie können die Windows Communication Foundation (WCF)-Client Konfiguration verwenden, um die Adresse, die Bindung, das Verhalten und den Vertrag, die "ABC"-Eigenschaften des Client Endpunkts anzugeben, die von Clients zum Herstellen einer Verbindung mit Dienst Endpunkten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1fd4f-104">You can use the Windows Communication Foundation (WCF) client configuration to specify the address, binding, behavior, and contract, the "ABC" properties of the client endpoint, which clients use to connect to service endpoints.</span></span> <span data-ttu-id="1fd4f-105">Das- [\<client>](../../configure-apps/file-schema/wcf/client.md) Element verfügt über ein- [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) Element, dessen Attribute zum Konfigurieren der Endpunkt ABCs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1fd4f-105">The [\<client>](../../configure-apps/file-schema/wcf/client.md) element has an [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) element whose attributes are used to configure the endpoint ABCs.</span></span> <span data-ttu-id="1fd4f-106">Diese Attribute werden im Abschnitt [Konfigurieren von Endpunkten](#configuring-endpoints) erläutert.</span><span class="sxs-lookup"><span data-stu-id="1fd4f-106">These attributes are discussed in the [Configuring Endpoints](#configuring-endpoints) section.</span></span>  
  
 <span data-ttu-id="1fd4f-107">Das [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) -Element enthält außerdem ein [\<metadata>](../../configure-apps/file-schema/wcf/metadata.md) -Element, das verwendet wird, um Einstellungen für das Importieren und Exportieren von Metadaten anzugeben, ein [\<headers>](../../configure-apps/file-schema/wcf/headers.md) -Element, das eine Auflistung von benutzerdefinierten Adress Headern enthält, und ein-Element, [\<identity>](../../configure-apps/file-schema/wcf/identity.md) das die Authentifizierung eines Endpunkts durch andere Endpunkte ermöglicht, die Nachrichten austauschen.</span><span class="sxs-lookup"><span data-stu-id="1fd4f-107">The [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) element also contains a [\<metadata>](../../configure-apps/file-schema/wcf/metadata.md) element that is used to specify settings for importing and exporting metadata, a [\<headers>](../../configure-apps/file-schema/wcf/headers.md) element that contains a collection of custom address headers, and an [\<identity>](../../configure-apps/file-schema/wcf/identity.md) element that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span> <span data-ttu-id="1fd4f-108">Das [\<headers>](../../configure-apps/file-schema/wcf/headers.md) -Element und das- [\<identity>](../../configure-apps/file-schema/wcf/identity.md) Element sind Teil der <xref:System.ServiceModel.EndpointAddress> und werden im [Adress](endpoint-addresses.md) Artikel erläutert.</span><span class="sxs-lookup"><span data-stu-id="1fd4f-108">The [\<headers>](../../configure-apps/file-schema/wcf/headers.md) and [\<identity>](../../configure-apps/file-schema/wcf/identity.md) elements are part of the <xref:System.ServiceModel.EndpointAddress> and are discussed in the [Addresses](endpoint-addresses.md) article.</span></span> <span data-ttu-id="1fd4f-109">Links zu Themen, in denen die Verwendung von Metadatenerweiterungen erläutert wird, finden Sie im Abschnitt [Konfigurieren von Metadaten](#configuring-metadata) .</span><span class="sxs-lookup"><span data-stu-id="1fd4f-109">Links to topics that explain the use of metadata extensions are provided in the [Configuring Metadata](#configuring-metadata) section.</span></span>  
  
## <a name="configuring-endpoints"></a><span data-ttu-id="1fd4f-110">Konfigurieren von Endpunkten</span><span class="sxs-lookup"><span data-stu-id="1fd4f-110">Configuring Endpoints</span></span>  

 <span data-ttu-id="1fd4f-111">Die Client Konfiguration ermöglicht es dem Client, einen oder mehrere Endpunkte anzugeben, die jeweils über einen eigenen Namen, eine eigene Adresse und einen eigenen Vertrag verfügen, wobei jeweils auf das [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) -Element und das- [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) Element in der Client Konfiguration verweisen, um diesen Endpunkt zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1fd4f-111">The client configuration is designed to allow the client to specify one or more endpoints, each with its own name, address, and contract, with each referencing the [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) and [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) elements in the client configuration to be used to configure that endpoint.</span></span> <span data-ttu-id="1fd4f-112">Die Client Konfigurationsdatei sollte mit dem Namen "App.config" benannt werden, da dies der Name ist, den die WCF-Laufzeit erwartet.</span><span class="sxs-lookup"><span data-stu-id="1fd4f-112">The client configuration file should be named "App.config" because this is the name that the WCF runtime expects.</span></span> <span data-ttu-id="1fd4f-113">Das folgende Beispiel zeigt eine Clientkonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="1fd4f-113">The following example shows a client configuration file.</span></span>  
  
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
            <!-- Add another endpoint by adding another <endpoint> element. -->
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
          <!-- Configure this binding here. -->  
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
  
 <span data-ttu-id="1fd4f-114">Das optionale `name`-Attribut identifiziert eindeutig einen Endpunkt für einen angegebenen Vertrag.</span><span class="sxs-lookup"><span data-stu-id="1fd4f-114">The optional `name` attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="1fd4f-115">Es wird von <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> oder <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> verwendet, um anzugeben, welcher Endpunkt in der Clientkonfiguration das Ziel ist, und muss beim Erstellen eines Kanals zur Verarbeitung geladen werden.</span><span class="sxs-lookup"><span data-stu-id="1fd4f-115">It is used by the <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> or by the <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> to specify which endpoint in the client configuration is being targeted and must be loaded when a channel is created to service.</span></span> <span data-ttu-id="1fd4f-116">Ein Name für die Platzhalter Endpunkt \* -Konfiguration ist verfügbar und gibt der Methode an, <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> dass jede Endpunkt Konfiguration in der Datei geladen werden soll, sofern genau eine verfügbar ist, und andernfalls wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="1fd4f-116">A wildcard endpoint configuration name "\*" is available and indicates to the <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> method that it should load any endpoint configuration in the file, provided there is precisely one available, and otherwise throws an exception.</span></span> <span data-ttu-id="1fd4f-117">Wenn dieses Attribut nicht angegeben wird, wird der entsprechende Endpunkt als Standardendpunkt verwendet, der mit dem angegebenen Vertragstyp verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="1fd4f-117">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified contract type.</span></span> <span data-ttu-id="1fd4f-118">Der Standardwert für das `name`-Attribut ist eine leere Zeichenfolge, die wie jeder andere Name abgeglichen wird.</span><span class="sxs-lookup"><span data-stu-id="1fd4f-118">The default value for the `name` attribute is an empty string which is matched like any other name.</span></span>  
  
 <span data-ttu-id="1fd4f-119">Jedem Endpunkt muss eine Adresse zugeordnet sein, um diesen suchen und identifizieren zu können.</span><span class="sxs-lookup"><span data-stu-id="1fd4f-119">Every endpoint must have an address associated with it to locate and identify the endpoint.</span></span> <span data-ttu-id="1fd4f-120">Das `address`-Attribut kann verwendet werden, um die URL anzugeben, die den Speicherort des Endpunkts bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="1fd4f-120">The `address` attribute can be used to specify the URL that provides the location of the endpoint.</span></span> <span data-ttu-id="1fd4f-121">Die Adresse für einen Dienstendpunkt kann jedoch auch im Code angegeben werden, indem ein Uniform Resource Identifier (URI) erstellt und dem <xref:System.ServiceModel.ServiceHost> mit einer der <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>-Methoden hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="1fd4f-121">But the address for a service endpoint can also be specified in code by creating a Uniform Resource Identifier (URI) and is added to the <xref:System.ServiceModel.ServiceHost> using one of the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> methods.</span></span> <span data-ttu-id="1fd4f-122">Weitere Informationen finden Sie unter [Adressen](endpoint-addresses.md).</span><span class="sxs-lookup"><span data-stu-id="1fd4f-122">For more information, see [Addresses](endpoint-addresses.md).</span></span> <span data-ttu-id="1fd4f-123">Wie die Einführung zeigt, [\<headers>](../../configure-apps/file-schema/wcf/headers.md) sind das-Element und das- [\<identity>](../../configure-apps/file-schema/wcf/identity.md) Element Teil der <xref:System.ServiceModel.EndpointAddress> und werden auch im Thema [Adressen](endpoint-addresses.md) erläutert.</span><span class="sxs-lookup"><span data-stu-id="1fd4f-123">As the introduction indicates, the [\<headers>](../../configure-apps/file-schema/wcf/headers.md) and [\<identity>](../../configure-apps/file-schema/wcf/identity.md) elements are part of the <xref:System.ServiceModel.EndpointAddress> and are also discussed in the [Addresses](endpoint-addresses.md) topic.</span></span>  
  
 <span data-ttu-id="1fd4f-124">Das `binding`-Attribut gibt den Typ der Bindung an, der vom Endpunkt beim Herstellen einer Verbindung zu einem Dienst erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="1fd4f-124">The `binding` attribute indicates the type of binding the endpoint expects to use when connecting to a service.</span></span> <span data-ttu-id="1fd4f-125">Dieser muss einen registrierten Konfigurationsabschnitt aufweisen, um darauf verweisen zu können.</span><span class="sxs-lookup"><span data-stu-id="1fd4f-125">The type must have a registered configuration section if it is to be referenced.</span></span> <span data-ttu-id="1fd4f-126">Im vorherigen Beispiel ist dies der [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) Abschnitt, der angibt, dass der Endpunkt einen verwendet <xref:System.ServiceModel.WSHttpBinding> .</span><span class="sxs-lookup"><span data-stu-id="1fd4f-126">In the previous example, this is the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) section, which indicates that the endpoint uses a <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="1fd4f-127">Möglicherweise sind jedoch mehrere Bindungen eines angegebenen Typs vorhanden, die vom Endpunkt verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="1fd4f-127">But there may be more than one binding of a given type that the endpoint can use.</span></span> <span data-ttu-id="1fd4f-128">Jede dieser Elemente verfügt über ein eigenes- [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) Element innerhalb des (Binding) Type-Elements.</span><span class="sxs-lookup"><span data-stu-id="1fd4f-128">Each of these has its own [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element within the (binding) type element.</span></span> <span data-ttu-id="1fd4f-129">Das `bindingconfiguration`-Attribut wird verwendet, um zwischen Bindungen des gleichen Typs zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="1fd4f-129">The `bindingconfiguration` attribute is used to distinguish between bindings of the same type.</span></span> <span data-ttu-id="1fd4f-130">Der Wert wird mit dem- `name` Attribut des- [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) Elements abgeglichen.</span><span class="sxs-lookup"><span data-stu-id="1fd4f-130">Its value is matched with the `name` attribute of the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element.</span></span> <span data-ttu-id="1fd4f-131">Weitere Informationen zum Konfigurieren einer Client Bindung mithilfe der Konfiguration finden Sie unter Gewusst [wie: Angeben einer Client Bindung in der Konfiguration](../how-to-specify-a-client-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="1fd4f-131">For more information about how to configure a client binding using configuration, see [How to: Specify a Client Binding in Configuration](../how-to-specify-a-client-binding-in-configuration.md).</span></span>  
  
 <span data-ttu-id="1fd4f-132">Das- `behaviorConfiguration` Attribut wird verwendet, um anzugeben, welcher [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) der [\<endpointBehaviors>](../../configure-apps/file-schema/wcf/endpointbehaviors.md) Endpunkt verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="1fd4f-132">The `behaviorConfiguration` attribute is used to specify which [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) of the [\<endpointBehaviors>](../../configure-apps/file-schema/wcf/endpointbehaviors.md) the endpoint should use.</span></span> <span data-ttu-id="1fd4f-133">Der Wert wird mit dem- `name` Attribut des- [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) Elements abgeglichen.</span><span class="sxs-lookup"><span data-stu-id="1fd4f-133">Its value is matched with the `name` attribute of the [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element.</span></span> <span data-ttu-id="1fd4f-134">Ein Beispiel für die Verwendung der Konfiguration zum Angeben von Client Verhaltensweisen finden Sie unter [Konfigurieren von Client Verhalten](../configuring-client-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="1fd4f-134">For an example of using configuration to specify client behaviors, see [Configuring Client Behaviors](../configuring-client-behaviors.md).</span></span>  
  
 <span data-ttu-id="1fd4f-135">Das `contract`-Attribut gibt den Vertrag an, den dieser Endpunkt verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="1fd4f-135">The `contract` attribute specifies which contract the endpoint is exposing.</span></span> <span data-ttu-id="1fd4f-136">Dieser Wert wird dem <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> des <xref:System.ServiceModel.ServiceContractAttribute> zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="1fd4f-136">This value maps to the <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> of the <xref:System.ServiceModel.ServiceContractAttribute>.</span></span> <span data-ttu-id="1fd4f-137">Der Standardwert ist der vollständige Typname der Klasse, die den Dienst implementiert.</span><span class="sxs-lookup"><span data-stu-id="1fd4f-137">The default value is the full type name of the class that implements the service.</span></span>  
  
### <a name="configuring-metadata"></a><span data-ttu-id="1fd4f-138">Konfigurieren von Metadaten</span><span class="sxs-lookup"><span data-stu-id="1fd4f-138">Configuring Metadata</span></span>  

 <span data-ttu-id="1fd4f-139">Das- [\<metadata>](../../configure-apps/file-schema/wcf/metadata.md) Element wird verwendet, um Einstellungen anzugeben, mit denen Metadaten-Import Erweiterungen registriert werden.</span><span class="sxs-lookup"><span data-stu-id="1fd4f-139">The [\<metadata>](../../configure-apps/file-schema/wcf/metadata.md) element is used to specify settings used to register metadata import extensions.</span></span> <span data-ttu-id="1fd4f-140">Weitere Informationen zum Erweitern des Metadatensystems finden Sie unter [Erweitern des Metadatensystems](../extending/extending-the-metadata-system.md).</span><span class="sxs-lookup"><span data-stu-id="1fd4f-140">For more information about extending the metadata system, see [Extending the Metadata System](../extending/extending-the-metadata-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fd4f-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1fd4f-141">See also</span></span>

- [<span data-ttu-id="1fd4f-142">Endpunkte: Adressen, Bindungen und Verträge</span><span class="sxs-lookup"><span data-stu-id="1fd4f-142">Endpoints: Addresses, Bindings, and Contracts</span></span>](endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="1fd4f-143">Konfigurieren von Clientverhalten</span><span class="sxs-lookup"><span data-stu-id="1fd4f-143">Configuring Client Behaviors</span></span>](../configuring-client-behaviors.md)
