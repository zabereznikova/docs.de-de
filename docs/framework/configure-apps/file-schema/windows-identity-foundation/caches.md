---
title: '&lt;Caches&gt;'
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 2a9766b826eb7a708b4b4e99b6bd984f9fc76812
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltcachesgt"></a>&lt;Caches&gt;
Registriert die Caches für die Sitzungstoken und token-Replay-Erkennung verwendet.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<Speichert >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keiner  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<SessionSecurityTokenCache >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md)|Registriert einen Cache für die Sitzungstoken mit einem Dienst oder einer Sicherheit Tokenhandler-Auflistung.|  
|[\<TokenReplayCache >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md)|Registriert einen token-Replay-Cache mit einem Dienst oder einer Sicherheit Tokenhandler-Auflistung.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Gibt an, Service Level identitätseinstellungen.|  
|[\<SecurityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Ermöglicht die Konfiguration für eine Auflistung der Tokenhandler.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `<caches>` Element angegeben werden kann, auf Dienstebene unter der `<identityConfiguration>` Element oder auf die Sicherheitsstufe für die Auflistung von Tokenhandler unter der `<securityTokenHandlerConfiguration>` Element. Einstellungen für eine Sammlung Tokenhandler außer Kraft für den Dienst angegeben.  
  
 Die `<caches>` Element dargestellt ist, durch die <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> Klasse. Die konfigurierten Caches werden durch dargestellt die <xref:System.IdentityModel.Configuration.IdentityModelCaches> Klasse.  
  
## <a name="example"></a>Beispiel  
 Das folgende XML zeigt die Konfiguration eines benutzerdefinierten Caches für die Aufnahme von Sicherheitstoken für die Sitzung (<xref:System.IdentityModel.Tokens.SessionSecurityToken>). Die Konfiguration stammt aus dem `ClaimsAwareWebFarm` Beispiel.  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
