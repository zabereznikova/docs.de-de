---
title: <serviceDiscovery>
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: b38496b77d80fcb66b1b48485a9eef6abfd72299
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198820"
---
# \<serviceDiscovery>

Gibt die Ermittelbarkeit von Dienstendpunkten an.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceDiscovery>**  
  
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
  
## <a name="remarks"></a>Bemerkungen  

 Wenn dieses Element der Verhaltenskonfiguration des Diensts hinzugefügt wird, macht es alle Endpunkte dieses Diensts auffindbar. Mithilfe der untergeordneten Elemente oder können Sie die Ermittlungs Funktionen solcher Endpunkte weiter konfigurieren [\<discoveryEndpoint>](discoveryendpoint.md) [\<announcementEndpoint>](announcementendpoint.md) . Verwenden [\<announcementEndpoint>](announcementendpoint.md) Sie den Abschnitt, um die Ankündigungen zu konfigurieren, indem Sie die Endpunkt Konfiguration angeben, die zum Senden von Dienst Ankündigungen verwendet werden soll (Online/Hello und Offline/bye). Verwenden [\<discoveryEndpoint>](discoveryendpoint.md) Sie den Abschnitt, um den Endpunkt manuell anzugeben, an dem auf die Ermittlungs Meldungen gelauscht werden soll.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
