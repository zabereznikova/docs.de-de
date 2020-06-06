---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: bd04e4ebdf5c58adaeea0ff0ca5993d7d9ce38f1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252166"
---
# \<audienceUris>
Gibt den Satz von URIs an, die akzeptable Bezeichner der vertrauenden Seite (RP) sind. Token werden nur akzeptiert, wenn sie im Bereich einer der zulässigen "Audience"-URIs liegen.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<audienceUris>**  
  
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
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|Modus|Ein- <xref:System.IdentityModel.Selectors.AudienceUriMode> Wert, der angibt, ob die Zielgruppen Einschränkung auf ein eingehendes Token angewendet werden soll. Mögliche Werte sind "Always", "Never" und "BearerKeyOnly". Der Standardwert ist "Always". (Optional)|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`<add value=xs:string>`|Fügt den URI, der vom- `value` Attribut angegeben wird, der audienceUris-Auflistung hinzu. Das `value`-Attribut ist erforderlich. Beim URI wird die Groß-/Kleinschreibung beachtet.|  
|`<clear>`|Löscht die audienceUris-Auflistung. Alle Bezeichner werden aus der Sammlung entfernt.|  
|`<remove value=xs:string>`|Entfernt den URI, der durch das- `value` Attribut aus der audienceUris-Auflistung angegeben wird. Das `value`-Attribut ist erforderlich. Beim URI wird die Groß-/Kleinschreibung beachtet.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.|  
  
## <a name="remarks"></a>Bemerkungen  
 Standardmäßig ist die Auflistung leer. verwenden `<add>` `<clear>` `<remove>` Sie die Elemente, und, um die Auflistung zu ändern. <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>-und- <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Objekte verwenden die Werte in der Zielgruppen-URI-Auflistung, um alle zulässigen Audience-URI-Einschränkungen in Objekten zu konfigurieren <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>  
  
 Das- `<audienceUris>` Element wird durch die- <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> Klasse dargestellt. Ein einzelner URI, der der Auflistung hinzugefügt wird, wird durch die- <xref:System.IdentityModel.Configuration.AudienceUriElement> Klasse dargestellt.  
  
> [!NOTE]
> Die Verwendung des- `<audienceUris>` Elements als untergeordnetes Element des- [\<identityConfiguration>](identityconfiguration.md) Elements wurde als veraltet markiert, wird jedoch aus Gründen der Abwärtskompatibilität weiterhin unterstützt. Die Einstellungen für das- `<securityTokenHandlerConfiguration>` Element überschreiben die für das- `<identityConfiguration>` Element.  
  
## <a name="example"></a>Beispiel  
 Der folgende XML-Code zeigt, wie die zulässigen Zielgruppen-URIs für eine Anwendung konfiguriert werden. In diesem Beispiel wird ein einzelner URI konfiguriert. Token, die für diesen URI gelten, werden akzeptiert, alle anderen werden abgelehnt.  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
