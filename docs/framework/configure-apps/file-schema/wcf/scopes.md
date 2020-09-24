---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 63f46753da13469147b378f373de9888a007bf52
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162217"
---
# \<scopes>

Enthält eine Auflistung von Konfigurationselementen, die benutzerdefinierte Bereichs-URIs angeben, die verwendet werden können, um Dienstendpunkte während der Abfrage zu filtern.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<scopes>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enable="Boolean">
        <scopes>
          <add scope="URI" />
        </scopes>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  

 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|[\<add>](add-of-scopes.md)|Fügt die Bereichsinformationen für den Endpunkt hinzu, die zum Vergleichen von Kriterien bei der Dienstsuche verwendet werden können.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<endpointDiscovery>](endpointdiscovery.md)|Gibt die verschiedenen Ermittlungseinstellungen für einen Endpunkt an, z. B. seine Ermittelbarkeit, seine Bereiche und benutzerdefinierte Erweiterungen seiner Metadaten.|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
