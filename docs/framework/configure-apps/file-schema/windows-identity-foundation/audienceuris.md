---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: 003221ed4dc7f4ccf72d2e0d3a91265e13172813
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941956"
---
# <a name="audienceuris"></a>\<audienceUris>
Gibt den Satz von URIs an, die akzeptable Bezeichner der vertrauenden Seite (RP) sind. Token werden nur akzeptiert, wenn Sie für eine der zulässigen Zielgruppen-URIs festgelegt sind.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers>  
\<securityTokenHandlerConfiguration>  
\<audienceUris>  
  
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
|Modus|Ein <xref:System.IdentityModel.Selectors.AudienceUriMode> -Wert, der angibt, ob die Zielgruppen Einschränkung auf ein eingehendes Token angewendet werden soll. Mögliche Werte sind "Always", "Never" und "BearerKeyOnly". Der Standardwert ist "Always". Optional.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`<add value=xs:string>`|Fügt den URI, der vom `value` -Attribut angegeben wird, der audienceUris-Auflistung hinzu. Das `value`-Attribut ist erforderlich. Beim URI wird die Groß-/Kleinschreibung beachtet.|  
|`<clear>`|Löscht die audienceUris-Auflistung. Alle Bezeichner werden aus der Sammlung entfernt.|  
|`<remove value=xs:string>`|Entfernt den URI, der durch `value` das-Attribut aus der audienceUris-Auflistung angegeben wird. Das `value`-Attribut ist erforderlich. Beim URI wird die Groß-/Kleinschreibung beachtet.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.|  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig ist die Auflistung leer. verwenden `<add>`Sie `<clear>`die Elemente `<remove>` , und, um die Auflistung zu ändern. <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>- <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> und-Objekte verwenden die Werte in der Zielgruppen-URI-Auflistung, um alle <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> zulässigen Audience-URI-Einschränkungen in Objekten zu konfigurieren  
  
 Das `<audienceUris>` -Element wird durch die <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> -Klasse dargestellt. Ein einzelner URI, der der Auflistung hinzugefügt wird, <xref:System.IdentityModel.Configuration.AudienceUriElement> wird durch die-Klasse dargestellt.  
  
> [!NOTE]
> Die Verwendung des `<audienceUris>` -Elements als untergeordnetes Element [ \<des identityconfiguration->](identityconfiguration.md) Elements ist veraltet, wird jedoch aus Gründen der Abwärtskompatibilität weiterhin unterstützt. Die Einstellungen für `<securityTokenHandlerConfiguration>` das-Element überschreiben `<identityConfiguration>` die für das-Element.  
  
## <a name="example"></a>Beispiel  
 Der folgende XML-Code zeigt, wie die zulässigen Zielgruppen-URIs für eine Anwendung konfiguriert werden. In diesem Beispiel wird ein einzelner URI konfiguriert. Token, die für diesen URI gelten, werden akzeptiert, alle anderen werden abgelehnt.  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
