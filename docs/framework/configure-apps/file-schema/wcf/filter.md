---
title: "&lt;Filter&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;Filter&gt;
Definiert einen Routingfilter, der den Typ von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> bestimmt, der bei der Auswertung eingehender Nachrichten verwendet werden soll, sowie alle für den Filter erforderlichen Daten oder Parameter.  
  
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
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|customType|Eine Zeichenfolge, die den vollqualifizierten Typnamen des als Filter zu verwendenden benutzerdefinierten Typs enthält. Wenn `filterType` auf `custom` festgelegt ist, enthält dieses Attribut den vollqualifizierten Typnamen der zu erstellenden Klasse. `filterData` enthält möglicherweise auch die während der Auswertung des benutzerdefinierten Typfilters verwendeten Werte.|  
|filterData|Eine Zeichenfolge, die die Filterdaten enthält.  Weitere Informationen zur Angabe dieses Attributs finden Sie unter <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.|  
|filterType|Eine Zeichenfolge, die den Filtertyp enthält.  Dieses Attribut ist vom Typ <xref:System.ServiceModel.Routing.Configuration.FilterType>.  Weitere Informationen zur Funktionsweise mit dem `filterData`\-Attribut finden Sie unter  <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.|  
|Name|Eine Zeichenfolge, die den eindeutigen Namen dieses Filterelements enthält.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Routing\>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Ein Konfigurationsabschnitt zum Definieren eines Satzes von Routingfiltern, die den Typ von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> bestimmen, der beim Auswerten eingehender Nachrichten verwendet werden soll.|  
  
## Siehe auch  
 [System.ServiceModel.Routing.Configuration.FilterElement](assetId:///System.ServiceModel.Routing.Configuration.FilterElement?qualifyHint=False&amp;autoUpgrade=True)   
 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>   
 <xref:System.ServiceModel.Routing.Configuration.FilterType>