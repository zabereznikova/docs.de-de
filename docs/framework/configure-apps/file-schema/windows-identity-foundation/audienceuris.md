---
title: '&lt;audienceUris&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 3ce884c19d205df4727dcce96ffdf34144ff1dd6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltaudienceurisgt"></a>&lt;audienceUris&gt;
Gibt den Satz von URIs, die akzeptable Bezeichner der vertrauenden (RP) sind. Token werden nicht akzeptiert, es sei denn, sie eines der zulässigen "Audience"-URIs begrenzt sind.  
  
 \<system.identityModel >  
\<IdentityConfiguration >  
\<SecurityTokenHandlers >  
\<SecurityTokenHandlerConfiguration >  
\<AudienceUris >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <audienceUris mode=xs:string>  
          <add value=xs:string />  
          <clear />  
          <remove value=xs:string />  
        </audienceUris>  
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
|mode|Ein <xref:System.IdentityModel.Selectors.AudienceUriMode> Wert, der angibt, ob die Zielgruppe Einschränkung auf ein eingehendes Token angewendet werden soll. Die möglichen Werte sind "Immer", "Nie" und "BearerKeyOnly". Der Standardwert ist "Immer". Dies ist optional.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`<add value=xs:string>`|Fügt den angegebenen URI der `value` -Attribut auf die AudienceUris-Auflistung. Das `value`-Attribut ist erforderlich. Der URI ist Groß-/Kleinschreibung beachtet.|  
|`<clear>`|Löscht die AudienceUris-Auflistung. Alle Bezeichner werden aus der Auflistung entfernt.|  
|`<remove value=xs:string>`|Entfernt den angegebenen URI der `value` Attribut aus der Auflistung AudienceUris. Das `value`-Attribut ist erforderlich. Der URI ist Groß-/Kleinschreibung beachtet.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<SecurityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Ermöglicht die Konfiguration für eine Auflistung der Tokenhandler.|  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig ist die Auflistung leer. Verwenden Sie `<add>`, `<clear>`, und `<remove>` Elemente zum Ändern der Auflistung. <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>und <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Objekte verwenden, die die Werte in der Zielgruppe URI Auflistung so konfigurieren Sie eine Zielgruppe URI-Einschränkungen in zulässige <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> Objekte.  
  
 Die `<audienceUris>` Element dargestellt ist, durch die <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> Klasse. Ein einzelne URI der Teamprojektsammlung hinzugefügt wird dargestellt, durch die <xref:System.IdentityModel.Configuration.AudienceUriElement> Klasse.  
  
> [!NOTE]
>  Die Verwendung von der `<audienceUris>` Element als untergeordnetes Element von der [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element wurde als veraltet markiert, aber noch für die Abwärtskompatibilität unterstützt. Einstellungen auf der `<securityTokenHandlerConfiguration>` Element, überschreiben Sie die auf die `<identityConfiguration>` Element.  
  
## <a name="example"></a>Beispiel  
 Das folgende XML zeigt, wie die zulässigen "Audience"-URIs für eine Anwendung zu konfigurieren. In diesem Beispiel wird einen einzelnen URI. Bereich für diesen URI Token akzeptiert, werden alle anderen zurückgewiesen werden.  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
