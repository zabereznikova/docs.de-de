---
title: "&lt;add&gt; von &lt;namespaceTable&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;add&gt; von &lt;namespaceTable&gt;
Stellt ein Konfigurationselement dar, das eine Namespace\-\/Präfix\-Zuordnung enthält, die zu Routingzwecken in XPath\-Filtern verwendet werden kann.  
  
## Syntax  
  
```vb  
  
<routing>  
   <namespaceTable>  
     <add namespace="String" prefix="String" />   
   </namespaceTable>  
</routing>  
  
```  
  
```csharp  
  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|namespace|Eine Zeichenfolge, die den Namespace enthält.|  
|prefix|Eine Zeichenfolge, die das Präfix für diesen Namespace enthält.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<namespaceTable\>](../../../../../docs/framework/configure-apps/file-schema/wcf/namespacetable.md)|Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Elementen dar, die Namespace\-\/Präfix\-Zuordnungen enthalten, die zu Routingzwecken in XPath\-Filtern verwendet werden können.|  
  
## Siehe auch  
 [System.ServiceModel.Routing.Configuration.NamespaceElement](assetId:///System.ServiceModel.Routing.Configuration.NamespaceElement?qualifyHint=False&amp;autoUpgrade=True)