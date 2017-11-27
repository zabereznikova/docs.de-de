---
title: '&lt;"userPrincipalName"&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b93a0cc24953024e265df418ec6dd738598dd0f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltuserprincipalnamegt"></a>&lt;"userPrincipalName"&gt;
Gibt den Benutzerprinzipalnamen (User Principal Name, UPN) eines Diensts an, der vom Client authentifiziert werden muss.  
  
 Weitere Informationen zum Festlegen des UPN finden Sie unter [-Dienstidentität und Authentifizierung](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
\<Identität >  
\<"userPrincipalName" >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<userPrincipalName value="String" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Wert|Ein Name für das Benutzerkonto (Name für die Benutzeranmeldung) sowie ein Domänenname zur Identifizierung der Domäne, in der sich das Benutzerkonto befindet. Dies ist das Standardverfahren für die Anmeldung an einer Windows-Domäne. Das Format lautet: someone@example.com (wie bei einer E-mail-Adresse).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Identität >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Gibt die Identität des Diensts für die Authentifizierung durch den Client an.|  
  
## <a name="remarks"></a>Hinweise  
 Ein sicherer [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Client, der mit dieser Identität eine Verbindung zu einem Endpunkt herstellt, verwendet den UPN für die SSPI-Authentifizierung mit dem Endpunkt.  
  
## <a name="example"></a>Beispiel  
 Der folgende Konfigurationscode gibt den UPN des Diensts an, der vom Client authentifiziert werden muss.  
  
```xml  
<identity>  
  <userPrincipalName value="someone@cohowinery.com" />  
</identity>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.UpnEndpointIdentity>  
 [Dienstidentität und Authentifizierung](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [\<Identität >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
