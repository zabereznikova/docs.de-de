---
title: "&lt;sessionSecurityTokenCache&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# &lt;sessionSecurityTokenCache&gt;
Registriert einen Cache für Sitzungstoken ein Dienst oder ein Security token Handler\-Auflistung.  
  
## Syntax  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <sessionSecurityTokenCache type=xs:string>  
      </sessionSecurityTokenCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|type|Ein Type, die von der <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> Klasse.  Weitere Informationen zum Angeben eines benutzerdefiniertes `type`, finden Sie unter [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_CustomTypeReferences).|  
  
### Untergeordnete Elemente  
 None  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<caches\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|Registriert die Caches, die durch einen Dienst oder ein Security token Handler\-Auflistung verwendet.|  
  
## Beispiel  
 Die folgende XML veranschaulicht die Konfiguration eines benutzerdefinierten Caches für die Abhaltung der Sitzung Sicherheitstoken \(<xref:System.IdentityModel.Tokens.SessionSecurityToken>\).  Die Konfiguration stammt aus der `ClaimsAwareWebFarm` Beispiel.  Weitere Informationen über dieses Beispiel finden Sie unter [Index für WIF\-Codebeispiele](../../../../../docs/framework/security/wif-code-sample-index.md).  
  
```  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## Siehe auch  
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>