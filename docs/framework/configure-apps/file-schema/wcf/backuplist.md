---
title: "&lt;backupList&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;backupList&gt;
Stellt einen Konfigurationsabschnitt zum Definieren einer Sicherungsliste dar, die einen Satz von Endpunkten auflistet, die vom Routingdienst verwendet werden sollen, falls der primäre Endpunkt nicht erreicht werden kann. Wenn der erste Endpunkt in der Liste ausgefallen ist, führt der Routingdienst automatisch einen Failover zum nächsten Endpunkt in der Liste aus. Dies erhöht effizient die Zuverlässigkeit Ihrer Anwendung, ohne die Clientanwendung zu unterweisen, wie komplexe Muster behandelt bzw. wo alle Dienste bereitgestellt werden.  
  
## Syntax  
  
```vb  
  
<routing>  
  <backupLists>  
    <backupList name="String">  
      <add endpointName="String" />  
    </backupList>    
  </backupLists>  
</routing>  
  
```  
  
```csharp  
  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|Name|Eine Zeichenfolge, die den Namen der Endpunktliste angibt.|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Filter\>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)||  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Routing\>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Eine Liste mit Sicherungsendpunkten.|  
  
## Hinweise  
 Dieser Abschnitt enthält eine sortierte Auflistung von Endpunkten, an die eine Nachricht gesendet wird, wenn beim Senden an den primären Endpunkt eine Kommunikationsausnahme auftritt.  
  
 Wenn das Senden an den im `endpointName`\-Attribut des [\<add\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md)\-Elements aufgelisteten primären Endpunkt aufgrund einer Kommunikationsausnahme fehlschlägt, versucht der Routingdienst, die Nachricht an den ersten in diesem Konfigurationsabschnitt aufgeführten Endpunkt zu senden.  Wenn auch dies mit einer Kommunikationsausnahme scheitert, versucht der Routingdienst so lange, die Nachricht an den nächsten Endpunkt in diesem Abschnitt zu senden, bis entweder der Sendeversuch erfolgreich ist, ein anderer Fehler als eine Kommunikationsausnahme zurückgegeben wird oder alle Endpunkte in der Auflistung einen Fehler zurückgegeben haben.  
  
 Im folgenden Beispiel versucht der Dienst, die Nachricht an die "alternateServiceQueue" zu senden, wenn ein Sendeversuch an den primären Endpunkt mit dem Namen "Destination" eine Kommunikationsausnahme zurückgibt.  Wenn auch dieser Versuch eine Kommunikationsausnahme zurückgibt, versucht der Routingdienst, die Meldung an den nächsten Endpunkt in der Auflistung zu senden.  
  
```  
  
<filterTables>  
     <filterTable name="filterTable1">  
          <add filterName="MatchAllFilter1" endpointName="Destination" backupList="backupEndpointList"/>  
     </filterTable>  
</filterTables>  
<backupLists>  
     <backupList name="backupEndpointList">  
          <add endpointName="backupServiceQueue" />  
          <add endpointName="alternateServiceQueue" />  
     </backupList>  
</backupLists>  
```  
  
## Siehe auch  
 [System.ServiceModel.Routing.Configuration.BackupEndpointCollection](assetId:///System.ServiceModel.Routing.Configuration.BackupEndpointCollection?qualifyHint=False&amp;autoUpgrade=True)