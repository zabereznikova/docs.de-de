---
title: '&lt;namespaceTable&gt;'
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: 31d661f39f9e3de0f7012c7fa52d4964e7ee4a69
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltnamespacetablegt"></a>&lt;namespaceTable&gt;

Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Elementen dar, die Namespace-/Präfix-Zuordnungen enthalten, die zu Routingzwecken in XPath-Filtern verwendet werden können.

**\<system.serviceModel >**   
&nbsp;&nbsp;**\<Routing >**   
&nbsp;&nbsp;&nbsp;&nbsp;**\<NamespaceTable >**

## <a name="syntax"></a>Syntax

```xml
<system.serviceModel>
  <routing>
    <namespaceTable>
      <add namespace="String" prefix="String" />
    </namespaceTable>
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
| [**\<Filter >**](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | Definiert eine für XPath-Ausdrücke verwendete Namespace-/Präfix-Zuordnung. |

### <a name="parent-elements"></a>Übergeordnete Elemente

|     | Beschreibung |
| --- | ----------- |
| [**\<Routing >**](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von routingfiltern, die den Typ der Windows Communication Foundation (WCF) zu bestimmen<xref:System.ServiceModel.Dispatcher.MessageFilter> verwendet werden, bei der Auswertung eingehender Nachrichten sowie das routing Tabellen, die die zielendpunkten, definieren Senden von Nachrichten bei filterübereinstimmung. |

## <a name="see-also"></a>Siehe auch

<xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
