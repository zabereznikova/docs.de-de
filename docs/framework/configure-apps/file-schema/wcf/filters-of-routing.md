---
title: "&lt;filters&gt; von &lt;routing&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;filters&gt; von &lt;routing&gt;
Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Routingfiltern dar, die den Typ von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> bestimmen, der beim Auswerten eingehender Nachrichten verwendet werden soll.  
  
## Syntax  
  
```vb  
  
<routing>  
      <filters>  
        <filter customType=”String”  
                filterData=”String”  
                filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath"   
                name="String" />  
      </filters>  
</routing>  
  
```  
  
```csharp  
  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Filter\>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)|Enthält einen Routingfilter, der den Typ von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter> bestimmt, der zum Auswerten eingehender Nachrichten verwendet wird.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Routing\>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Routingfiltern dar, die den Typ von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> bestimmen, der bei der Auswertung eingehender Nachrichten verwendet werden soll, sowie zum Definieren von Routingtabellen mit den Zielendpunkten, an die Nachrichten bei Filterübereinstimmung gesendet werden sollen.|  
  
## Siehe auch  
 [System.ServiceModel.Routing.Configuration.FilterElement](assetId:///System.ServiceModel.Routing.Configuration.FilterElement?qualifyHint=False&amp;autoUpgrade=True)