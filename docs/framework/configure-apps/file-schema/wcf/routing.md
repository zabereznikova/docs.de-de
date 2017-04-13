---
title: "&lt;Routing&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;Routing&gt;
Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Routingfiltern dar, die den Typ von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> bestimmen, der bei der Auswertung eingehender Nachrichten verwendet werden soll, sowie zum Definieren von Routingtabellen mit den Zielendpunkten, an die Nachrichten bei Filterübereinstimmung gesendet werden sollen.  
  
## Syntax  
  
```vb  
  
<routing>  
      <filters>  
        <filter customType=”String”  
                filterData=”String”  
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
|[\<Filter\>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|Enthält einen Satz von Routingfiltern, die den Typ von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] MessageFilter bestimmen, der zum Auswerten eingehender Nachrichten verwendet wird.|  
|[\<filterTables\>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md)|Enthält Zuordnungen zwischen den Routingfiltern und den Zielendpunkten, die angeben, welcher Endpunkt bei Filterübereinstimmung verwendet wird.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|system.ServiceModel|Das Stammelement aller WCF\-Konfigurationselemente.|  
  
## Siehe auch  
 [System.ServiceModel.Routing.Configuration.RoutingSection](assetId:///System.ServiceModel.Routing.Configuration.RoutingSection?qualifyHint=False&amp;autoUpgrade=True)