---
title: <behaviors>des Workflows
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: 7dd3b0b20c9d7accd80a85b3693e67ffc9b729e5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945997"
---
# <a name="behaviors-of-workflow"></a>\<Verhaltens > des Workflows
Dieses Element enthält die **Service** Verhaltens-Auflistung.  Jedes Element der Auflistung definiert von Workflowdiensten verarbeitete Verhaltenselemente. Jedes Behavior-Element wird durch das eindeutige **Name** -Attribut identifiziert.  
  
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
 None  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<serviceverhaltens>](servicebehaviors-of-workflow.md)|Dieser Konfigurationsabschnitt stellt alle für einen bestimmten Workflowdienst definierten Verhalten dar.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<system.serviceModel>](../wcf/system-servicemodel.md)|Das Stammelement aller Workflow-Konfigurationselemente.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [Konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
