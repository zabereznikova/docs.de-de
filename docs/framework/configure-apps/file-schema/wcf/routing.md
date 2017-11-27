---
title: '&lt;Routing&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ed2dd4e68584d6e79e18fc9b61fcc8f078615dac
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltroutinggt"></a>&lt;Routing&gt;

Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Routingfiltern dar, die den Typ von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> bestimmen, der bei der Auswertung eingehender Nachrichten verwendet werden soll, sowie zum Definieren von Routingtabellen mit den Zielendpunkten, an die Nachrichten bei Filterübereinstimmung gesendet werden sollen.

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

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|     | Beschreibung |
| --- | ----------- |
| [**\<Filter >**](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md) | Enthält einen Satz von Routingfiltern, die den Typ von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] MessageFilter bestimmen, der zum Auswerten eingehender Nachrichten verwendet wird. |
| [**\<FilterTables >**](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) | Enthält Zuordnungen zwischen den Routingfiltern und den Zielendpunkten, die angeben, welcher Endpunkt bei Filterübereinstimmung verwendet wird. |

### <a name="parent-elements"></a>Übergeordnete Elemente

|     | Beschreibung |
| --- | ----------- |
| **\<System. ServiceModel >** | Das Stammelement aller WCF-Konfigurationselemente. |

## <a name="see-also"></a>Siehe auch

<xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
