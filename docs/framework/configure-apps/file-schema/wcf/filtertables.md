---
title: '&lt;filterTables&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 75e06b0258f2e4f65d441c25b5081cf7a6627518
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltfiltertablesgt"></a>&lt;filterTables&gt;
Stellt einen Konfigurationsabschnitt zum Definieren von Routingtabellen dar, die Zuordnungen zwischen den Routingfiltern und den Zielendpunkten enthalten, an die bei Filterübereinstimmung Nachrichten gesendet werden.  
  
 \<system.serviceModel >  
\<Routing >  
\<RoutingTables >  
  
## <a name="syntax"></a>Syntax  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine.  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Filter >](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|Eine Routingtabelle, die Zuordnungen zwischen den Routingfiltern und den Zielendpunkten enthält, an die bei Filterübereinstimmung Nachrichten gesendet werden.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Routing >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Ein Konfigurationsabschnitt, der Routingfilter und Routingtabellen enthält.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>    
