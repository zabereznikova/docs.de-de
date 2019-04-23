---
title: Clientkonfiguration
ms.date: 03/30/2017
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
ms.openlocfilehash: b9975c6caeedc94bf4a7773e71a95eb0d8c7aed2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59144689"
---
# <a name="client-configuration"></a>Clientkonfiguration
Sie können die Windows Communication Foundation (WCF) Clientkonfiguration verwenden, an die Adresse, Bindung, Verhalten und Vertrag, der Eigenschaften "ABC" den Clientendpunkt an, welche Clients verwenden, um den Dienstendpunkten herstellen. Die [ \<Client >](../../configure-apps/file-schema/wcf/client.md) Element verfügt über eine [ \<Endpunkt >](../../configure-apps/file-schema/wcf/endpoint-of-client.md) Element, dessen Attribute werden zum Konfigurieren des Endpunkts abc. Diese Attribute werden in erläutert die [Konfigurieren von Endpunkten](#configuring-endpoints) Abschnitt.  
  
 Die [ \<Endpunkt >](../../configure-apps/file-schema/wcf/endpoint-of-client.md) -Element enthält auch eine [ \<Metadaten >](../../configure-apps/file-schema/wcf/metadata.md) -Element, das verwendet wird, geben Sie Einstellungen für das Importieren und Exportieren von Metadaten eine [ \<Header >](../../configure-apps/file-schema/wcf/headers.md) -Element, das eine Auflistung von benutzerdefinierten Adressheadern enthält und eine [ \<Identität >](../../configure-apps/file-schema/wcf/identity.md) Element, das die Authentifizierung eines Endpunkts durch andere Endpunkte ermöglicht. mit denen er Meldungen austauscht. Die [ \<Header >](../../configure-apps/file-schema/wcf/headers.md) und [ \<Identität >](../../configure-apps/file-schema/wcf/identity.md) Elemente sind Teil der <xref:System.ServiceModel.EndpointAddress> und finden Sie im der [Adressen](../../wcf/feature-details/endpoint-addresses.md) Artikel. Links zu Themen, in denen die Verwendung von Metadatenerweiterungen erläutert finden Sie unter den [Konfigurieren von Metadaten](#configuring-metadata) Abschnitt.  
  
## <a name="configuring-endpoints"></a>Konfigurieren von Endpunkten  
 Die Clientkonfiguration soll es ermöglicht den Client an eine oder mehrere Endpunkte, die jeweils über einen eigenen Namen, Adresse und Vertrag verfügt jeder Verweis auf die [ \<Bindungen >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) und [ \< Verhaltensweisen >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) Elemente in der Clientkonfiguration zum Konfigurieren des jeweiligen Endpunkts verwendet werden. Die Clientkonfigurationsdatei sollte "App.config" benannt werden, da dies der Name ist, die die WCF-Laufzeit erwartet. Das folgende Beispiel zeigt eine Clientkonfigurationsdatei.  
  
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
  
 Das optionale `name`-Attribut identifiziert eindeutig einen Endpunkt für einen angegebenen Vertrag. Es wird von <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> oder <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> verwendet, um anzugeben, welcher Endpunkt in der Clientkonfiguration das Ziel ist, und muss beim Erstellen eines Kanals zur Verarbeitung geladen werden. Einen Platzhalter-Endpunkt-Konfigurationsnamen "\*" verfügbar ist, und gibt an, um die <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> Methode, die jede Endpunktkonfiguration in der Datei geladen werden soll, vorausgesetzt, es ist genau einem andernfalls löst eine Ausnahme aus. Wenn dieses Attribut nicht angegeben wird, wird der entsprechende Endpunkt als Standardendpunkt verwendet, der mit dem angegebenen Vertragstyp verknüpft ist. Der Standardwert für das `name`-Attribut ist eine leere Zeichenfolge, die wie jeder andere Name abgeglichen wird.  
  
 Jedem Endpunkt muss eine Adresse zugeordnet sein, um diesen suchen und identifizieren zu können. Das `address`-Attribut kann verwendet werden, um die URL anzugeben, die den Speicherort des Endpunkts bereitstellt. Die Adresse für einen Dienstendpunkt kann jedoch auch im Code angegeben werden, indem ein Uniform Resource Identifier (URI) erstellt und dem <xref:System.ServiceModel.ServiceHost> mit einer der <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>-Methoden hinzugefügt wird. Weitere Informationen finden Sie unter [Adressen](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md). Wie die Einführung gibt an, die [ \<Header >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) und [ \<Identität >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) Elemente sind Teil der <xref:System.ServiceModel.EndpointAddress> und werden auch in behandelt die [ Adressen](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) Thema.  
  
 Das `binding`-Attribut gibt den Typ der Bindung an, der vom Endpunkt beim Herstellen einer Verbindung zu einem Dienst erwartet wird. Dieser muss einen registrierten Konfigurationsabschnitt aufweisen, um darauf verweisen zu können. Im vorherigen Beispiel ist dies die [ \<WsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) Abschnitt, der angibt, dass der Endpunkt verwendet einen <xref:System.ServiceModel.WSHttpBinding>. Möglicherweise sind jedoch mehrere Bindungen eines angegebenen Typs vorhanden, die vom Endpunkt verwendet werden können. Diese verfügen jeweils über eine eigene [ \<Bindung >](../../../../docs/framework/misc/binding.md) -Element im Typelement (Bindung). Das `bindingconfiguration`-Attribut wird verwendet, um zwischen Bindungen des gleichen Typs zu unterscheiden. Der Wert zugeordnet ist die `name` Attribut der [ \<Bindung >](../../../../docs/framework/misc/binding.md) Element. Weitere Informationen dazu, wie Sie einen Client zu konfigurieren von Clientbindungen mit der Konfiguration finden Sie unter [Vorgehensweise: Angeben eine Clientbindung in einer Konfiguration](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md).  
  
 Die `behaviorConfiguration` Attribut wird verwendet, um anzugeben, welche [ \<Verhalten >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) von der [ \<EndpointBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) den Endpunkt verwenden sollten. Der Wert zugeordnet ist die `name` Attribut der [ \<Verhalten >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) Element. Ein Beispiel für das Verwenden der Konfiguration zur Clientverhalten anzugeben, finden Sie unter [Konfigurieren von Clientverhalten](../../../../docs/framework/wcf/configuring-client-behaviors.md).  
  
 Das `contract`-Attribut gibt den Vertrag an, den dieser Endpunkt verfügbar macht. Dieser Wert wird dem <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> des <xref:System.ServiceModel.ServiceContractAttribute> zugeordnet. Der Standardwert ist der vollständige Typname der Klasse, die den Dienst implementiert.  
  
### <a name="configuring-metadata"></a>Konfigurieren von Metadaten  
 Die [ \<Metadaten >](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) Element wird verwendet, um die Einstellungen zur Registrierung von metadatenimporterweiterungen angegeben. Weitere Informationen zum Erweitern des metadatensystems finden Sie unter [Erweitern des Metadatensystems](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md).  
  
## <a name="see-also"></a>Siehe auch

- [Endpunkte: Adressen, Bindungen und Verträge](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [Konfigurieren von Clientverhalten](../../../../docs/framework/wcf/configuring-client-behaviors.md)
