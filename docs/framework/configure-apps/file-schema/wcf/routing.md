---
title: '&lt;routing&gt;'
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: 855faedfd2e9523e939174441b0cfa50e052b375
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54565877"
---
# <a name="ltroutinggt"></a>&lt;routing&gt;

Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von routingfiltern, die den Typ der Windows Communication Foundation (WCF) bestimmen <xref:System.ServiceModel.Dispatcher.MessageFilter> verwendet werden, bei der Auswertung eingehender Nachrichten sowie das routing, Tabellen, die die zielendpunkten, definieren Senden von Nachrichten bei filterübereinstimmung.

[**\<system.serviceModel>**](system-servicemodel.md)   
&nbsp;&nbsp;**\<routing>**
  
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

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|     | Beschreibung |
| --- | ----------- |
| [**\<filters>**](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md) | Enthält einen Satz von routingfiltern, die bestimmen, dass der Typ des Windows Communication Foundation (WCF)-MessageFilter beim Auswerten eingehender Nachrichten verwendet wird. |
| [**\<filterTables>**](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) | Enthält Zuordnungen zwischen den Routingfiltern und den Zielendpunkten, die angeben, welcher Endpunkt bei Filterübereinstimmung verwendet wird. |

### <a name="parent-elements"></a>Übergeordnete Elemente

|     | Beschreibung |
| --- | ----------- |
| **\<system.ServiceModel>** | Das Stammelement aller WCF-Konfigurationselemente. |

## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
