---
title: '&lt;behaviors&gt; des Workflows'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 40278c0a3d99dd5c37df1d642b8a2e13e9f62633
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltbehaviorsgt-of-workflow"></a>&lt;behaviors&gt; des Workflows
Dieses Element enthält die **ServiceBehaviors** Auflistung.  Jedes Element der Auflistung definiert von Workflowdiensten verarbeitete Verhaltenselemente. Jedes verhaltenselement wird durch seinen eindeutigen identifiziert **Namen** Attribut.  
  
 \<System. ServiceModel >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
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
|[\<ServiceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|Dieser Konfigurationsabschnitt stellt alle für einen bestimmten Workflowdienst definierten Verhalten dar.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<system.serviceModel>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|Das Stammelement aller Workflow-Konfigurationselemente.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.BehaviorsSection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>  
 [Konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
