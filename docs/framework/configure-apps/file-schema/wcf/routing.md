---
title: '&lt;Routing&gt;'
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: 1771d8a2603a8f61af6ba6e2acf6243d2fd073f7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltroutinggt"></a>&lt;Routing&gt;

Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von routingfiltern, die den Typ der Windows Communication Foundation (WCF) zu bestimmen <xref:System.ServiceModel.Dispatcher.MessageFilter> verwendet werden, bei der Auswertung eingehender Nachrichten sowie das routing Tabellen, die die zielendpunkten, definieren Senden von Nachrichten bei filterübereinstimmung.

[**\<system.serviceModel >**](system-servicemodel.md)   
&nbsp;&nbsp;**\<Routing >**

## <a name="syntax"></a>Syntax

```xml
<system.serviceModel>
  <routing>
    <filters>
      <filter customType="String" 
              filterData="String" 
              filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath" 
              name="String" />
    </filters>
    <routingTables>
      <table name="String">
        <entries>
          <add endpoint="String" 
               filterName="String" 
               priority="Integer" />
        </entries>
      </table>
    </routingTables>
  </routing>
</system.serviceModel>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

Keiner

### <a name="child-elements"></a>Untergeordnete Elemente

|     | Beschreibung |
| --- | ----------- |
| [**\<Filter >**](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md) | Enthält einen Satz von routingfiltern, die bestimmen, dass der Typ des Windows Communication Foundation (WCF)-MessageFilter beim Auswerten eingehender Nachrichten verwendet wird. |
| [**\<FilterTables >**](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) | Enthält Zuordnungen zwischen den Routingfiltern und den Zielendpunkten, die angeben, welcher Endpunkt bei Filterübereinstimmung verwendet wird. |

### <a name="parent-elements"></a>Übergeordnete Elemente

|     | Beschreibung |
| --- | ----------- |
| **\<System. ServiceModel >** | Das Stammelement aller WCF-Konfigurationselemente. |

## <a name="see-also"></a>Siehe auch

<xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
