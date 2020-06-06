---
title: <behaviors>
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: bcdd26f038b343040d81b0add83bf166a5e3151f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74139689"
---
# \<behaviors>
Dieses Element definiert zwei untergeordnete Auflistungen mit dem Namen `endpointBehaviors` und `serviceBehaviors`.  Jede Auflistung definiert von Endpunkten und Diensten verwendete Verhaltenselemente. Jedes Verhaltenselement wird durch seinen eindeutigen `name` identifiziert. Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben. Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**  
  
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
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[\<endpointBehaviors>](endpointbehaviors.md)|Dieser Konfigurationsabschnitt stellt alle für einen bestimmten Endpunkt definierten Verhalten dar.|  
|[\<serviceBehaviors>](servicebehaviors.md)|Dieser Konfigurationsabschnitt stellt alle für einen bestimmten Dienst definierten Verhalten dar.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|Das Stammelement aller Windows Communication Foundation (WCF)-Konfigurationselemente.|  
  
## <a name="remarks"></a>Bemerkungen  
 Sie können das `<remove>`-Element verwenden, um ein bestimmtes Verhalten aus der Auflistung zu entfernen. Geben Sie hierzu im `name`-Attribut des `<remove>`-Elements den Namen des zu entfernenden Verhaltens an.  Sie können auch das `<clear>`-Element verwenden, um sicherzustellen, dass eine Verhaltensauflistung zu Beginn leer ist, indem Sie den gesamten Inhalt der Auflistung entfernen.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [Konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
- [Konfigurieren von Clientverhalten](../../../wcf/configuring-client-behaviors.md)
- [Angeben des Clientlaufzeitverhaltens](../../../wcf/specifying-client-run-time-behavior.md)
- [Angeben des Dienstlaufzeitverhaltens](../../../wcf/specifying-service-run-time-behavior.md)
- [Sicherheitsverhalten](../../../wcf/feature-details/security-behaviors-in-wcf.md)
