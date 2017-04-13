---
title: "Konfigurieren von Bindungen f&#252;r Windows Communication Foundation-Dienste | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Bindungskonfiguration [WCF]"
ms.assetid: 99a85fd8-f7eb-4a84-a93e-7721b37d415c
caps.latest.revision: 36
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 36
---
# Konfigurieren von Bindungen f&#252;r Windows Communication Foundation-Dienste
Beim Erstellen einer Anwendung möchten Sie dem Administrator nach Bereitstellung der Anwendung möglicherweise Entscheidungen mitteilen.Beispielsweise wissen Sie häufig nicht im Voraus, welche Dienstadresse oder welcher URI \(Uniform Resource Identifier\) verwendet wird.Anstatt eine Adresse fest zu programmieren, sollte diese Aufgabe einem Administrator nach dem Erstellen eines Diensts übergeben werden.Diese Flexibilität wird durch Konfiguration ermöglicht.  
  
> [!NOTE]
>  Zum schnellen Erstellen von Konfigurationsdateien verwenden Sie das [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) mit dem `/config`\-Schalter.  
  
## Hauptabschnitte  
 Das [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\-Konfigurationsschema schließt die folgenden drei Hauptabschnitte ein \(`serviceModel`, `bindings` und `services`\):  
  
```  
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
  
### ServiceModel\-Elemente  
 Sie können den vom `system.ServiceModel` \-Element umschlossenen Abschnitt zum Konfigurieren eines Diensttyps mit mindestens einem Endpunkt und die Einstellungen eines Diensts verwenden.Jeder Endpunkt kann dann mit einer Adresse, einem Vertrag und einer Bindung konfiguriert werden.[!INCLUDE[crabout](../../../includes/crabout-md.md)] zu Endpunkten finden Sie unter [Übersicht über die Endpunkterstellung](../../../docs/framework/wcf/endpoint-creation-overview.md).Wenn Sie keine Endpunkte angeben, werden von der Runtime automatisch Standardendpunkte hinzugefügt.[!INCLUDE[crabout](../../../includes/crabout-md.md)] zu Standardendpunkten, Bindungen und Verhaltensweisen finden Sie unter [Vereinfachte Konfiguration](../../../docs/framework/wcf/simplified-configuration.md) und [Vereinfachte Konfiguration für WCF\-Dienste](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
 Eine Bindung gibt Transporte \(HTTP, TCP, Pipes und Message Queuing\) sowie Protokolle \(Sicherheit, Verlässlichkeit, Transaktionsflüsse\) an und besteht aus Bindungselementen, von denen jedes einen Aspekt der Kommunikation eines Endpunkts mit der Welt angibt.  
  
 Das Angeben des [\<basicHttpBinding\>](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)\-Elements zeigt z. B. an, dass HTTP als Transport für einen Endpunkt verwendet wird.Auf diese Weise wird der Endpunkt zur Laufzeit aktiviert, wenn der Dienst, der diesen Endpunkt verwendet, geöffnet wird.  
  
 Es gibt zwei Arten von Bindungen: vordefinierte und benutzerdefinierte.Vordefinierte Bindungen enthalten nützliche Kombinationen von Elementen, die in allgemeinen Szenarien verwendet werden.Eine Liste vordefinierter Bindungstypen, die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] bereitstellt, finden Sie unter [Vom System bereitgestellte Bindungen](../../../docs/framework/wcf/system-provided-bindings.md).Wenn keine vordefinierte Bindungsauflistung über die korrekte Kombination von Features verfügt, die eine Dienstanwendung benötigt, können Sie benutzerdefinierte Bindungen erstellen, um den Anforderungen der Anwendung zu entsprechen.[!INCLUDE[crabout](../../../includes/crabout-md.md)] zu benutzerdefinierten Bindungen finden Sie unter [\<customBinding\>](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).  
  
 In den folgenden vier Beispielen werden die am häufigsten verwendeten Bindungskonfigurationen dargestellt, die zum Einrichten eines [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Diensts verwendet werden.  
  
#### Angeben eines Endpunkts, um einen Bindungstyp zu verwenden  
 Das erste Beispiel zeigt, wie ein Endpunkt angegeben wird, der mit einer Adresse, einem Vertrag und einer Bindung konfiguriert wurde.  
  
```  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
  <!—- This section is optional with the default configuration introduced  
       in .NET Framework 4. -->  
  <endpoint   
      address="/HelloWorld2/"  
      contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
      binding="basicHttpBinding" />  
  </endpoint>  
</service>  
```  
  
 In diesem Beispiel gibt das `name`\-Attribut an, für welchen Diensttyp die Konfiguration verwendet wird.Wenn Sie in Ihrem Code einen Dienst mit dem `HelloWorld`\-Vertrag erstellen, wird er mit allen in der Beispielkonfiguration definierten Endpunkten initialisiert.Wenn die Assembly nur einen Dienstvertrag implementiert, kann das `name` \-Attribut weggelassen werden, da der Dienst den einzigen verfügbaren Typ verwenden.Das Attribut nimmt eine Zeichenfolge, die im Format `Namespace.Class, AssemblyName, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null` vorliegen muss  
  
 Das `address`\-Attribut gibt den URI an, den andere Endpunkte für die Kommunikation mit dem Dienst verwenden.Der URI kann entweder ein absoluter oder relativer Pfad sein.Bei Bereitstellung einer relativen Adresse wird vom Host erwartet, dass er eine Basisadresse bereitstellt, die für das in der Bindung verwendete Transportschema geeignet ist.Wenn keine Adresse konfiguriert wird, wird angenommen, dass die Basisadresse der Adresse für diesen Endpunkt entspricht.  
  
 Das `contract`\-Attribut gibt den Vertrag an, den dieser Endpunkt verfügbar macht.Der Dienstimplementierungstyp muss den Vertragstyp implementieren.Wenn eine Dienstimplementierung einen einzelnen Vertragstyp implementiert, kann diese Eigenschaft ausgelassen werden.  
  
 Das `binding`\-Attribut wählt eine vordefinierte oder benutzerdefinierte Bindung aus, die für diesen speziellen Endpunkt verwendet werden soll.Ein Endpunkt, der eine Bindung nicht explizit auswählt, verwendet die standardmäßige Bindungsauswahl `BasicHttpBinding`.  
  
#### Ändern einer vordefinierten Bindung  
 Im folgenden Beispiel wird eine vordefinierte Bindung geändert.Sie kann anschließend verwendet werden, um einen beliebigen Endpunkt im Dienst zu konfigurieren.Die Bindung wird geändert, indem der <xref:System.ServiceModel.Configuration.IBindingConfigurationElement.ReceiveTimeout%2A>\-Wert auf 1 Sekunde festgelegt wird.Beachten Sie, dass die Eigenschaft ein <xref:System.TimeSpan>\-Objekt zurückgibt.  
  
 Diese geänderte Bindung finden Sie im Bindungsabschnitt.Sie kann jetzt beim Erstellen von Endpunkten durch Festlegen des `binding`\-Attributs im `endpoint`\-Element verwendet werden.  
  
> [!NOTE]
>  Wenn Sie der Bindung einen besonderen Namen geben, muss die im Dienstendpunkt angegebene `bindingConfiguration` diesem Namen entsprechen.  
  
```  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
  <endpoint   
      address="/HelloWorld2/"  
      contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
      binding="basicHttpBinding" />  
  </endpoint>  
</service>  
<bindings>  
    <basicHttpBinding   
        receiveTimeout="00:00:01"  
    />  
</bindings>  
```  
  
## Konfigurieren eines Verhaltens für einen Dienst  
 Im folgenden Beispiel wird ein bestimmtes Verhalten für den Diensttyp konfiguriert.Das `ServiceMetadataBehavior`\-Element wird zum Aktivieren des [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) verwendet, um den Dienst abzufragen und WSDL\-Dokumente \(Web Services Description Language\) aus den Metadaten zu generieren.  
  
> [!NOTE]
>  Wenn Sie dem Verhalten einen besonderen Namen geben, muss die im Dienst\- oder Endpunktabschnitt angegebene `behaviorConfiguration` diesem Namen entsprechen.  
  
```  
<behaviors>  
    <behavior>  
        <ServiceMetadata httpGetEnabled="true" />   
    </behavior>  
</behaviors>  
<services>  
    <service   
       name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
       <endpoint   
          address="http://computer:8080/Hello"  
          contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
          binding="basicHttpBinding" />  
       </endpoint>  
    </service>  
</services>  
```  
  
 Die vorangehende Konfiguration ermöglicht einem Client, den "HelloWorld"\-Dienst aufzurufen und die Metadaten des Diensts abzurufen.  
  
 `svcutil /config:Client.exe.config http://computer:8080/Hello?wsdl`  
  
## Angeben eines Diensts mit zwei Endpunkten mithilfe unterschiedlicher Bindungswerte  
 In diesem letzten Beispiel werden zwei Endpunkte für den `HelloWorld`\-Diensttyp konfiguriert.Jeder Endpunkt verwendet ein anderes benutzerdefiniertes `bindingConfiguration`\-Attribut desselben Bindungstyps \(jedes ändert die `basicHttpBinding`\).  
  
```  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
    <endpoint  
        address="http://computer:8080/Hello1"  
        contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
        binding="basicHttpBinding"  
        bindingConfiguration="shortTimeout"  
    </endpoint>  
    <endpoint  
        address="http://computer:8080/Hello2"  
        contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
        binding="basicHttpBinding"  
        bindingConfiguration="Secure"  
     </endpoint>  
</service>  
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
  
 Sie können dasselbe Verhalten mit der Konfiguration erzielen, indem Sie einen `protocolMapping`\-Abschnitt hinzufügen und die Bindungen konfigurieren, wie im folgenden Beispiel gezeigt.  
  
```xml  
<protocolMapping>  
    <add scheme=”http” binding=”basicHttpBinding” bindingConfiguration=”shortTimeout” />  
    <add scheme=”https” binding=”basicHttpBinding” bindingConfiguration=”Secure” />  
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
  
## Siehe auch  
 [Vereinfachte Konfiguration](../../../docs/framework/wcf/simplified-configuration.md)   
 [Vom System bereitgestellte Bindungen](../../../docs/framework/wcf/system-provided-bindings.md)   
 [Übersicht über die Endpunkterstellung](../../../docs/framework/wcf/endpoint-creation-overview.md)   
 [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)