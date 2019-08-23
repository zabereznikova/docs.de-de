---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: f9e64e667befb70d617574b2a03c3e6bebb2a143
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925602"
---
# <a name="filtertable"></a>\<filterTable>
Stellt eine Routing Tabelle dar, die eine Liste von Filtern zum Auswerten von Nachrichten sowie den Client Endpunkt enthält, an den Nachrichten weitergeleitet werden sollen, wenn der Filter zu true ausgewertet wird.  
  
 \<system.serviceModel>  
\<routing>  
\<RoutingTables->  
\<Tabellen >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<routing>
  <filterTables>
    <filterTable name="String">
      <entries>
        <add backupList="String"
             endpointName="String"
             filterName="String"
             priority="Integer" />
      </entries>
    </filterTable>
  </filterTables>
</routing>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|Name|Eine Zeichenfolge, die den eindeutigen Namen dieses Konfigurationselements enthält.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|Zuordnungen zwischen den Routingfiltern und den Zielendpunkten, an die bei Filterübereinstimmung Nachrichten gesendet werden.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<routing>](routing.md)|Ein Konfigurationsabschnitt mit Routingtabellen.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
