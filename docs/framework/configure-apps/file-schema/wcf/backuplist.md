---
title: '&lt;backupList&gt;'
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: c11fd38e7c40f740d4c1c36ab87c44744ed0daab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627982"
---
# <a name="ltbackuplistgt"></a>&lt;backupList&gt;
Stellt einen Konfigurationsabschnitt zum Definieren einer Sicherungsliste mit einem Satz von Endpunkten, die Sie möchten den Routingdienst verwenden soll, falls der primäre Endpunkt nicht erreicht werden kann. Wenn der erste Endpunkt in der Liste ausgefallen ist, führt der Routingdienst automatisch ein Failover zum nächsten Endpunkt in der Liste aus.  So können Sie die Zuverlässigkeit einer Anwendung schnell verbessern, wobei die Clientanwendung weder komplexe Muster behandeln noch den Bereitstellungsort aller Dienste kennen muss.  
  
 \<system.serviceModel>  
\<routing>  
\<backupLists>  
\<backupList>  
  
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
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Name|Eine Zeichenfolge, die den Namen der Endpunktliste angibt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<filter>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)||  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<routing>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Eine Liste mit Sicherungsendpunkten.|  
  
## <a name="remarks"></a>Hinweise  
 Dieser Abschnitt enthält eine sortierte Auflistung von Endpunkten, an die eine Nachricht gesendet wird, wenn beim Senden an den primären Endpunkt eine Kommunikationsausnahme auftritt.  
  
 Wenn ein Senden an den primären Endpunkt im aufgeführt der `endpointName` Attribut [ \<hinzufügen >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md) tritt der Fehler eine kommunikationsausnahme auftritt, versucht der Routingdienst zum Senden der Nachricht an den ersten Endpunkt in diesem Konfigurationsabschnitt. Wenn auch dies mit einer Kommunikationsausnahme scheitert, versucht der Routingdienst so lange, die Nachricht an den nächsten Endpunkt in diesem Abschnitt zu senden, bis entweder der Sendeversuch erfolgreich ist, ein anderer Fehler als eine Kommunikationsausnahme zurückgegeben wird oder alle Endpunkte in der Auflistung einen Fehler zurückgegeben haben.  
  
 Im folgenden Beispiel wenn ein Senden an den primären Endpunkt mit dem Namen "Destination" eine kommunikationsausnahme zurückgibt versucht der Dienst zum Senden der Nachricht an die "AlternateServiceQueue". Wenn auch dieser Versuch eine Kommunikationsausnahme zurückgibt, versucht der Routingdienst, die Meldung an den nächsten Endpunkt in der Auflistung zu senden.  
  
```xml  
<filterTables>
  <filterTable name="filterTable1">
    <add filterName="MatchAllFilter1"
         endpointName="Destination"
         backupList="backupEndpointList" />
  </filterTable>
</filterTables>
<backupLists>
  <backupList name="backupEndpointList">
    <add endpointName="backupServiceQueue" />
    <add endpointName="alternateServiceQueue" />
  </backupList>
</backupLists>
```  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
