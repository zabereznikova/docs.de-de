---
title: <backupLists>
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: 5f2bb030d13389e15cb44f1ddff3b8168b4f2140
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850258"
---
# \<backupLists>
Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Sicherungsdiensten dar, die in der Fehlerbehandlung verwendet werden. Jedes untergeordnete Element ist eine Sicherungsliste mit einem Satz von Endpunkten, die der Routingdienst verwenden soll, falls der primäre Endpunkt nicht erreicht werden kann. Wenn der erste Endpunkt in der Liste ausgefallen ist, führt der Routingdienst automatisch ein Failover zum nächsten Endpunkt in der Liste aus.  So können Sie die Zuverlässigkeit einer Anwendung schnell verbessern, wobei die Clientanwendung weder komplexe Muster behandeln noch den Bereitstellungsort aller Dienste kennen muss.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<backupLists>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[\<filter>](filter.md)|Enthält eine Reihe von Endpunkten, die der Routingdienst verwenden soll, falls der primäre Endpunkt nicht erreicht werden kann.  .|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[\<routing>](routing.md)|Stellt einen Konfigurations Abschnitt zum Definieren eines Satzes von Routing Filtern dar, die den Typ des Windows Communication Foundation (WCF) bestimmen, der <xref:System.ServiceModel.Dispatcher.MessageFilter> bei der Auswertung eingehender Nachrichten verwendet werden soll, sowie Routing Tabellen, die die Ziel Endpunkte definieren, an die Nachrichten gesendet werden sollen, wenn ein Filter übereinstimmt.|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
