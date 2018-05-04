---
title: '&lt;Verhalten&gt;'
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: ca9cf5daa6590c14d4b5fd15c502d67af1f93b52
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltbehaviorsgt"></a>&lt;Verhalten&gt;
Dieses Element definiert zwei untergeordnete Auflistungen mit dem Namen `endpointBehaviors` und `serviceBehaviors`.  Jede Auflistung definiert von Endpunkten und Diensten verwendete Verhaltenselemente. Jedes Verhaltenselement wird durch seinen eindeutigen `name` identifiziert. Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen. Weitere Informationen zur Standardkonfiguration und namenlos Bindungen und Verhaltensweisen finden Sie unter [vereinfachte Konfiguration](../../../../../docs/framework/wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
 \<system.ServiceModel>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<behaviors>  
   <serviceBehaviors>  
   </serviceBehaviors>  
   <endpointBehaviors>  
   </endpointBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keiner  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<EndpointBehaviors >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)|Dieser Konfigurationsabschnitt stellt alle für einen bestimmten Endpunkt definierten Verhalten dar.|  
|[\<ServiceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)|Dieser Konfigurationsabschnitt stellt alle für einen bestimmten Dienst definierten Verhalten dar.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<system.serviceModel>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|Das Stammelement aller Windows Communication Foundation (WCF)-Konfigurationselemente.|  
  
## <a name="remarks"></a>Hinweise  
 Sie können das `<remove>`-Element verwenden, um ein bestimmtes Verhalten aus der Auflistung zu entfernen. Geben Sie hierzu im `name`-Attribut des `<remove>`-Elements den Namen des zu entfernenden Verhaltens an.  Sie können auch das `<clear>`-Element verwenden, um sicherzustellen, dass eine Verhaltensauflistung zu Beginn leer ist, indem Sie den gesamten Inhalt der Auflistung entfernen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.BehaviorsSection>  
 <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>  
 <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>  
 [Konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)  
 [Konfigurieren von Clientverhalten](../../../../../docs/framework/wcf/configuring-client-behaviors.md)  
 [Angeben des Clientlaufzeitverhaltens](../../../../../docs/framework/wcf/specifying-client-run-time-behavior.md)  
 [Angeben des Dienstlaufzeitverhaltens](../../../../../docs/framework/wcf/specifying-service-run-time-behavior.md)  
 [Sicherheitsverhalten](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
