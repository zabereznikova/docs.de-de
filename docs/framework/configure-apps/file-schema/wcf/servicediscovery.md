---
title: "&lt;serviceDiscovery&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;serviceDiscovery&gt;
Gibt die Ermittelbarkeit von Dienstendpunkten an.  
  
## Syntax  
  
```  
  
<behaviors>  
  <serviceBehaviors>  
    <behavior name=String">  
      <serviceDiscovery>  
        <announcementEndpoints>  
              <endpoint name="String”  
                        kind="Type" />  
        </announcementEndpoints>  
        <discoveryEndpoints>  
              <endpoint name="String”  
                        kind="Type" />  
        </discoveryEndpoints>  
      </serviceDiscovery>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<announcementEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)|Eine Auflistung von Ankündigungsendpunkten.  Verwenden Sie diesen Abschnitt, um die Endpunkte anzugeben, die zum Senden von Ankündigungsnachrichten verwendet werden sollen.|  
|[\<discoveryEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)|Eine Auflistung von Ermittlungsendpunkten.  Verwenden Sie diesen Abschnitt, um die Endpunkte anzugeben, die auf Ankündigungsnachrichten überwacht werden sollen.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Verhalten\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Gibt ein Verhaltenselement an.|  
  
## Hinweise  
 Wenn dieses Element der Verhaltenskonfiguration des Diensts hinzugefügt wird, macht es alle Endpunkte dieses Diensts auffindbar.  Sie können die Suchfunktionen von solchen Endpunkten mit den [\<discoveryEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) oder untergeordneten [\<announcementEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)\-Elementen weiter konfigurieren.  Verwenden Sie den [\<announcementEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)\-Abschnitt, um die Ankündigungen zu konfigurieren, indem Sie die Endpunktkonfiguration zum Senden von Dienstankündigungen \(online\/Hello und offline\/Bye\) angeben.  Verwenden Sie den [\<discoveryEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)\-Abschnitt, um den zu überwachenden Endpunkt manuell anzugeben.  
  
## Beispiel  
 Im folgenden Konfigurationsbeispiel wird angegeben, dass der CalculatorService sichtbar ist, und optional wird der zu verwendende Ankündigungsendpunkt angegeben.  
  
```  
  
<services>  
  <service name="CalculatorService"  
           behaviorConfiguration="CalculatorServiceBehavior">  
  ...  
  </service>  
</services>  
  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceDiscovery>  
        <announcementEndpoints>  
              <endpoint name="udpEndpoint"  
                        kind="udpAnnouncementEndpoint" />  
        </announcementEndpoints>  
      </serviceDiscovery>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
  
```  
  
## Siehe auch  
 <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>