---
title: '&lt;filters&gt; von &lt;routing&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b2687101aa868ae77ce0ae818afd9df906f8525c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltfiltersgt-of-ltroutinggt"></a>&lt;filters&gt; von &lt;routing&gt;

Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Routingfiltern dar, die den Typ von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> bestimmen, der beim Auswerten eingehender Nachrichten verwendet werden soll.

[**\<system.serviceModel >**](system-servicemodel.md)   
&nbsp;&nbsp;[**\<Routing >**](routing.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<Filter >**

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
| [**\<Filter >**](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | Enthält einen Routingfilter, der bestimmt, welche [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter> werden beim Auswerten eingehender Nachrichten verwendet. |

### <a name="parent-elements"></a>Übergeordnete Elemente

|     | Beschreibung |
| --- | ----------- |
| [**\<Routing >**](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von routingfiltern, die bestimmen, welche [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter> verwendet werden, bei der Auswertung eingehender Nachrichten sowie das routing Tabellen, die definieren, die Zielendpunkte zum Senden von Nachrichten, wenn ein Filter übereinstimmt. |

## <a name="see-also"></a>Siehe auch

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
