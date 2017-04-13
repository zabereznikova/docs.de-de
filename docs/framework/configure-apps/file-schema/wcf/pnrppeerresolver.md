---
title: "&lt;pnrpPeerResolver&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# &lt;pnrpPeerResolver&gt;
Gibt an, dass der PNRP \(Peer Name Resolution Protocol\)\-Resolver als Resolver verwendet werden soll.  Dieses Element ist optional, da das PNRP der Standardresolver ist.  
  
## Syntax  
  
```  
  
<pnrpResolver resolverType="String" />  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|resolverType|Eine Zeichenfolge, die den zu verwendenden Resolver angibt.  Dieses Attribut ist optional.  Wenn es nicht festgelegt wurde oder eine leere Zeichenfolge angegeben wurde, wird das PNRP verwendet.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Bindung\>](../../../../../docs/framework/misc/binding.md)|Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.|  
  
## Beispiel  
  
```  
<pnrpResolver resolverType="" />  
```  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>   
 <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)   
 [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)   
 [Peerresolver](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)