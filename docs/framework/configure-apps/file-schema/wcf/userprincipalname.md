---
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 423a3249a9298675517f0cff08566c3735fa35f1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940513"
---
# <a name="userprincipalname"></a>\<userPrincipalName>
Gibt den Benutzerprinzipalnamen (User Principal Name, UPN) eines Diensts an, der vom Client authentifiziert werden muss.  
  
 Weitere Informationen zum Festlegen des UPN finden Sie unter [Dienst Identität und Authentifizierung](../../../wcf/feature-details/service-identity-and-authentication.md).  
  
\<identity>  
\<userPrincipalName>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Wert|Ein Name für das Benutzerkonto (Name für die Benutzeranmeldung) sowie ein Domänenname zur Identifizierung der Domäne, in der sich das Benutzerkonto befindet. Dies ist das Standardverfahren für die Anmeldung an einer Windows-Domäne. Das Format ist: someone@example.com (wie bei einer e-Mail-Adresse).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<identity>](identity.md)|Gibt die Identität des Diensts für die Authentifizierung durch den Client an.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Secure Windows Communication Foundation (WCF)-Client, der eine Verbindung mit einem Endpunkt mit dieser Identität herstellt, verwendet den UPN beim Ausführen der SSPI-Authentifizierung mit dem Endpunkt.  
  
## <a name="example"></a>Beispiel  
 Der folgende Konfigurationscode gibt den UPN des Diensts an, der vom Client authentifiziert werden muss.  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [Dienstidentität und Authentifizierung](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
