---
title: <serviceDiscovery>
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: a99edd3a62a40c2efbc63a166b8c0b0d124e8a72
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936273"
---
# <a name="servicediscovery"></a>\<serviceDiscovery>
Gibt die Ermittelbarkeit von Dienstendpunkten an.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<behavior>  
\<serviceDiscovery>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceDiscovery>
        <announcementEndpoints>
          <endpoint name="String"
                    kind="Type" />
        </announcementEndpoints>
        <discoveryEndpoints>
          <endpoint name="String"
                    kind="Type" />
        </discoveryEndpoints>
      </serviceDiscovery>
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<announcementEndpoint>](announcementendpoint.md)|Eine Auflistung von Ankündigungsendpunkten. Verwenden Sie diesen Abschnitt, um die Endpunkte anzugeben, die zum Senden von Ankündigungsnachrichten verwendet werden sollen.|  
|[\<discoveryEndpoint>](discoveryendpoint.md)|Eine Auflistung von Ermittlungsendpunkten. Verwenden Sie diesen Abschnitt, um die Endpunkte anzugeben, die auf Ankündigungsnachrichten überwacht werden sollen.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|Gibt ein Verhaltenselement an.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn dieses Element der Verhaltenskonfiguration des Diensts hinzugefügt wird, macht es alle Endpunkte dieses Diensts auffindbar. Sie können die Ermittlungs Funktionen solcher Endpunkte weiter konfigurieren, indem Sie den [ \<DiscoveryEndpoint->](discoveryendpoint.md) oder [ \<den >](announcementendpoint.md) untergeordneten-Endpunkt verwenden. Verwenden Sie den [ \<>](announcementendpoint.md) Abschnitt "vorangestellt", um die Ankündigungen zu konfigurieren, indem Sie die Endpunkt Konfiguration angeben, die zum Senden von Dienst Ankündigungen verwendet werden soll (Online/Hello und Offline/bye). Verwenden Sie den [ \<> Abschnitt DiscoveryEndpoint](discoveryendpoint.md) , um den Endpunkt manuell anzugeben, an dem auf die Ermittlungs Nachrichten gelauscht werden soll.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Konfigurationsbeispiel wird angegeben, dass der CalculatorService sichtbar ist, und optional wird der zu verwendende Ankündigungsendpunkt angegeben.  
  
```xml  
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
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
