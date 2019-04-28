---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: b1d04280ef993297102d446ba5a7db54e8404dd8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750786"
---
# <a name="caches"></a>\<caches>
Registriert die Caches für Sitzungstoken und Erkennung von tokenwiederholungen verwendet.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<caches>  
  
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
|[\<sessionSecurityTokenCache>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md)|Registriert ein Zwischenspeicher für Sitzungstoken mit einem Dienst oder ein Sicherheitstoken-Handlerauflistung an.|  
|[\<tokenReplayCache>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md)|Registriert einen tokenwiederholungscache mit einem Dienst oder ein Sicherheitstoken-Handlerauflistung an.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Gibt die identitätseinstellungen der Servicelevel.|  
|[\<securityTokenHandlerConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Stellt die Konfiguration für eine Auflistung der Tokenhandler.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `<caches>` Element kann angegeben werden, auf der Dienstebene unter der `<identityConfiguration>` Element oder die Sicherheitsstufe für die Auflistung von Tokenhandler unter der `<securityTokenHandlerConfiguration>` Element. Einstellungen für eine Auflistung der Tokenhandler überschreiben jene, die für den Dienst angegeben.  
  
 Die `<caches>` Element wird dargestellt, durch die <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> Klasse. Die konfigurierten Caches werden durch dargestellt die <xref:System.IdentityModel.Configuration.IdentityModelCaches> Klasse.  
  
## <a name="example"></a>Beispiel  
 Das folgende XML zeigt die Konfiguration eines benutzerdefinierten Cache zum Speichern von Sicherheitstoken für die Sitzung (<xref:System.IdentityModel.Tokens.SessionSecurityToken>). Die Konfiguration stammt aus dem `ClaimsAwareWebFarm` Beispiel.  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
