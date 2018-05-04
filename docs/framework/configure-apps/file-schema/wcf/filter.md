---
title: '&lt;Filter&gt;'
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 93d47fc6b25a75eedae43cd70582abc863a74e6c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltfiltergt"></a>&lt;Filter&gt;

Definiert einen Routingfilter, der den Typ der Windows Communication Foundation (WCF) bestimmt<xref:System.ServiceModel.Dispatcher.MessageFilter> beim Auswerten eingehender Nachrichten, als sowie alle Daten oder den Filter erforderlichen Parameter verwendet werden.

\<system.serviceModel > \<routing > \<Filter > \<Filter >

## <a name="syntax"></a>Syntax

```xml
<routing>
  <filters>
    <filter customType="String" 
            filterData="String" 
            filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath" 
            name="String" />
  </filters>
</routing>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

| Attribut  | Beschreibung |
| ---------- | ----------- |
| customType | Eine Zeichenfolge, die den vollqualifizierten Typnamen des benutzerdefinierten Typs enthält, der als Filter verwendet werden soll. Wenn `filterType` festgelegt ist, um `custom`, dieses Attribut enthält den vollqualifizierten Typnamen des zu erstellenden Klasse.  `filterData` Es enthält auch Werte, die während der Auswertung des Filters benutzerdefinierten Typ verwendet werden. |
| filterData | Eine Zeichenfolge, die die Filterdaten enthält. Weitere Informationen zur Angabe dieses Attributs finden Sie unter <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>. |
| filterType | Eine Zeichenfolge, die den Filtertyp enthält. Dieses Attribut ist vom Typ <xref:System.ServiceModel.Routing.Configuration.FilterType>.  Weitere Informationen zur Funktionsweise mit dem `filterData`-Attribut finden Sie unter  <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>. |
| Name       | Eine Zeichenfolge, die den eindeutigen Namen dieses Filterelements enthält. |

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

| Element | Beschreibung |
| ------- | ----------- |
| [\<Routing >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | Ein Konfigurationsabschnitt zum Definieren eines Satzes von routingfiltern, die den Typ der Windows Communication Foundation (WCF) bestimmen<xref:System.ServiceModel.Dispatcher.MessageFilter> beim Auswerten eingehender Nachrichten verwendet werden. |

## <a name="see-also"></a>Siehe auch

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>    
<xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>   
<xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>   
