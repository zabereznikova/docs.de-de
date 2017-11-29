---
title: '&lt;pnrpPeerResolver&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cd93bdadec120050813fcc1097d3041d6be94f66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltpnrppeerresolvergt"></a>&lt;pnrpPeerResolver&gt;
Gibt an, dass der PNRP (Peer Name Resolution-Protokoll)-Resolver als Resolver verwendet werden soll. Dieses Element ist optional, da das PNRP der Standardresolver ist.  
  
 \<system.serviceModel >  
\<Bindungen >  
\<CustomBinding >  
\<Binden von >  
\<PnrpResolver >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<pnrpResolver resolverType="String" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|resolverType|Eine Zeichenfolge, die den zu verwendenden Resolver angibt. Dieses Attribut ist optional. Wenn es nicht festgelegt wurde oder eine leere Zeichenfolge angegeben wurde, wird das PNRP verwendet.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Binden von >](../../../../../docs/framework/misc/binding.md)|Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.|  
  
## <a name="example"></a>Beispiel  
  
```xml  
<pnrpResolver resolverType="" />  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>  
 <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)  
 [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<CustomBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [PeerResolver](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
