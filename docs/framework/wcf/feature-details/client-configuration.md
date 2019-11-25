---
title: Clientkonfiguration
ms.date: 03/30/2017
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
ms.openlocfilehash: 6a5cbf5d536af8649b0b8bb93600e94a48c507c1
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141769"
---
# <a name="client-configuration"></a>Clientkonfiguration
Sie können die Windows Communication Foundation (WCF)-Client Konfiguration verwenden, um die Adresse, die Bindung, das Verhalten und den Vertrag, die "ABC"-Eigenschaften des Client Endpunkts anzugeben, die von Clients zum Herstellen einer Verbindung mit Dienst Endpunkten verwendet werden. Das [\<Client >](../../configure-apps/file-schema/wcf/client.md) Element verfügt über einen [\<Endpunkt >](../../configure-apps/file-schema/wcf/endpoint-of-client.md) Element, dessen Attribute zum Konfigurieren der Endpunkt ABCs verwendet werden. Diese Attribute werden im Abschnitt [Konfigurieren von Endpunkten](#configuring-endpoints) erläutert.  
  
 Das [\<Endpoint >](../../configure-apps/file-schema/wcf/endpoint-of-client.md) -Element enthält außerdem ein [\<Metadaten >](../../configure-apps/file-schema/wcf/metadata.md) Element, das verwendet wird, um Einstellungen für das Importieren und Exportieren von Metadaten anzugeben, ein [\<-Header >](../../configure-apps/file-schema/wcf/headers.md) Element, das eine Auflistung von benutzerdefinierten Adress Headern enthält, und ein [\<Identity->](../../configure-apps/file-schema/wcf/identity.md) Element, das die Authentifizierung eines Endpunkts durch andere Endpunkte ermöglicht, die Nachrichten austauschen. Die [\<Header >](../../configure-apps/file-schema/wcf/headers.md) und [\<Identity >](../../configure-apps/file-schema/wcf/identity.md) Elemente sind Teil der <xref:System.ServiceModel.EndpointAddress> und werden im Artikel " [Adressen](../../wcf/feature-details/endpoint-addresses.md) " erläutert. Links zu Themen, in denen die Verwendung von Metadatenerweiterungen erläutert wird, finden Sie im Abschnitt [Konfigurieren von Metadaten](#configuring-metadata) .  
  
## <a name="configuring-endpoints"></a>Konfigurieren von Endpunkten  
 Die Client Konfiguration ermöglicht es dem Client, einen oder mehrere Endpunkte anzugeben, die jeweils über einen eigenen Namen, eine eigene Adresse und einen eigenen Vertrag verfügen, wobei jeweils auf die [\<Bindungen >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) und [\<Verhalten >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) Elemente in der Client Konfiguration, die zum Konfigurieren dieses Endpunkts verwendet werden sollen. Die Client Konfigurationsdatei sollte "App. config" heißen, da dies der Name ist, den die WCF-Laufzeit erwartet. Das folgende Beispiel zeigt eine Clientkonfigurationsdatei.  
  
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
  
 Das optionale `name`-Attribut identifiziert eindeutig einen Endpunkt für einen angegebenen Vertrag. Es wird von <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> oder <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> verwendet, um anzugeben, welcher Endpunkt in der Clientkonfiguration das Ziel ist, und muss beim Erstellen eines Kanals zur Verarbeitung geladen werden. Ein Platzhalter-Endpunkt Konfigurations Name "\*" ist verfügbar und zeigt der <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> Methode an, dass jede Endpunkt Konfiguration in der Datei geladen werden soll, vorausgesetzt, dass genau eine verfügbar ist, und löst andernfalls eine Ausnahme aus. Wenn dieses Attribut nicht angegeben wird, wird der entsprechende Endpunkt als Standardendpunkt verwendet, der mit dem angegebenen Vertragstyp verknüpft ist. Der Standardwert für das `name`-Attribut ist eine leere Zeichenfolge, die wie jeder andere Name abgeglichen wird.  
  
 Jedem Endpunkt muss eine Adresse zugeordnet sein, um diesen suchen und identifizieren zu können. Das `address`-Attribut kann verwendet werden, um die URL anzugeben, die den Speicherort des Endpunkts bereitstellt. Die Adresse für einen Dienstendpunkt kann jedoch auch im Code angegeben werden, indem ein Uniform Resource Identifier (URI) erstellt und dem <xref:System.ServiceModel.ServiceHost> mit einer der <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>-Methoden hinzugefügt wird. Weitere Informationen finden Sie unter [Adressen](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md). Wie die Einführung zeigt, sind die [\<-Header >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) und [\<Identity >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) -Elemente Teil der <xref:System.ServiceModel.EndpointAddress> und werden auch im Thema " [Adressen](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) " erläutert.  
  
 Das `binding`-Attribut gibt den Typ der Bindung an, der vom Endpunkt beim Herstellen einer Verbindung zu einem Dienst erwartet wird. Dieser muss einen registrierten Konfigurationsabschnitt aufweisen, um darauf verweisen zu können. Im vorherigen Beispiel ist dies der [\<WSHttpBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) Abschnitt, der angibt, dass der Endpunkt eine <xref:System.ServiceModel.WSHttpBinding>verwendet. Möglicherweise sind jedoch mehrere Bindungen eines angegebenen Typs vorhanden, die vom Endpunkt verwendet werden können. Jede dieser Elemente verfügt über eine eigene [\<Bindung >](../../configure-apps/file-schema/wcf/bindings.md) Element innerhalb des (Binding) Type-Elements. Das `bindingconfiguration`-Attribut wird verwendet, um zwischen Bindungen des gleichen Typs zu unterscheiden. Der Wert wird mit dem `name`-Attribut des [\<Bindungs >](../../configure-apps/file-schema/wcf/bindings.md) Elements abgeglichen. Weitere Informationen zum Konfigurieren einer Client Bindung mithilfe der Konfiguration finden Sie unter Gewusst [wie: Angeben einer Client Bindung in der Konfiguration](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md).  
  
 Das `behaviorConfiguration`-Attribut wird verwendet, um anzugeben, welches [\<Verhalten >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) der [\<endpointBehavior->](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) der Endpunkt verwenden soll. Der Wert wird mit dem `name`-Attribut des [\<Behavior >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) -Elements abgeglichen. Ein Beispiel für die Verwendung der Konfiguration zum Angeben von Client Verhaltensweisen finden Sie unter [Konfigurieren von Client Verhalten](../../../../docs/framework/wcf/configuring-client-behaviors.md).  
  
 Das `contract`-Attribut gibt den Vertrag an, den dieser Endpunkt verfügbar macht. Dieser Wert wird dem <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> des <xref:System.ServiceModel.ServiceContractAttribute> zugeordnet. Der Standardwert ist der vollständige Typname der Klasse, die den Dienst implementiert.  
  
### <a name="configuring-metadata"></a>Konfigurieren von Metadaten  
 Mit den [\<Metadaten >](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) -Element werden Einstellungen angegeben, die zum Registrieren von Metadatenimporterweiterungen verwendet werden. Weitere Informationen zum Erweitern des Metadatensystems finden Sie unter [Erweitern des Metadatensystems](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md).  
  
## <a name="see-also"></a>Siehe auch

- [Endpunkte: Adressen, Bindungen und Verträge](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [Konfigurieren von Clientverhalten](../../../../docs/framework/wcf/configuring-client-behaviors.md)
