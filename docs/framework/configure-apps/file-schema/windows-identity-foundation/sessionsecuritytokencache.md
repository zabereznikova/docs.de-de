---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: 5c68fe618f965f364a3716c3bc65de5e165b12ec
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207798"
---
# <a name="sessionsecuritytokencache"></a>\<sessionSecurityTokenCache>
Registriert ein Zwischenspeicher für Sitzungstoken mit einem Dienst oder ein Sicherheitstoken-Handlerauflistung an.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<caches>  
\<sessionSecurityTokenCache>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <sessionSecurityTokenCache type=xs:string>  
      </sessionSecurityTokenCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Typ|Ein Typ, der von abgeleitet ist die <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> Klasse.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keiner  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<caches>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|Registriert die Caches, die von einem Dienst oder ein Sicherheitstoken-Handlerauflistung verwendet.|  
  
## <a name="example"></a>Beispiel  
 Das folgende XML zeigt die Konfiguration eines benutzerdefinierten Cache zum Speichern von Sicherheitstoken für die Sitzung (<xref:System.IdentityModel.Tokens.SessionSecurityToken>). Die Konfiguration stammt aus dem `ClaimsAwareWebFarm` Beispiel. Weitere Informationen zu diesem Beispiel finden Sie unter [Index für WIF-Codebeispiele](../../../../../docs/framework/security/wif-code-sample-index.md).  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
