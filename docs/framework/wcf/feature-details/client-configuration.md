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
# <a name="client-configuration"></a>Clientkonfiguration

Sie können die Windows Communication Foundation (WCF)-Client Konfiguration verwenden, um die Adresse, die Bindung, das Verhalten und den Vertrag, die "ABC"-Eigenschaften des Client Endpunkts anzugeben, die von Clients zum Herstellen einer Verbindung mit Dienst Endpunkten verwendet werden. Das- [\<client>](../../configure-apps/file-schema/wcf/client.md) Element verfügt über ein- [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) Element, dessen Attribute zum Konfigurieren der Endpunkt ABCs verwendet werden. Diese Attribute werden im Abschnitt [Konfigurieren von Endpunkten](#configuring-endpoints) erläutert.  
  
 Das [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) -Element enthält außerdem ein [\<metadata>](../../configure-apps/file-schema/wcf/metadata.md) -Element, das verwendet wird, um Einstellungen für das Importieren und Exportieren von Metadaten anzugeben, ein [\<headers>](../../configure-apps/file-schema/wcf/headers.md) -Element, das eine Auflistung von benutzerdefinierten Adress Headern enthält, und ein-Element, [\<identity>](../../configure-apps/file-schema/wcf/identity.md) das die Authentifizierung eines Endpunkts durch andere Endpunkte ermöglicht, die Nachrichten austauschen. Das [\<headers>](../../configure-apps/file-schema/wcf/headers.md) -Element und das- [\<identity>](../../configure-apps/file-schema/wcf/identity.md) Element sind Teil der <xref:System.ServiceModel.EndpointAddress> und werden im [Adress](endpoint-addresses.md) Artikel erläutert. Links zu Themen, in denen die Verwendung von Metadatenerweiterungen erläutert wird, finden Sie im Abschnitt [Konfigurieren von Metadaten](#configuring-metadata) .  
  
## <a name="configuring-endpoints"></a>Konfigurieren von Endpunkten  

 Die Client Konfiguration ermöglicht es dem Client, einen oder mehrere Endpunkte anzugeben, die jeweils über einen eigenen Namen, eine eigene Adresse und einen eigenen Vertrag verfügen, wobei jeweils auf das [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) -Element und das- [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) Element in der Client Konfiguration verweisen, um diesen Endpunkt zu konfigurieren. Die Client Konfigurationsdatei sollte mit dem Namen "App.config" benannt werden, da dies der Name ist, den die WCF-Laufzeit erwartet. Das folgende Beispiel zeigt eine Clientkonfigurationsdatei.  
  
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
  
 Das optionale `name`-Attribut identifiziert eindeutig einen Endpunkt für einen angegebenen Vertrag. Es wird von <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> oder <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> verwendet, um anzugeben, welcher Endpunkt in der Clientkonfiguration das Ziel ist, und muss beim Erstellen eines Kanals zur Verarbeitung geladen werden. Ein Name für die Platzhalter Endpunkt \* -Konfiguration ist verfügbar und gibt der Methode an, <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> dass jede Endpunkt Konfiguration in der Datei geladen werden soll, sofern genau eine verfügbar ist, und andernfalls wird eine Ausnahme ausgelöst. Wenn dieses Attribut nicht angegeben wird, wird der entsprechende Endpunkt als Standardendpunkt verwendet, der mit dem angegebenen Vertragstyp verknüpft ist. Der Standardwert für das `name`-Attribut ist eine leere Zeichenfolge, die wie jeder andere Name abgeglichen wird.  
  
 Jedem Endpunkt muss eine Adresse zugeordnet sein, um diesen suchen und identifizieren zu können. Das `address`-Attribut kann verwendet werden, um die URL anzugeben, die den Speicherort des Endpunkts bereitstellt. Die Adresse für einen Dienstendpunkt kann jedoch auch im Code angegeben werden, indem ein Uniform Resource Identifier (URI) erstellt und dem <xref:System.ServiceModel.ServiceHost> mit einer der <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>-Methoden hinzugefügt wird. Weitere Informationen finden Sie unter [Adressen](endpoint-addresses.md). Wie die Einführung zeigt, [\<headers>](../../configure-apps/file-schema/wcf/headers.md) sind das-Element und das- [\<identity>](../../configure-apps/file-schema/wcf/identity.md) Element Teil der <xref:System.ServiceModel.EndpointAddress> und werden auch im Thema [Adressen](endpoint-addresses.md) erläutert.  
  
 Das `binding`-Attribut gibt den Typ der Bindung an, der vom Endpunkt beim Herstellen einer Verbindung zu einem Dienst erwartet wird. Dieser muss einen registrierten Konfigurationsabschnitt aufweisen, um darauf verweisen zu können. Im vorherigen Beispiel ist dies der [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) Abschnitt, der angibt, dass der Endpunkt einen verwendet <xref:System.ServiceModel.WSHttpBinding> . Möglicherweise sind jedoch mehrere Bindungen eines angegebenen Typs vorhanden, die vom Endpunkt verwendet werden können. Jede dieser Elemente verfügt über ein eigenes- [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) Element innerhalb des (Binding) Type-Elements. Das `bindingconfiguration`-Attribut wird verwendet, um zwischen Bindungen des gleichen Typs zu unterscheiden. Der Wert wird mit dem- `name` Attribut des- [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) Elements abgeglichen. Weitere Informationen zum Konfigurieren einer Client Bindung mithilfe der Konfiguration finden Sie unter Gewusst [wie: Angeben einer Client Bindung in der Konfiguration](../how-to-specify-a-client-binding-in-configuration.md).  
  
 Das- `behaviorConfiguration` Attribut wird verwendet, um anzugeben, welcher [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) der [\<endpointBehaviors>](../../configure-apps/file-schema/wcf/endpointbehaviors.md) Endpunkt verwenden soll. Der Wert wird mit dem- `name` Attribut des- [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) Elements abgeglichen. Ein Beispiel für die Verwendung der Konfiguration zum Angeben von Client Verhaltensweisen finden Sie unter [Konfigurieren von Client Verhalten](../configuring-client-behaviors.md).  
  
 Das `contract`-Attribut gibt den Vertrag an, den dieser Endpunkt verfügbar macht. Dieser Wert wird dem <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> des <xref:System.ServiceModel.ServiceContractAttribute> zugeordnet. Der Standardwert ist der vollständige Typname der Klasse, die den Dienst implementiert.  
  
### <a name="configuring-metadata"></a>Konfigurieren von Metadaten  

 Das- [\<metadata>](../../configure-apps/file-schema/wcf/metadata.md) Element wird verwendet, um Einstellungen anzugeben, mit denen Metadaten-Import Erweiterungen registriert werden. Weitere Informationen zum Erweitern des Metadatensystems finden Sie unter [Erweitern des Metadatensystems](../extending/extending-the-metadata-system.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Endpunkte: Adressen, Bindungen und Verträge](endpoints-addresses-bindings-and-contracts.md)
- [Konfigurieren von Clientverhalten](../configuring-client-behaviors.md)
