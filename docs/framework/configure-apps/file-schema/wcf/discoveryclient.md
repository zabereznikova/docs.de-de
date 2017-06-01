---
title: "&lt;discoveryClient&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;discoveryClient&gt;
Ein Konfigurationselement zum Erstellen einer benutzerdefinierten Bindung, mit der eine Clientanwendung automatisch nach einem sichtbaren Workflowdienst suchen und zur Laufzeit dessen Adresse abrufen kann.  
  
## Syntax  
  
```  
  
<discoveryClient discoveryEndpoint=”String” >  
   <findCriteria duration=”TimeSpan”  
       maxResults=”Integer”   
       scopeMatchBy=”Uri” >  
       <contractTypeNames>  
          <add name="String" namespace="String" />  
       <contractTypeNames>  
       <extensions />  
       <scopes>  
          <add scope="URI"/>  
       </scopes>  
   </findCriteria>  
</discoveryClient>  
  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|discoveryEndpoint|Eine Zeichenfolge mit dem Namen des Ermittlungsendpunkts, der einer Clientanwendung ermöglicht, automatisch nach einem sichtbaren Dienst zu suchen und zur Laufzeit dessen Adresse abzurufen.|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<standardEndpoints\>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|Ein Konfigurationselement, das einen Kriteriensatz bereitstellt, der von einer Clientanwendung zum Suchen nach einem Ermittlungsdienst verwendet wird.  Kriterien können in Suchkriterien \(nach welchen Diensten soll gesucht werden\) und Beendigungskriterien für die Suche \(wie lange soll die Suche dauern\) gruppiert werden.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Bindung\>](../../../../../docs/framework/misc/binding.md)|Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.|  
  
## Siehe auch  
 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>   
 <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>