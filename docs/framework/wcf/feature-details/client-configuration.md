---
title: Clientkonfiguration
ms.date: 03/30/2017
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
ms.openlocfilehash: 141b7f7fc04f98f267ce520544fb89451beac7b6
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463870"
---
# <a name="client-configuration"></a>Clientkonfiguration
Sie können die Windows Communication Foundation (WCF)-Clientkonfiguration verwenden, um die Adresse, Bindung, das Verhalten und den Vertrag, die ABC-Eigenschaften des Clientendpunkts anzugeben, die Clients zum Herstellen einer Verbindung mit Dienstendpunkten verwenden. Das [ \<Client->-Element](../../configure-apps/file-schema/wcf/client.md) verfügt über einen [ \<Endpunkt](../../configure-apps/file-schema/wcf/endpoint-of-client.md)>-Element, dessen Attribute zum Konfigurieren der Endpunkt-ABCs verwendet werden. Diese Attribute werden im Abschnitt Konfigurieren von [Endpunkten](#configuring-endpoints) erläutert.  
  
 Das [ \<Endpunktelement>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) Element enthält außerdem ein [ \<Metadatenelement>,](../../configure-apps/file-schema/wcf/metadata.md) das zum Angeben von Einstellungen zum Importieren und Exportieren von Metadaten verwendet wird, ein [ \<Header>](../../configure-apps/file-schema/wcf/headers.md) Element, das eine Auflistung benutzerdefinierter Adressheader enthält, und eine [ \<Identität>](../../configure-apps/file-schema/wcf/identity.md) Element, die die Authentifizierung eines Endpunkts durch andere Endpunkte ermöglicht, die Nachrichten mit ihm austauschen. Die [ \<Header>](../../configure-apps/file-schema/wcf/headers.md) und [ \<Identität>](../../configure-apps/file-schema/wcf/identity.md) <xref:System.ServiceModel.EndpointAddress> Elemente sind Teil der und werden im Artikel [Adressen](../../wcf/feature-details/endpoint-addresses.md) erläutert. Links zu Themen, die die Verwendung von Metadatenerweiterungen erläutern, finden Sie im Abschnitt Konfigurieren von [Metadaten.](#configuring-metadata)  
  
## <a name="configuring-endpoints"></a>Konfigurieren von Endpunkten  
 Die Clientkonfiguration ist so konzipiert, dass der Client einen oder mehrere Endpunkte mit einem eigenen Namen, seiner eigenen Adresse und einem eigenen Vertrag angeben kann, wobei jede Bindung [ \<auf](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) die Bindungen>und [ \<Verhaltensweisen>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) Elemente in der Clientkonfiguration verweist, die zum Konfigurieren dieses Endpunkts verwendet werden sollen. Die Clientkonfigurationsdatei sollte den Namen "App.config" haben, da dies der Name ist, den die WCF-Laufzeit erwartet. Das folgende Beispiel zeigt eine Clientkonfigurationsdatei.  
  
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
  
 Das optionale `name`-Attribut identifiziert eindeutig einen Endpunkt für einen angegebenen Vertrag. Es wird von <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> oder <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> verwendet, um anzugeben, welcher Endpunkt in der Clientkonfiguration das Ziel ist, und muss beim Erstellen eines Kanals zur Verarbeitung geladen werden. Ein Platzhalter-Endpunktkonfigurationsname "\*ist <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> verfügbar und gibt der Methode an, dass eine Beliebige Endpunktkonfiguration in die Datei geladen werden soll, sofern genau eine vorhanden ist und andernfalls eine Ausnahme ausgelöst wird. Wenn dieses Attribut nicht angegeben wird, wird der entsprechende Endpunkt als Standardendpunkt verwendet, der mit dem angegebenen Vertragstyp verknüpft ist. Der Standardwert für das `name`-Attribut ist eine leere Zeichenfolge, die wie jeder andere Name abgeglichen wird.  
  
 Jedem Endpunkt muss eine Adresse zugeordnet sein, um diesen suchen und identifizieren zu können. Das `address`-Attribut kann verwendet werden, um die URL anzugeben, die den Speicherort des Endpunkts bereitstellt. Die Adresse für einen Dienstendpunkt kann jedoch auch im Code angegeben werden, indem ein Uniform Resource Identifier (URI) erstellt und dem <xref:System.ServiceModel.ServiceHost> mit einer der <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>-Methoden hinzugefügt wird. Weitere Informationen finden Sie unter [Adressen](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md). Wie die Einleitung zeigt, sind <xref:System.ServiceModel.EndpointAddress> die [ \<Kopfzeilen>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) und [ \<Identitätselemente>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) Elemente Teil des Elements und werden auch im Thema [Adressen](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) behandelt.  
  
 Das `binding`-Attribut gibt den Typ der Bindung an, der vom Endpunkt beim Herstellen einer Verbindung zu einem Dienst erwartet wird. Dieser muss einen registrierten Konfigurationsabschnitt aufweisen, um darauf verweisen zu können. Im vorherigen Beispiel ist dies der <xref:System.ServiceModel.WSHttpBinding> [ \<abschnitt wsHttpBinding>,](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) der angibt, dass der Endpunkt eine verwendet. Möglicherweise sind jedoch mehrere Bindungen eines angegebenen Typs vorhanden, die vom Endpunkt verwendet werden können. Jeder dieser Elemente verfügt über ein eigenes [ \<Bindungselement>](../../configure-apps/file-schema/wcf/bindings.md) Element innerhalb des Typelements (binding). Das `bindingconfiguration`-Attribut wird verwendet, um zwischen Bindungen des gleichen Typs zu unterscheiden. Sein Wert wird `name` mit dem Attribut des [ \<Bindungselements>](../../configure-apps/file-schema/wcf/bindings.md) Element s. Weitere Informationen zum Konfigurieren einer Clientbindung mithilfe der Konfiguration finden Sie unter [Gewusst wie: Angeben einer Clientbindung in Configuration](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md).  
  
 Das `behaviorConfiguration` Attribut wird verwendet, um anzugeben, welches [ \<Verhalten>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) der [ \<Endpunkt-Verhalten->](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) der Endpunkt verwendet werden soll. Sein Wert wird `name` mit dem Attribut des [ \<Verhaltens>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) Elements abgeglichen. Ein Beispiel für die Verwendung von Konfiguration zum Angeben von Clientverhalten finden Sie unter [Konfigurieren von Clientverhalten](../../../../docs/framework/wcf/configuring-client-behaviors.md).  
  
 Das `contract`-Attribut gibt den Vertrag an, den dieser Endpunkt verfügbar macht. Dieser Wert wird dem <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> des <xref:System.ServiceModel.ServiceContractAttribute> zugeordnet. Der Standardwert ist der vollständige Typname der Klasse, die den Dienst implementiert.  
  
### <a name="configuring-metadata"></a>Konfigurieren von Metadaten  
 Die [ \<Metadaten>](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) Elements werden verwendet, um Einstellungen anzugeben, die zum Registrieren von Metadatenimporterweiterungen verwendet werden. Weitere Informationen zum Erweitern des Metadatensystems finden Sie unter [Erweitern des Metadatensystems](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Endpunkte: Adressen, Bindungen und Verträge](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [Konfigurieren von Clientverhalten](../../../../docs/framework/wcf/configuring-client-behaviors.md)
