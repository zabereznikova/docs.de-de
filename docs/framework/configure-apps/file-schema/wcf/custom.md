---
title: "&lt;Benutzerdefiniert&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# &lt;Benutzerdefiniert&gt;
Gibt die spezifischen Einstellungen für einen benutzerdefinierten Peerresolverdienst an.  
  
## Syntax  
  
```  
  
<custom address="Uri"  
   resolverType="String">  
      <headers/>  
   <identity/>  
</peerResolver>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|`address`|Ein URI, der die Endpunktadresse des Peerknotens angibt, der den benutzerdefinierten Peerresolverdienst hostet.|  
|`resolverType`|Eine Zeichenfolge, die den Typ des benutzerdefinierten Peerresolverdiensts angibt.|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Identität\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Gibt die Identität für benutzerdefinierte Peerresolver an, die mit diesem Element konfiguriert wurden.  Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IdentityElement>.|  
|[\<Kopfzeilen\>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|Eine Auflistung von Adressheadern, die für SOAP\-Nachrichten verwendet werden, die vom benutzerdefinierten Peerresolver verarbeitet werden.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<resolver\>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|Ein Peerresolver, der zum Auflösen einer Peermesh\-ID in einen Satz von Peerknotenadressen verwendet wird, der mehrere Knoten im Mesh darstellt.|  
  
## Hinweise  
 Mit diesem Element werden die Basiseinstellungen für einen benutzerdefinierten Peerresolverdienst definiert. Berücksichtigt werden dabei unter anderem die Endpunktadresse des Peers, der den Dienst hostet, sowie alle spezifischen Bindungseinstellungen.  Weitere Informationen zum Erstellen eines benutzerdefinierten Resolvers finden Sie unter [Adding a Custom Resolver to a PeerChannel Application](http://msdn.microsoft.com/de-de/12aa3787-2962-439c-ad27-46523c8b0419).  
  
## Siehe auch  
 <xref:System.Servicemodel.PeerResolvers.CustomPeerResolverService>   
 <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>   
 <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>   
 <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>   
 [Peerresolver](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)   
 [Adding a Custom Resolver to a PeerChannel Application](http://msdn.microsoft.com/de-de/12aa3787-2962-439c-ad27-46523c8b0419)