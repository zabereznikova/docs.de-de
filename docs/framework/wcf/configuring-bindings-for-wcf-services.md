---
title: Konfigurieren von Bindungen für Windows Communication Foundation-Dienste
ms.date: 03/30/2017
helpviewer_keywords:
- binding configuration [WCF]
ms.assetid: 99a85fd8-f7eb-4a84-a93e-7721b37d415c
ms.openlocfilehash: 7b5a91091a0902928eb2b72bdf69612f2e3f2f48
ms.sourcegitcommit: 3b9b7ae6771712337d40374d2fef6b25b0d53df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/04/2019
ms.locfileid: "54029410"
---
# <a name="configuring-bindings-for-windows-communication-foundation-services"></a>Konfigurieren von Bindungen für Windows Communication Foundation-Dienste
Beim Erstellen einer Anwendung möchten Sie dem Administrator nach Bereitstellung der Anwendung möglicherweise Entscheidungen mitteilen. Beispielsweise wissen Sie häufig nicht im Voraus, welche Dienstadresse oder welcher URI (Uniform Resource Identifier) verwendet wird. Anstatt eine Adresse fest zu programmieren, sollte diese Aufgabe einem Administrator nach dem Erstellen eines Diensts übergeben werden. Diese Flexibilität wird durch Konfiguration ermöglicht.  
  
> [!NOTE]
>  Verwenden der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) mit der `/config` Schalter, um rasch Konfigurationsdateien zu erstellen.  
  
## <a name="major-sections"></a>Hauptabschnitte  
 Die Windows Communication Foundation (WCF)--Konfigurationsschema schließt die folgenden drei Hauptabschnitte (`serviceModel`, `bindings`, und `services`):  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <bindings>  
        </bindings>  
        <services>  
        </services>  
        <behaviors>  
        </behaviors>  
    </system.serviceModel>  
</configuration>  
```  
  
### <a name="servicemodel-elements"></a>ServiceModel-Elemente  
 Können Sie im Abschnitt begrenzt durch die `system.ServiceModel` Element, um einen Diensttyp mit einem oder mehreren Endpunkten sowie Einstellungen für einen Dienst zu konfigurieren. Jeder Endpunkt kann dann mit einer Adresse, einem Vertrag und einer Bindung konfiguriert werden. Weitere Informationen zu Endpunkten finden Sie unter [Übersicht über die Endpunkterstellung](../../../docs/framework/wcf/endpoint-creation-overview.md). Wenn Sie keine Endpunkte angeben, werden von der Runtime automatisch Standardendpunkte hinzugefügt. Weitere Informationen über Standardendpunkte, Bindungen und Verhalten finden Sie unter [Simplified Configuration (Vereinfachte Konfiguration)](../../../docs/framework/wcf/simplified-configuration.md) und [Simplified Configuration for WCF Services (Vereinfachte Konfiguration für WCF-Dienste)](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
 Eine Bindung gibt Transporte (HTTP, TCP, Pipes und Message Queuing) sowie Protokolle (Sicherheit, Verlässlichkeit, Transaktionsflüsse) an und besteht aus Bindungselementen, von denen jedes einen Aspekt der Kommunikation eines Endpunkts mit der Welt angibt.  
  
 Z. B. die [ \<BasicHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) Element gibt an, dass um HTTP als Transport für einen Endpunkt zu verwenden. Auf diese Weise wird der Endpunkt zur Laufzeit aktiviert, wenn der Dienst, der diesen Endpunkt verwendet, geöffnet wird.  
  
 Es gibt zwei Arten von Bindungen: vordefinierte und benutzerdefinierte. Vordefinierte Bindungen enthalten nützliche Kombinationen von Elementen, die in allgemeinen Szenarien verwendet werden. Eine Liste vordefinierter Bindungstypen, die WCF bietet, finden Sie unter [System-provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md). Wenn keine vordefinierte Bindungsauflistung über die korrekte Kombination von Funktionen verfügt, die eine Dienstanwendung benötigt, können Sie benutzerdefinierte Bindungen erstellen, um den Anforderungen der Anwendung zu entsprechen. Weitere Informationen zu benutzerdefinierten Bindungen finden Sie unter [ \<CustomBinding >](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).  
  
 Die folgenden vier Beispiele veranschaulichen, die am häufigsten verwendeten Bindungskonfigurationen für das Einrichten eines WCF-Diensts verwendet wird.  
  
#### <a name="specifying-an-endpoint-to-use-a-binding-type"></a>Angeben eines Endpunkts, um einen Bindungstyp zu verwenden  
 Das erste Beispiel zeigt, wie ein Endpunkt angegeben wird, der mit einer Adresse, einem Vertrag oder einer Bindung konfiguriert wurde.  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
  <!-- This section is optional with the default configuration introduced  
       in .NET Framework 4. -->  
  <endpoint   
      address="/HelloWorld2/"  
      contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
      binding="basicHttpBinding" />
</service>  
```  
  
 In diesem Beispiel gibt das `name`-Attribut an, für welchen Diensttyp die Konfiguration verwendet wird. Wenn Sie in Ihrem Code einen Dienst mit dem `HelloWorld`-Vertrag erstellen, wird er mit allen in der Beispielkonfiguration definierten Endpunkten initialisiert. Wenn die Assembly nur einen Dienstvertrag implementiert die `name` -Attribut ausgelassen werden, da der Dienst den einzigen verfügbaren Typ verwendet. Das Attribut nimmt eine Zeichenfolge, die im Format `Namespace.Class, AssemblyName, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null` vorliegen muss  
  
 Das `address`-Attribut gibt den URI an, den andere Endpunkte für die Kommunikation mit dem Dienst verwenden. Der URI kann entweder ein absoluter oder relativer Pfad sein. Bei Bereitstellung einer relativen Adresse wird vom Host erwartet, dass er eine Basisadresse bereitstellt, die für das in der Bindung verwendete Transportschema geeignet ist. Wenn keine Adresse konfiguriert wird, wird angenommen, dass die Basisadresse der Adresse für diesen Endpunkt entspricht.  
  
 Das `contract`-Attribut gibt den Vertrag an, den dieser Endpunkt verfügbar macht. Der Dienstimplementierungstyp muss den Vertragstyp implementieren. Wenn eine Dienstimplementierung einen einzelnen Vertragstyp implementiert, kann diese Eigenschaft ausgelassen werden.  
  
 Das `binding`-Attribut wählt eine vordefinierte oder benutzerdefinierte Bindung aus, die für diesen speziellen Endpunkt verwendet werden soll. Ein Endpunkt, der eine Bindung nicht explizit auswählt, verwendet die standardmäßige Bindungsauswahl `BasicHttpBinding`.  
  
#### <a name="modifying-a-predefined-binding"></a>Ändern einer vordefinierten Bindung  
 Im folgenden Beispiel wird eine vordefinierte Bindung geändert. Sie kann anschließend verwendet werden, um einen beliebigen Endpunkt im Dienst zu konfigurieren. Die Bindung wird geändert, indem der <xref:System.ServiceModel.Configuration.IBindingConfigurationElement.ReceiveTimeout%2A>-Wert auf 1 Sekunde festgelegt wird. Beachten Sie, dass die Eigenschaft ein <xref:System.TimeSpan>-Objekt zurückgibt.  
  
 Diese geänderte Bindung finden Sie im Bindungsabschnitt. Sie kann jetzt beim Erstellen von Endpunkten durch Festlegen des `binding`-Attributs im `endpoint`-Element verwendet werden.  
  
> [!NOTE]
>  Wenn Sie der Bindung einen besonderen Namen geben, muss die im Dienstendpunkt angegebene `bindingConfiguration` diesem Namen entsprechen.  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
  <endpoint   
      address="/HelloWorld2/"  
      contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
      binding="basicHttpBinding" />
</service>  
<bindings>  
    <basicHttpBinding   
        receiveTimeout="00:00:01"  
    />  
</bindings>  
```  
  
## <a name="configuring-a-behavior-to-apply-to-a-service"></a>Konfigurieren eines Verhaltens für einen Dienst  
 Im folgenden Beispiel wird ein bestimmtes Verhalten für den Diensttyp konfiguriert. Die `ServiceMetadataBehavior` Element dient zum Aktivieren der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) auf den Dienst abzufragen und Web Services Description Language (WSDL)-Dokumente aus den Metadaten zu generieren.  
  
> [!NOTE]
>  Wenn Sie dem Verhalten einen besonderen Namen geben, muss die im Dienst- oder Endpunktabschnitt angegebene `behaviorConfiguration` diesem Namen entsprechen.  
  
```xml  
<behaviors>  
    <behavior>  
        <ServiceMetadata httpGetEnabled="true" />   
    </behavior>  
</behaviors>  
<services>  
    <service   
       name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">
       <endpoint   
          address="http://computer:8080/Hello"  
          contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
          binding="basicHttpBinding" />
    </service>  
</services>  
```  
  
 Die vorangehende Konfiguration ermöglicht einem Client, den "HelloWorld"-Dienst aufzurufen und die Metadaten des Diensts abzurufen.  
  
 `svcutil /config:Client.exe.config http://computer:8080/Hello?wsdl`  
  
## <a name="specifying-a-service-with-two-endpoints-using-different-binding-values"></a>Angeben eines Diensts mit zwei Endpunkten mithilfe unterschiedlicher Bindungswerte  
 In diesem letzten Beispiel werden zwei Endpunkte für den `HelloWorld`-Diensttyp konfiguriert. Jeder Endpunkt verwendet ein anderes benutzerdefiniertes `bindingConfiguration` -Attribut desselben Bindungstyps (jedes ändert die `basicHttpBinding`).  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
    <endpoint  
        address="http://computer:8080/Hello1"  
        contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
        binding="basicHttpBinding"  
        bindingConfiguration="shortTimeout" />
    <endpoint  
        address="http://computer:8080/Hello2"  
        contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
        binding="basicHttpBinding"  
        bindingConfiguration="Secure" />
</service>  
<bindings>  
    <basicHttpBinding   
        name="shortTimeout"  
        timeout="00:00:00:01"   
     />  
     <basicHttpBinding   
        name="Secure">  
        <Security mode="Transport" />  
     </basicHttpBinding>
</bindings>  
```  
  
 Sie können dasselbe Verhalten mit der Konfiguration erzielen, indem Sie einen `protocolMapping`-Abschnitt hinzufügen und die Bindungen konfigurieren, wie im folgenden Beispiel gezeigt.  
  
```xml  
<protocolMapping>  
    <add scheme="http" binding="basicHttpBinding" bindingConfiguration="shortTimeout" />  
    <add scheme="https" binding="basicHttpBinding" bindingConfiguration="Secure" />  
</protocolMapping>  
<bindings>  
    <basicHttpBinding   
        name="shortTimeout"  
        timeout="00:00:00:01"   
     />  
     <basicHttpBinding   
        name="Secure" />  
        <Security mode="Transport" />  
</bindings>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Vereinfachte Konfiguration](../../../docs/framework/wcf/simplified-configuration.md)  
 [Vom System bereitgestellte Bindungen](../../../docs/framework/wcf/system-provided-bindings.md)  
 [Übersicht über die Endpunkterstellung](../../../docs/framework/wcf/endpoint-creation-overview.md)  
 [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
