---
title: "&lt;behaviors&gt; des Workflows | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;behaviors&gt; des Workflows
Dieses Element enthält die **serviceBehaviors**\-Auflistung.  Jedes Element der Auflistung definiert von Workflowdiensten verarbeitete Verhaltenselemente.  Jedes Verhaltenselement wird durch seinen eindeutigen **name** identifiziert.  
  
 \<system.ServiceModel\>  
  
## Syntax  
  
```  
  
<behaviors>  
   <serviceBehaviors>  
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
|[\<serviceBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|Dieser Konfigurationsabschnitt stellt alle für einen bestimmten Workflowdienst definierten Verhalten dar.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<system.serviceModel\>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|Das Stammelement aller Workflow\-Konfigurationselemente.|  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.BehaviorsSection>   
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>   
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>   
 [Konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)