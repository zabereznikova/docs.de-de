---
title: "&lt;routing&gt; von &lt;serviceBehavior&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;routing&gt; von &lt;serviceBehavior&gt;
Bietet Laufzeitzugriff auf den Routingdienst, um eine dynamische Änderung der Routingkonfiguration zu ermöglichen.  
  
## Syntax  
  
```  
  
<behaviors>  
  <serviceBehaviors>  
    <behavior name=String">  
      <routing filterTable=”String”  
         routeOnHeadersOnly="Boolean"  
         SoapProcessingEnabled=”Boolean” />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|filterTable|Eine Zeichenfolge, die den Namen der Routingtabelle angibt, die Filter enthält, die vom Routingdienst ausgewertet werden sollen.  Dieser Wert muss mit dem `name`\-Attribut des [\<filterTable\>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertable.md)\-Elements im [\<filterTables\>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md)\-Abschnitt übereinstimmen.|  
|routeOnHeaderOnly|Ein boolescher Wert, der angibt, ob der Filter sowohl den Nachrichtentext als auch den Header oder nur den Header prüft.  Die Standardeinstellung ist `true`.|  
|soapProcessingEnabled|Ein boolescher Wert, der angibt, ob SOAP\-Verarbeitung erfolgen soll.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Verhalten\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Gibt ein Verhaltenselement an.|  
  
## Hinweise  
 Wenn dieses Konfigurationselement der Verhaltenskonfiguration des Diensts hinzugefügt wird, aktiviert es Routing für den Dienst.  Sie können die Routingtabelle angeben, die vom Dienst in diesem Element verwendet werden soll.  
  
 Mit diesem Konfigurationsabschnitt können Sie die Routingeinstellungen dynamisch ändern, wenn sich das Bereitstellungsmuster ändert.  Zur Laufzeit können Sie eine eigene Routingerweiterung mit neuen Routingeinstellungen registrieren, wobei der Routingdienst die aktualisierten Konfigurationsinformationen für neue Nachrichten und Sitzungen verwendet, während die Regeln für bereits bestehende Nachrichten\/Sitzungen nicht geändert werden. Auf diese Weise kann der Routingdienst zur Laufzeit neu konfiguriert werden, ohne dass Sitzungen gefährdet oder zu viele Konfigurationsinformationen wiederverwendet werden müssen.  
  
## Siehe auch  
 <xref:System.ServiceModel.Routing.RoutingExtenstion>   
 <xref:System.ServiceModel.Routing.Configuration.RoutingExtenstionElement>