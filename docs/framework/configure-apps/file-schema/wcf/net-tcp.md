---
title: <net.tcp>
ms.date: 03/30/2017
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
ms.openlocfilehash: 4a3a17655f5469fe84c0b684ebdac9848bbfba84
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397695"
---
# \<net.tcp>
Gibt Konfigurationseinstellungen für den NET.TCP-Anschlussfreigabedienst an, der ermöglicht, dass mehrere Prozesse den gleichen TCP-Anschluss nutzen.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<net.tcp>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <net.tcp listenBacklog="Integer"
             maxPendingAccepts="Integer"
             maxPendingConnections="Integer"
             receiveTimeout="TimeSpan"
             teredoEnabled="Boolean">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18"/>
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19"/>
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-20"/>
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only)-->
        <add securityIdentifier="S-1-5-32-568"/>
      </allowAccounts>
    </net.tcp>
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a>type  
 `Type`  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|`listenBacklog`|Eine ganze Zahl, die die maximale Anzahl ausstehender Verbindungen angibt, die von der freigegebenen Verbindung angenommen werden, aber noch nicht an Windows Communication Foundation (WCF)-Dienste weitergeleitet werden. Der Standardwert ist 10.|  
|`maxPendingAccepts`|Eine ganze Zahl, die den Höchstwert für ausstehende gleichzeitig annehmende Threads am überwachenden Endpunkt für den Freigabedienst festlegt. Der Standardwert ist 2.|  
|`MaxPendingConnections`|Die maximale Anzahl von Verbindungen, die für einen Listener darauf warten können, von der Anwendung angenommen zu werden. Wenn dieser Kontingentwert überstiegen wird, werden neue eingehende Verbindungen gelöscht, statt weiter auf die Annahme zu warten. Verbindungsfunktionen, wie Nachrichtensicherheit, können dazu führen, dass ein Client mehr als eine Verbindung öffnet. Dienstadministratoren sollten diese zusätzlichen Verbindungen bei der Einrichtung des Kontingentwerts berücksichtigen. Der Standardwert ist 10.|  
|`receiveTimeout`|Eine <xref:System.TimeSpan>, die das Timeout für das Lesen der Rahmendaten und das Ausführen der Verbindungsverteilung der zugrunde liegenden Verbindungen angibt. Der Standardwert ist "00:00:10".|  
|`teredoEnabled`|Ein boolescher Wert, der angibt, ob der Port Freigabe Dienst den Microsoft Teredo-Dienst verwendet, um im Auftrag von WCF-Diensten TCP-Ports zu lauschen. Der Standardwert lautet `false`.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<allowAccounts>](allowaccounts.md)|Eine Auflistung von Konfigurationselementen, die ein `securityIdentifier` -Attribut zum Angeben von Benutzerkonten für Prozesse enthalten, die WCF-Dienste hosten und Verbindungs Zugriff auf den Freigabe Dienst erhalten.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](system-servicemodel-activation.md)|Enthält Konfigurationseinstellungen für den Listenerprozess SMSvcHost.exe.|  
  
## <a name="remarks"></a>Bemerkungen  
 Weitere Informationen zur Port Freigabe finden Sie unter [net. TCP-Port Freigabe](../../../wcf/feature-details/net-tcp-port-sharing.md). Informationen zum Konfigurieren des Port Freigabe diensdienstanbieter finden Sie unter [Konfigurieren des net. TCP-Port Freigabe Dienstanbieter](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>
- [Net.TCP-Anschlussfreigabe](../../../wcf/feature-details/net-tcp-port-sharing.md)
- [Konfigurieren des Net.TCP-Portfreigabediensts](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
