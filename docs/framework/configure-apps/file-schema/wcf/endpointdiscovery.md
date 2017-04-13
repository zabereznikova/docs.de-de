---
title: "&lt;endpointDiscovery&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;endpointDiscovery&gt;
Gibt die verschiedenen Ermittlungseinstellungen für einen Endpunkt an, z. B. seine Ermittelbarkeit, seine Bereiche und benutzerdefinierte Erweiterungen seiner Metadaten.  
  
## Syntax  
  
```  
  
<behaviors>  
  <endpointBehaviors>  
    <behavior name="String">  
      <endpointDiscovery enabled="Boolean">  
        <scopes>  
          <add scope="URI"/>  
        </scopes>  
        <extensions>  
        </extensions>  
      </endpointDiscovery>  
    </behavior>  
  </endpointBehaviors>  
</behaviors>  
  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|enabled|Ein boolescher Wert, der angibt, ob die Ermittelbarkeit für diesen Endpunkt aktiviert ist.  Die Standardeinstellung ist `false`.|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<scopes\>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|Eine Auflistung von Bereichs\-URIs für den Endpunkt.  Einem Endpunkt können mehrere Bereichs\-URIs zugeordnet werden.|  
|[\<Erweiterungen\>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) \[von \<endpointDiscovery\>\]|Eine Auflistung von XML\-Elementen, die Ihnen ermöglicht, benutzerdefinierte Metadaten anzugeben, die für einen Endpunkt veröffentlicht werden sollen.|  
|\<types\>|Eine Auflistung von Schnittstellen, nach denen gesucht werden soll.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Verhalten\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Gibt ein Verhaltenselement an.|  
|||  
  
## Hinweise  
 Bei Hinzufügung zur Verhaltenskonfiguration des Endpunkts und bei Festlegen des `enabled`\-Attributs auf `true` aktiviert dieses Konfigurationselement seine Ermittelbarkeit.  Darüber hinaus können Sie mit dem untergeordneten [\<scopes\>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)\-Element benutzerdefinierte Bereichs\-URIs angeben, mit denen Dienstendpunkte während der Abfrage gefiltert werden können, und mit dem untergeordneten [\<Erweiterungen\>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md)\-Element können Sie benutzerdefinierte Metadaten angeben, die mit den standardmäßigen sichtbaren Metadaten \(EPR, ContractTypeName, BindingName, Scope und ListenURI\) veröffentlicht werden sollen.  
  
 Dieses Konfigurationselement ist abhängig vom [\<serviceDiscovery\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md)\-Element, das die Steuerung der Ermittelbarkeit auf Dienstebene bereitstellt.  Das heißt, die Einstellungen dieses Elements werden ignoriert, wenn [\<serviceDiscovery\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) in der Konfiguration nicht vorhanden ist.  
  
## Beispiel  
 Im folgenden Konfigurationsbeispiel werden Filterbereiche und Erweiterungsmetadaten angegeben, die für einen Endpunkt veröffentlicht werden sollen.  
  
```  
  
<services>  
  <service name="CalculatorService"  
           behaviorConfiguration="CalculatorServiceBehavior">  
     <endpoint binding="basicHttpBinding"  
              address="calculator"  
              contract="ICalculatorService"  
              behaviorConfiguration="calculatorEndpointBehavior" />  
  </service>  
</services>  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceDiscovery />  
    </behavior>  
  </serviceBehaviors>  
  <endpointBehaviors>  
    <behavior name="calculatorEndpointBehavior">  
      <endpointDiscovery enabled="true">  
        <scopes>  
          <add scope="http://contoso/test1"/>  
          <add scope="http://contoso/test2"/>  
        </scopes>  
        <extensions>  
          <e:Publisher xmlns:e="http://example.org">  
            <e:Name>The Example Organization</e:Name>  
            <e:Address>One Example Way, ExampleTown, EX 12345</e:Address>  
            <e:Contact>support@example.org</e:Contact>  
          </e:Publisher>  
          <AnotherCustomMetadata>Custom Metadata</AnotherCustomMetadata>  
        </extensions>  
      </endpointDiscovery>  
    </behavior>  
  </endpointBehaviors>  
</behaviors>  
  
```  
  
## Siehe auch  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>