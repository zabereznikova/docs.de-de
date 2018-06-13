---
title: '&lt;behaviors&gt; des Workflows'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: 762fd1ff0de7980848ac3921706f406932c7f35d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32767309"
---
# <a name="ltbehaviorsgt-of-workflow"></a>&lt;behaviors&gt; des Workflows
Dieses Element enthält die **ServiceBehaviors** Auflistung.  Jedes Element der Auflistung definiert von Workflowdiensten verarbeitete Verhaltenselemente. Jedes verhaltenselement wird durch seinen eindeutigen identifiziert **Namen** Attribut.  
  
 \<system.ServiceModel>  
  
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
 Keiner  
  
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
