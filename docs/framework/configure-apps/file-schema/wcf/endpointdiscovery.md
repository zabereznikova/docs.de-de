---
title: <endpointDiscovery>
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: 125baba917a49135aaa426df2cfa1a4dbe8ac1e8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700909"
---
# <a name="endpointdiscovery"></a>\<endpointDiscovery>
Gibt die verschiedenen Ermittlungseinstellungen für einen Endpunkt an, z. B. seine Ermittelbarkeit, seine Bereiche und benutzerdefinierte Erweiterungen seiner Metadaten.  
  
\<system.ServiceModel>  
\<behaviors>  
\<endpointBehaviors>  
\<behavior>  
\<endpointDiscovery>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enabled="Boolean">
        <scopes>
          <add scope="URI"/>
        </scopes>
        <extensions />
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|enabled|Ein boolescher Wert, der angibt, ob die ermittelbarkeit für diesen Endpunkt aktiviert ist. Die Standardeinstellung ist `false`.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<scopes>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|Eine Auflistung von Bereichs-URIs für den Endpunkt. Einem Endpunkt können mehrere Bereichs-URIs zugeordnet werden.|  
|[\<Extensions >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) [von \<EndpointDiscovery >]|Eine Auflistung von XML-Elementen, die Ihnen ermöglicht, benutzerdefinierte Metadaten anzugeben, die für einen Endpunkt veröffentlicht werden sollen.|  
|\<types>|Eine Auflistung von Schnittstellen, nach denen gesucht werden soll.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Gibt ein Verhaltenselement an.|  
|||  
  
## <a name="remarks"></a>Hinweise  
 Bei Hinzufügung zur Verhaltenskonfiguration des Endpunkts und bei Festlegen des `enabled`-Attributs auf `true` aktiviert dieses Konfigurationselement seine Ermittelbarkeit. Darüber hinaus können Sie die [ \<Bereiche >](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)untergeordnetes Element angeben benutzerdefinierter Bereichs-Uris, die verwendet werden kann, um Dienstendpunkte während der Abfrage filtern als auch die [ \<Extensions >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) untergeordnetes Element, um benutzerdefinierte Metadaten anzugeben, die zusammen mit den standardmäßigen sichtbaren Metadaten (EPR, ContractTypeName, BindingName, Scope und ListenURI) veröffentlicht werden sollen.  
  
 Dieses Konfigurationselement ist abhängig von der [ \<ServiceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) Element, das der dienststeuerungs-Ebene für die Auffindbarkeit bereitstellt. Dies bedeutet, dass die Einstellungen dieses Elements ignoriert werden, wenn [ \<ServiceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) nicht in der Konfiguration vorhanden ist.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Konfigurationsbeispiel werden Filterbereiche und Erweiterungsmetadaten angegeben, die für einen Endpunkt veröffentlicht werden sollen.  
  
```xml  
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
          <add scope="http://contoso/test1" />
          <add scope="http://contoso/test2" />
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
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
