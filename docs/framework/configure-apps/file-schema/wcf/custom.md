---
title: '&lt;benutzerdefinierte&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4e4b96e1274ad59ae5e63e7935d7408afd069a8c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltcustomgt"></a>&lt;benutzerdefinierte&gt;
Gibt die spezifischen Einstellungen für einen benutzerdefinierten Peerresolverdienst an.  
  
\<system.serviceModel >  
\<Bindungen >  
\<NetPeerBinding >  
\<Binden von >  
\<Konfliktlöser >  
\<Benutzerdefinierte >  
  
## <a name="syntax"></a>Syntax  
  
```xml
<custom address="Uri" 
        resolverType="String">  
  <headers/>  
  <identity/>  
</custom>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`address`|Ein URI, der die Endpunktadresse des Peerknotens angibt, der den benutzerdefinierten Peerresolverdienst hostet.|  
|`resolverType`|Eine Zeichenfolge, die den Typ des benutzerdefinierten Peerresolverdiensts angibt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Identität >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Gibt die Identität für benutzerdefinierte Peerresolver an, die mit diesem Element konfiguriert wurden. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IdentityElement>.|  
|[\<Header >](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|Eine Auflistung von Adressheadern, die für SOAP-Nachrichten verwendet werden, die vom benutzerdefinierten Peerresolver verarbeitet werden.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Konfliktlöser >](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|Ein Peerresolver, der zum Auflösen einer Peermesh-ID in einen Satz von Peerknotenadressen verwendet wird, der mehrere Knoten im Mesh darstellt.|  
  
## <a name="remarks"></a>Hinweise  
 Mit diesem Element werden die Basiseinstellungen für einen benutzerdefinierten Peerresolverdienst definiert. Berücksichtigt werden dabei unter anderem die Endpunktadresse des Peers, der den Dienst hostet, sowie alle spezifischen Bindungseinstellungen. Weitere Informationen zum Erstellen eines benutzerdefinierten Konfliktlösers finden Sie unter [Hinzufügen eines benutzerdefinierten Konfliktlösers zu einer PeerChannel-Anwendung](http://msdn.microsoft.com/en-us/12aa3787-2962-439c-ad27-46523c8b0419).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>  
 <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>  
 <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>  
 <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>  
 [PeerResolver](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)  
 [Hinzufügen eines benutzerdefinierten Konfliktlösers zu einer PeerChannel-Anwendung](http://msdn.microsoft.com/en-us/12aa3787-2962-439c-ad27-46523c8b0419)
