---
title: '&lt;audienceUris&gt;'
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: af138a4da49a48ed43e1bc8f2c2c81c56892feed
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2018
ms.locfileid: "48034479"
---
# <a name="ltaudienceurisgt"></a>&lt;audienceUris&gt;
Gibt den Satz von URIs, die akzeptable Bezeichner der vertrauenden Seite (RP) sind. Token werden nicht akzeptiert werden, es sei denn, sie eines der zulässigen Audience-URI zugeordnet sind.  
  
 \<system.identityModel>  
\<identityConfiguration>  
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
|mode|Ein <xref:System.IdentityModel.Selectors.AudienceUriMode> Wert, der angibt, ob die zielgruppeneinschränkung auf ein eingehendes Token angewendet werden soll. Die möglichen Werte sind "Immer", "Never" und "BearerKeyOnly". Der Standardwert ist "Immer". Dies ist optional.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`<add value=xs:string>`|Fügt den vom angegebenen URI die `value` -Attribut auf die Sammlung von AudienceUris. Das `value`-Attribut ist erforderlich. Der URI ist Groß-/Kleinschreibung beachtet.|  
|`<clear>`|Löscht die Auflistung von AudienceUris. Alle Bezeichner werden aus der Auflistung entfernt werden.|  
|`<remove value=xs:string>`|Entfernt den angegebenen URI die `value` Attribut aus der Sammlung von AudienceUris. Das `value`-Attribut ist erforderlich. Der URI ist Groß-/Kleinschreibung beachtet.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<SecurityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Stellt die Konfiguration für eine Auflistung der Tokenhandler.|  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig ist die Auflistung leer. Verwenden Sie `<add>`, `<clear>`, und `<remove>` Elementen, die die Auflistung geändert werden. <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> und <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Objekte verwenden, die die Werte in der Zielgruppe URI-Auflistung so konfigurieren Sie eine Zielgruppe URI-Einschränkungen in zulässige <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> Objekte.  
  
 Die `<audienceUris>` Element wird dargestellt, durch die <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> Klasse. Ein einzelner URI der Auflistung hinzugefügt wird dargestellt, durch die <xref:System.IdentityModel.Configuration.AudienceUriElement> Klasse.  
  
> [!NOTE]
>  Die Verwendung der `<audienceUris>` -Element als untergeordnetes Element von der [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element ist veraltet, jedoch wird für die Abwärtskompatibilität weiterhin unterstützt. Einstellungen für die `<securityTokenHandlerConfiguration>` Element überschreiben diejenigen auf dem `<identityConfiguration>` Element.  
  
## <a name="example"></a>Beispiel  
 Das folgende XML zeigt, wie Sie die zulässigen Audience-URI für eine Anwendung zu konfigurieren. In diesem Beispiel wird einen einzigen URI. Akzeptiert Token, die für diesen URI beschränkt, alle anderen werden abgelehnt.  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
