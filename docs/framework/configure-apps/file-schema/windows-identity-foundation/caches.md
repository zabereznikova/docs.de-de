---
title: "&lt;caches&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# &lt;caches&gt;
Registriert die Caches für Sitzung Tokens und Tokens Replay\-Erkennung verwendet.  
  
## Syntax  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 None  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<sessionSecurityTokenCache\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md)|Registriert einen Cache für Sitzungstoken ein Dienst oder ein Security token Handler\-Auflistung.|  
|[\<tokenReplayCache\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md)|Registriert einen token Replay\-Cache mit einem Dienst oder ein Security token Handler\-Auflistung.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Gibt die von Service\-Level\-Identitätseinstellungen.|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Stellt die Konfiguration für eine Auflistung von Sicherheit Tokenhandler.|  
  
## Hinweise  
 A `<caches>` Element kann angegeben werden, auf der Service\-Ebene unter der `<identityConfiguration>` Element oder auf die Sicherheitsstufe für die Sammlung von Tokenhandler unter der `<securityTokenHandlerConfiguration>` Element.  Einstellungen für eine Auflistung der Tokenhandler überschreiben festgelegten Einstellungen für den Dienst.  
  
 Die `<caches>` Element dargestellt durch die <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> Klasse.  Konfigurierte Caches sind, vertreten durch die <xref:System.IdentityModel.Configuration.IdentityModelCaches> Klasse.  
  
## Beispiel  
 Die folgende XML veranschaulicht die Konfiguration eines benutzerdefinierten Caches für die Abhaltung der Sitzung Sicherheitstoken \(<xref:System.IdentityModel.Tokens.SessionSecurityToken>\).  Die Konfiguration stammt aus der `ClaimsAwareWebFarm` Beispiel.  
  
```  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```