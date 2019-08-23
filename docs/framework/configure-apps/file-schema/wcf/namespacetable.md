---
title: <namespaceTable>
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: 0316e983446644671ead2f8f843dc91b493b29c9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933169"
---
# <a name="namespacetable"></a>\<namespaceTable>

Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Elementen dar, die Namespace-/Präfix-Zuordnungen enthalten, die zu Routingzwecken in XPath-Filtern verwendet werden können.

**\<system.serviceModel>**    
&nbsp;&nbsp; **\<Routing >**    
&nbsp;&nbsp;&nbsp;&nbsp; **\<namespacetable->**
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.serviceModel>
  <routing>
    <namespaceTable>
      <add namespace="String"
           prefix="String" />
    </namespaceTable>
  </routing>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

None

### <a name="child-elements"></a>Untergeordnete Elemente

|     | Beschreibung |
| --- | ----------- |
| [ **\<filter>** ](filter.md) | Definiert eine für XPath-Ausdrücke verwendete Namespace-/Präfix-Zuordnung. |

### <a name="parent-elements"></a>Übergeordnete Elemente

|     | Beschreibung |
| --- | ----------- |
| [ **\<Routing >** ](routing.md) | Stellt einen Konfigurations Abschnitt zum Definieren eines Satzes von Routing Filtern dar, die den Typ des Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> bestimmen, der bei der Auswertung eingehender Nachrichten verwendet werden soll, sowie Routing Tabellen, die die Ziel Endpunkte definieren. Senden von Nachrichten an, wenn ein Filter übereinstimmt. |

## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
