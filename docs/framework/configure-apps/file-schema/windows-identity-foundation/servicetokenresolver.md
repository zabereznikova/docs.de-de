---
title: '&lt;serviceTokenResolver&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 06e871ee31880a219d9105ff4ce667618bfb78f0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltservicetokenresolvergt"></a>&lt;serviceTokenResolver&gt;
Registriert die Dienst-Resolver, die vom Handler in der Auflistung Tokenhandler verwendet wird. Die Dienst-tokenresolver dient zum Auflösen des Tokens Verschlüsselung auf eingehende Token und Nachrichten.  
  
 \<system.identityModel >  
\<IdentityConfiguration >  
\<SecurityTokenHandlers >  
\<SecurityTokenHandlerConfiguration >  
\<ServiceTokenResolver >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <serviceTokenResolver type=xs:string>  
        </serviceTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Typ|Gibt den Typ des Diensts token Konfliktlösers. Entweder die <xref:System.IdentityModel.Selectors.SecurityTokenResolver> Typ oder ein Typ, der von abgeleitet ist die <xref:System.IdentityModel.Selectors.SecurityTokenResolver> Klasse. Weitere Informationen zum Angeben der `type` -Attribut angegeben wird, finden Sie unter [benutzerdefinierte Typverweise]. Erforderlich.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<SecurityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Ermöglicht die Konfiguration für eine Auflistung der Tokenhandler.|  
  
## <a name="remarks"></a>Hinweise  
 Die Dienst-tokenresolver kann zum Auflösen des Tokens Verschlüsselung auf eingehende Token und Nachrichten verwendet werden. Es dient zum Abrufen des Schlüssels, der zum Entschlüsseln der eingehender Tokens verwendet werden soll. Sie müssen angeben, die `type` Attribut. Der angegebene Typ kann entweder <xref:System.IdentityModel.Selectors.SecurityTokenResolver> oder einen benutzerdefinierten Typ abgeleitet, die die <xref:System.IdentityModel.Selectors.SecurityTokenResolver> Klasse.  
  
 Einige Tokenhandler können Sie tokenresolver diensteinstellungen in der Konfiguration angeben. Einstellungen für einzelne Tokenhandler überschreiben für die Sicherheit Tokenhandler Auflistung angegebenen.  
  
> [!NOTE]
>  Angeben der `<serviceTokenResolver>` Element als untergeordnetes Element von der [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element wurde als veraltet markiert, aber noch für die Abwärtskompatibilität unterstützt. Einstellungen auf der `<securityTokenHandlerConfiguration>` Element, überschreiben Sie die auf die `<identityConfiguration>` Element.  
  
## <a name="example"></a>Beispiel  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
