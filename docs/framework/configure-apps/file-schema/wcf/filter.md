---
title: '&lt;Filter&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: af2095289d5f711733c71238b855c685114d1997
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltfiltergt"></a>&lt;Filter&gt;

Definiert einen Routingfilter, der den Typ von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> bestimmt, der bei der Auswertung eingehender Nachrichten verwendet werden soll, sowie alle für den Filter erforderlichen Daten oder Parameter.

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
| customType | Eine Zeichenfolge, die den vollqualifizierten Typnamen des benutzerdefinierten Typs enthält, der als Filter verwendet werden soll. Wenn `filterType` festgelegt ist, um `custom`, dieses Attribut enthält den vollqualifizierten Typnamen des zu erstellenden Klasse.  `filterData`Es enthält auch Werte, die während der Auswertung des Filters benutzerdefinierten Typ verwendet werden. |
| filterData | Eine Zeichenfolge, die die Filterdaten enthält. Weitere Informationen zur Angabe dieses Attributs finden Sie unter <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>. |
| filterType | Eine Zeichenfolge, die den Filtertyp enthält. Dieses Attribut ist vom Typ <xref:System.ServiceModel.Routing.Configuration.FilterType>.  Weitere Informationen zur Funktionsweise mit dem `filterData`-Attribut finden Sie unter  <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>. |
| Name       | Eine Zeichenfolge, die den eindeutigen Namen dieses Filterelements enthält. |

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

| Element | Beschreibung |
| ------- | ----------- |
| [\<Routing >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | Ein Konfigurationsabschnitt zum Definieren eines Satzes von Routingfiltern, die den Typ von [!INCLUDE[ indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> bestimmen, der beim Auswerten eingehender Nachrichten verwendet werden soll. |

## <a name="see-also"></a>Siehe auch

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>    
<xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>   
<xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>   
