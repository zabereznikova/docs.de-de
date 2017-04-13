---
title: "&lt;persistenceProvider&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;persistenceProvider&gt;
Gibt den Typ der zu verwendenden Persistenzanbieterimplementierung sowie das Timeout für Persistenzvorgänge an.  
  
## Syntax  
  
```  
  
<persistenceProvider persistenceOperationTimeout="TimeSpan"  
   type="String" />  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|persistenceOperationTimeout|Ein <xref:System.TimeSpan>\-Wert, der das Timeout angibt, das für Persistenzvorgänge verwendet wird.  Der Standardwert ist "00:00:30".|  
|Typ|Eine Zeichenfolge, die den Typ der zu verwendenden Persistenz\-Providerfactory angibt.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Verhalten\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Gibt ein Verhaltenselement an.|  
  
## Hinweise  
 Dieses Element gibt den Persistenz\-Provider an, der verwendet werden soll, um den Zustand eines WCF\-Dienstes zu serialisieren.  Es sollte zusammen mit der `wsHttpContextBinding` verwendet werden, die Zustandsinformationen in HTTP\-Headern übergibt.  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.PersistenceProviderElement>   
 <xref:System.ServiceModel.Persistence.PersistenceProvider>